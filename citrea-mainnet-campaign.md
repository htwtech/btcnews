---
title: "Citrea Bitcoin L2 Mainnet Campaign: Dashboard, Bridge, ctUSD & Metrics"
slug: "citrea-mainnet-dashboard-bridge-ctusd"
date: "2026-02-03"
description: "Inside Citrea’s mainnet launch: dashboard mechanics, ctUSD design, BitVM bridge architecture and early on-chain metrics."
author: "HighTower"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/HTW.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Citrea%20Mainnet%20Campaign%20Analysis.png"
coverAlt: "Citrea Mainnet Campaign Analysis"
tags: ["bitcoin", "btc", "l2", "citrea", "ctusd", "bitvm", "zkrollup"]
---

Citrea went live on MAINNET January 27. By early February, 157,213 transactions had settled on-chain, with 1.23K total accounts active and 636 cBTC transfers recorded. The team deployed a dashboard tracking six distinct participation categories.

This is what bootstrap activity looks like when the infrastructure actually works.

---

![Citrea Mainnet Campaign dashboard overview](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Citrea%20mainnet%20dashboard.jpeg)

<sub>Citrea Mainnet Dashboard Status as of January 27, 2026.</sub>

---

## How the Dashboard Works (And Why It Matters)

The campaign tracks real on-chain behavior across six categories. The theory is that measuring capital deployment, liquidity depth, and trading activity instead of point counts pulls participation in a different direction.

### Live Categories (as of Feb 3):

- **Bridger**  
Measures net asset inflow and duration. How much BTC or stablecoins enter Citrea, and for how long users keep capital deployed. The longer you hold, the higher your score.

- **Liquidity Provider**  
Pool depth across pairs, plus how long funds stay committed.

- **Trader**  
On-chain swap volume and frequency.

### Coming Soon:

- **Lender**  
BTC-backed lending markets tracking cBTC deposits and ctUSD borrows.

- **Yield Strategist**  
Participation in vaults and structured yield products from institutional market makers.

- **Adventurer**  
New or experimental features — prediction markets, privacy tools, Lightning swaps.

What's notable: retroactive accounting. Bridging from day one counted toward scores even though the Bridger tracker didn't go live until January 30. Week 1 boosts applied to early activity, then metrics ran independently.

Whether this fully prevents farming is harder to say. It at least makes farming less obvious.

---

## The Stablecoin Play: ctUSD as Institutional Bridge

MoonPay issued ctUSD as Citrea's native stablecoin, powered by M0 infrastructure.

The structural advantage is obvious: instant on/off ramps without exchange gatekeeping.

The catch is issuer and regulatory dependency — as with every new stablecoin.

### What matters operationally:

- **Instant fiat ramps**  
Users in 49 US states can buy ctUSD with a credit card via MoonPay. No exchange account required.

- **Institutional settlement**  
ctUSD redeems to actual dollars. Lock BTC, borrow ctUSD, cash out to your bank account. That is the bridge to traditional finance workflows.

- **Unified liquidity pool**  
One canonical stablecoin from day one means liquidity pools form instead of fragmenting.

- **Compliance infrastructure**  
MoonPay’s licensing footprint across 160+ countries is operational infrastructure, not marketing.

First week: ctUSD held its peg, remained liquid for large swaps, LPs earned real fees. Pairs like cBTC/ctUSD formed immediately.

Baseline looks solid. But it is still week one.

---

![Citrea with ctUSD ecosystem maturity comparison](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Citrea%20graphic.jpeg)

<sub>Citrea with ctUSD compared to typical network maturity curves.</sub>

---

## The Bridge Architecture: BitVM in Practice

Clementine, Citrea's bridge, uses Bitcoin itself as the security mechanism — a design shift from federated multisigs or custodial vaults.

Ten signers control a shared BTC vault via N-of-N MuSig2. All ten must collaborate to release BTC. However, security only requires one honest signer to prevent theft.

Pre-signed spending rules lock what BTC can be released. If withdrawal does not match a cBTC burn on L2, any signer can initiate a BitVM challenge on Bitcoin L1.

Bitcoin consensus enforces the rules. No separate validator set.

### Cost compression

Bridge validation dropped from ~$15,000 per batch to under $100.

That means ~5,000 L2 transactions settle to Bitcoin for roughly $0.02 each in fees.

Batches post regularly without congesting Bitcoin. State diffs and proofs are posted via Taproot.

Citrea operates as a ZK rollup. Validity proofs are generated off-chain, posted to Bitcoin, and BitVM enforces settlement without soft forks or native SNARK verification.

ZK execution + BitVM dispute resolution + N-of-N accountability forms a new BTC bridge security model.

---

## Early Metrics

Explorer stats (early February):

- Total transactions: ~156K  
- cBTC transfers: ~660  
- Total accounts: 1.23K  
- Total addresses: 4.09K  

Transaction success rate stayed above 99% throughout the first month.

Average gas spend remains negligible.

UX friction around stablecoin-only wallets without cBTC for gas was acknowledged quickly. Account abstraction improvements are coming.

That response speed suggests active operational control, not delegated infrastructure.

---

![Citrea Mainnet Explorer metrics](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Citrea%20explorer.jpeg)

<sub>Citrea Mainnet Explorer statistics snapshot.</sub>

---

## Remaining Categories

When Lender launches, BTC-collateralized lending becomes a live Bitcoin capital markets product.

Deposit cBTC. Borrow ctUSD. Deploy capital.

Yield Strategist will track structured yield products. If execution matches institutional standards, this becomes real Bitcoin-native yield infrastructure.

Adventurer covers prediction markets, privacy tooling, and experimental features including shielded transfers.

---

## Partnership Lineup

The partner list signals operational responsibility more than branding.

Major crypto institutions are running bridge signers and nodes. Infrastructure providers are managing validator networks and capital. On/off ramps connect directly to banking rails. Lending and market-making integrations form the early DeFi stack.

If something breaks, it is infrastructure teams resolving it — not marketing.

---

Ultimately, mainnet traction, bridge resilience, capital depth, and derivatives liquidity will determine whether Citrea evolves into durable Bitcoin capital markets infrastructure or remains a launch-phase spike.
