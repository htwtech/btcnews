---
title: "Lightning Network: a faster, cheaper layer-two solution for Bitcoin"
slug: "lightning-network-faster-cheaper-layer-two-solution-for-bitcoin"
date: "2026-01-02"
description: "An overview of the Lightning Network, its funding history, technical model, strengths, weaknesses, and role in scaling Bitcoin payments."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/network/Lightning-network-faster-and-cheaper-transactions.png"
coverAlt: "Lightning Network: Faster and cheaper transactions on Bitcoin"
tags: ["bitcoin", "btc", "lightning", "payments", "layer-2", "scaling"]
---

# Lightning Network: a faster, cheaper layer-two solution for Bitcoin

The Lightning Network is a layer-two solution for Bitcoin that aims to make transactions faster and cheaper. By creating a secure network of participants using the underlying technology of the Bitcoin blockchain, it addresses some of the current limitations associated with transaction speed and fees. Lightning remains one of the main production Bitcoin payment-scaling systems in use today.

## Investors and Funding

According to River's 2023 report, a total of $530.93 million was funneled into 39 Lightning companies between 2018 and end of 2022 — a historical snapshot that reflects the sector's early growth phase. That figure has since grown substantially: Lightning Labs alone raised an additional $70M Series B in April 2022, bringing its total known funding well above the $10M Series A led by Craft Ventures in 2020. Strike, another key player in the Lightning ecosystem, raised $80 million in a round led by Ten31, while Lightspark secured $175M in a Series A. These investments suggest sustained investor confidence in Lightning infrastructure and Bitcoin payment applications.

## Project Background

Proposed by Joseph Poon and Thaddeus Dryja, with the canonical whitepaper published in January 2016, Lightning reached mainnet in 2018. The network has since grown well beyond any single company: today it is maintained across multiple independent implementations, including LND (Lightning Labs), Core Lightning (Blockstream), and Eclair (ACINQ), each with its own development track and contributor base. Lightning Labs, led by CEO and co-founder Elizabeth Stark, remains one of the most prominent teams building on the protocol. Lightning's goal is to provide a faster, cheaper, and global payment solution, ultimately enabling Bitcoin to handle everyday transactions at scale.

## Problem the project solves

### Current challenges

Bitcoin faces challenges related to high transaction fees and slower processing times, particularly during times of high demand. These issues can limit its use for small transactions, especially during periods of high demand, making routine low-value payments less practical on the base layer.

### Solution

The Lightning Network addresses these problems by enabling off-chain transactions that maintain on-chain security. Participants open bidirectional payment channels, allowing them to conduct numerous transactions without immediately recording each one on the blockchain. This reduces congestion and fees, while ensuring security through the use of smart-contract scripting.

## Key features

Enables faster transactions by allowing off-chain settlements. Supports low fees for small transactions, making Bitcoin more practical for everyday use. Utilizes bidirectional payment channels to enable multiple transactions without broadcasting them all to the blockchain. Ensures transaction security through hashed timelock contracts (HTLCs), timelocks, and on-chain enforceability. Maintains on-chain enforceability, similar to legal contracts that only require court intervention when disputes arise. Allows instant payments without block confirmations, making it suitable for retail point-of-sale transactions and device-to-device payments. Lightning commonly supports sub-satoshi accounting in millisatoshis for channel balance tracking and invoice amounts, while on-chain settlement remains satoshi-denominated. Lightning substantially increases Bitcoin payment throughput for suitable use cases without requiring a new custodial base layer.

## Technology Stack

The Lightning Network relies on Bitcoin's proof-of-work consensus mechanism and functions as a layer-two solution built on the Bitcoin blockchain. It makes use of Bitcoin's native smart-contract scripting language, incorporating bidirectional payment channels, decrementing time-locks, and multisignature channels to ensure both security and efficiency in transactions.

## Strengths and Weaknesses

### Strengths

High-speed, low-cost transactions due to off-chain settlements. Scalability with substantially increased transaction throughput for suitable use cases. Enhanced security through the use of smart-contract scripting. Ability to conduct micropayments and sub-satoshi channel accounting, which are impractical on the Bitcoin base layer.

### Weaknesses

Complexity in setting up and managing payment channels. Limited adoption and liquidity in comparison to traditional payment systems. Potential risks related to routing and channel closures, especially in case of uncooperative participants.

The Lightning Network offers an innovative approach to tackling Bitcoin's scalability issues by enabling faster and cheaper transactions. It remains one of the main approaches to making Bitcoin more usable for everyday payments.

To learn more, check out the official Lightning Network documentation.
