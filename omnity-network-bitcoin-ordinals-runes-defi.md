---
title: "Omnity Network: Bridging Bitcoin Ordinals and Runes into DeFi"
slug: "omnity-network-bitcoin-ordinals-runes-defi"
date: "2026-01-28"
description: "Omnity Network is a cross-chain protocol built on DFINITY Internet Computer (ICP) that functions as a Bitcoin asset hub for decentralized finance."
author: "Bitcoin Board"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://pbs.twimg.com/media/HDsWqB0WwAE9M3-.jpg"
coverAlt: "Omnity Network"
tags: ["bitcoin", "omnity", "ordinals", "runes", "defi", "interoperability"]
---

# Omnity Network: Bridging Bitcoin Ordinals and Runes into DeFi

[Omnity Network](https://www.omnity.network) is a cross-chain protocol built on DFINITY Internet Computer (ICP) that functions as a Bitcoin asset hub for decentralized finance. The platform provides two core services: Omnity Hub for interoperability and Runes Exchange Environment (REE) for on-chain execution.

## Architecture and Core Components

Omnity Hub connects Bitcoin with numerous Layer-1 and Layer-2 blockchains through a fully on-chain approach without custodial solutions. This setup makes it possible to move BTC-based assets like Ordinals and Runes across networks directly — without handing them to a custodian.

REE represents a new Bitcoin-native execution layer that enables smart contract-like functionality on Bitcoin’s blockchain itself. This unlocks possibilities for swaps, lending, and other DeFi operations without altering Bitcoin’s protocol. By leveraging ICP’s Chain-Key cryptography and direct Bitcoin integration, Omnity can coordinate cross-chain transactions and even directly sign Bitcoin transactions in a decentralized manner.

## Bitcoin-Native Assets: Ordinals and Runes

Omnity supports two emerging Bitcoin-native asset standards:

* Ordinals — a protocol allowing data attachment (inscriptions) to individual satoshis, effectively creating NFTs on Bitcoin. This enables unique digital art or collectibles on Bitcoin’s blockchain, though trading Ordinal NFTs on L1 can be slow and costly.
* Runes — a fungible token standard on Bitcoin introduced by Casey Rodarmor (creator of Ordinals) to improve upon earlier Bitcoin token experiments like BRC-20. Runes use Bitcoin’s native UTXO model and embed token instructions in transaction scripts (via OP_RETURN), avoiding heavy data inscriptions. As a result, Runes work with existing tooling like full nodes and indexers, and use less blockspace than inscription-heavy formats.

In practice, a “Rune” token is created through an etching process (defining name, supply, divisibility) and managed through standard Bitcoin transactions. For example, transferring Runes requires consuming and producing UTXOs similar to regular BTC transactions.

## Omnity Hub: Integrating Bitcoin Assets Across Chains

Omnity Hub serves as the interoperability backbone connecting Bitcoin and its assets (BTC, Ordinals, Runes, etc.) with other networks. Built as an on-chain hub-and-spoke system: Bitcoin serves as the hub while various blockchains (Ethereum, Solana, Cosmos chains, ICP itself, and even Bitcoin Layer-2s like Bitlayer or Rootstock) are spokes.

Through this hub, users can transfer Bitcoin or Bitcoin-derived tokens to other ecosystems and back in a trustless way. In April 2024, Omnity executed the first ever trustless Rune token transfer between Bitcoin and ICP, demonstrating that a Bitcoin-native token could be moved to a different chain without custodial bridges. The architecture below shows how Omnity Hub facilitates a 1:1 token migration between Ethereum and ICP, with assets redistributed across staking rewards, auctions, and the Hub itself.

![Omnity Hub Architecture Migration](https://miro.medium.com/v2/resize:fit:828/format:webp/1*nUyiMmknKqMPNrnTxDEaJA.png)
*Omnity Hub enables trustless migration between Ethereum and ICP. Here, $OCT tokens are converted 1:1 into $OT, redistributed across staking, auctions, and the Hub itself (source: [Omnity Blog](https://medium.com/omnity/the-evolution-from-octopus-to-omnity-fbe1860e797f))*

Today, the Hub supports major networks including Bitcoin, Ethereum, Solana, TON, ICP, and Bitcoin L2s like Bitfinity and Core. Omnity lets users move Runes across chains directly — all transfers are verified on-chain, with no need for relayers or custodians.

## Technical Implementation of Cross-Chain Operations

![Omnity Hub Runes Interface](https://miro.medium.com/v2/resize:fit:828/format:webp/1*YHwGH8DGWrHBnLjPaVa3tw.png)
*(Source: [Omnity Hub Runes](https://hub.omnity.network/runes))*

Omnity Hub employs light-client verification and ICP’s chain integration to trustlessly observe one chain and act on another. When a user moves assets, the Hub uses on-chain “tickets” representing the transfer: a Bitcoin deposit or Rune mint on one side triggers the release or creation of an equivalent asset on the target chain.

All of this is handled by ICP smart contracts (canisters) that run a Bitcoin full node light client and can cryptographically sign Bitcoin transactions via Chain-Key technology. The result is non-custodial bridging — users never hand their keys to any middleman.

For instance, bridging a Rune token from Bitcoin to an EVM chain involves:
* Burning the Rune on Bitcoin (via an on-chain transaction the canister detects)
* Instructing a small Omnity contract on the EVM side to mint an equivalent token for the user

To bring an asset into Bitcoin as a Rune, Omnity’s EVM contract might call a function like `mintRunes(tokenId, receiver)` which emits an event. The Omnity Hub listens and then etches or mints the corresponding Rune on Bitcoin to the user's address.

Throughout this process, transaction validation is critical — Omnity waits for sufficient Bitcoin confirmations (typically 4–6 blocks) to finalize a deposit and uses on-chain verification (not off-chain oracles) to ensure that a reported transaction or event is authentic. By maintaining verifiable light clients for each integrated chain, the Hub upholds a high security standard (comparable to running full nodes) for all cross-chain operations.

The Hub is designed to be asset-agnostic, and support for NFTs like Ordinals was added through specialized “anchor” modules. Multi-chain functionality for Bitcoin Ordinals is now live, enabling users to wrap and transfer inscriptions across chains such as ICP, Ethereum, Solana, and more via the Hub.

## REE: Bitcoin-Native Smart Contracts via Runes Exchange Environment

![REE Architecture](https://miro.medium.com/v2/resize:fit:828/format:webp/1*30lygSyU6K4HkoOsW9ZqcQ.png)
*(source: REE Whitepaper)*

While the Hub handles interoperability, REE brings complex transaction logic to Bitcoin without relying on changes to the base layer. Bitcoin’s base layer normally cannot execute multi-step DeFi logic. REE coordinates logic off-chain, while signing and settling transactions on Bitcoin through native UTXOs and PSBTs. It relies on a process called Decentralized PSBT Signing (DPS), where Bitcoin transactions are co-signed across participants before being finalized.

In REE, financial protocols (like DEXs or lending platforms) are implemented as ICP canister smart contracts termed “exchanges.” These exchanges manage liquidity pools of Bitcoin or Rune assets and have dedicated Bitcoin keys (generated by ICP’s Chain-Key cryptography) to hold funds and sign transactions.

## Transaction Coordination Process

![REE Transaction Flow](https://miro.medium.com/v2/resize:fit:828/format:webp/1*aG3_N3QUPGh8AIsYUGNBpg.png)
*The full flow of REE execution: from user PSBT signing to orchestrator coordination and final Bitcoin broadcast. Multiple exchanges can sign within a single atomic transaction (source: REE Whitepaper)*

When a user wants to perform a DeFi action (say swap BTC for a Rune token), the user’s wallet and the REE canister protocols co-create a Bitcoin transaction that executes the swap directly on L1.

The process begins with the user’s front-end (or SDK) constructing a PSBT that specifies all intended inputs and outputs for the operation. For example:
* Input: the user’s BTC UTXO
* Outputs: the Rune tokens UTXO to the user and BTC change back to the pool

The user signs the PSBT first with their Bitcoin key, effectively approving the spend of their UTXO under the agreed terms. This signed PSBT is then sent to the REE Orchestrator, a coordinating canister that oversees execution.

![REE Orchestrator Interface](https://miro.medium.com/v2/resize:fit:828/format:webp/1*_YOs2w5u9WgEFN_9NXrIFw.png)
*(Source: [Omnity REE](https://www.omnity.network/ree))*

The orchestrator validates everything before proceeding — it checks that the inputs are valid and unspent and that the transaction format is correct. For Rune tokens, this involves consulting an on-chain Runes indexer (also built by Omnity) to verify any OP_RETURN instructions and ensure the user actually has the Rune amounts claimed.

Once input validation passes, the orchestrator calls each relevant exchange canister to co-sign the PSBT. In our swap example, it would call the RichSwap exchange canister which manages the liquidity pool. The exchange logic verifies that the swap rate or pool state is acceptable and then uses its pool’s Bitcoin private key (stored securely via ICP’s multi-party computation) to sign the PSBT as well.

With all required signatures collected (user and exchange(s)), the PSBT is complete — the orchestrator broadcasts the finalized transaction to the Bitcoin network, where it gets mined like any normal transaction.

## Atomicity and Security

Crucially, if any step fails, REE aborts the whole operation. All signatures are gathered before broadcasting; if an exchange refuses to sign (say the price moved or pool ran out of liquidity), the orchestrator will roll back and not broadcast anything. This ensures atomicity: either the entire multi-party transaction executes, or nothing does — funds never get stuck in an intermediate state.

No assets move until both parties sign and the transaction is mined — custody never leaves the user’s wallet during the process. As a result, transactions on REE are either executed completely or not at all, protecting users from partial fills or front-running attacks. By locking inputs at the start, REE makes front-running practically impossible — even orchestrators can’t modify what’s already signed.

## Developer Capabilities

For developers, REE opens up programmable logic on Bitcoin without introducing new opcodes or protocol changes. Everything runs via smart contracts on ICP that coordinate native Bitcoin transactions. The logic resides in Rust-based canisters on ICP, but these canisters are tightly coupled to Bitcoin through ICP’s Bitcoin integration (ICP runs special subnets that track Bitcoin blocks and handle signing).

![ICP Canisters and REE](https://miro.medium.com/v2/resize:fit:828/format:webp/1*qmVoharfs6dKnJbpV1ecHA.png)
*(source: REE Whitepaper)*

The REE whitepaper describes this as the “Exchange-Pool” model, aligning with Bitcoin’s UTXO nature: an exchange (like a DEX or lending platform) manages one or more pools (Bitcoin addresses holding coins) and participates in PSBTs by contributing inputs/outputs from those pools.

Because exchanges are independent canisters, this model is highly composable — multiple protocols can cooperate within one transaction. For instance, a single Bitcoin transaction could swap BTC for a Rune in one pool and then use those Runes as collateral in a lending protocol, all in one atomic transfer.

The orchestrator handles signature order and consistency — making sure all steps complete cleanly before anything hits the chain. This composability also means shared liquidity: different dApps on REE can tap into the same Bitcoin liquidity pools, avoiding the fragmentation seen on separate chains.

## RichSwap: A Bitcoin AMM for Runes and BTC

To showcase REE’s capabilities, Omnity built RichSwap, the first automated market maker (AMM) exchange operating entirely on Bitcoin. Launched in February 2025, RichSwap allows users to swap between Bitcoin and Rune-based tokens without any bridging or wrapping.

Users simply connect a Bitcoin wallet and trade, and behind the scenes RichSwap coordinates the PSBT signing as described above. Because of REE’s properties, traders keep full custody of their BTC at all times — no deposits into a smart contract are required. If a swap is successful, it confirms on-chain as a Bitcoin transaction; if not, nothing is lost or locked.

RichSwap’s design emphasizes security and user protection: every swap is all-or-nothing and transparently validated. According to Omnity, if any condition isn’t met (say the price changed beyond slippage tolerance), the transaction is rolled back in full, safeguarding users from unwanted outcomes.

## Technical Implementation and Performance

RichSwap works like a typical Ethereum AMM, using constant-product math — but every swap settles in a native Bitcoin transaction. It maintains pools of BTC and various Rune tokens, pricing swaps via the typical constant-product formula. The difference is that trades are settled in a Bitcoin transaction rather than on a separate chain.

Thanks to several optimizations like UTXO proofs and transaction batching, RichSwap offers significantly faster confirmation times compared to traditional Bitcoin workflows, approaching the responsiveness users expect from modern blockchains. It accomplishes this by using UTXO proofs and careful infrastructure deployment. For example, the client (user’s browser or app) supplies a proof of their input UTXO to the orchestrator, allowing RichSwap to avoid extra round-trips to the Bitcoin network for validation.

In practice, multiple PSBTs can even be batched into one Bitcoin block, so a user could perform several trades back-to-back and have them confirmed together. Batching lets users confirm multiple swaps at once, cutting the lag that usually comes with on-chain Bitcoin trading.

## Impact on the Runes Ecosystem

RichSwap’s launch represents a major contribution to the Runes ecosystem. It provides the first venue for Rune token liquidity directly on Bitcoin — for example, trading sats against the “HOPE•YOU•GET•RICH” token (symbol RICH) or other Rune assets can now happen without leaving the Bitcoin network.

The exchange’s code is open-source and meant to be a blueprint for developers building on REE. By studying RichSwap, one can create new protocols (like stablecoin issuers or derivatives platforms) that plug into REE’s composable environment, reusing liquidity from RichSwap’s pools. Protocols launching on REE can tap into existing pools, skipping the usual scramble to bootstrap liquidity from scratch— on REE, all protocols can draw from the common pool of Bitcoin liquidity injected by any one of them.

## Extending to Ordinals

Omnity is also extending the DEX concept to Ordinal NFTs. The team has been developing “RichOrdi,” a protocol and interface to swap Ordinal inscriptions in a similar trustless fashion. The idea is to enable trading of Bitcoin NFTs with AMM-like efficiency and deep liquidity, which could revitalize the Ordinals market by pooling what are otherwise illiquid collectibles.

With an Ordinals indexer already live on Omnity and integration on the roadmap, swapping an NFT embedded in a satoshi for BTC (or even for a Rune token) could soon be as straightforward as a Uniswap trade.

Omnity adds tooling around Bitcoin’s base layer — instead of proposing upgrades, it builds composability on top of what already works. With ICP’s Chain-Key cryptography at its core, the project brings verifiable coordination and real-time programmability to Bitcoin-native assets.

The Omnity Hub connects Bitcoin to other chains through cryptographic validation, while the REE layer introduces execution logic that settles directly on Bitcoin. Together, they form an ecosystem where Ordinals, Runes, and BTC itself can move, trade, and interact across chains or stay fully native to Layer 1.

This architecture respects the integrity of Bitcoin while expanding what users and developers can do with it. Transfers are verified on-chain and coordinated through native signatures, with no custody shifts or external dependencies involved.

For developers, it’s a toolkit for building with Bitcoin’s security model as the base layer. For users, it’s access to trading, swaps, lending and more — powered entirely by Bitcoin infrastructure.
