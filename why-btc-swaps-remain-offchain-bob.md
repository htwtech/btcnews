---
title: "Why BTC Swaps Still Remain Mostly Off-Chain"
slug: "why-btc-swaps-remain-offchain-bob"
date: "2026-04-01"
description: "Roughly $800B in BTC swaps takes place each month, yet less than 1% happens on-chain. BOB is looking to fix this structural bottleneck."
author: "BitBoard"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/bob-square-test.png"
coverAlt: "BOB Bank of Bitcoin Stage 1"
tags: ["bitcoin", "swaps", "bob", "infrastructure", "liquidity"]
---

# Why BTC Swaps Still Remain Mostly Off-Chain

A large BTC swaps market already exists. Roughly **$800B in BTC swaps takes place each month**, yet less than 1% of that volume happens on-chain. At the same time, a significant share of Bitcoin continues to be held in self-custody. That gap has been hard to ignore.

In principle, self-custodied BTC should be able to move into stablecoins, wBTC, and DeFi without forcing users back through centralized venues. In practice, the on-chain route has remained difficult to rely on. Execution is often too slow, quoted outcomes are not always dependable by the time settlement happens, and users are left carrying timing risk they did not really intend to take on.

That has shaped behavior for a while now. A large share of BTC swap activity still flows through centralized exchanges not simply because users prefer custody tradeoffs, but because the on-chain alternative has usually involved too much friction. This is the problem space BOB (Build on Bitcoin) has been working in.

## The Bank of Bitcoin: Starting with Swaps

The broader direction at BOB is the **Bank of Bitcoin**: infrastructure for swapping, saving, earning, and borrowing on Bitcoin rails. But there is a sequencing issue inside that vision. Before anything more expansive can work, the path from native BTC into the wider on-chain economy has to become more usable. That is why Stage 1 is focused on swaps.

Native BTC swaps have remained difficult to use on-chain for fairly obvious reasons. They take too long, and the quoted outcome is not always as firm as users need it to be. That combination has pushed a lot of activity toward centralized venues, even when users would rather stay in self-custody.

> BOB’s zero-conf work is focused on that specific gap: reducing swap time to under 10 seconds while keeping the quoted rate fixed through execution, without adding pre-deposits, pre-staking, or extra account setup around the process.

![BOB Zero-Conf Swap Mechanics](https://pbs.twimg.com/media/HEwrsTZXkAAhdqc.jpg)

In practical terms, that means instant, fixed-rate BTC swaps are coming soon. The intention is to make the route out of native BTC more usable when timing matters, and more predictable when users need to know the outcome before committing capital.

## Removing the Operational Overhead

The operational side matters as well. A number of fast Bitcoin systems improve speed by shifting complexity onto the user through pre-funding, pre-staking, or separate setup requirements. BOB’s approach is designed to avoid that overhead. No pre-staking, no pre-deposit, and no account setup. The aim is to fit more directly into the way wallets, dapps, aggregators, and on/off-ramp flows already work.

From BOB’s perspective, this is not only a swaps feature. If self-custodied BTC is going to become more productive, then the route from native BTC into stablecoins, wBTC, and DeFi has to improve first. Swaps are the access layer. If that layer remains slow or uncertain, everything built on top of it inherits the same limitation.

BOB Gateway already routes across 11 chains, and this next step is focused on making that route from native BTC more practical. In that sense, Stage 1 is less about announcing a standalone feature and more about addressing one of the structural bottlenecks in Bitcoin’s on-chain economy.

The product is not live yet. For now, BOB has opened [early access registration](https://www.gobob.xyz/) for users who want to follow the rollout and, in some cases, qualify for fee-free swaps on BOB Gateway. There is also a demo on the page.

The broader point is fairly simple. As long as BTC swaps remain slow and unpredictable on-chain, a large share of Bitcoin activity will continue to default to centralized venues. BOB’s view is that this can be improved, and swaps are the first place to do it.
