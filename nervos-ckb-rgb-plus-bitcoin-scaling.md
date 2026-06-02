---
title: "Nervos CKB Is Extending Bitcoin Through RGB++"
slug: "nervos-ckb-rgb-plus-bitcoin-scaling"
date: "2024-11-19"
description: "Nervos Network uses CKB and the RGB++ protocol to expand Bitcoin’s capabilities around scalability, smart contracts, asset issuance, and data availability. Its bet is that Bitcoin can gain more expressive functionality without changing Bitcoin L1 itself."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/Group-2131329953-1-.png"
coverAlt: "Nervos CKB and RGB++ protocol concept extending Bitcoin with execution, data availability, smart contracts, and asset issuance"
tags: ["bitcoin", "nervos", "ckb", "rgb", "btcfi"]
---

# Nervos CKB Is Extending Bitcoin Through RGB++

Nervos Network is taking a different route in the Bitcoin scaling conversation.

Instead of trying to turn Bitcoin itself into a more expressive smart contract chain, Nervos uses its Layer 1 blockchain, Common Knowledge Base, or CKB, as an execution and data layer around Bitcoin.

The key piece is RGB++.

RGB++ is designed to improve on the original RGB model by using CKB to support execution, data availability, and asset state management for Bitcoin-linked assets.

That makes Nervos interesting because it is not just building another Bitcoin L2 narrative.

It is trying to give Bitcoin assets more functionality through a separate but Bitcoin-aligned infrastructure layer.

## The Bitcoin limitation Nervos is attacking

Bitcoin is secure, decentralized, and widely trusted, but it has real limits around scalability and programmability.

Its scripting system is intentionally constrained. That is part of Bitcoin’s security model, but it also makes complex applications difficult to build directly on L1.

Asset issuance, smart contracts, richer data storage, and application-level logic all become hard if the system stays entirely inside Bitcoin’s native scripting environment.

Nervos approaches this by using CKB as a more flexible layer that can support richer state and computation while keeping Bitcoin as the core asset and settlement reference.

The goal is not to modify Bitcoin.

The goal is to expand what Bitcoin-connected assets can do.

## CKB uses a Cell Model

One of the most important parts of Nervos is its Cell Model.

The Cell Model can be understood as a more flexible generalization of Bitcoin’s UTXO model.

Bitcoin’s UTXO structure is simple and powerful, but limited in what it can store and express. Nervos extends that idea into cells that can hold different types of data and support more flexible state transitions.

That matters for applications.

A more expressive data model can support smart contracts, asset issuance, and richer onchain data without forcing every piece of functionality into Bitcoin Script.

This is where CKB becomes useful for RGB++.

It can act as both an execution environment and a data storage layer for Bitcoin-related assets.

## RGB++ improves the asset layer

The original RGB protocol is built around client-side validation and single-use seals.

That model is elegant, but it also has practical challenges around data availability and user experience.

RGB++ tries to solve part of that by using CKB as an additional layer for execution and data availability.

In practice, this means Bitcoin assets can gain more flexible functionality while CKB helps manage the state and data layer.

That is the main Nervos thesis: use Bitcoin for what it is best at, and use CKB to handle the programmability and data requirements Bitcoin does not natively support.

For BTCFi and Bitcoin-native assets, this is a meaningful design direction.

The market does not only need faster transfers.

It needs reliable ways to issue, move, verify, and interact with Bitcoin-connected assets.

## CKB-VM and developer flexibility

Nervos uses CKB-VM, a virtual machine based on the RISC-V instruction set.

This gives developers more flexibility than Bitcoin Script and supports multiple programming languages, including C and Rust.

That is important because developer experience matters.

If building around Bitcoin-connected assets requires a completely unfamiliar and constrained environment, adoption becomes harder. CKB-VM gives Nervos a more general-purpose execution environment while keeping the architecture closer to Bitcoin’s UTXO-inspired model.

This makes Nervos different from EVM-compatible Bitcoin L2s.

It is not simply importing Ethereum’s execution model into Bitcoin.

It is building a separate architecture with its own assumptions, tooling, and tradeoffs.

## Proof of Work and NC-MAX

Nervos CKB uses Proof of Work.

Its consensus mechanism is based on NC-MAX, an upgraded version inspired by Bitcoin’s PoW design.

That gives Nervos a security model that feels more aligned with Bitcoin than many proof-of-stake app chains.

For Bitcoin users, that can matter.

A lot of Bitcoin-aligned infrastructure gets judged by whether it respects the design principles Bitcoin users already trust: proof-of-work security, conservative assumptions, transparent verification, and resistance to arbitrary governance control.

Nervos does not become Bitcoin because it uses PoW.

But it does make its infrastructure story more compatible with Bitcoin’s own design culture.

## Network activity and adoption signals

CKB has shown meaningful activity.

In 2024, average daily transactions reached around 43,600, more than double the Q4 2023 level. In April, 387,600 new addresses were created, a sharp increase from March.

RGB++ also started showing usage after its April 2024 launch, with more than 13,200 transactions and 4,400 unique addresses using the protocol.

Those numbers do not make Nervos a dominant Bitcoin scaling layer by themselves.

But they show that the RGB++ direction has started attracting real activity rather than staying only at the protocol-paper stage.

The next question is whether this activity turns into durable application usage, asset issuance, payments, and liquidity.

## CKB token and storage economics

CKByte, or CKB, is the native token of Nervos.

It is used for data storage rights, transaction fees, and miner incentives.

This is an important design point.

CKB is not only a gas token. It represents a claim on state storage inside the network. That connects token demand to the amount of data and state users want to keep onchain.

Tokenholders can also lock CKB in the Nervos DAO to earn rewards and reduce the dilution effect of secondary issuance.

That gives the token a role in the long-term storage and incentive model of the network.

## Roadmap and future direction

Nervos’ roadmap around RGB++ points toward deeper Bitcoin integration.

The team plans to connect RGB++ with the CKB Lightning Network, develop cross-chain issuance for RGB++ assets across UTXO chains, and launch payment channel infrastructure that integrates with Bitcoin’s Lightning Network.

That direction is important.

If RGB++ stays limited to isolated asset issuance, the opportunity is smaller.

If it connects into payment channels, UTXO-chain interoperability, and Bitcoin’s broader scaling stack, the design becomes much more relevant.

The strongest version of Nervos is not just “smart contracts for Bitcoin.”

It is a UTXO-aligned infrastructure layer for Bitcoin assets, payments, and application state.

## Strengths of Nervos and RGB++

Nervos’ biggest strength is its architecture.

The Cell Model gives it a more expressive data structure while remaining conceptually close to Bitcoin’s UTXO model.

The second strength is RGB++.

By using CKB for execution and data availability, RGB++ addresses some of the practical limitations of the original RGB approach.

The third strength is developer flexibility.

CKB-VM gives developers more options than Bitcoin Script and supports more familiar programming environments.

The fourth strength is Bitcoin alignment.

Nervos uses Proof of Work and builds around Bitcoin-adjacent asset functionality rather than treating BTC as just another bridged token.

## Weaknesses and open questions

The main weakness is complexity.

Nervos depends on an external blockchain, CKB, to support data availability and execution for Bitcoin-connected assets. That adds more moving parts than using Bitcoin alone.

For users, this creates an education problem.

They need to understand what lives on Bitcoin, what lives on CKB, how RGB++ state is managed, and what assumptions are introduced by using CKB as an execution and data layer.

The second risk is adoption.

Bitcoin infrastructure is becoming crowded. Nervos competes for attention with Stacks, Rootstock, Bitlayer, Citrea, Merlin, BOB, Botanix, Midl, and many other approaches to Bitcoin scaling and BTCFi.

The third risk is ecosystem liquidity.

Useful asset issuance is only the first step. For RGB++ to matter at scale, users need wallets, markets, liquidity, tooling, bridges, payment routes, and applications that make the assets useful.

The fourth risk is narrative clarity.

Nervos is technically interesting, but the market often understands simpler stories faster. “EVM on Bitcoin” is easier to sell than “UTXO-aligned execution and data availability for RGB++ assets.”

That does not make Nervos weaker.

It just means the project has to communicate the value clearly.

## Where Nervos fits in Bitcoin scaling

Nervos sits in a specific part of the Bitcoin scaling map.

It is not trying to be a simple BTC wrapper.

It is not just an EVM sidechain.

It is not only a payment channel.

It is building a flexible execution and data layer that extends Bitcoin’s asset capabilities through CKB and RGB++.

That makes it worth watching.

Bitcoin does not need one scaling solution. It will probably develop through multiple layers: Lightning, sidechains, rollups, asset protocols, data layers, bridges, and app-specific infrastructure.

Nervos’ role is to make Bitcoin-connected assets more programmable and easier to scale without forcing everything directly onto Bitcoin L1.

The opportunity is clear.

If RGB++ becomes a practical standard for issuing and using Bitcoin assets, and if CKB can provide the execution and data layer those assets need, Nervos can become one of the more important infrastructure pieces in the Bitcoin ecosystem.

Still early.

Still complex.

But the thesis is real: Bitcoin assets need more than issuance.

They need execution, data availability, and usable application rails.

That is where Nervos is trying to fit.
