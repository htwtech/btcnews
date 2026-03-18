---
title: "Citrea’s Future Research: Decentralized Sequencers, Atomic Swaps, and Volition"
slug: "citrea-future-research-sequencers-atomic-swaps"
date: "2026-01-22"
description: "Breaking down three specific directions from Citrea's research: Decentralized Sequencer Networks, Trustless Atomic Swaps, and the Volition Model."
author: "Bitcoin Board"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://pbs.twimg.com/media/HDsS6S5XMAAKEVx.jpg"
coverAlt: "Citrea Future Research"
tags: ["bitcoin", "citrea", "l2", "infrastructure", "rollups"]
---

# Citrea’s Future Research: Decentralized Sequencers, Atomic Swaps, and Volition

We were digging through Citrea’s documentation the other day and came across a section labeled Future Research. Usually, these kinds of sections are full of vague ideas that may or may not ever make it past the brainstorming phase. But here, a few things stood out — real, tangible improvements that could have an actual impact on how Bitcoin L2s evolve.

Instead of just skimming over all the ideas they’re exploring, We wanted to break down three specific directions that seemed particularly interesting: Decentralized Sequencer Networks, Trustless Atomic Swaps, and the Volition Model. Not just what they are, but why they matter, what challenges they introduce, and where similar approaches are already being used in other ecosystems.

Bitcoin L2s are still in their early days, and a lot of the tech is being borrowed from what’s already been tested in Ethereum rollups. But not everything translates 1:1, and Citrea’s approach to some of these problems feels unique in the Bitcoin space. Let’s get into it.

## Decentralized sequencer networks

Transaction ordering might seem like a boring detail, but it’s one of the most important pieces of any L2 system. Before anything gets committed to the base layer, transactions need to be sorted and batched properly. That’s what a sequencer does — it makes sure transactions don’t collide, double-spending is avoided, and things stay efficient.

Most rollups today, including Bitcoin L2s, take the easy route: they use a single, centralized sequencer. It’s simple, it works, but it’s also a huge risk. If the sequencer goes offline, the whole network stalls. If it starts censoring transactions, users are at its mercy. And let’s not forget the financial side — whoever runs the sequencer can front-run transactions, prioritize their own trades, and extract MEV (Maximal Extractable Value) at the expense of everyone else.

Citrea wants to change that. Instead of trusting one party, they’re looking into a decentralized sequencer network where multiple independent nodes handle transaction ordering. That means no single entity can decide which transactions go through and which get blocked. If one sequencer fails, others pick up the slack.

Of course, this comes with trade-offs. The biggest challenge? Speed. When multiple sequencers need to coordinate, communication overhead kicks in. Ethereum projects like Optimism and Arbitrum are already wrestling with this problem as they explore decentralized sequencing. There’s also the question of incentives — how do you ensure sequencers don’t just collude or act selfishly? Some protocols, like Hotstuff, CometBFT, and MonadBFT, offer interesting approaches to balancing speed and security, but none of them are a perfect fit for Bitcoin’s unique constraints.

Metis has done some early work on decentralized sequencers in Ethereum, but in Bitcoin rollups, this is still largely unexplored territory. If Citrea pulls it off, it won’t just be another incremental improvement — it’ll be a fundamental shift in how Bitcoin L2s are structured.

That being said, failures of centralized sequencers aren’t theoretical — they’ve already happened. Arbitrum One suffered a major outage in early 2023, where transactions couldn’t be processed for an extended period due to a sequencer failure. Events like this reinforce why decentralization is needed, not just for resilience but also to prevent single entities from becoming critical failure points in the system.

## Trustless atomic swaps

Most Bitcoin L2 solutions today rely on bridges to move assets between Bitcoin and the rollup. These bridges, whether custodial or federated, introduce a fundamental problem — users have to trust a third party to hold their BTC. If the bridge gets hacked or the operators disappear, funds can vanish. And we’ve seen that happen before.

Citrea is trying something different. Instead of wrapping BTC or relying on a centralized custodian, they’re integrating trustless atomic swaps at the protocol level. The idea is simple: let users swap BTC for Citrea’s native cBTC directly, without middlemen. No third parties, no bridges — just cryptographic guarantees.

![Basic Atomic Swap Diagram](https://miro.medium.com/v2/resize:fit:828/format:webp/1*p9_-Ww_pyntWKYinJdX3hg.png)
*Basic Atomic Swap Diagram ([Source](https://docs.citrea.xyz/future-research/trustless-atomic-swaps))*

Atomic swaps work using a technique called hashed timelock contracts (HTLCs). If two people want to trade BTC and cBTC, they each lock their funds in a contract with a special cryptographic condition. Either both sides fulfill the trade, or it doesn’t happen at all. There’s no way for one party to take the other’s funds and run. If the time runs out, both just get their money back.

The tricky part is verification. Citrea uses BitcoinLightClient to make sure that the Bitcoin transaction actually happened before finalizing the swap on its rollup. That’s crucial — without it, you’re either trusting an oracle or adding unnecessary complexity.

So why does this matter? Because bridging Bitcoin to L2s has always been a messy process. Right now, most solutions rely on wrapped assets like WBTC (which is basically BTC held in a smart contract issued on Ethereum) or federated multisigs that introduce centralization risks. Even AtomicDEX, which supports atomic swaps, does it as a separate protocol rather than building it into the network itself.

One question that remains unaddressed in their documentation is how this system will handle liquidity depth and market-making. Atomic swaps are elegant cryptographically, but need sufficient liquidity to be practically useful at scale.

Citrea is taking a different approach. Instead of treating atomic swaps as an external service, they’re making them part of the L2’s core architecture. That means no reliance on bridges, no wrapped BTC, and a direct way to move assets between Bitcoin and Citrea without extra trust assumptions. If they pull this off at scale, it could be one of the cleanest BTC interoperability solutions we’ve seen.

## Volition Model: hybrid data availability

The way Bitcoin rollups handle data is a constant trade-off between cost and security. On-chain storage is the gold standard — fully transparent, verifiable by anyone, and as secure as Bitcoin itself. But it’s expensive. Every byte stored on L1 competes for space, and fees can skyrocket. The alternative is off-chain storage, which cuts costs but introduces new risks — data is no longer inherently secured by Bitcoin, and users have to trust some external system to keep it available.

![Volition Model Diagram](https://miro.medium.com/v2/resize:fit:828/format:webp/1*knLVKET91uXRPNODQhOu8w.png)
*Volition Model Diagram ([Source](https://docs.citrea.xyz/future-research/volition-model))*

Citrea’s Volition Model takes a different approach. Instead of forcing one method or the other, it lets users decide. If they want full security, they can store data on-chain, ensuring that every transaction is directly verifiable on Bitcoin L1. No trust assumptions, just raw cryptographic security. But if cost efficiency is the priority, they can store data off-chain while still proving validity through ZK proofs. The network doesn’t rely on a single storage method; both on-chain and off-chain data are combined into a single, unified Citrea state.

This is more than just a toggle switch. The real challenge is ensuring that no matter where the data lives, the rollup state remains valid, consistent, and fraud-proof. Transactions still need to be cryptographically verified, and the system has to work seamlessly whether the data is anchored directly to Bitcoin or managed externally.

Other rollups have experimented with this kind of model — zkSync on Ethereum, for example, has its own version of Volition. But in Bitcoin L2s, this level of data availability flexibility is practically nonexistent. Most BTC L2s, like Stacks, Botanix, and Rootstock, either go all-in on on-chain DA (secure but costly) or offload everything to external DA providers (cheaper but riskier). Citrea is trying to carve out a middle ground, making Bitcoin rollups both scalable and decentralized.

A particularly interesting aspect that isn’t fully explored in their docs is how the economic model will work with this hybrid approach. Different fee structures would make sense for on-chain versus off-chain storage, adding another layer of complexity to the design.

Looking at Citrea’s research priorities, it’s clear they’re thinking beyond just another standard Bitcoin rollup. Decentralizing sequencers, embedding atomic swaps into the protocol, and introducing a flexible data availability model all point toward a more resilient, scalable L2 architecture. These aren’t just incremental improvements — they’re fundamental shifts in how Bitcoin L2s can be designed.

The translation from research to implementation remains the most significant hurdle. Theoretical designs often encounter unexpected challenges when moved to production, especially in the Bitcoin ecosystem where conservatism and security take precedence over rapid iteration.

That said, Citrea’s research directions provide a valuable roadmap not just for their own development, but potentially for the entire Bitcoin L2 ecosystem. By tackling sequencer centralization, bridge security, and data availability flexibility, they’re addressing precisely the areas that need innovation for Bitcoin L2s to reach their full potential.

We’ll be following their progress closely, particularly on the Volition Model which could fundamentally change how we think about scaling on Bitcoin. If even a portion of these research initiatives makes it to production, it would represent a significant leap forward for Bitcoin’s L2 landscape.

Check out [Citrea docs](https://docs.citrea.xyz) for technical details.
