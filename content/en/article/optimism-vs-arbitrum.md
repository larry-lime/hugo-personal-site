---
title: "Optimism vs. Arbitrum - A Complete Comparison"
date: 2022-07-01
draft: false
author: 0xLawrence
categories: ["research"]
tags: ["blockchain","programming"]
cover:
  image: img/optimism_vs_arbitrum.jpg
  alt: "Optimism vs. Arbitrum"
ShowToc: true
ShowReadingTime: true
ShowBreadCrumbs: true
---
> Optimism and Arbitrum , two of the largest layer-two (L2) solutions that utilize Optimistic rollup technology to scale the Ethereum network. I will do a full comparison in this article.

*This article was first published to [TokenInsight](https://tokeninsight.com/en/cryptocurrencies) by Lawrence Lim. Original article linked [here](https://tokeninsight.com/en/research/miscellaneous/vitalik-s-vision-ethcc-paris-recap)*

## Background

Optimism and Arbitrum are two of the largest layer-two (L2) solutions that utilize Optimistic rollup technology to scale the Ethereum network.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/202207010833367a2599ca-6c67-4deb-a99c-b028445667c7.jpg)Source: https://l2fees.info/

At present, Ethereum's high transaction fees and limited throughput of ~15 transactions per second (TPS) severely limits its scalability.

As a solution to this problem, there exist rollup scaling solutions, classified into Zero-Knowledge[ (ZK) ](https://www.alchemy.com/blog/zero-knowledge-rollups#:~:text=Zero-knowledge rollups (ZK-rollups) are similar to,as one transaction onto Ethereum.)and Optimistic rollups; the latter of which we will focus on in this article. The two most prominent Optimistic rollups, Optimism, and Arbitrum, allow for the transaction of Ether or ERC-20 tokens at a throughput of ~2000-4000 TPS and at a fraction of the baseline Ethereum gas fee.

## Optimistic Rollups

Optimistic rollups work by executing transactions on a layer-2 rollup chain while a node, called a sequencer, rolls up and subsequently posts transaction state data to layer-1. This method of processing transactions has the advantage of compressing the data posted to the Ethereum mainnet while also amortizing gas fees among transactions in each rollup batch.

Moreover, unlike side chains, rollup scaling solutions utilize the blockchain consensus mechanism of layer-one, allowing rollups to benefit from the security of large networks such as Ethereum. Also, as transaction throughput scales on layer-1, it does so too on the rollup layer. So, when combined with the ETH 2.0 merge, rollups have the potential to improve transaction throughput to [~100,000 TPS](https://twitter.com/VitalikButerin/status/1277961594958471168?ref_src=twsrc^tfw|twcamp^tweetembed|twterm^1277961594958471168|twgr^|twcon^s1_c10&ref_url=https%3A%2F%2Fdecrypt.co%2F34204%2Fethereum-2-0-will-walk-and-roll-for-two-years-before-it-can-run).

## Optimistic vs. ZK Rollups

Unlike Optimistic rollups, which use a dispute-resolution process to secure transactions, ZK rollups utilize Zero-Knowledge mathematical proofs for transaction validation. Some key differences between them are as follows:

Optimistic rollups have a longer fund withdrawal period due to their security model.

Optimistic rollups are computationally less complex, resulting in layer-two nodes having lower hardware requirements.

Ethereum Virtual Machine (EVM) compatibility is much simpler on Optimistic rollups than on ZK rollups.

Currently, on both Optimism and Arbitrum, centralized sequencers must be trusted to post valid transaction data to layer-1. Theoretically, this is a security risk as it must be assumed there is at least one honest party between a sequencer and validator. However, sequencers are incentivized to act honestly, so in reality, the risk is minimal.

Optimistic rollups are the more popular of the two protocols with Optimism and Arbitrum controlling ~71% of layer-two market share.

## Arbitrum vs. Optimism

While Arbitrum and Optimism are both classified as Optimistic rollups, they do have a few fundamental differences.

For one, they utilize a different dispute-resolution process to validate transactions. Optimism uses single-round fraud proofs executed on layer-1, whereas Artibrum uses muli-round fraud proofs executed off-chain. Arbitrum's multi-round fraud proofing is the more advanced of the two, with it being cheaper and more efficient than single-round proofing.

Also, while Optimism and Arbitrum are both EVM compatible, Optimism uses Ethereum's EVM, whereas Arbitrum runs its own Arbitrum Virtual Machine (AVM). This results in Optimism having only a Solidity compiler, while Arbitrum supports all EVM compiled languages (Vyper, Yul, etc).

## Ecosystem Comparison

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/202207010833362ced18d9-da2b-4148-8c64-5d644a162238.jpg)Source: https://l2beat.com/#projects

The technical differences between Arbitrum and Optimism are very much "under-the-hood" and not very relevant to the average user. But, what is very visible is the size of their ecosystems and communities, which rounds out the differences between the two:

Arbitrum's total-value-locked (TVL), as of writing on June 28th, 2022, totals $2.09B, more than double that of Optimism's $807M.

Arbitrums's official Twitter and Discord currently have ~255K followers and 95K members respectively, whereas Optimism has ~214K Twitter followers and ~44K discord server members.

Optimism's ecosystem, though slightly more mature, is the smaller of the two with 50+ dapps compared to Arbitrum's 80+.

Both protocols also share many DEXs, DApps, and lending protocols. The largest platform on Arbitrum is [GMX](https://tokeninsight.com/en/coins/gmx/overview), a decentralized spot and perpetual exchange which prides itself on low swap fees and zero slippage. The second largest is [dForce](https://tokeninsight.com/en/coins/dforce/overview), a DeFi infrastructure protocol providing lending, trading, and staking services.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/20220701083337cc1763a7-7c27-41c3-b4d2-47ded72eaaf7.jpg)Source: https://defillama.com/

On Optimism, [Synthetix ](https://tokeninsight.com/en/coins/synthetix-network-token/overview)is the largest protocol by TVL and is a derivative liquidity protocol that enables the creation of synthetic assets on the blockchain. Additionally, [Velodrome Finance](https://tokeninsight.com/en/coins/velodrome-finance/overview) is a decentralized exchange for protocols exclusive to Optimism, created with the intent to ensure better interoperability between DeFi protocols on Optimism.

## Community Initiatives

Another significant difference between Optimism and Arbitrum is the types of initiatives they hold to engage their respective communities.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/202207010833376542312c-f339-4adb-9954-fa976602d853.jpg)Source: [community.optimism.io](https://community.optimism.io/)

Optimism recently Airdropped its governance token $OP on June 1st, 2022. This will extend Optimism's governance to its community members through the creation of the Optimism Collective and Optimism Foundation.

The Optimism Collective is a DAO, which itself is split into two houses, the Citizen's House and Token House. Members of these houses join by obtaining $[OP](https://tokeninsight.com/en/coins/optimism/overview), and will receive perks such as voting rights on protocol upgrades, project incentives, and [public goods funding](https://community.optimism.io/docs/governance/allocations/#retroactive-public-goods-funding).

The Optimism Foundation contains (now former) members of the Optimism PBC team, and will act as the steward of the Collective and run governance experiments on its behalf of them.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/20220701083337bc27d5cf-80d2-48d6-b6f9-a536387b05b8.jpg)

Arbitrum on the other hand, is not DAO governed, with the protocol run solely by [Offchain Labs](https://offchainlabs.com/). To engage their community, they recently launched their eight-week-long NFT event called Arbitrum Odyssey.

Arbitrum Odyssey is a collaborative event between Arbitrum and NFT artists, Ratwell & Sugoi, where participants must complete various tasks on-chain over the course of eight weeks in order to win prizes. For instance, users may be tasked to provide liquidity on one protocol, make a swap on another, and so on.

![img](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://image.tokeninsight.com/feishuimage/20220701083338d9d6dd09-f07e-42b7-be55-b91148fecd6d.jpg)Source: twitter.com/arbitrum

The first week, for example, will require users to onboard ETH into Arbitrum via any of the bridges & Fiat-on-ramps shown in the image above. Users that use the bridge that ends up getting the most volume at the end of the week will also be able to claim a bonus NFT. We wrote a complete overview of the event which can be found [here](https://tokeninsight.com/en/research/analysts-pick/the-poems-in-the-arbitrum-odyssey).

## Development Roadmap

Another area where Optimism and Arbitrum differ is in their development roadmap. Optimism clearly lays out its [development roadmap](https://www.optimism.io/about) until 2024, and some of its goals include the implementation of next-generation interactive fraud proofs, sharded rollups, and a decentralized sequencer.

Arbitrum does not have any of its future plans publicly available on either its website or Github. Though, one can speculate that as a competitor to Optimism, Offchain Labs may be tempted by the release of $OP to launch their own governance token sometime in the future.

## Closing Thoughts

In my opinion, both Optimism and Arbitrum each have advantages over the other without one of them being objectively better.

I find Arbitrum's team makes their marketing prowess quite clear through their ability to rapidly expand their social media presence and attract DApp developers to their chain. And in its current state, the rollup architecture of Arbitrum trumps that of Optimism in both security and longevity due to their superior fraud-proof mechanism and their proprietary VM.

Something I quite like about Optimism's team is that they place a strong emphasis on both the decentralization of its protocol and its governance, more so than Arbitrum's. It's also currently cheaper to transact and swap tokens on Optimism, and their promising future plans may enable them to lead the charge in Optimistic rollup innovation which could eventually sway the market in their favor.
