---
title: "Midl Is Building a Bitcoin Execution Layer, Not Just Another BTCFi App"
slug: "midl-bitcoin-execution-layer-btcfi"
date: "2026-05-29"
description: "Midl is trying to reduce the distance between Bitcoin-native assets and usable DeFi actions. The project is still early, but its focus on Bitcoin transactions, EVM-style execution, and developer tooling makes it one of the more interesting BTCFi infrastructure plays to watch."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/Group-2131329951-1780151973329.png"
coverAlt: "Midl Bitcoin execution layer concept connecting BTC, Bitcoin-native assets, EVM-compatible applications, validators, and DeFi flows"
tags: ["bitcoin", "btcfi", "midl", "bitcoinl2", "infrastructure"]
---

# Midl Is Building a Bitcoin Execution Layer, Not Just Another BTCFi App

That is the part of BTCFi that still feels unfinished.

A user can hold the most liquid asset in crypto, but the moment they want to do something more complex with it — swap, lend, borrow, provide liquidity, interact with a new asset standard, or use a structured product — the experience often stops feeling like Bitcoin very quickly.

There is usually a bridge.

Then a new network.

Then a new wallet flow.

Then a wrapped asset.

Then a risk model the user may or may not understand.

For a lot of people, that is where the journey breaks.

Midl is interesting because it is trying to attack that specific break.

Not by saying Bitcoin needs another app. And not exactly by saying Bitcoin needs another generic L2.

The more useful way to understand Midl is as an attempt to build an external execution environment for Bitcoin: users interact through Bitcoin transactions and Bitcoin-native assets, while developers get something much closer to an EVM-style programming environment.

## The user and developer problems are different

A normal Bitcoin user does not want to think in terms of execution environments, RPC endpoints, validators, virtual assets, or transaction intentions.

They want to know whether they can use BTC without leaving the mental model of Bitcoin completely.

A developer, on the other hand, usually does not want to rebuild a full application stack around Bitcoin Script limitations.

They want contracts, tooling, testing frameworks, wallet integrations, indexers, and a familiar way to ship.

Midl is trying to sit between those two needs.

The promise is simple on the surface: let BTC and Bitcoin-native assets become usable inside more expressive applications without forcing the user into the usual bridge-first ritual.

Underneath that, the design is much less simple.

Midl uses a model where a user signs a Bitcoin transaction and connects that action to an intention inside Midl’s execution environment. Validators observe and process those Bitcoin-side actions, execute the corresponding logic in Midl’s EVM-compatible environment, and then connect state back to Bitcoin through proofs and transaction flows.

So the pitch is not “smart contracts inside Bitcoin Script.”

That would be misleading.

The better read is this: Bitcoin remains the base asset and settlement reference, while Midl provides the programmable environment around it.

That also explains why Midl is not trying to compete only on “we are another Bitcoin L2.”

Its real bet is UX and developer accessibility.

If the team can make BTCFi feel less like moving funds into a parallel world and more like triggering applications from Bitcoin-native actions, that is a meaningful unlock.

## The infrastructure work is the signal

Midl originally looked at the problem from a more familiar DeFi direction: how do you build something like an AMM for Bitcoin-native assets?

That is the obvious starting point.

Swaps are the first primitive every ecosystem wants.

But the team seems to have run into the bigger issue quite early: before Bitcoin DeFi can have a deep application layer, it needs the boring infrastructure that makes applications viable in the first place.

The most interesting part of Midl’s development diaries is how much of the work sits below the product surface.

They talk about BIP-322 signatures, forking Ethers, Viem and Hardhat, building MIDL.js, working through Runes support, improving validator coordination, moving from earlier TSS assumptions toward FROST, and redesigning parts of the UTXO model.

That is a good sign in one sense.

It suggests the team is not only writing a Bitcoin narrative over a standard EVM chain. They are dealing with the awkward parts of making Bitcoin assets usable in a more programmable environment.

But it also makes the risk clearer.

Midl is not a finished, battle-tested mainnet system yet. It is still closer to an early infrastructure stack moving from R&D and testnet into something that has to prove itself under real capital, real users, and real adversarial conditions.

That matters because the most fragile part of BTCFi is not always the interface.

It is the trust model hiding behind the interface.

## “No bridge” does not mean “no risk”

When a project says “no bridge,” users often hear “no bridge risk.”

Those are not the same thing.

Midl can remove the visible bridge step from the user journey, but it still introduces its own validator layer, asset-mapping logic, virtual mint and burn flows, FROST/TSS assumptions, and execution environment.

That does not make the design weak by default.

Every Bitcoin scaling or BTCFi design makes tradeoffs somewhere.

Stacks makes one set of tradeoffs. Botanix makes another. Babylon is focused on a different layer entirely, turning BTC into a security and staking asset rather than a general-purpose app execution surface.

Midl’s tradeoff is that it tries to preserve a more Bitcoin-native user entry point while giving developers an EVM-like surface.

If it works, the user gets less friction and the developer gets less pain.

If it fails, it becomes another system where the “Bitcoin-native” language hides a complex middle layer that users still need to trust.

## The current surface is still early

The current product surface points toward a few practical primitives: swaps, lending, Runes-to-ERC20-style mapping, BTC-backed assets, and developer examples for contracts that interact with Bitcoin-side deposits and withdrawals.

None of that should be read as a mature BTCFi economy yet.

There is a difference between having the rails and having deep usage.

Midl appears to have real rails in progress: SDKs, examples, testnet deployments, wallet integrations, developer docs, and infrastructure work.

But the public signs still look more developer-native than capital-native.

We can see engineering movement more clearly than we can see mainnet TVL, user retention, protocol revenue, or risk-adjusted capital flows.

For an early infrastructure project, that is not a problem.

It is just the stage.

The more important question is what Midl needs to prove next.

## What Midl needs to prove

First, security.

The FROST/TSS and validator model has to be publicly auditable, not just described. BTCFi users are going to be much less forgiving than typical testnet users. If BTC is being used as the base asset, the bar is higher.

The project needs published audits, clear validator assumptions, understandable slashing rules, and a clean explanation of what can go wrong.

Second, mainnet credibility.

A testnet app can prove that a design is possible. Mainnet proves whether users and developers are willing to rely on it.

Midl’s next important moment will not be another technical post. It will be the point where real users can interact with real assets under a clearly defined risk model.

Third, wallet UX.

This is probably underestimated.

A lot of BTCFi products lose users before the user ever reaches the actual product. If Midl can make signing and interaction feel natural through Bitcoin wallets, and not like a stitched-together bridge between two worlds, it will have a real advantage.

Fourth, the first serious apps.

Infrastructure becomes interesting when something useful sits on top of it.

AMMs, lending markets, Runes liquidity, BTC-backed assets, launchpad mechanics, maybe stable-asset flows — these are the areas where Midl can start proving whether the architecture creates better user behavior or just better documentation.

A Bitcoin execution layer is only as useful as the actions it makes possible.

## The bigger BTCFi shift

The first phase of BTCFi was mostly narrative.

Bitcoin has the largest asset, therefore Bitcoin DeFi should be large.

The second phase was wrappers and bridges.

Move BTC somewhere else, use existing DeFi patterns, accept the trust assumptions.

The third phase is starting to look more practical.

It is about reducing the distance between BTC capital and usable on-chain actions.

That is where Midl’s direction becomes interesting.

It does not ask the market to believe that Bitcoin should become Ethereum.

It asks whether Bitcoin users can access a more expressive application layer without fully leaving the Bitcoin flow.

That is a cleaner question.

BTCFi does not need every new project to become a full financial universe. It needs better primitives, cleaner risk surfaces, and more honest execution paths.

If Midl can make Bitcoin-native transactions feel like the starting point for DeFi rather than the asset you first have to wrap, bridge, or mentally translate, it will occupy an important niche.

Not the loudest niche.

A useful one.

The most interesting version of Midl is not “another Bitcoin L2.”

It is a Bitcoin execution layer that hides less of the wrong complexity from developers and less of the wrong risk from users.

And that is why it is worth tracking before the narrative gets too simple.
