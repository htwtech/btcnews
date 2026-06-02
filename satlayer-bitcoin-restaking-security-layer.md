---
title: "SatLayer Turns Bitcoin Restaking Into Modular Security"
slug: "satlayer-bitcoin-restaking-security-layer"
date: "2025-04-10"
description: "SatLayer is building a modular security layer on top of Babylon, where BTC-based assets can be restaked to secure Bitcoin Validated Services. Its bet is that Bitcoin can become slashable economic security for external apps without changing Bitcoin L1."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/Group-2131329951-3-.png"
coverAlt: "SatLayer modular Bitcoin restaking infrastructure with Babylon, BTC collateral, operators, slashing, and Bitcoin Validated Services"
tags: ["bitcoin", "btcfi", "satlayer", "babylon", "restaking"]
---

# SatLayer Turns Bitcoin Restaking Into Modular Security

SatLayer is a modular security layer for Bitcoin.

Built on Babylon, it lets BTC holders restake BTC-based assets to secure decentralized applications and protocols known as Bitcoin Validated Services, or BVS.

That puts SatLayer in one of the more interesting corners of BTCFi.

It is not trying to build another Bitcoin DeFi app. It is trying to turn Bitcoin’s economic weight into programmable, slashable security for external systems.

The idea is simple from a market perspective: Bitcoin has the largest collateral base in crypto, but very little of that collateral is used to secure applications beyond Bitcoin itself.

SatLayer wants to change that without modifying the Bitcoin base layer.

## Bitcoin security becomes programmable

Bitcoin has always had enormous economic security.

The problem is that this security has mostly stayed inside Bitcoin’s own monetary system. BTC holders could store value, move value, or use wrapped versions of BTC elsewhere, but they could not easily delegate Bitcoin’s economic weight to secure external services.

SatLayer is built around that gap.

It lets BTC-based assets become restakable collateral. Developers can launch Bitcoin Validated Services that rely on this collateral for security. Operators run the infrastructure and can be punished if they violate the rules defined by each service.

That makes SatLayer closer to Bitcoin-native restaking infrastructure than a simple yield product.

The point is not only to earn more BTC yield.

The point is to make BTC-backed security usable by new networks, apps, and protocols.

## Babylon is the base layer

SatLayer is built on Babylon Genesis.

Babylon provides the base infrastructure for Bitcoin staking and slashing, while SatLayer adds a developer-facing restaking layer for external services.

This distinction matters.

Babylon is focused on bringing BTC into staking and Bitcoin-secured networks. SatLayer builds on top of that idea and gives developers a more modular way to define services, operator behavior, reward logic, and slashing conditions.

In practice, SatLayer turns Bitcoin staking into a more flexible security market.

A BVS can define what it needs.

Restakers can delegate collateral.

Operators can provide service-level infrastructure.

Rewards and penalties can be handled according to service-specific rules.

That is the restaking model: security becomes reusable.

## How SatLayer works

SatLayer has three main participant groups.

Restakers deposit BTC-based assets such as WBTC, stBTC, LBTC, or other supported Bitcoin liquid staking and wrapped assets.

Operators run infrastructure for Bitcoin Validated Services and accept slashing risk if they fail or act maliciously.

BVS developers build services that use SatLayer’s restaked Bitcoin collateral as external security.

Under the hood, SatLayer uses Babylon’s BTC staking foundation and EOTS, or Extractable One-Time Signatures, to support slashing behavior without requiring smart contracts directly on Bitcoin.

That is a key part of the design.

Bitcoin itself does not have expressive smart contracts in the Ethereum sense. So BTC restaking infrastructure has to work around Bitcoin’s constraints while still creating credible penalties for bad behavior.

SatLayer adds programmability through CosmWasm, allowing services to define rules and logic around staking, delegation, rewards, and slashing.

Its modular contract architecture includes components such as StateBank, BVSDriver, and SlashManager.

That makes the system flexible, but it also means risk depends on how each BVS is designed.

Restaking gives Bitcoin more utility.

It also introduces new responsibility.

## Restaking is not the same as liquid staking

SatLayer should not be confused with liquid staking protocols.

Liquid staking protocols usually issue liquid tokens that represent staked assets. Their core use case is liquidity: users stake, receive a liquid representation, and can continue using that asset elsewhere.

SatLayer is different.

It does not issue its own liquid staking token. Instead, it integrates with BTC-based assets and liquid staking tokens such as WBTC, stBTC, FBTC, LBTC, and others.

The core use case is security, not liquidity.

Restaked BTC collateral is used to secure external services. In return, users may receive rewards from BVS-level emissions or service-specific incentives.

That also means slashing risk exists.

This is the major difference.

In a liquid staking product, the user mostly thinks about staking yield and liquidity. In a restaking system, the user also has to understand what external services are being secured, who the operators are, what behavior can be slashed, and how risk is priced.

That makes SatLayer more similar to EigenLayer in concept, but with Bitcoin-based collateral and Babylon as the underlying BTC security layer.

## Funding and early-stage status

SatLayer raised $8 million in pre-seed funding led by Hack VC and Castle Island Ventures.

Other investors include Franklin Templeton, OKX Ventures, Amber Group, Finality, CMS Holdings, Arcanum, UTXO, Maven 11, and Blkcelerate.

That investor base is notable because SatLayer is still early.

Its devnet is open, and testnet is still forthcoming. The project is actively developing and iterating on infrastructure before broader production usage.

That matters for how the market should read it.

SatLayer is not a mature restaking economy yet. It is an early attempt to define the modular security layer for Bitcoin.

The thesis is strong.

The production proof is still ahead.

## Security work is already part of the story

SatLayer has undergone multiple audits across different parts of its stack.

Its EVM contracts across Ethereum, BNB, Berachain, and Bitlayer have been reviewed by Zellic and Salus. Its Move-based staking app for Sui has been reviewed by Zenith and Asymptotic. Its CosmWasm contracts on Babylon have been reviewed by Oak Security, Hashlock, Coinspect, and Dedaub.

The covered modules include staking, delegation, slashing, and reward logic.

SatLayer also maintains an active bug bounty through Sherlock.

That is important because restaking protocols sit in a dangerous part of the stack.

They are not just applications.

They become shared security infrastructure.

If a normal app fails, the damage can be contained to that app.

If a restaking layer fails, the damage can spread across multiple services, operators, and asset holders.

Audits do not remove risk, but they are a necessary baseline for infrastructure that handles slashable collateral.

## Where SatLayer fits against other projects

SatLayer sits at the intersection of BTC restaking, modular security, and Babylon-based infrastructure.

Babylon is the base PoS chain and Bitcoin staking layer. SatLayer builds on top by adding developer-facing restaking logic and infrastructure for Bitcoin Validated Services.

BounceBit is more focused on yield and dual staking across CeFi and DeFi rails. It is not primarily a permissionless infrastructure layer for external app security.

Bitlayer is a Bitcoin L2 focused on scalable computation and EVM compatibility through BitVM-style infrastructure. It is closer to execution than security-as-a-service.

EigenLayer is the closest conceptual comparison, but it is Ethereum-native and built around ETH and ETH LSTs rather than BTC-based collateral.

Stroom, Lorenzo, Lombard, and similar projects are better understood as BTC liquid staking or BTC liquid asset providers. They are not direct competitors in the same sense. They can become upstream collateral sources for SatLayer.

That is the important positioning.

SatLayer is not trying to be the only BTC asset issuer.

It is trying to become the place where BTC-based assets become slashable security for external services.

## The upside is large, but the risk is real

The opportunity is clear.

If Bitcoin can become reusable security, BTC stops being only passive collateral and starts becoming part of the infrastructure layer for new applications.

That could create a new market around Bitcoin Validated Services: oracles, data layers, bridges, rollups, automation networks, middleware, and other protocols that need economic security.

But the risk surface is also larger than simple staking.

Restakers need to understand what they are securing. Operators need to be reliable. BVS developers need to design slashing logic carefully. The protocol needs to keep reward accounting, delegation, and punishment mechanics clean.

Bad slashing design can punish users unfairly.

Weak operator coordination can reduce reliability.

Poor BVS risk disclosure can make users chase yield without understanding what their collateral is exposed to.

SatLayer’s modularity is powerful, but it also means the quality of each BVS matters.

Not all restaking opportunities will carry the same risk.

## What to watch next

The most important milestones are not just new integrations.

The better watchlist is more specific.

Watch the testnet launch and how clear the operator model becomes.

Watch which BTC assets are supported as restakable collateral.

Watch the first Bitcoin Validated Services and whether they solve real infrastructure problems or mainly exist to farm early incentives.

Watch how slashing rules are explained to normal users.

Watch whether rewards are tied to real service demand or mostly to bootstrap emissions.

And watch whether SatLayer can make restaking feel understandable without hiding the risk underneath a clean interface.

Bitcoin restaking is a big category if it works.

But it will only work if users can understand what their BTC-based collateral is doing and why the reward is worth the risk.

SatLayer is one of the first serious attempts to turn Bitcoin into permissionless, slashable security for external apps.

That makes it worth tracking.

Not because it is already proven.

Because it is aiming at one of the most important questions in BTCFi:

Can Bitcoin’s economic weight secure more than Bitcoin itself?
