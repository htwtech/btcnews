---
title: "Botanix Amplifi: Market Depth as Infrastructure"
slug: "botanix-amplifi-market-depth"
date: "2026-02-26"
description: "Amplifi vault live on Bitzy and what it means for BTC/stable market structure on Botanix."
author: "Bitboard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Botanix%20Amplifi_%20%20Market%20Depth.png"
coverAlt: "Botanix Amplifi Market Depth"
tags: ["bitcoin", "botanix", "defi", "liquidity", "market structure"]
---

# Botanix Amplifi: Market Depth as Infrastructure


Continuing our Botanix series. [Amplifi vault is now live on Bitzy App](https://x.com/botanix/status/2026283626866905217?s=20) — and the structural angle here is different from what we covered with Blend money.

Blend was about allocation: whose balance sheet your USDC.e sits on, how capital gets routed, what segregation actually means in practice. Amplifi on Bitzy operates one layer below that. It addresses whether a functional BTC/stable market exists to support allocation in the first place.

The configuration is "High Volatility, Narrow" with a 0.30% fee tier. In concentrated liquidity AMMs (Uniswap v3-style), LPs deploy capital only inside a chosen price range, which improves efficiency but creates a real operational problem: the moment price exits that range, you earn nothing until the position gets repositioned. "Narrow" means higher fee density when active, and a higher probability of going out-of-range fast. Managing this manually at scale quickly becomes operationally intensive. Automation is therefore the core product layer. Amplifi's ACLM recalibrates ranges in real time using TWAP deviations and volatility signals, manages fee tier selection, and applies IL mitigation heuristics on top.

A quick look at Bitzy right now (Feb 26 snapshot): ~$526.8K in 24h volume across 1,846 transactions, with the USDC.e/pBTC pool accounting for $511.74K of that on $315.99K in liquidity. The USDC.e/pBTC pair currently accounts for the majority of activity on Bitzy, which is precisely why this integration matters — yield infrastructure only works if there's a functioning market underneath it.

The framing we find more interesting is what Botanix is assembling as a stack: Blend as the savings/allocation primitive, Amplifi as the liquidity/market-making primitive. Different risk surfaces, different jobs. One shows up in your APY dashboard; the other determines whether that APY reflects anything real.

Contracts audited by CertiK, Quantstamp, Halborn, BailSec (per team disclosure), with Code4rena and Pessimistic reports published on Amplifi's security page.
