---
title: "Ztarknet: A Technical Alliance of Starknet and Zcash (translated from the original analysis by web3ru research)"
slug: "ztarknet-technical-alliance-starknet-zcash"
date: "2025-12-15"
description: "A deep technical breakdown of Ztarknet, exploring the Starknet and Zcash alliance, zero-knowledge proofs, L2 architecture, and programmable privacy."
author: "BitBoard Research"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/btcboard%20logo.png"
cover: "https://fiphsgznopoesjaxwkwz.supabase.co/storage/v1/object/public/networks/ztarknet-new.png"
coverAlt: "Ztarknet cover"
tags: ["bitcoin", "btc", "l2"]
---

Ztarknet: A Technical Alliance of Starknet and Zcash (translated from the original analysis by web3ru research)

So, we came across this analysis on web3ru.ai. Basically a deep technical breakdown of Ztarknet, the whole Starknet and Zcash alliance thing. We thought it was too good not to translate and share. The piece digs into zero-knowledge proofs, L2 architecture, privacy mechanics, market implications, the works. It’s the kind of material that crypto infrastructure teams, researchers, and anyone tracking Bitcoin L2 developments actually need to read.

Original article (in Russian): https://web3ru.ai/ztarknet-tiekhnichieskii-alians-starknet-i-zcash/  
All rights to the original content belong to [web3ru research](https://web3ru.ai).

How two crypto projects with a shared founder are building the first programmable privacy in history.

September–December 2025

## Preamble

Fall 2025 will go down in cryptocurrency industry history as the moment when two parallel branches of zero-knowledge technology development — privacy and scalability — finally converged in a single architecture. StarkNet, a leading Layer-2 solution based on zk-STARK proofs, and Zcash, the oldest and most reliable private blockchain, announced the creation of Ztarknet — the first programmable privacy layer in history.

This is not a marketing partnership and not an integration for the sake of a press release. We are talking about a fundamental technical merger whose roots go back to 2016, when Israeli professor Eli Ben-Sassoon became one of the co-authors of the Zerocash scientific paper — the theoretical foundation of Zcash. Two years later, that same Ben-Sassoon founded StarkWare Industries and developed zk-STARK technology, which is now returning to its origins.

The essence of what is happening can be expressed in a single phrase: Zcash remains a private value store, while StarkNet becomes its programmable engine.
Users get the ability to run smart contracts, participate in DeFi, play onchain games — and all of this with the guarantee of privacy that, until now, only Zcash’s base layer could provide.

This material represents a comprehensive analysis of this technical alliance: from the first forum proposals to a working proof-of-concept, from cryptographic nuances to market reaction. The temporal focus is September–December 2025, the period of the project’s most intensive development.

## Part I. Context and Prerequisites

### 1.1. Two Projects, One Founder

Eli Ben-Sassoon is the key figure uniting both projects. A computer science professor at the Technion (Israel Institute of Technology), he is:

• Founding Scientist of Zcash (since 2016), co-author of the Zerocash protocol  
• Co-founder and CEO of StarkWare Industries (since 2018)  
• Inventor of STARK and FRI technologies — cryptographic protocols underlying modern zero-knowledge proof systems

In 2018, Electric Coin Company (then Zcash Company) invested in StarkWare as part of a $6 million seed round, which cemented the relationship between the projects at the institutional level. Another connecting element is Alessandro Chiesa, also a co-founder of both projects.

Zooko Wilcox, founder and CEO of Electric Coin Company, which developed Zcash, actively participates in discussions of integration. It is precisely the dialogue between Wilcox and Ben-Sassoon that determined the strategic direction of Ztarknet development.

### 1.2. Why Now?

Several factors made fall 2025 the optimal moment for integration:

Technological maturity of StarkNet. By fall 2025, StarkNet had proven its viability on Ethereum, processing millions of transactions. The new Stwo prover (Starks Two) based on Circle STARKs provided a hundredfold acceleration in proof generation compared to the previous Stone prover.

Resurgence of interest in privacy. On October 1, 2025, well-known investor Naval Ravikant publicly mentioned Zcash as “privacy insurance,” which triggered a wave of interest and a manifold increase in ZEC price. Within weeks, Zcash’s market cap exceeded $7.2 billion, surpassing Monero.

Zcash infrastructure readiness. The Transparent Zcash Extension (TZE) mechanism, described in the ZIP-222 specification, was deliberately built into the Zcash protocol for such expansions. This allows STARK-proof verification to be added without changing the blockchain’s core logic.

## Part II — Translation Draft with Quote Research Status

### 2.1. September–October: From Idea to Proposal

Mid-October 2025. StarkWare engineer Abdel publishes the first rough draft of integration on the Zcash Community Forum. In his message, he greets the “Zcash family” on behalf of StarkWare and outlines the key idea:

I’m proposing a Transparent Zcash Extension (TZE) that verifies a bounded-size STARK proof within Zcash consensus. The intent is to make Zcash a credible base layer for a Starknet-style L2: account abstraction, a Cairo VM execution environment (i.e., full programmability on L2), and high throughput with very low per-tx L2 fees, while keeping L1 privacy exactly as it is today.

The publication sparks lively discussion. It is at this moment that the term “Ztarknet” emerges — a combination of Zcash and StarkNet. In informal discussions, the project is also called “Darknet,” underscoring its private nature.

### 2.2. November: Breakthrough and Resonance

November 3, 2025 — First STARK proof on Zcash testnet. Developers successfully verify a STARK proof on the Zcash network (regtest). For the first time, a Zcash node (modified) validates within consensus a complex cryptographic proof from L2. This is a historic moment: technologically, the proof-of-concept for a StarkNet rollup on Zcash has demonstrated feasibility.

November 5, 2025 — Public dialogue between Zooko and Eli. StarkWare publishes a video conversation between the founders titled “Zooko & Eli on Zcash, ZK, Privacy, and Scaling.” From this discussion, the community learns several important details:

A finality gadget is discussed — an additional finalization mechanism atop PoW, possibly via a hybrid PoW/PoS scheme  
At the community level, this idea receives the name Crosslink  
Parallel work on StarkNet over Bitcoin is mentioned

November 6, 2025 — [Eli Ben-Sassoon’s tweet](https://x.com/EliBenSasson/status/1986489267724710219?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1986489267724710219%7Ctwgr%5E%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Fwww.coindesk.com%2Fmarkets%2F2025%2F11%2F10%2Fprivacy-coin-bid-continues-as-zcash-goes-on-lifting-dino-sector-starknet-s-strk-rockets-40). The co-founder of both projects publicly supports the initiative.

November 9–10, 2025 — Market resonance. Token STRK rises 35–40%, trading volume reaches $832 million. Traders and analysts formulate the “Ztarknet thesis” — an investment hypothesis about the correlation between STRK and ZEC.

DeFi researcher Avocado Toast [writes](https://x.com/avotoast/status/1987724861335072795):

“Tell me why $strk isn’t the continuation of the $zec trade

strk co-founder also zec co-founder

strk effectively expands privacy tech from an L1 to a programmable L2 environment”

Analyst chainyoda [states more succinctly](https://x.com/chainyoda/status/1987559023802278355): “$STRK is $ZEC beta”

November 10 — December 1, 2025 — Zypherpunk hackathon. The first major event uniting developers from both ecosystems takes place. Prize pool exceeds $300,000, including $35,000 for Starknet builders and a separate $10,000 specifically for Ztarknet projects.

November 27, 2025 — Event “Where Privacy meets Bitcoin, Zcash & NEAR.” Participants discuss the concept of a “holy trinity”: Zcash provides privacy, StarkNet — scalable computation, NEAR — convenient UX.

### 2.3. November — Key Quotes from Founders

Eli Ben-Sassoon in an interview with Cointelegraph:

“We knew zero-knowledge proofs solve two problems: scalability and privacy. They offer integrity. They basically can convince you that the right thing has been done, even when you’re not watching and even when you don’t actually see all the details.”

On prospects for Bitcoin expansion:

“The technology is ready. All you need is a soft fork that adds nine lines of code, which Satoshi actually introduced. It’s called OP_CAT. It’s very, very easy. If there’s a will, there’s a way.”

Eli Ben-Sassoon in The Block podcast “Big Brain”:

“I am very long-term Bitcoin bullish. I’m Ethereum bullish. I’m starknet bullish. I’m Zcash bullish. I’m bullish on lot of innovative things that are true to the values of decentralization, which not all projects in blockchain world are.”

StarkNet Official November Recap:

“[STARK proofs](https://starkware.co/stark/), the ZK tech powering Starknet, are ideally suited for two domains:

- Scalability

- Privacy

Starknet has solved the first, and capacity will only improve from here. Now the focus is shifting toward privacy at scale”

## Part III. Ztarknet Architecture

### 3.1. Core Concept: What Remains Unchanged

The foundational principle of Ztarknet is minimal intervention at L1. Zcash continues to function exactly as before.

• Private (shielded) transactions remain untouched  
• Monetary policy stays unchanged (21 million ZEC cap)  
• Transaction format is preserved  
• The shielded pool mechanism is not modified

The only change is the addition of a narrowly scoped STARK proof verifier through the TZE mechanism. This verifier:

• Takes a byte string (proof) as input
• Returns true/false
• Cannot create new coins
• Does not execute arbitrary logic

As [developers put it colorfully](https://forum.zcashcommunity.com/t/proposal-ztarknet-a-starknet-l2-for-zcash/52926): “Don’t change L1 privacy. Add a tiny STARK proof‑checker (TZE) so experimentation happens on L2”

### 3.2. How It Works: Five Steps

Step 1. Transaction Execution on L2. Users send transactions to L2 through a sequencer node. The sequencer batches them, executes all operations within the Cairo VM environment, and updates the L2 state (state root). This could be token transfers, smart contract execution, or interaction with a DeFi protocol.

Step 2. Proof Generation. Along with the state update, a computation trace is generated. An independent process (the prover) computes a zk-STARK proof that the transition from the old L2 state to the new one is correct. Ztarknet uses Circle STARK (the Stwo implementation), optimized for Cairo traces.

Step 3. Publishing the Proof to L1. A designated participant (the submitter) constructs a transaction on the Zcash L1 network containing:

• The old L2 state root (root_old)
• The new L2 state root (root_new)
• The STARK proof
• A data commitment ensuring availability (DA)

This transaction uses a new TZE output type with the condition: “the proof is valid for the stated data.”

Step 4. Verification on L1. Full Zcash nodes run the embedded STARK proof verification function (tze_verify). If the proof is valid, the transaction is included in a block, and the new root_newbecomes the current on-chain commitment. If not, the transaction is rejected.  

Step 5. Cycle Repeats. L2 continues processing the next set of transactions, building on the new state.

### 3.3. Anchor UTXO Chain Mechanism

L2 progression is represented as a chain of TZE outputs. At each step, a transaction spends the previous anchor and creates a new one. The TZE witness carries proof that executing the Cairo L2 program from the previous state with a block of transactions yields the new state.

This creates an unbreakable chain: each L2 update is cryptographically linked to the previous one, and any attempt to forge history requires breaking the STARK proofs.

### 3.4. ZEC Bridge Between L1 and L2

Deposit (L1 → L2):

1. The user creates a special transaction on L1 that locks ZEC in a UTXO (on a dedicated transparent bridge address)
2. The L2 sequencer registers the lock event
3. An equivalent amount of “wrapped-ZEC” (1:1) is credited to the user’s account on L2

Withdrawal (L2 → L1):

1. The user initiates a withdrawal operation on L2 (burning L2 assets)
2. A STARK proof is generated, confirming the withdrawal
3. The proof is published to L1 through the TZE mechanism
4. L1 nodes verify the proof
5. The previously locked ZEC is unlocked and sent to the recipient

Important: ZEC on L2 is always fully backed by real ZEC on L1. Withdrawal is only possible upon presenting a valid proof.

In the future, when Zcash introduces private tokens through ZSA (Zcash Shielded Assets), the bridge can be extended to support them as well.

## Part IV. Technical Implementation Details

### 4.1. Transparent Zcash Extension (TZE)

To enable integration, a new extension type is proposed — STARK_VERIFY_V1. How it works:

1. In an L1 transaction, a special input appears with an extension type designation = STARK_VERIFY and a mode parameter
2. Precondition includes: root_old , root_new , program identifier, data commitment
3. Witness — byte representation of the STARK proof (size-bounded)
4. Full nodes run the tze_verify function, which parses the mode, retrieves verifier algorithm parameters, hashes the public inputs, and verifies the proof
5. If true — the transaction is valid; if false — it is rejected

### 4.2. Two STARK Verification Modes

Mode 1 — Stone (Conservative):

“Vanilla” STARK with baseline FRI parameters  
Longer proofs, but maximum reliability  
Implemented in C++  
Battle-tested over time  

Mode 2 — Stwo / Circle STARK (High-Performance):

Modern Circle STARK, optimized for Cairo  
Operates over 31-bit Mersenne prime field  
Delivers up to 100x acceleration compared to Stone  
Implemented in Rust  
Less “battle-tested,” but significantly faster  

Both modes have pinned parameters: the algorithm, size limits, hash choices — all declared once and for all in the specification and cannot change without a hard fork.

### 4.3. STARK vs SNARK: Why It Matters

Zcash has historically been built on zk-SNARKs (Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge). Their defining feature is a trusted setup ceremony: a procedure for generating parameters in which participants must destroy their secret data. Compromise of any participant theoretically allows creation of false proofs.

zk-STARKs (Zero-Knowledge Scalable Transparent Arguments of Knowledge) eliminate this problem:

![Alt text here](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/ztarknet_image1.png)

For Zcash, integrating a STARK verifier through TZE allows harvesting the best of both: SNARKs continue to provide privacy for shielded transactions on L1, while STARKs add scalable L2 verification without trusted setup.

Eli Ben-Sassoon emphasizes: in the long run, every serious blockchain will need to embed STARK proofs for scaling and post-quantum defense.

### 4.4. Ztarknet Technology Stack

The project adheres to a “Rust-all-the-way” approach — maximum reuse of Rust components:

Zebra fork — A Rust implementation of a Zcash node with support for the new TZE and verification code (using the Circle STARK library). This node can validate a chain with transactions containing proofs.

L2 client based on Madara — A StarkNet-compatible sequencer in Rust, providing JSON-RPC interfaces, L2 state management, and mempool mechanisms. Madara was originally designed for other networks but has been adapted for Ztarknet’s needs.

Stwo / Cairo prover — A module for generating Circle STARK proofs that verify the correctness of Cairo execution traces.

TZE transaction assembler — A custom Rust module that takes a proof from Stwo, packages state roots, and constructs a valid transaction for the Zebra node.

### 4.5. Security Parameters and DoS Resistance

To protect against attacks, the following constraints are proposed:

• Maximum proof size: 0.25–1 MB
• Maximum public data volume: up to 32 MB
• Block allocation for TZE proofs: 5–10% (under discussion)
• Frequency: possibly limited to one proof per block
The fee for publishing a proof will scale with its byte size, much like current Zcash transaction fees scale with transaction size. This economically disciplines L1 usage.

## Part V. What Ztarknet Offers Users

### 5.1. Programmability

For the first time, Zcash becomes a base for running full-fledged smart contracts. L2 is compatible with the StarkNet ecosystem — it uses the Cairo VM and Cairo language for writing contracts.

This opens the door to:

• Turing-complete computation: DeFi protocols, games, DAOs, NFTs  
• Account abstraction: smart accounts with multisig, social recovery  
• Tokenization: issuing tokens, stablecoins, private assets  

### 5.2. Scalability and Low Fees

Thousands of transactions are aggregated into a single proof. L2 users pay significantly less than if those same transactions ran on L1.

### 5.3. Built-in Privacy

Unlike Tornado Cash or other mixers, privacy is built into the L2 protocol itself. No additional steps are needed — confidentiality is ensured architecturally.

### 5.4. L1 Security

L2 security is inherited from L1 security. If the L2 operator (sequencer) maliciously breaks the rules, the proof will not verify, and the state update will not be accepted on L1. Funds on L2 are protected from arbitrary issuance or theft.

## Part VI. Zoro Project and Other StarkWare Initiatives

### 6.1. Zoro — STARK-proven Zcash Light Client

In parallel with Ztarknet, StarkWare is developing Zoro — a STARK-proven Zcash light client aimed at compressing Zcash validation into succinct, verifiable proofs.

What this enables: any chain can verify Zcash’s privacy state without running a full Zcash node. This opens the path to cross-chain integrations — Zcash’s privacy becomes accessible to other ecosystems.

AI agent aixbt [commented](https://x.com/aixbt_agent/status/1991249468130488778):

“starkware’s zoro compresses zcash validation into stark proofs. any chain can now verify zec’s privacy state without running a full node. cypherpunk holdings accumulated $150m worth targeting 5% of supply. eli ben-sasson co-founded both zcash and starknet. this is 10 years of cryptographic research converging into production infrastructure”

### 6.2. NUT Specification for Cashu

The StarkWare exploration team proposed a new NUT specification for integrating ZK programs into Cashu — a protocol for private digital cash on Bitcoin. This opens possibilities for private innovation on Bitcoin through ZK proofs.

## Part VII. Open Questions and Challenges

### 7.1. Data Availability (DA)

One of the key unresolved questions is: where should L2 transaction data be stored?

Possible approaches:

1. Publishing all data to L1 — would dramatically increase blockchain load (unlikely)
2. External data networks — specialized nodes store L2 data, while only hashes go to L1 (Data Availability Committees, Celestia)
3. Hybrid models — large data via IPFS, minimal state diffs to L1

Developers lean toward a minimalist approach: for now, only state root hashes are posted to L1.

### 7.2. Impact on Shielded Pool Fees

Forum participants raised concerns: increased block load could raise the cost of regular transactions. Developers agree that a mechanism is needed where miners receive sufficient compensation for storing L2 data, but L1 private transactions don’t become too expensive.

There is discussion of a separate fee market for TZE operations.

### 7.3. Finality and Crosslink

Zcash is a PoW network without fast finality (block reorgs are possible). For a rollup, this is not ideal. A finality gadget is being discussed — an additional finalization mechanism, possibly through a hybrid PoW/PoS scheme.

At the community level, this concept has been named Crosslink — a cross-consensus mechanism that could improve UX (reduce deposit/withdrawal wait times from L2).

### 7.4. Sequencer Decentralization

In the prototype, L2 runs on a single centralized node. Future work involves decentralizing sequencers and provers. StarkNet is already experimenting with distributed proving and various L2 consensus schemes.

A native token may emerge, or STRK could be used for economic incentives, but this remains an open question. For now, the proposal is to operate in ZEC: L2 block publication fees are paid in ZEC to L1 miners.

### 7.5. Coordination with the Tachyon Upgrade

Developers from ECC note that the upcoming major Zcash protocol upgrade (Project Tachyon) is complex in its own right. Integration of TZE with STARK will likely be considered after Tachyon’s implementation.

## Part VIII. Market Reaction and Investment Context

### 8.1. Price Movement

ZEC:

• Surge to $635  
• Market cap exceeding $7.2 billion  
• Surpassed Monero by market capitalization  

STRK:

• Rise of 35–40% over several days  
• Trading volume reached $832 million  
• Starknet achieved second place in net inflows among all L1/L2s after Arbitrum (approximately $300 million in a month)  

### 8.2. Institutional Interest

By late November, more than 1 billion STRK (~20% of circulating supply) and over 1,260 BTC had been staked in Starknet’s BTCFi initiatives, with total value reaching $365 million.

On November 19, 2025, Anchorage Digital — the first federally chartered digital asset bank in the US — activated Bitcoin staking on Starknet.

Cypherpunk Holdings accumulated a $150 million position, targeting 5% of the ZEC supply.

### 8.3. Analyst Warnings

Despite the excitement, prudent voices warned: significant technical work and STRK token unlocks lie ahead. Speculation may be outpacing reality. Launching Ztarknet on mainnet will require time and passage through Zcash’s governance processes.

## Part IX. Roadmap

### 9.1. Current Status (December 2025)

![Alt text here](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/ztarknet_image2.png)

### 9.2. Plans for 2026

![Alt text here](https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/ztarknet_image3.png)

### 9.3. Dependencies

The key constraint is the Draft status of ZIP-222 (Transparent Zcash Extensions). Activating TZE functionality requires consensus from the Zcash community.

## Part X. Significance for the Industry

### 10.1. A New Paradigm: Programmable Privacy

Before Ztarknet, one had to choose:

• Private but slow L1 (Zcash, Monero)  
• Fast but public L2 (Arbitrum, Optimism, StarkNet on Ethereum)  

Ztarknet offers both “out of the box”. Transactions can be simultaneously private and cheap/fast.

### 10.2. Regulatory Aspect

Privacy is implemented at the protocol level, not as a third-party mixer. This enables:

• Preserving the ability for selective audit (if the user themselves reveals the key)  
• Avoiding issues like Tornado Cash sanctions  

### 10.3. Universality of STARK Technology

The project demonstrates: STARK technology is applicable not only for Ethereum. StarkNet becomes a multipurpose “engine” for blockchains — from Bitcoin to Zcash.

As Eli Ben-Sassoon noted: every blockchain that survives 10–20 years will likely have a STARK-like component.

## Conclusion

The StarkNet × Zcash initiative is not another “protocol for protocol’s sake.” It’s a convergence of two fundamental directions in zero-knowledge cryptography, which have developed in parallel for nearly a decade.

Zcash created the most reliable private layer. StarkNet created the fastest proof system. Together, they create programmable privacy at L2 speeds.

Key takeaways:

1. Minimal intervention at L1. Zcash doesn’t “break” — only a single STARK verifier is added. All value preservation rules, private pools, and monetary policy remain unchanged.
2. All complexity on L2. Smart contracts, DeFi, games, high-frequency transactions — everything runs at the second level. The base layer remains uncluttered.
3. Economic linkage to ZEC. Fees are paid in ZEC; bridged ZEC serves as the primary L2 currency. This creates new demand for the token without changing its properties.
4. Quantum resistance. STARK proofs are plausibly post-quantum, which is critical for long-term security.
5. Real progress. This is not a whitepaper or promises — proof-of-concept works, the hackathon succeeded, devnet is in development.

The path to realizing Ztarknet requires passage through Zcash’s governance processes, security audits, and resolution of Data Availability issues. But the swift successes of fall 2025 — from the first demonstrative testnet launch to the multi-million-dollar hackathon — show: Ztarknet is not theory, but a practically achievable goal.

If this architecture is realized, the crypto industry will gain something it has never had: a scalable, programmable, and at the same time fully private blockchain stack — from L1 to L2.

## Sources

Official Resources:

• Ztarknet Website: https://www.ztarknet.cash/  
• GitHub Ztarknet: https://github.com/Ztarknet/ztarknet  
• Zcash Community Forum: https://forum.zcashcommunity.com/t/proposal-ztarknet-a-starknet-l2-for-zcash/52926  
• StarkNet Blog: https://www.starknet.io/blog/  

Key Publications:

• “Zooko & Eli on Zcash, ZK, Privacy, and Scaling” — StarkNet Blog, November 5, 2025  
• “Starknet’s November Recap” — StarkNet Blog, November 2025  
• “Where Privacy meets Bitcoin, Zcash & NEAR” — StarkNet Blog, November 27, 2025  

News Sources:

• BeInCrypto: “Zcash–Starknet Link Fuels Bullish STRK Price Outlook”  
• CoinDesk: “Privacy Coin Bid Continues as Zcash Rally Lifts ‘Dino’ Sector; Starknet’s STRK Rockets 40%”  
• Cointelegraph: “Zcash Revival Sparks Debate on Bringing Privacy Back to Bitcoin”  
• The Block: “Zcash co-founder: ‘The world is demanding more privacy’”  

Technical Specifications:

• ZIP-222: Transparent Zcash Extensions — https://zips.z.cash/zip-0222  
• StarkWare: “Why I’m Excited By Circle STARK And Stwo” — https://starkware.co/integrity-matters-blog/why-im-excited-by-circle-stark-and-stwo/  

Hackathon:

• Zypherpunk Hackathon: https://zypherpunk.devfolio.co/overview  

Try:

[₿itcoin ecosystem dashboard overview](https://btcboard.io)
[Our Infrastructure Builders Program](https://www.htw.tech/builders)
