---
title: "Native Protocol: A Year Later, Where Bitcoin DeFi Actually Stands"
slug: "native-protocol-a-year-later-where-bitcoin-defi-actually-stands"
date: "2025-08-27"
description: "A year after its initial pitch, Native Protocol is closer to mainnet with nBTC, BYield, and the BLISS stack. This review looks at what actually shipped, how the architecture works, and whether the product can find real demand in Bitcoin DeFi."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/native_main.png"
coverAlt: "Native Protocol BTCFi check cover"
tags: ["bitcoin", "btc", "l2"]
---

Almost a year ago [we covered Native Protocol](https://htwtech.medium.com/native-improving-bitcoins-programmability-and-interoperability-993c9d724052) — back then they had big plans for Bitcoin DeFi but zero product. Mainnet drops next month according to their roadmap. Time to check what actually shipped versus the initial pitch.

## The Technical Foundation: Beyond Another Wrapped Bitcoin

The combine permissionless Bitcoin proving on Sui with IKA’s two-party computation. Users get one key half, MPC network gets the other. Sounds complex but basically means you can’t lose funds to a bridge hack while the protocol still functions.

![nBTC bridging diagram](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/native_img1.webp)

<sub>Diagram from Native showing how nBTC combines trust-minimized bridging, decentralization (Bitcoin + Sui), and self-sovereign verification (source: [gonative.cc/post/nbtc](https://www.gonative.cc/post/nbtc))</sub>

They created nBTC, their cryptographic representation of Bitcoin. Each token matches one BTC sitting in a decentralized dWallet, redeemable anytime through light-client proofs. Verification happens on-chain, making issuance and redemption transparent. The yield comes from three places: DeFi lending markets, Native’s bootstrap incentives, and rewards from partner protocols seeking Bitcoin liquidity. Different from wBTC or tBTC where you trust custodians or committees — here the cryptography enforces the peg.

## BYield Hub: The User Interface Layer

The consumer-facing product is BYield, positioned as a Bitcoin Yield Hub on Sui. Standard yield aggregator interface — connect wallet, pick strategy, collect yield. The infrastructure runs on three layers: interoperable layer for trust-minimized transfers, application layer for Bitcoin staking and DeFi primitives, security layer with state verification and slashing.

![Trust spectrum of BTC interoperability](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/native_img2.webp)

<sub>Native’s “trust spectrum” compares BTC interoperability models — from custodial bridges and multisig to trustless designs — positioning nBTC as a trust-minimized step toward full trustlessness (source: BYield deck)</sub>

Their testnet launched in April 2024 and by September reported over two million transactions with 200,000+ users. The team also won the DeFi category at the Sui Overflow hackathon and became SuiHub Accelerator finalists. Developers seem interested, though testnet metrics always need skepticism. I tracked their Discord during testnet — lot of activity but hard to tell real users from farmers.

## Timeline: From Beta to Mainnet

Native divided their roadmap into three phases. Native Alpha launched in April 2024, introducing nBTC minting, the Bitcoin proving system, and basic partner integrations. Native Beta, scheduled for Summer 2025, includes IKA testnet integration, withdrawals, bridge transactions, and a “Beelievers” NFT testnet campaign.

![Official Native roadmap](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/native_img3.png)

<sub>Official Native roadmap (source: [gonative.cc](https://www.gonative.cc))</sub>

Beta phase running now. The mainnet launch is planned for late September 2025 — basically three weeks from now if they stick to schedule. Token generation and UTXO assets coming Q4 2025/Q1 2026.

## BLISS Stack: Infrastructure for Bitcoin L2s

BYield targets individual users. Native positions BLISS (Bitcoin Liquidity, Interoperability and Security Stack) as infrastructure for Bitcoin rollups. The stack aggregates security, data availability, and interoperability services across Bitcoin L2s, aiming to unify liquidity across the fragmented L2 landscape while providing fast finality through a standard settlement protocol.

![BLISS Stack architecture](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/native_img4.webp)

<sub>Architecture of the BLISS Stack: trust-minimized bridging and L2 state verification at the base, a coordination layer with unified commits, a security layer with slashing and nBTC, and integrations with Union, Avail and Nuffle (source: https://www.gonative.cc/post/bihelix-partners-with-native-to-integrate-with-bliss-for-seamless-interoperability-and-unified-liquidity)</sub>

They integrated with Union for ZK bridging, Avail for data availability, Nuffle for fast finality. Bitcoin rollups can inherit security from Bitcoin while offering EVM-level programmability. They picked Sui for proving because it actually has the throughput — most L1s would choke on verification at scale. Makes more sense than trying to squeeze this onto Ethereum or even Solana.

They spent 2024 signing partners left and right. BiHelix, building on RGB and Lightning Network, partnered to enable unified liquidity across Bitcoin L2s for DeFi, AI, and gaming applications. Satochain integrated BLISS for cross-chain staking and yield aggregation. Secret Network collaboration brought confidential computing to Bitcoin DeFi.

## Security Architecture and Trust Assumptions

The Zero Trust Protocols assume every system component could misbehave, enforcing continuous verification. The Bitcoin proving system uses simplified payment verification and light-client techniques on Sui to verify Bitcoin transactions. When users deposit BTC into a dWallet, IKA’s network produces signatures, but users always retain part of the signing key.

The system validates both Bitcoin state and L2 execution, can slash misbehaving relayers or signers. Integration with Avail’s data availability layer and Nuffle’s fast finality module extends the security model further. Data availability ensures rollups can post transaction data securely while fast finality reduces settlement times.

IKA’s setup splits keys between user and network — different from a 3-of-5 multisig where if three signers collude, funds are gone. Here you’d need both the user AND the MPC network compromised.

## Community Building and Ecosystem Growth

Native spent 2024 building community presence. Their Twitter following grew to 86,000+, with Telegram and Discord communities reaching 18,000 and 85,000 members respectively. The team hosted “Native Summer Spaces” on X discussing Bitcoin interoperability and BTCfi cycles, while hitting the conference circuit at Bitcoin Nashville, Token2049, ETHGlobal, and Cosmoverse.

The “Beelievers” campaign rewarded testnet users, and their hackathon success led to a $25,000 community reward pool. Strategic relationships extended beyond typical DeFi protocols — they partnered with projects working on RWA tokenization (physical gemstones, renewable energy certificates). Unusual mix with DeFi yields, but maybe they’re exploring different revenue streams to see what gets traction.

## Market Position

Native’s 2025 roadmap continues the phased expansion. Testnet-1 (Q1 2025) onboarded validators and introduced smart accounts, governance modules, and dWallet integration. Testnet-2 adds IBC support, Rust-based smart contracts, and formal nBTC primitives. The mainnet, targeting next month, promises dual-staking of their future NTIV token alongside BTC, EVM smart-contract support via evmOS, and the public BYield launch.

Post-launch plans include a unified dashboard, multi-wallet support, fast finality through Nuffle, account abstraction, alternative VM integration (like MoveVM), and expanded cross-chain orchestration. Bitcoin L2s tend to launch late. Native’s September target is ambitious for a stack this complex.

## Where Native Fits

Native built tech that solves real custody problems — bridge hacks, multisig risks, wrapped token trust issues. The Zero Trust Architecture and dWallets represent genuine technical innovation, and mainnet launching next month will show if the market actually needs this complexity.

When October rolls around and we see real TVL numbers, yield performance, and actual user adoption metrics, we’ll know if Native found product-market fit or built another technically impressive solution that nobody uses.

I’m watching those October metrics closely — TVL migration from wrapped products will tell us everything about whether self-custody Bitcoin DeFi has real demand.

## Links

[Website](https://gonative.cc)  
[X (Twitter)](https://x.com/goNativeCC)

[₿itcoin ecosystem dashboard overview](https://x.com/Syntetika)  
[Apply form to be assisted as: Chain or Builder](https://www.htw.tech/builders)  
[HighTower’s X (Twitter)](https://x.com/htwtech_)
