---
title: "From primitives to native yield: how Veda reshapes DeFi infrastructure"
slug: "from-primitives-to-native-yield-how-veda-reshapes-defi-infrastructure"
date: "2025-04-08"
description: "Veda introduces a native yield layer that embeds on-chain yield directly into applications, simplifying DeFi UX and infrastructure."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/VEDA_primitives_cover.jpg"

tags: ["bitcoin", "btc", "l2"]
---

Veda is the infrastructure layer that turns passive crypto assets into productive capital. It allows apps and protocols to embed yield directly into user interfaces — with no gas, no manual strategy switching, and no complexity.

• Users deposit into Veda vaults — smart contracts managing capital.  
• Strategists or AI agents rebalance assets across DeFi protocols.  
• Yield is streamed back to users through composable vault tokens.  

All operations are permissioned via Merkle proofs, secured by audits, and optimized for cross-chain deployments.

Think of Veda as an automated yield engine — bridging assets, strategies, and user flows into one native layer.

Veda Labs is building the native yield layer for crypto — modular infrastructure for protocols, wallets, and ecosystems to embed on-chain yield at scale.

Not long ago, Veda was an [idea](https://x.com/veda_labs/status/1907469181643272202).  
Today, it powers over $3 billion in DeFi strategies — quietly embedding yield into user flows across protocols and chains. It doesn’t try to replace DeFi’s composability. It builds on top of it — by making yield a first-class, modular, and verifiable primitive.

Let’s break down what Veda actually is, how it works under the hood, and why it matters for the next wave of DeFi applications.

## Key numbers

• $3.5B+ in total yield infrastructure powered by Veda (ATH as of Jan 2025)  
• First-ever vault token listed on Aave (eBTC)  
• 3 audits: 2 by 0xMacro, 1 by Spearbit — available on [GitHub](https://github.com/Se7en-Seas/boring-vault/tree/main/audit)

## What is Veda Labs?

At its core, Veda is a native yield infrastructure layer. It allows any protocol or application to embed on-chain yield into its interface — without requiring users to interact with individual strategies, rebalance positions, or understand underlying primitives.

Users deposit into Veda contracts (called BoringVaults), and the system handles everything from liquidity routing to strategy execution, using off-chain algorithms and verifiable on-chain constraints.

Think of it as a yield compiler: Veda abstracts away the complexity, but preserves full control and security.

## Why native yield?

DeFi has yield everywhere — but it’s scattered, hard to access, and constantly shifting.

Protocols often need to:  

• Manually integrate yield sources  
• Incentivize users with extra rewards  
• Deal with liquidity fragmentation across chains and rollups

Veda flips this: yield becomes embedded by design.

With Veda, protocols can:  

• Offer higher base yields without extra token incentives  
• Simplify onboarding by removing strategy friction  
• Dynamically optimize liquidity across ecosystems

And users get a cleaner, more intuitive UX — one deposit, no gas for rebalances, no active management.

## Under the hood: modular by design

How Veda works — from user deposits to strategy execution.  
This diagram illustrates the core vault architecture, including Teller, Manager, Accountant, and the Merkle-verified flow of off-chain rebalancing.

![Alt text here](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/VEDA_primitives_how_it_works.png)

Veda’s architecture is built around modular contracts that isolate responsibilities.

### The key components:

• BoringVault — the minimal core vault, delegating logic externally  
• Manager — rebalances vaults by executing whitelisted strategies (Merkle verified)  
• Teller — mints/redeems shares for users  
• Accountant — off-chain pricing module for vault shares  
• Atomic Queue — handles batch user entries and exits (used for withdrawal UX)  
• DecoderAndSanitizer — parses and verifies strategy call data for each protocol

This modularity means Veda can quickly adapt to new protocols, chains, and use cases — without central points of failure or upgrade risk.

Security is enforced through constraints: strategists must submit Merkle proofs for every rebalance call, and all address/function combinations are verified.

Great DeFi products aren’t just contracts — they require infrastructure, product thinking, and market awareness. This diagram from Veda captures that stack clearly.

## Cross-chain by default

Veda isn’t limited to a single chain — yield vaults on Ethereum can deploy capital across L2s, abstracting away the bridging layer. This solves the fragmentation problem without requiring users to move assets manually.

It also opens the door for automated capital routing across ecosystems — governed by either DeFi strategists or AI agents.

## Use cases already live

Veda is not a prototype — it powers real yield infrastructure today.

• PumpBTC vaults: unlocking Bitcoin-native yield  
• cmETH & Modular Assets: a new token class powered by Veda  
• Lombard, Bedrock, MEV Capital: building vaults across use cases  
• Plasma: a stablecoin-focused chain with a $1B Veda-powered vault
• Kraken DeFi Earn: surpassed $100M in total deposits, running on three Veda vaults  
• Binance Wallet & Bybit Web3: both integrating Veda infrastructure for their users  
• BOB: vault now live
• Mizu Labs (Hyperliquid ecosystem): Veda-powered vault  

## Ecosystem and partnerships

Veda Labs connects to a broad range of DeFi systems — protocols, curators, and capital networks — to embed yield directly into user and protocol flows.

Major yield sources supported: Aave, Morpho, Pendle, Curve, Convex.

Key assets: ETHx, mETH, cbBTC, stables.

Curated vaults: Live across TAC ecosystem — via UltraYield, Tulipa, Re7 Labs.

Flagship integrations:

• eBTC on Aave — first vault token listed  
• Liquid BTC with MEV Capital — BTC-native yield layer

Campaigns and strategy layers:

• The Summoning (TAC/Turtle): Ethereum-to-TON liquidity migration  
• Rings Protocol on Sonic: staked assets, veNFT incentives, Telegram-native UX

These aren’t just plug-ins. Veda is present across the stack — from origination to delivery.

## Security and audits

Veda Labs has undergone multiple third-party audits to validate the safety and correctness of its BoringVault architecture. These reviews ensure that vault mechanics — including capital entry/exit, strategy execution, and asset pricing — are governed by transparent and verifiable constraints.

Audit reports available:

• 0xMacro ([artic 0](https://github.com/Se7en-Seas/boring-vault/blob/main/audit/0xmacro-boring-vault-arctic-0.pdf))  
• acro ([artic 1](https://github.com/Se7en-Seas/boring-vault/blob/main/audit/0xmacro-boring-vault-arctic-1.pdf))  
• Spearbit ([artic 0](https://github.com/Se7en-Seas/boring-vault/blob/main/audit/0xmacro-boring-vault-arctic-1.pdf))  

Key coverage areas:

• Merkle-based permission system: All rebalance calls must pass Merkle proof checks, ensuring strategists can only call pre-approved functions on specific protocols and with bounded inputs.  
• Share accounting and price integrity: The Accountant module ensures that off-chain-calculated share prices cannot change too much between updates, protecting users from mispriced exits.  
• Reentrancy and role control: Vault operations like deposits, mints, and rebalances were reviewed for possible reentrancy vectors or privilege escalations.  
• Emergency behavior and refund logic: User deposits can be safely refunded during volatile or invalid conditions via the Deposit Refaunded mechanism.  

No critical issues were found in the Arctic 0 audit. A few minor and informational observations were addressed or documented by the Veda team.

By publishing all audit reports publicly, Veda Labs emphasizes its commitment to open infrastructure, proactive risk management, and scalable, production-grade yield architecture.

“The system’s use of Merkle proofs to gate strategic execution, combined with modularized vault mechanics and off-chain pricing constraints, represents a thoughtfully scoped security model.”  
— from 0xMacro Arctic Audit 0

This quote reflects the auditors’ confidence in the design approach of BoringVault and its supporting contracts. Instead of relying on monolithic permission models, Veda decomposes responsibilities across isolated modules, each governed by explicit constraints — reviewed and enforced.

“Veda’s BoringVault ecosystem exhibits a clean separation of concerns, and reasonable safety properties under adversarial conditions.”  
— from Spearbit Arctic Audit 0

This reinforces that Veda is not only secure by design, but also resilient under real-world stress — with architecture that prioritizes isolation, bounded permissions, and capital recovery mechanisms.

## Beyond Ethereum: Veda as multi-chain yield rails

Veda is becoming the default vault layer across ecosystems — not through splashy launches, but through infrastructure that sticks.

TON expansion via TAC and Turtle: ETH, BTC, and USD vaults live and migrating post-mainnet.

Vault tokens on Aave: eBTC, built with ether.fi and Lombard, remains the first vault token listed on Aave — turning yield-bearing assets into usable collateral.

Upcoming:

• Deeper institutional integrations (exchanges, fintech, neobanks)
• Continued expansion of the exVaults and vVaults product line
• Hybrid BTC products with Pendle

Each of these isn’t just a product — it’s a small extension of a system that routes yield where it’s most useful. Ethereum, Telegram, Bitcoin — Veda doesn’t care where the capital is. It just moves it.

## Learn more

If you’re building with or around Veda:

Start with the [docs](https://docs.veda.tech) for contract structure and integration logic.  
Try the [app](https://docs.veda.tech) to see vaults in action.  

## What’s next?

The goal is not to become a single vault product — it’s to become the native yield layer of crypto. Wherever there’s idle capital, Veda wants to make it productive. Wherever there’s an app, yield should be built in.

Expect deeper integrations, more modular asset types, and a broader cross-chain footprint.

Yield in DeFi has never been scarce. But it’s been scattered — across vaults, rollups, wrappers, fee models, and governance layers.

Veda doesn’t invent new sources of yield. It makes them accessible, composable, and embedded.

What started as a vault architecture is now evolving into something closer to an operating layer — one that protocols don’t notice until they need it, and users benefit from without realizing.

You don’t need to understand Merkle trees or off-chain rebalancers to use a vault. But someone needs to build them right.

That’s the layer Veda is trying to be.

[🔹OUR BITCOIN LAYER 2 DASHBOARD](https://btcboard.io)
