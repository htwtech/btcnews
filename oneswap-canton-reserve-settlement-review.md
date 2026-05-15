---
title: "OneSwap Review Adds Clarity Around Reserves and Settlement Risk"
slug: "oneswap-canton-reserve-settlement-review"
date: "2026-05-16"
description: "OneSwap’s latest review gives LPs and institutional users a clearer look at reserve accounting, settlement exception handling, and production controls on Canton. The key signal is not hype, but operational transparency."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/post-2--1778879702230.png"
coverAlt: "OneSwap audit and infrastructure review for Canton trading infrastructure"
tags: ["canton", "oneswap", "defi", "audit", "infrastructure"]
---

# OneSwap Review Adds Clarity Around Reserves and Settlement Risk

OneSwap’s latest review gives a clearer look at how the platform manages reserves, settlement uncertainty, and production infrastructure on Canton.

For trading venues, especially those serving liquidity providers and institutional counterparties, this is the kind of operational detail that matters. Not every risk is visible at the interface level. Reserve accounting, settlement handling, and deployment controls are part of the trust surface.

## Reserve accounting matched on-chain balances

In practical terms, the review found that OneSwap’s internal reserve accounting was aligned with balances recorded on-chain.

That is the main signal.

The platform’s available liquidity calculations excluded fees and other non-tradable balances, giving liquidity providers a cleaner view of the capital actually available for trading activity.

This distinction matters because headline balances can be misleading if they include assets that are not realistically usable for execution. For LPs, the more important number is not just what exists in the system, but what is available to support live trading.

## Settlement exceptions stay visible

The report also details how OneSwap handles failed or uncertain settlements.

Instead of automatically treating unclear outcomes as finalized, the platform keeps these cases visible for review and resolution. That creates a more traceable operational record when follow-up is required.

For liquidity providers and institutional users, this is a practical risk-control point.

Settlement uncertainty does not disappear just because a system abstracts it away. The better approach is to make unclear states observable, reviewable, and resolvable without pretending they were cleanly finalized.

## Mainnet systems are separated by function

OneSwap also describes how its mainnet infrastructure is organized.

The platform separates trading backend services, ledger-facing processes, maintenance operations, and workflow execution. According to OneSwap, production releases are gated by automated testing and dependency checks before deployment.

That kind of separation is not flashy, but it is important for a trading system.

A platform handling liquidity and settlement needs more than product UX. It needs clear operational boundaries, controlled release processes, and enough internal structure to reduce avoidable failure modes.

## One open item remains

The review includes one open item focused on further strengthening recovery processes across settlement paths.

OneSwap frames this as an operational hardening measure rather than a reserve solvency concern. The company also notes that it does not affect the 100% reserve alignment observed during the review.

That is the right way to read it: not as a red flag around reserves, but as an area where the platform is continuing to improve recovery behavior and settlement-path resilience.

## A useful transparency step for Canton liquidity

Overall, the publication is a positive transparency step for OneSwap.

It gives liquidity providers and institutional users a concise view into how reserves are verified, how settlement exceptions are managed, and how production changes are controlled as the platform continues building trading infrastructure on Canton.

For Canton’s broader DeFi and institutional liquidity layer, this kind of reporting is useful. The market needs more than integrations and volume claims. It also needs clear evidence that trading venues can explain how capital is accounted for, how edge cases are handled, and how infrastructure changes are shipped.

Check out the audit report at oneswap.cc/audit.
