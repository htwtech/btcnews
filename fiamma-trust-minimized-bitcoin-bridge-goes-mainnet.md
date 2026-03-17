---
title: "Fiamma: Trust-Minimized Bitcoin Bridge Goes Mainnet"
slug: "fiamma-trust-minimized-bitcoin-bridge-goes-mainnet"
date: "2025-12-19"
description: "Fiamma brings a trust-minimized, non-custodial Bitcoin bridge powered by BitVM2 to mainnet, unlocking BTC-backed liquidity across multiple chains."
author: "BTCBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Fiamma_%20Trust%20Minimized%20Bitcoin%20Bridge%20Goes%20Mainnet.webp"
coverAlt: "Fiamma trust-minimized Bitcoin bridge goes mainnet"
tags: ["bitcoin", "btc", "bridge", "bitvm2", "defi"]
---

# Fiamma: Trust-Minimized Bitcoin Bridge Goes Mainnet

Bitcoin holds over $2T in value but sits idle outside DeFi. Without native programmability, BTC holders have relied on centralized wrapped tokens like WBTC — introducing trust assumptions and single points of failure. Billions have been stolen from such bridges over the years.

Fiamma changes this. It’s a Bitcoin bridge where Bitcoin itself checks every move — and as of August 7 2025, it’s live across 11 chains after extensive public testing.

## What Is Fiamma Bridge?

Fiamma is the first trust-minimized, non-custodial Bitcoin bridge powered by BitVM2. It lets users mint FiaBTC, a 1:1 BTC-backed token, directly on supported chains without giving up control of their coins.

At mainnet launch, the bridge supports 11 networks, including Ethereum, Solana, Aptos, Arbitrum, Base, and Polygon. Once minted, FiaBTC can be used in DeFi for trading, lending, or farming, and redeemed for native BTC at any time.

Fiamma differs from traditional BTC bridges by having no central custodian, settling disputes directly on Bitcoin L1, and allowing open, permissionless fraud challenges.

## Funding and Investors

In December 2024, Fiamma raised an oversubscribed $4M seed round, led by Lightspeed Faction and L2 Iterative Ventures, with participation from Astera Ventures, Contribution Capital, Sats Ventures, Chapter One, FoundersHead, and strategic partner BOB. This funding fuels the development of Fiamma Bridge and the Fiamma Layer, a zero-knowledge verification network secured by Bitcoin via BitVM2.

## Partnerships and Ecosystem Activity

Fiamma collaborates with leading projects to expand BTC’s role in multi-chain DeFi. Strategic partnerships include:

- BOB — co-author of the BitVM2 paper and collaborator on production-grade trust-minimized infrastructure.
- Babylon — working together on integrating BTC into proof-of-stake systems through secure bridging.
- Hyperion and OKX — providing liquidity pools and APY opportunities for FiaBTC on Aptos.

These partnerships create a ready-to-use ecosystem for BTC holders from day one of mainnet.

## BitVM2 in Plain Language

BitVM2 acts like a virtual machine for Bitcoin, enabling it to verify complex computations without changing consensus rules. Fiamma uses it to run the bridge on an optimistic model where transactions are considered valid unless someone challenges them.

If a dispute arises, anyone can submit a proof to Bitcoin showing the rules were violated. The challenge is resolved on-chain with compact zero-knowledge proofs. One honest challenger is enough to keep the bridge honest.

Key technical features include the first Groth16 verifier on Bitcoin (built with Succinct and Blake3 hashing), an open Challenge Protocol for permissionless fraud disputes, and the Fiamma Layer — a ZK verification network for Bitcoin-secured apps.

## Isolated Safe Architecture

Beyond cryptography, bridge security often fails because of architecture. Most bridges pool user funds into a single vault, so a single breach can wipe out everything.

Fiamma’s Isolated Safe Architecture assigns every user their own vault, jointly controlled by the user and the bridge committee. Even if the entire committee were compromised, an attacker would also need each user’s key to steal funds. This eliminates the “one breach, total loss” scenario.

## Mission Fiamma

To mark the launch, Fiamma [introduced Mission Fiamma](https://x.com/fiamma_labs/status/1953176659336806687), a campaign combining yield opportunities with simple tasks that reward points:

![Mission Fiamma](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/Mission%20Fiamma%20(1).webp)

<sub>Mission Fiamma.</sub>

You can:

- **Mint** — bridge as little as 0.00001 BTC to any supported chain via Fiamma Bridge to get 1 point.
- **Hold** — keep at least 0.00001 FiaBTC in your wallet on Sei or Aptos and earn 0.1 points per day.
- **Deposit** — add at least 0.00001 FiaBTC into integrated DeFi protocols for 0.4 points per day.

There’s a catch: withdrawing in the first month wipes your points, and withdrawing within the first three months cuts them in half.

The incentives are generous — 50%+ liquid APY with FiaBTC on Aptos via Hyperion, a 4M $mama reward pool, exclusive perks for the first 50 BTC minted, 8x Alpaca Points for the first 10 minters, and up to 103% APY by pairing FiaBTC with xBTC and providing liquidity.

Full guide: [Mission Fiamma](https://app.fiammalabs.io/mission-fiamma)

If Fiamma’s model succeeds, it could unlock billions in idle BTC for productive use across DeFi and RWAs without compromising self-custody or decentralization. Bitcoin remains Bitcoin, but now it can move everywhere.

To dive deeper into the tech behind Fiamma, check out the official docs: https://docs.fiammalabs.io/
