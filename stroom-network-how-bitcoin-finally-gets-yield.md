---
title: "Stroom Network: How Bitcoin Finally Gets Yield"
slug: "stroom-network-how-bitcoin-finally-gets-yield"
date: "2025-12-10"
description: "An in-depth look at how Stroom Network turns bridged Bitcoin into a yield-bearing asset by deploying BTC liquidity across Lightning and emerging Bitcoin infrastructure."
author: "HighTower"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/HTW.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/stroom-network.png"
coverAlt: "Stroom Network Bitcoin yield infrastructure"
tags: ["bitcoin", "btc", "defi", "lightning"]
---

## Stroom Network: How Bitcoin Finally Gets Yield

Bitcoin’s architecture limits what can be built on the chain itself. This is intentional. The constraint ensures security. But it also means Bitcoin cannot host DeFi natively. Bitcoin L2s and sidechains solve this by allowing users to bridge BTC into other ecosystems. So users bridge.

As of December 2025, approximately $35 billion in Bitcoin is bridged across various chains. WBTC remains the largest bridge with roughly $13.5 billion in TVL, with Binance’s Bitcoin bridge to BSC holding the second position. The market’s growth reflects increased institutional demand for Bitcoin in DeFi, even as security concerns persist.

Two problems have haunted every bridge design built so far.

The first is custody risk. Whether a bridge is run by a single company, a multisig federation, or a decentralized protocol, something holds the Bitcoin. When custodians are compromised or collude, there is no insurance. No recovery mechanism. Counterparty risk persists through relocation.

The second problem is opportunity cost. Native BTC liquidity sits in a vault, earning nothing while the bridge operator keeps any revenue generated. Users pay entry and exit fees. The asset backing the wrapped token remains completely unproductive.

Stroom Network was built because both problems are solvable.

---

## Origins and Team

Stroom was founded in 2021 and is based in Kyiv, Ukraine. The company is led by Rostyslav Shvets, CEO and founder. Shvets previously worked at blockchain service provider Bitfury and at Lido, the leading Ethereum liquid staking protocol. Co-founder and CTO Slava Zhygulin completes the core leadership.

The founders recognized an underutilized opportunity in the Lightning Network, Bitcoin’s second-layer scaling solution. According to Shvets, Lightning Network is one of the most promising payment rails technologies, but it still has not reached mass adoption. One of the main constraints is liquidity, which directly affects payment reliability and success rates.

In August 2023, Stroom raised $3.5 million in an oversubscribed seed funding round led by Berlin-based crypto investment firm Greenfield. The round included participation from Lemniscap, No Limit Holdings, Cogitent Ventures and Mission Street, Ankr’s venture arm.

The funding was allocated to team expansion and launching Bitcoin “liquid staking” on Lightning, including the release of a corresponding Ethereum-based wrapped token.

---

## The Core Innovation: Yield-Bearing Bitcoin

Stroom is a bridge. But instead of storing BTC in a static multisig vault, it deploys the liquidity.

![Stroom protocol architecture diagram](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/stroom_graph2.png)

<sub>Validators compute daily BTC snapshots and mint new stroomBTC proportionally to all holders, maintaining the 1:1 peg to native Bitcoin.</sub>

When you deposit Bitcoin to Stroom, two processes occur simultaneously.

First, validators detect your deposit on the Bitcoin blockchain and sign a minting message using FROST, a distributed key generation algorithm for Schnorr signatures. You submit this message to the Ethereum smart contract. The contract verifies the signature and mints strBTC to your wallet, a rebasing token that increases in balance as rewards accumulate.

Second, your underlying Bitcoin is deployed to generate yield.

Stroom’s roadmap includes routing payments on the Lightning Network, earning routing fees, BitVM2 operator staking, Babylon restaking, and integrations with Bitcoin L2 protocols. As of December 2025, the Lightning Network has approximately 4,200 BTC in public channels.

The yield flows back to you.

Daily, Stroom validators compute a snapshot of BTC in the system after accumulating rewards. They mint additional strBTC proportionally to all holders. Your balance rebases upward. You earn native Bitcoin yield without moving your asset off-chain.

This is the core mechanic. Yield and bridging are integrated.

Redemption works in reverse. You burn strBTC on Ethereum, specifying your Bitcoin payout address. Validators detect the burn, prepare a BTC payout transaction, and sign it using FROST. Within one hour, your BTC arrives. The 1-to-1 peg to Bitcoin is maintained.

---

## Three Tokens for Different Strategies

Stroom launched with a soft launch in August 2025, initially offering wBTC deposits rather than native Bitcoin. Users can now interact with three tokens in the Stroom ecosystem.

**strBTC**

A rebasing token that increases in balance as daily rewards accumulate. Every holder receives proportional yield automatically. If the protocol earns 1 BTC in routing fees and the total supply is 100 strBTC, each strBTC balance increases by 1/100.

**wstrBTC**

An ERC-4626 wrapped version of strBTC designed for DeFi composition. Unlike strBTC, wstrBTC has a fixed balance. Yield accrues through increasing exchange rates, similar to Lido’s stETH. Protocols that do not support rebasing tokens can integrate wstrBTC seamlessly.

**bstBTC**

An ERC-4626 vault token targeting staking strategies within DeFi, enabling yield-on-yield opportunities.

---

## The Security Model: Economic Incentives, Not Reputation

A federated bridge has an inherent weakness.

If a supermajority of validators collude, they can:

- Steal BTC directly from the multisig wallet  
- Mint unbacked strBTC on the Ethereum side  
- Censor user deposits or redemptions  

Standard protections such as unique deposit addresses, block confirmation delays, and nonce protection mitigate some risks but not all. The fundamental problem remains: a multisig is only as strong as its weakest signers.

Stroom’s roadmap includes integrating restaking.

The plan is for validators to collateralize their operations with restaking protocols such as Symbiotic and EigenLayer. This would bring economic security from ETH, stablecoins, and liquid staking tokens like stETH, assets with deep liquidity and real market value.

If implemented successfully, validators would face slashing penalties if they act maliciously. The slashing premium would go to the entity that detected and reported the malicious behavior.

---

## Restaking Infrastructure Context (December 2025)

As of December 2025, the restaking market has matured.

EigenLayer holds approximately $17B+ TVL. Its mainnet launched in April 2024, and slashing mechanisms became active on April 17, 2025.

Symbiotic has around $1.7B TVL. It launched in January 2025 and offers multi-asset restaking with slashing from the start.

However, Stroom has not publicly announced how much restaking collateral has been committed to secure the bridge. This remains a future implementation step rather than active infrastructure.

---

## Phased Rollout

Stroom is rolling out in three phases, each reducing trust assumptions while increasing decentralization.

### Phase 0 — Soft Launch

Only whitelisted assets are accepted. In August 2025, Stroom began with wrapped Bitcoin deposits. Users convert wBTC to strBTC through an immutable on-chain converter contract. The federation manually manages yield allocation.

### Phase 1 — Native Staking

The bridge opens to all users. Validators run with a permissioned operator set. Yield flows from initial yield sources, but cryptoeconomic security is not yet active.

### Phase 2 — Full Economic Security

Restaking becomes active. Validators are fully collateralized by external assets and slashing conditions go live.

As of December 2025, this phase remains a roadmap item.

---

## Technology Stack

Stroom’s architecture rests on three protocols: Bitcoin, Ethereum, and the Lightning Network.

The bridge uses FROST, a distributed key generation algorithm, to create a joint validator public key. Validators jointly sign minting messages and payout transactions, ensuring that no single validator can move funds unilaterally.

Bitcoin deposit addresses are derived from the validators’ joint public key combined with each user’s Ethereum address. Every user receives a unique deposit address, preventing address reuse and double minting.

The Ethereum smart contracts manage strBTC supply, verify validator signatures, and process redemptions. strBTC is ERC-4626 compliant, enabling deep DeFi integration.

Lightning Network nodes managed by Stroom participate in payment routing and collect fees from transaction flows.

![Lightning routing mechanism](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/stroom_graph1.png)

<sub>Lightning nodes route payments, collect fees on each transaction, and generate yields by maintaining efficient channel liquidity.</sub>

Node performance is monitored by the DAO. Poorly performing nodes can be disconnected.

---

## Security Audit

Arcadia Group completed a security audit in July 2025.

The audit identified 35 findings. As of that time, 34 had been resolved or acknowledged, with one finding acknowledged but not yet remediated.

Critical issues addressed included:

- Validator key management  
- Signature replay vulnerabilities  
- Token supply verification mechanisms  

---

## Governance and Incentives

The Stroom DAO governs four key aspects of the protocol:

- Revenue allocation  
- Restaking collateralization rate  
- Operator selection  
- Slashing conditions  

Locking STROOM tokens grants voting rights.

Governance participants direct liquidity to particular yield strategies and decide how protocol revenue splits between users and restakers.

Voters are accountable. If their chosen strategy underperforms, they receive fewer rewards. If a strategy causes losses, their stakes are slashed.

This mechanism ensures governance participants have skin in the game.

---

## Current State and Adoption

As of December 2025, Stroom has $26.4 million in TVL according to the official application.

The soft launch in August 2025 created the first live opportunity for users to earn strBTC yield on wrapped Bitcoin.

Community engagement has grown through a testnet points program. Users who participated in testing from March to August 2024 earned points redeemable for incentives during the mainnet phase.

The protocol currently integrates with Ethereum DeFi.

Partnerships include ecosystem validators such as Allnodes, Stakin, and P-OPS. The project has also collaborated with infrastructure providers like Gateway.fm and Lnfi.

---

## What Makes This Different

Bitcoin bridging solved the first problem: access to DeFi.

Stroom attempts to solve the second problem: making BTC productive while in DeFi.

Most bridges treat BTC collateral as idle backing for wrapped assets. Stroom treats it as productive capital.

Over the past year the Lightning Network has maintained roughly 4,000–5,000 BTC locked in channels, with increasing participation from major exchanges. Stroom’s model could create additional incentives for liquidity providers if yield sources scale.

The planned restaking-backed security model also differentiates Stroom from traditional multisig bridges.

Rather than relying solely on operator reputation, the design aims to leverage existing liquid staking infrastructure for economic security. However, this mechanism has not yet been implemented.

The FROST threshold signature scheme ensures that no single validator can move funds unilaterally.

The multisig federation is distributed, but not yet fully decentralized.

---

## What Comes Next

Stroom’s roadmap includes several expansions:

1. Additional yield sources such as BitVM2 operator staking, Babylon restaking, and integrations with Bitcoin L2 protocols  
2. Chain expansion from Ethereum to Solana, Bitcoin L2 ecosystems, and other EVM chains  
3. Activation of Phase 2 cryptoeconomic security through restaking  

All yield integrations depend on ecosystem maturation and are not currently live in Phase 0.

The long-term vision is to build infrastructure that unlocks Bitcoin’s potential in DeFi by making yield a default feature rather than an afterthought.

As the ecosystem evolves, protocols that combine security, yield, and usability may define the next phase of Bitcoin’s financial architecture.

---

## Links

Website  
https://stroom.network

Documentation  
https://docs.stroom.network/stroom/

X / Twitter  
https://x.com/StroomNetwork
