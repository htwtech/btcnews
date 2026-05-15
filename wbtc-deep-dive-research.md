---
title: "wBTC Deep Dive Research"
slug: "wbtc-deep-dive-research"
date: "2026-05-15"
description: "Explore the significance of Wrapped Bitcoin (WBTC) in bridging Bitcoin and Ethereum, enhancing DeFi accessibility and functionality."
author: "Bitcoin Board Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/btcboard_articles/wbtc_ecosystem_1778830580715.png"
coverAlt: "wBTC"
tags: ["bitcoin", "wbtc", "bitboard"]
---

# Wrapped Bitcoin (WBTC): A Comprehensive Research Article

**Author:** Manus AI  
**Date:** May 15, 2026

## Executive Summary

Wrapped Bitcoin, usually abbreviated **WBTC**, is one of the earliest and most important attempts to make Bitcoin usable in Ethereum-style decentralized finance. It represents BTC as an ERC-20 token, allowing Bitcoin-denominated value to move through smart contracts, decentralized exchanges, lending markets, and other applications that cannot directly process native Bitcoin. The basic promise is simple: **one WBTC is intended to correspond to one BTC held in custody**, with minting and redemption mediated by approved institutions rather than by Bitcoin’s base-layer consensus itself.[^1] [^2]

That simplicity has made WBTC a core liquidity instrument in DeFi, but it also defines its main trade-off. WBTC is not native Bitcoin and does not inherit Bitcoin’s full trust-minimized security model. It depends on custodians, merchants, governance participants, smart contracts, proof-of-reserve processes, and the legal-operational integrity of the organizations controlling the backing BTC and token contracts.[^1] [^3] The result is a highly useful but structurally hybrid asset: **Bitcoin price exposure and liquidity in Ethereum-compatible environments, mediated by institutional custody and on-chain governance**.

As of a CoinGecko API query on May 15, 2026, WBTC had a market capitalization of approximately **$9.46 billion**, a circulating and total supply of about **117,487.96 WBTC**, a price near **$80,459**, and 24-hour volume of roughly **$205.69 million**.[^4] Etherscan separately showed the Ethereum WBTC contract as a verified ERC-20 token contract with **8 decimals**, more than **180,000 holders**, and contract address `0x2260fac5e5542a773aa44fbcfedf7c193bc2c599`.[^5]

| Dimension | WBTC in Brief |
|---|---|
| Asset type | Bitcoin-backed ERC-20 token, primarily used across Ethereum and EVM DeFi.[^1] [^5] |
| Core value proposition | Brings BTC liquidity to smart-contract ecosystems, especially lending, trading, collateral, and yield strategies.[^1] [^6] |
| Backing model | Intended 1:1 backing by BTC held in custody, with public reserve-verification mechanisms.[^1] [^2] |
| Minting and redemption | Conducted through approved merchants and custodians rather than directly by ordinary retail users.[^1] |
| Governance | Governed through WBTC DAO structures and multisignature controls for key system changes.[^1] [^7] |
| Main risk | Counterparty, governance, legal, custody, reserve-verification, smart-contract, and bridge/integration risk.[^3] [^8] |
| Strategic significance | One of the dominant tokenized Bitcoin assets used as collateral and liquidity in DeFi.[^6] [^9] |

## 1. What WBTC Is and Why It Exists

WBTC emerged from a practical interoperability problem. Bitcoin has the deepest liquidity and strongest monetary brand in crypto, while Ethereum and EVM-compatible networks became the main venues for programmable finance. Native BTC cannot be directly deposited into an Ethereum smart contract because Bitcoin and Ethereum are separate blockchains with different execution environments. WBTC solves this by representing BTC as an ERC-20 token that Ethereum applications can recognize and transfer.[^1] [^9]

The official wrapped-token whitepaper, published in January 2019 by Kyber Network, BitGo, and Republic Protocol, describes wrapped tokens as asset-backed tokens that follow a centralized reserve model but distribute responsibilities across a consortium of institutions. It states that the first wrapped token would be an ERC-20 token backed by Bitcoin and named **Wrapped BTC**, or WBTC.[^1]

> “Wrapped tokens follow the centralized model, but instead of relying entirely on one institution, they rely on a consortium of institutions performing different roles in the network.” — WBTC wrapped-token whitepaper[^1]

WBTC’s purpose is therefore not to replace Bitcoin. It is to make Bitcoin-denominated liquidity portable into environments where ERC-20 assets are the default building blocks. Once BTC is represented as WBTC, it can be traded on decentralized exchanges, posted as collateral, deposited into lending protocols, integrated into structured products, and composed with other smart-contract systems.[^6] [^9]

## 2. The WBTC Operating Model

The WBTC whitepaper defines four central roles: **custodian**, **merchant**, **user**, and **WBTC DAO member**. The custodian holds the underlying BTC and has the authority to mint tokens, merchants distribute WBTC and initiate minting or burning, users hold and transact the token, and DAO members govern system-level changes such as adding or removing custodians and merchants.[^1]

| Role | Function in the WBTC System | Practical Significance |
|---|---|---|
| Custodian | Holds the underlying BTC and mints WBTC after merchant-initiated deposits.[^1] | Custody is the foundation of WBTC’s backing and redemption credibility. |
| Merchant | Interfaces with users, performs KYC/AML where applicable, and initiates mint or burn processes.[^1] | Merchants are the distribution and redemption access layer. |
| User | Holds WBTC and uses it like any other ERC-20 token.[^1] | Users gain access to DeFi utility but generally do not mint directly through the protocol. |
| WBTC DAO member | Participates in governance through multisignature controls over system changes.[^1] [^7] | Governance determines who can operate key roles and how contracts evolve. |

### 2.1 Minting

Minting is the process by which new WBTC enters circulation. According to the whitepaper, a merchant first initiates a transaction authorizing the custodian to mint WBTC to the merchant’s Ethereum address. The merchant then sends BTC to the custodian. After the custodian waits for six Bitcoin confirmations, it mints the corresponding amount of WBTC on Ethereum.[^1]

This process is deliberately institutional. The whitepaper emphasizes that minting occurs between the merchant and custodian, not directly between an ordinary user and the protocol. A user who wants WBTC typically requests it from a merchant or obtains it through an exchange or DeFi market, while the merchant handles the necessary compliance and operational steps.[^1]

### 2.2 Burning and Redemption

Burning is the reverse process. A merchant burns WBTC on Ethereum, reducing the token supply. After the custodian waits for Ethereum confirmations, it releases BTC to the merchant’s Bitcoin address and marks the burn request as completed.[^1]

This design means WBTC’s supply can expand and contract with demand, but only through approved entities. The mechanism is transparent on-chain because mint and burn events can be observed on Ethereum, while the reserve side depends on the public disclosure and verification of Bitcoin custody balances.[^1] [^8]

### 2.3 Transferability

The WBTC whitepaper states that WBTC itself has no on-chain transfer restrictions. Once minted, WBTC can move like an ERC-20 token, subject to the rules and risks of Ethereum and the applications into which it is deposited.[^1] This is central to its usefulness: WBTC can be composable in DeFi precisely because it behaves like a standard fungible token rather than like native BTC.

## 3. Governance, Contracts, and Auditability

WBTC’s governance model is based on multisignature control. The whitepaper states that contract changes and the addition or removal of custodians and merchants are controlled by a multisig contract held by institutions participating in the WBTC DAO.[^1] The WrappedBTC DAO GitHub repository lists important addresses, including the WBTC token address, controller, factory, members contract, and a DAO multisig wallet.[^7]

The token contract on Ethereum is `0x2260fac5e5542a773aa44fbcfedf7c193bc2c599`. Etherscan identifies it as a verified contract named **WBTC**, compiled with Solidity v0.4.24, and implemented with 8 decimals.[^5] The token’s 8-decimal precision mirrors Bitcoin’s divisibility convention, which is operationally important because BTC itself is commonly denominated to eight decimal places.

The WBTC smart-contract audit summary states that the WBTC DAO code was audited by three independent audit firms: Chain Security, Solidified, and Coinspect. It also provides a procedure for verifying that deployed code matches audited code, that contract owners correspond to the DAO, that custodian and merchant configurations match public records, and that BTC custody balances are greater than or equal to WBTC total supply.[^8]

| Security or Governance Layer | Evidence or Mechanism | Interpretation |
|---|---|---|
| Verified token contract | Etherscan reports verified source code for the WBTC ERC-20 contract.[^5] | Users and developers can inspect token logic and ABI. |
| DAO and multisig governance | WBTC documentation identifies multisig and system contract addresses.[^7] | Contract control is institutional and procedural, not purely algorithmic. |
| Third-party audits | Audit summary names Chain Security, Solidified, and Coinspect as auditors.[^8] | Audits reduce but do not eliminate smart-contract and configuration risk. |
| Proof-of-reserve process | WBTC documentation and verification guide emphasize comparing BTC custody balances with WBTC supply.[^8] | Backing can be monitored, but users still depend on correct address disclosure and custody integrity. |
| Merchant/custodian access controls | Minting and burning are restricted to approved parties.[^1] | This supports operational control but introduces permissioned access. |

## 4. Market Position and On-Chain Footprint

WBTC has become a major tokenized Bitcoin asset because it was early, liquid, and deeply integrated into Ethereum DeFi. Gemini describes WBTC as the dominant and valuable form of tokenized Bitcoin compared with more decentralized alternatives such as tBTC.[^10] Hiro similarly notes that WBTC is widely used because it is readily available on many DeFi platforms and because developers can integrate it as they would any ERC-20 token.[^9]

The current size of WBTC remains large. CoinGecko’s API data fetched on May 15, 2026 showed approximately **117,487.96 WBTC** outstanding and a market capitalization of approximately **$9.46 billion**.[^4] Etherscan’s token page showed more than **180,000 holders** and a similar multi-billion-dollar market capitalization.[^5]

| Metric | Value Observed | Source and Timing |
|---|---:|---|
| Price | Approximately $80,459 | CoinGecko API, fetched May 15, 2026.[^4] |
| Market capitalization | Approximately $9.46 billion | CoinGecko API, fetched May 15, 2026.[^4] |
| Circulating supply | 117,487.96173308 WBTC | CoinGecko API, fetched May 15, 2026.[^4] |
| Total supply | 117,487.96173308 WBTC | CoinGecko API, fetched May 15, 2026.[^4] |
| 24-hour volume | Approximately $205.69 million | CoinGecko API, fetched May 15, 2026.[^4] |
| Ethereum holders | More than 180,000 | Etherscan, extracted May 15, 2026.[^5] |
| Contract address | `0x2260fac5e5542a773aa44fbcfedf7c193bc2c599` | Etherscan and WBTC DAO documentation.[^5] [^7] |

These figures should be treated as a time-sensitive market snapshot, not a fixed description of the asset. WBTC supply changes as BTC is deposited and redeemed, while market capitalization changes with both supply and BTC price.

## 5. WBTC in DeFi

WBTC’s central economic function is to make BTC useful in DeFi without requiring users to sell BTC exposure into ETH or stablecoins. Gemini describes WBTC as enabling Bitcoin holders to participate in lending, yield farming, margin trading, and other DeFi activities.[^6] In lending markets, WBTC can serve as collateral; in decentralized exchanges, it can form trading pairs; in yield strategies, it can be deposited into pools or vaults; and in structured products, it can be combined with derivatives, leverage, or restaking strategies depending on protocol design.[^6] [^9]

Gemini listed MakerDAO, Compound, Kyber Network, Aave, Uniswap, and Balancer as protocols that had supported WBTC use cases by December 2020.[^6] The exact status and risk parameters of WBTC in any particular protocol can change through governance, as later controversies around custody changes demonstrated. Nevertheless, WBTC’s established infrastructure has made it a common denominator for Bitcoin liquidity across Ethereum-style DeFi.[^3] [^6]

| DeFi Use Case | How WBTC Is Used | Main Benefit | Main Risk |
|---|---|---|---|
| Lending collateral | Users deposit WBTC to borrow other assets.[^6] | BTC holders can access liquidity without selling BTC exposure. | Liquidation, oracle, protocol, and WBTC custody risk. |
| Decentralized exchange liquidity | WBTC pairs trade against ETH, stablecoins, and other tokens.[^6] | BTC liquidity becomes available in automated markets. | Impermanent loss, smart-contract exploits, and market slippage. |
| Yield farming | WBTC can be deposited into pools or vaults seeking yield.[^6] | Converts otherwise passive BTC exposure into productive DeFi capital. | Strategy, leverage, counterparty, and protocol risk. |
| Margin trading | WBTC can be used in leveraged trading systems.[^6] | Enables Bitcoin-denominated directional or hedged strategies. | Amplified losses and liquidation risk. |
| Developer integration | Developers can support WBTC as a standard ERC-20 token.[^9] | Simple composability in EVM applications. | Reliance on WBTC’s external custody and governance stack. |

## 6. Proof of Reserves and Transparency

A tokenized BTC product must answer a basic question: does the issuer or custodian actually hold enough BTC to back the token supply? WBTC’s framework addresses this through public reserve disclosure and verification. The whitepaper says WBTC would be fully accounted for and that proof of reserves would be posted on the Bitcoin chain.[^1] The smart-contract audit summary provides a verification step that checks whether BTC in custody is greater than or equal to WBTC total supply.[^8]

NYDIG described the model as one in which BitGo holds BTC in cold storage and issues a commensurate amount of WBTC across networks on a 1:1 basis. It also noted that BitGo disclosed Bitcoin custody addresses so users could self-verify that custody balances matched token supply.[^3]

However, proof of reserves should not be confused with a complete proof of solvency, legal enforceability, or operational safety. A reserve dashboard can show that assets exist at disclosed addresses, but it does not by itself prove that those assets are free of encumbrances, immune from legal seizure, operationally recoverable, or redeemable by every token holder under stress. This distinction matters because WBTC is not only a smart contract; it is also a custody, governance, legal, and institutional arrangement.[^3] [^8]

## 7. The 2024 Custody Restructure and Its Consequences

In August 2024, BitGo announced that WBTC custody operations would move toward a **multi-jurisdictional and multi-institutional custody** model through a joint venture with BiT Global. BitGo said the change would diversify custody jurisdictions and locations for the underlying Bitcoin, which it said had previously been held in the United States. The announcement also stated that WBTC operations would include Hong Kong and Singapore, that the joint venture would continue using BitGo multi-signature technology and cold storage, and that proof of reserves would remain available through WBTC’s website.[^2]

The announcement was controversial because it explicitly framed the partnership as involving BiT Global, Justin Sun, and the Tron ecosystem.[^2] NYDIG wrote that the arrangement raised concerns in the digital asset community, including concerns about the security of the underlying BTC and the risk that WBTC could be minted without proper backing.[^3] Blockworks reported that MakerDAO initiated a governance discussion aimed at reducing or removing WBTC exposure from DAI collateral after the announcement.[^11]

Blockworks also reported that BitGo’s existing model used a 2-of-3 multisignature security arrangement and that, under the planned changes, one key would move to BiT Global, one would remain with BitGo in the United States, and another would be held by BitGo Singapore. BitGo CEO Mike Belshe argued that the same underlying technology would continue and that distributing keys across jurisdictions could reduce concentration risk.[^11]

| Stakeholder Concern | Reason for Concern | Counterargument or Mitigation Presented |
|---|---|---|
| Custody concentration | WBTC depends on institutions controlling backing BTC and minting processes.[^3] | BitGo described the restructure as diversifying custody across jurisdictions.[^2] |
| Justin Sun association | Community participants questioned influence or control through the BiT Global arrangement.[^3] [^11] | BitGo stated that the technology and operational standards would remain consistent.[^2] [^11] |
| DeFi collateral risk | MakerDAO and others had to assess whether WBTC remained suitable as collateral.[^11] | Protocol governance can adjust risk parameters, debt ceilings, or collateral listings. |
| Proof-of-backing risk | Concerns centered on whether WBTC could be minted without sufficient BTC backing.[^3] | WBTC’s transparency model emphasizes public reserve verification.[^1] [^8] |
| Jurisdictional risk | Multi-jurisdictional structures can diversify or complicate legal control.[^2] [^11] | BitGo framed geographic distribution as an upgrade to resilience.[^2] |

The controversy had market-structure consequences beyond WBTC itself. Coinbase later launched its own wrapped Bitcoin product, cbBTC, and delisted WBTC. CoinDesk reported that BiT Global sued Coinbase over the delisting, alleging harm to WBTC liquidity and reputation while Coinbase favored cbBTC. CoinDesk also reported that Coinbase cited “unacceptable risk” associated with Justin Sun’s affiliation with the token, and that the legal dispute was later dismissed with prejudice in 2025.[^12]

## 8. Risk Analysis

WBTC’s risks are best understood as layered rather than singular. Some risks arise from the token contract, others from custody, others from governance, and still others from DeFi applications that accept WBTC. A user holding WBTC in a wallet faces a different risk profile from a user using WBTC as collateral in a lending protocol or depositing it into a leveraged yield strategy.

The most fundamental risk is **custody risk**. WBTC users rely on the custody stack to hold the backing BTC securely and to honor redemption processes through merchants. Hiro emphasizes that WBTC requires trust in a central service and that users no longer control native BTC once it has been wrapped.[^9]

The second major risk is **governance and key-management risk**. Because minting, burning, merchant membership, custodian arrangements, and contract controls are mediated by institutions and multisignatures, WBTC’s security depends on operational procedures, signer independence, legal obligations, and governance responsiveness.[^1] [^7] [^11]

The third risk is **reserve-verification risk**. Public proof-of-reserve mechanisms are valuable, but they depend on accurate address disclosure, correct supply accounting, and the assumption that disclosed BTC is legally and operationally available to back outstanding WBTC.[^3] [^8]

The fourth risk is **DeFi integration risk**. When WBTC is deposited into lending markets, automated market makers, bridges, or yield vaults, the holder also takes on risks of that protocol: smart-contract exploits, oracle failures, liquidation cascades, governance attacks, liquidity shortages, and adverse parameter changes.[^6] [^9]

| Risk Category | Description | Who Bears It? | Possible Mitigations |
|---|---|---|---|
| Custody risk | Backing BTC may be lost, frozen, mismanaged, or legally impaired.[^9] | WBTC holders and protocols accepting WBTC. | Monitor proof of reserves, custody disclosures, legal structure, and custodian reputation. |
| Redemption risk | Users may not be able to redeem directly and may depend on merchants or markets.[^1] | Users needing conversion back to BTC. | Understand merchant access, exchange liquidity, and redemption terms. |
| Smart-contract risk | Token, DAO, or integrated protocol code may contain vulnerabilities.[^8] | Holders and DeFi users. | Use audited contracts, conservative protocols, and diversified exposure. |
| Governance risk | Multisig signers or DAO processes may change system parameters or participants.[^1] [^7] | All WBTC stakeholders. | Track governance repositories, contract ownership, and protocol announcements. |
| Market-liquidity risk | WBTC may trade at a discount if confidence in backing or redemption weakens. | Traders, lenders, and collateral protocols. | Monitor peg, liquidity depth, lending parameters, and exchange support. |
| Regulatory risk | Custodians, merchants, or users may face jurisdictional restrictions.[^1] [^2] | Custodians, merchants, and users. | Understand jurisdictional access, KYC/AML obligations, and custody entities. |
| DeFi composability risk | Protocols using WBTC can propagate stress through liquidations or integrations.[^6] | Borrowers, lenders, LPs, and protocols. | Use conservative loan-to-value ratios and monitor protocol governance. |

## 9. WBTC Versus Alternatives

WBTC is not the only way to bring BTC into smart-contract ecosystems. It is best understood as one point on a design spectrum. On one end are **centralized custodial wrappers** that prioritize liquidity, operational simplicity, and institutional accountability. On the other end are **more decentralized or cryptographic bridge designs** that attempt to reduce reliance on a single custodian but may introduce technical complexity, different security assumptions, or lower liquidity.[^10]

Gemini frames WBTC and tBTC as two fundamentally different approaches: WBTC relies on centralized custodians, while tBTC seeks a more decentralized cryptographic process.[^10] Avalanche Support similarly contrasts BTC.b with WBTC, describing BTC.b as more decentralized and WBTC as more centralized but more established and potentially more liquid.[^13]

| Asset or Model | Core Design | Strengths | Trade-Offs |
|---|---|---|---|
| WBTC | Custodial BTC-backed ERC-20 token governed through institutional roles and multisig controls.[^1] | Deep liquidity, broad DeFi integration, familiar ERC-20 implementation.[^6] [^9] | Custody, governance, legal, and proof-of-reserve dependence.[^3] [^9] |
| tBTC | More decentralized Bitcoin-on-Ethereum design using cryptographic mechanisms.[^10] | Attempts to reduce reliance on centralized custodians.[^10] | Higher technical complexity and historically less dominant liquidity than WBTC.[^10] |
| BTC.b | Avalanche-oriented wrapped BTC model using decentralized bridging infrastructure.[^13] | More aligned with decentralization ideals in Avalanche’s framing.[^13] | Depends on bridge assumptions and may have different liquidity depth than WBTC.[^13] |
| cbBTC | Coinbase-issued wrapped BTC product, launched as a competing centralized wrapper. | Strong exchange integration where supported. | Depends on Coinbase custody, terms, supported chains, and platform policy. |
| Native BTC on Bitcoin layers | BTC used through Bitcoin-adjacent smart-contract or layer systems. | Potentially closer to Bitcoin-native security assumptions. | Ecosystem maturity, liquidity, and composability may vary. |

No alternative eliminates risk; each reallocates risk. WBTC’s enduring advantage is liquidity and integration. Its enduring weakness is that its trust model is visibly different from native Bitcoin’s.

## 10. Strategic Outlook

WBTC remains strategically important because it connects two of crypto’s largest economic zones: Bitcoin liquidity and Ethereum-compatible DeFi. As long as Bitcoin remains the dominant store-of-value asset in crypto and smart-contract ecosystems remain major venues for on-chain finance, demand will likely persist for reliable BTC representations on programmable chains.[^6] [^9]

However, WBTC’s future depends on trust as much as technology. The 2024 custody restructure showed that DeFi protocols do not treat wrapped assets as neutral commodities; they evaluate custody, governance, jurisdiction, and reputation. If confidence in WBTC’s custody or governance weakens, lending protocols can reduce exposure, exchanges can delist, and liquidity can migrate to alternatives. If WBTC maintains transparent reserves, strong operational controls, and deep liquidity, it can remain a default institutional-grade Bitcoin wrapper.

The broader market is also becoming more competitive. Coinbase’s cbBTC, Threshold’s tBTC, Avalanche’s BTC.b, and Bitcoin-layer approaches all express dissatisfaction with a single dominant model. This competitive pressure may improve transparency, fees, decentralization, and user choice. It may also fragment liquidity and complicate risk assessment for protocols that must decide which BTC representations to accept as collateral.

## Conclusion

WBTC is best described as **institutionally wrapped Bitcoin for programmable finance**. It is not native BTC, but it gives BTC holders access to Ethereum-style DeFi by converting Bitcoin exposure into an ERC-20 format. Its design has proven useful, liquid, and highly composable, which explains its enduring position among tokenized Bitcoin assets.

The same design also creates unavoidable trade-offs. WBTC holders rely on custodians, merchants, DAO governance, reserve transparency, smart contracts, and legal entities. These layers are not incidental; they are the mechanism by which WBTC exists. The central analytical question is therefore not whether WBTC is “as trustless as Bitcoin”—it is not—but whether its institutional and technical safeguards are sufficient for a given use case.

For traders, WBTC may be a liquid BTC proxy inside DeFi. For developers, it is a familiar ERC-20 asset with extensive integrations. For risk managers, it is a collateral asset whose value depends on both BTC market price and confidence in the wrapper’s custody-governance stack. For long-term Bitcoin holders, it is a tool that can unlock utility but only by accepting counterparty and smart-contract risks that native BTC deliberately avoids.

## References

[^1]: Kyber Network, BitGo, and Republic Protocol, *Wrapped Tokens: A multi-institutional framework for tokenizing any asset*, Whitepaper v0.2, January 24, 2019, https://www.wbtc.network/assets/wrapped-tokens-whitepaper.pdf.

[^2]: BitGo, *BitGo to Move WBTC to Multi-Jurisdictional Custody to Accelerate Global Expansion Plan*, August 9, 2024, https://www.bitgo.com/resources/blog/bitgo-to-move-wbtc-to-multi-jurisdictional-custody-to-accelerate-global/.

[^3]: Greg Cipolaro, NYDIG, *Risks and Rewards with Changes to WBTC*, August 16, 2024, https://www.nydig.com/research/risks-and-rewards-with-changes-to-wbtc.

[^4]: CoinGecko API, *Wrapped Bitcoin market data*, fetched May 15, 2026, https://api.coingecko.com/api/v3/coins/wrapped-bitcoin.

[^5]: Etherscan, *Wrapped BTC (WBTC) ERC-20 token page*, extracted May 15, 2026, https://etherscan.io/token/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599.

[^6]: Gemini Cryptopedia, *wBTC: What Can You Do with Wrapped Bitcoin?*, updated March 20, 2025, https://www.gemini.com/cryptopedia/wrapped-bitcoin-what-can-you-do.

[^7]: WrappedBTC DAO GitHub repository, *WBTC DAO README*, https://github.com/WrappedBTC/DAO/blob/master/README.md.

[^8]: WrappedBTC smart-contract repository, *DAO Member Guide for Verifying the deployment of WBTC contracts*, https://github.com/WrappedBTC/bitcoin-token-smart-contracts/blob/master/docs/audit_summary.md.

[^9]: Hiro, Elena Giralt, *A Developer’s Guide to Wrapped Bitcoin (WBTC)*, August 23, 2024, https://www.hiro.so/blog/a-developers-guide-to-wrapped-bitcoin-wbtc.

[^10]: Gemini Cryptopedia, *Bitcoin on Ethereum: wBTC and tBTC*, updated November 2, 2023, https://www.gemini.com/cryptopedia/wtbtc-vs-tbtc.

[^11]: Blockworks, Donovan Choy and Macauley Peterson, *BitGo moves to allay fears over WBTC custodial changes*, August 16, 2024, https://blockworks.com/news/bitgo-wbtc-custodial-changes.

[^12]: CoinDesk, Francisco Rodrigues, *Coinbase, BiT Global End Legal Fight Over WBTC Delisting*, June 7, 2025, https://www.coindesk.com/policy/2025/06/07/coinbase-bit-global-end-legal-fight-over-wbtc-delisting.

[^13]: Avalanche Support, *What are the differences between BTC.b & WBTC?*, October 15, 2025, https://support.avax.network/en/articles/8699991-what-are-the-differences-between-btc-b-wbtc.
