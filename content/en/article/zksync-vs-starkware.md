---
title: "zkSync vs StarkWare - What's the difference between the top two ZK Rollups?"
date: 2022-07-15
draft: false
author: ["Lawrence Lim"]
categories: ["research"]
tags: ["blockchain, programming"]
ShowToc: true
ShowReadingTime: true
ShowBreadCrumbs: true
---
> We compare zkSync and StarkNet - two prominent ZK-rollups scaling the Ethereum network. What are ZK-Rollups? How are zkSync and StarkNet different? What are SNARKs and STARKs? We answer these questions and more while also exploring each protocol's respective roadmaps and ecosystems.

*This article was first published to [TokenInsight](https://tokeninsight.com/en/cryptocurrencies) by Lawrence Lim. Original article linked [here](https://tokeninsight.com/en/research/market-analysis/zksync-vs-starkware-what-s-the-difference-between-the-top-two-zk-rollups)*

## Table of Contents

- [Prerequisites](#prerequisites)
- [Background](#background)
- [Zero-Knowledge Rollups](#zero-knowledge-rollups)
- [Optimistic vs. ZK Rollups](optimistic-vs.-zk-rollups)
- [zkSync vs. StarkNet](zksync-vs.-starknet)
- [SNARKs vs. STARKs](snarks-vs.-starks)
- [EVM Compatability](evm-compatability)
- [StarkNet vs. StarkEx](starknet-vs.-starkex)
- [Ecosystem Comparison](ecosystem-comparison)
- [Development Roadmap](development-roadmap)
- [Closing Thoughts](closing-thoughts)

## Prerequisites

To get the most out of this article, you should have a solid understanding of blockchain fundamentals and [Layer-2](https://ethereum.org/en/layer-2/) scaling. Having prior knowledge of [Optimistic rollups](https://tokeninsight.com/en/research/market-analysis/optimism-vs.-arbitrum-a-complete-comparison) and [zero-knowledge proofs](https://www.youtube.com/watch?v=fOGdb1CTu5c) is also highly encouraged.

## Background

zkSync and StarkNet are two of the largest Layer-two (L2) solutions that utilize ZK rollup technology to scale the Ethereum network. Upon finishing this article, you'll understand how ZK rollups function and learn the key differences in how zkSync and StarkNet apply this technology. Beyond that, you'll get an overview of zkSync and StarkNet's ecosystems and their respective development roadmaps.

## Zero-Knowledge Rollups

Before we cover ZK-rollups, let's refresh: what are zero-knowledge proofs (ZKP)? And how are they used in rollups? In cryptography, a zero-knowledge proof or protocol is a method by which one party (the prover) can prove to another party (the verifier) that a given statement is true while avoiding disclosure of additional information beyond the fact the statement is true.

In the case of ZK-rollups, a sequencer node batches hundreds of rollup chain transactions, generate a SNARK or STARK proof (more on them later), and then posts these transactions to Layer-1. These proofs, known as validity proofs, cryptographically validate the transactions before their state gets posted to the Ethereum Mainnet.

## Optimistic vs. ZK Rollups

![Technical comparison of Optimistic Rollup and ZK-Rollup](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/content/img/Optimistic_vs._ZK_Rollups.png)Source: [Vitalik Buterin](https://vitalik.ca/general/2021/01/05/rollup.html), [zkSync](https://www.youtube.com/watch?v=el-9YYGN1nw&feature=youtu.be), and [MatterLabs Medium](https://blog.matter-labs.io/optimistic-vs-zk-rollup-deep-dive-ea141e71e075)

ZKPs allow ZK-rollups to have a negligible fund withdrawal delay plus a higher level of security compared to Optimistic rollups, as you don't need to wait for the fraud-proof window to close or rely on the honesty of transaction validators.

Besides those advantages, ZK-rollups also have the potential to enable private transactions in future iterations. Projects like [Zcash ](https://z.cash/)and [Aztec Network](https://aztec.network/) have implemented ZK-proof enabled privacy features, and zkSync has openly [stated](https://docs.zksync.io/userdocs/privacy/) its intent to make their transactions private future.

ZK-rollups have the advantage in theoretical transactions-per-second (TPS) cap, transaction finality time, and security over Optimistic rollups. However, they fall behind in EVM compatibility (which we will explore later). These traits of ZK-rollups [lead Vitalik Buterin to believe that in the short term, Optimistic rollups will likely be superior in general-purpose EVM computation](https://vitalik.ca/general/2021/01/05/rollup.html). But in the medium to long term, ZK-rollups will win out in all use cases as the technology improves.

## zkSync vs. StarkNet

Now that you have an intuitive understanding of how ZK-rollups work, we can begin comparing zkSync and StarkNet. But first, let's quickly summarize them.

zkSync V1 is a SNARK proof rollup protocol released by MatterLabs to the Ethereum Mainnet in June 2020. MatterLabs released zkSync V2, the first EVM-compatible ZK-rollup, on the Ethereum Testnet in February 2022.

StarkNet is a STARK proof rollup protocol released on the Ethereum Testnet in November 2021 by StarkWare Ltd. The protocol, at the time in Alpha version 0.4.0, was released to Mainnet later the same month.

One key difference between zkSync and StarkNet is that they utilize different proofing protocols, called SNARKs (Succinct Non-Interactive ARgument of Knowledge) and STARKs (Scalable Transparent ARguments of Knowledge).

## SNARKs vs. STARKs

The fundamental differences between SNARK and STARK proofs lie in their setup procedure, scalability, and quantum computer attack resistance.

ZK-SNARKs must undergo a trusted setup phase where a small group of developers must be trusted to not manipulate code or divulge vulnerability information. This setup only needs to be done once and isn't a significant security risk but nonetheless undermines its decentralization.

ZK-STARKs, on the other hand, use publicly verifiable randomness to create trustless verifiable systems, removing the need for a trusted setup. STARKs are also currently quantum resilient, whereas SNARKs have the possibility of being cryptographically cracked by a quantum computer attack.

Finally, ZK-STARKs are also more scalable in computational speed and size than ZK-SNARKs, with potential proving speed increases of 10x. However, ZK-STARKs' one present downside is that the technology is not very mature, which limits its generalizability.

## EVM Compatability

So, because they utilize two different proofing methods, zkSync and StarkNet differ in their EVM compatibility. zkSync V2 claims to be 99% EVM compatible with Solidity and Vyper needing to first compile to [Yul](https://docs.soliditylang.org/en/latest/yul.html), an intermediate language, before compiling down to zkEVM bytecode through [LLVM](https://llvm.org/). Additionally, zkSync supports their ZKP optimized Rust-like language, Zinc, which compiles directly to bytecode using LLVM. However, Zinc is currently not Turing complete, and its development has halted since September 2021 due to zkSync's focus on Solidity compatibility.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/content/img/image144.png)Source: [Twitter@_supercycled](https://twitter.com/_supercycled/status/1469244938605019143)

StarkNet, on the other hand, is not currently developing for EVM compatibility. To deploy smart contracts on StarkNet, developers need to learn Cairo, a programming language built for STARK provable programs by StarkWare. Alternatively, smart contract developers can also opt to convert their Solidity code to Cairo using [Warp](https://github.com/NethermindEth/warp), a transpiler developed by NetherindEth. Although there are still a number of Solidity features not supported by the transpiler and are far from matching the EVM compatibility of zkSync V2.

## StarkNet vs. StarkEx

You may have heard of StarkEx, StarkWare's other premier technology. StarkEx is not a ZK-rollup, but instead is a customizable Layer-2 SaaS (Software as a Service) that uses STARK proofs to provide massive scaling for applications.

An easy way to not confuse the two is to remember a few key points:

1. StarkNet is a general purpose rollup chain. StarkEx is a toolkit made specifically for applications.
2. StarkNet scales Ethereum. StarkEx scales decentralized exchanges.
3. StarkNet allows interoperability between DApps but StarkEx does not.

The differences between the two are important to understand because while it's common for DApps using StarkEx to be included in the StarkNet ecosystem, metrics like TVL are completely separate.

## Ecosystem Comparison

Now we'll look at StarkNet and zkSync respective ecosystems and see how they compare. A graphical comparison can be found below.

![Ecosystem landscape of StarkNet & zkSync](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/content/img/Landscope2.png)Source: [StarkNet Ecosystem](https://www.starknet-ecosystem.com/), [zkSync Ecosystem](https://ecosystem.zksync.io/)

zkSync's (V1 & V2) TVL, as of writing on July 12th, 2022, is $57M. The entire protocol is also [100% open source](https://github.com/matter-labs/zksync) and their Github repo currently has 1.4k stars and 350+ forks. Their infrastructure is built mainly in Rust and Typescript. There are 112 DApps currently building on zkSync, with ten live on Mainnet. Some notable projects live on zkSync include [Zigzag](https://info.zigzag.exchange/), a non-custodial order book exchange, and [Argent](https://www.argent.xyz/) a DeFi and Web3 smart wallet.

StarkNet's TVL is currently around $635K with 78 DApps being built and only a few live on Mainnet. Unlike other prominent rollup protocols, StarkNet is currently closed source and its infrastructure is built with Cairo. Some notable protocols on StarkNet include [ArgentX](https://www.argent.xyz/argent-x/), Argent's Web3 wallet built for StarkNet, and [Orbiter Finance](https://orbiter-finance.medium.com/), a decentralized cross-rollup bridge.

When comparing their social media presence, zkSync has the slightly larger of the two with almost ~87K more followers on Twitter and comparable member counts on Discord and Telegram.![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/content/img/Social_Data2.png)

As you can see, both zkSync and StarkNet's ecosystems are far less mature than the ecosystems of Optimistic rollup protocols like [Optimism and Arbitrum](https://tokeninsight.com/en/research/market-analysis/optimism-vs.-arbitrum-a-complete-comparison). However, both zkSync and StarkNet have strong user and developer communities, promising future growth.

## Development Roadmap

In the short term, zkSync's next major leap following their Testnet launch will be their V2 Alpha Mainnet release, currently without an anticipated release date. zkSync's long-term plans include full decentralization, a zkSync Token Airdrop, and implementing privacy-protected smart contracts. As a part of their decentralization plans, their future token will be for staking in order to become a validator on the zkSync network.

StarkWare's short-term goal is to upgrade their Alpha Mainnet, prepping for a stable release. Their long-term goals are threefold: to establish usability, improve performance, and decentralize.

StarkWare feels they have accomplished their first goal of establishing usability and are presently focusing their development on throughput, transaction cost, and latency. StarkWare also recently released their decentralization proposal, containing [an announcement for a StarkNet token Airdrop](https://medium.com/starkware/part-1-starknet-sovereignty-a-decentralization-proposal-bca3e98a01ef), planned for September 2022. StarkNet's token will be for system governance, transaction fee payments, and participation in StarkNet's consensus mechanism.

## Closing Thoughts

By this point, we have covered how ZK rollups function, why they are implemented, and how they compare to Optimistic rollups. We also answered the question, what's the differences between zkSync and StarkNet? We did this by examining their ZK-SNARK versus ZK-STARK proofing methods and respective levels of EVM compatibility. Finally, we got a high-level snapshot of both protocols' ecosystems and roadmaps. Hopefully, this knowledge can serve as more fuel for your journey down the Layer-2 rabbit hole.
