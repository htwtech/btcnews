---
title: "L402 on Lightning: the protocol that makes http payable"
slug: "l402-on-lightning-http-payable"
date: "2026-02-23"
description: "L402 is what finally gave HTTP 402 working semantics — and it runs on Lightning."
author: "BTCBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/L402%20Powers%20%20Lightning%20%20Payments2.png"
coverAlt: "L402 Powers Lightning Payments"
tags: ["bitcoin", "lightning", "l402", "infrastructure", "btcfi"]
---

# L402 on Lightning: the protocol that makes http payable

HTTP 402 sat reserved in the web spec for over thirty years, waiting.  
L402 is what finally gave it working semantics — and it runs on Lightning.

## What L402 actually is

[After the AI agent toolkit announcement](https://btcboard.io/news/lightning-labs-ai-agent-toolkit-l402) drew a lot of attention to Lightning's payment infrastructure, it makes sense to zoom in on the piece that outlasts any particular product cycle: the protocol design itself.

L402, formerly known as LSAT, is a way to make an HTTP resource payable — using Lightning invoices and macaroons, with no user accounts and no centralized database. The mechanism is worth unpacking carefully because the design lies in how the pieces interlock.

Every Lightning invoice contains a `payment_hash` — a SHA-256 hash of a secret preimage. When a payment completes, the preimage gets revealed on the way back to the sender. That preimage is a cryptographic proof of payment, something you can only hold if the invoice was settled.

L402 uses that proof as half of an auth credential. The other half is a macaroon — a bearer token that carries its own permissions and can be validated using only a root key and basic cryptography, with no centralized lookup required. Macaroons support attenuation via caveats: time limits, usage caps, permission scopes. LND has used macaroons for internal RPC auth since early on, so the pattern fits naturally into Lightning infrastructure.

The credential is macaroon + preimage, and the design means you can only assemble a valid one after a Lightning payment has cleared. The payment receipt becomes part of the auth token itself.

## The HTTP flow, spelled out
```http
GET /premium-data HTTP/1.1
Host: api.example.com

HTTP/1.1 402 Payment Required
WWW-Authenticate: L402 macaroon="BASE64_MACAROON", invoice="BOLT11_INVOICE"

# client pays invoice → obtains preimage

GET /premium-data HTTP/1.1
Authorization: L402 BASE64_MACAROON:HEX_PREIMAGE
```

A server issues a 402 with a macaroon and a Lightning invoice. The client pays, extracts the preimage, concatenates it with the macaroon in the Authorization header, and retries. The server verifies both against its root key — cryptographically, with no user lookup.

The spec is explicit that L402 requires TLS. Macaroons and preimages travel as cleartext at the application layer, so transport security is a hard dependency, same as any bearer token scheme. The docs also flag a spoofing risk — a client hitting a malicious endpoint could leak usable credentials. Binding credentials to an IP address is one mitigation, though it creates friction if the client's network changes.

The spec covers gRPC as well, which matters because Lightning infrastructure is gRPC-heavy. The L402 proxy detects gRPC via the Content-Type header and must run HTTP/2.

On macaroon revocation: in a distributed system, revoking a macaroon typically means rotating or deleting the root key, which invalidates everything issued under it. Lightning Labs recommends embedding per-user identifiers to make revocation more targeted. It's manageable, but it's part of the operational surface that any team building on this needs to account for upfront.

## Where it runs in production

L402 has been in production use authenticating Lightning Labs' own services — Loop (the non-custodial Bitcoin swap service) and Pool (the channel liquidity marketplace). Both are gated via Aperture, an open-source L402 reverse proxy that fronts REST and gRPC backends, handling macaroon issuance, invoice generation, and credential verification.

Aperture also supports dynamic pricing per endpoint — per-request rates, surge pricing, automatic tier upgrades. That flexibility positions L402 as a general infrastructure layer, and Loop and Pool give it a production track record outside of demos.

## What fits L402, practically

The use cases that actually map well:

1. Paid API access without billing infrastructure — a client pays a Lightning invoice, gets a credential, uses it until expiry or the usage cap hits. The credential exists only because a payment happened first, which is structurally different from OAuth or API keys where credentials are issued ahead of any payment.

2. Machine-to-machine metering — one service pays another per call, with Lightning settling in milliseconds. The preimage-as-receipt means the seller verifies payment cryptographically, without querying an invoice database.

3. Content and data paywalls — the "paid web resource" framing goes back to Boltwall in 2019. L402 is the formalized version: HTTP-native micropayment authorization via standard headers.

The automation question is central here. The 402 → pay → preimage → retry loop is straightforward to implement in a client library but clumsy to do manually at volume. lnget handles the buyer side automatically; Aperture handles the seller side. That pairing is what allows L402 to function as infrastructure instead of a demo flow.

The Lightning liquidity reality is also part of the picture. Selling via L402 means receiving many small payments, which requires inbound channel capacity. Buying means needing outbound liquidity available on demand. Channel management is a non-trivial operational dependency, and managed node providers are the practical path for teams that don't want to own that layer themselves.

## Why HTTP 402 being "reserved" matters

HTTP status code 402 has been in the spec since the mid-1990s — reserved as a placeholder for the assumption that internet-native payments would eventually need a standard home in the HTTP layer. L402 gives that placeholder an actual implementation.

The protocol name maps directly to the HTTP code, which is the point: payment authorization at the HTTP layer, using Lightning as the settlement rail. And as of early 2026, IETF drafts are exploring how to give 402 concrete semantics at the standards level — these are drafts, worth being precise about that — but the broader signal is that groups beyond Lightning Labs are now working on HTTP-native payment semantics seriously, across different settlement layers.

Many early x402 integrations use USDC on L2s like Base, though the protocol itself is chain-agnostic by design; Stripe, Coinbase, and others have agent payment layers of their own. L402 is the Lightning-native implementation, with both the settlement layer and the credential design rooted in Bitcoin-native primitives. For teams building on Lightning infrastructure specifically, that distinction is the relevant one.

## The piece that compounds

L402 binds payment and authentication together cryptographically, which collapses an entire coordination layer that most paid API architectures assume you need. The credential is self-verifying because the payment proof is embedded inside it — the server doesn't need to call out to a billing system or check an invoice ledger.

For teams building on infrastructure — validator dashboards selling read access, data feeds priced per query, inference endpoints metering by call — this is probably the most operationally relevant piece of Lightning's current tooling stack.
