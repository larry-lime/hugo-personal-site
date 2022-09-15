---
title: "Vitalik's Vision - EthCC Paris Recap"
date: 2022-07-27
draft: false
author: 0xLawrence
categories: ["research"]
tags: ["blockchain", "programming"]
cover:
  image: img/vitalik_vision.jpg
  alt: "Vitalik's Vision"
ShowToc: true
ShowReadingTime: true
ShowBreadCrumbs: true
---
> Vitalik Buterin recently spoke at EthParis 2022, outlining his long-term and short-term goals for Ethereum. We examine the roadmap he lays out and will also break down vital technical features to play an essential role in Ethereum's future.

## Prerequisites

Knowledge of [Proof of Work (PoW)](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/), [Proof of Stake (PoS)](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/), and [Layer-2 (L2)](https://ethereum.org/en/layer-2/#:~:text=A layer 2 is a separate blockchain that extends Ethereum.&text=A layer 2 blockchain regularly,layer 1 protocol (Ethereum).) scaling is needed to get the most out of this article. After finishing this article, it's also encouraged to watch [Vitalik's full panel talk at Ethereum Community Conference 5 (EthCC 5)](https://www.youtube.com/watch?v=kGjFTzRTH3Q).

## Background

Vitalik Buterin's panel talk last week at EthCC 5 reminds aficionados of the decentralized web that we are living through a period of unprecedented technological innovation. This article will recap Vitalik's vision for Ethereum's future and explain key technical details in plain English.

## Merge, Surge, Verge, ...

Vitalik begins his panel by summarizing Ethereum's major development stages (the Merge, Surge, Verge, Purge, and Splurge) first outlined in his [December 2021 Ethereum Roadmap](https://twitter.com/VitalikButerin/status/1466411377107558402).

![Ethereum Roadmap by Vitalik, Decmeber 2021](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img202207270534440013a058-d0a2-4da6-8853-029e5e7eb454.jpg)

The Ethereum Merge's primary accomplishment will be to move the network from PoW to PoS. Its key advantage is that the shift will increase the protocol's decentralization and reduce Ethereum's electricity expenditure by over 99%.

Next, the Surge will introduce sharding which will increase Ethereum network capacity, reduce congestion, and increase transaction throughput. Sharding also works synergistically with L2 rollups by distributing the burden of handling data needed by rollups over the entire network.

Then the Verge will optimize storage on Ethereum and reduce node size by introducing Verkle tree proofs. Verkle trees serve the same function as [Merkle trees](https://blog.ethereum.org/2015/11/15/merkling-in-ethereum/) but are more efficient in proof size. [Vitalik explains](https://vitalik.ca/general/2021/06/18/verkle.html) how, in a tree containing a billion pieces of data, generating a proof with a Merkle tree would require 1 kilobyte, whereas a Verkle tree would be less than 150 bytes, a more than 85% reduction in proof size.

![Ethereum Roadmap by Vitalik, Decmeber 2021](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img2022072705344590500a7a-526e-4227-85b3-beeab63ffe75.jpg)Source: [Vitalik's Twitter](https://twitter.com/VitalikButerin/status/1466411377107558402)

The Purge will involve changes to the network meant to reduce protocol complexity. The changes include Ethereum Improvement Proposal (EIP) 4444, which will remove the need for Ethereum clients to store and retrieve old historical data. Both changes will further reduce node size, enabling a full Ethereum node to be run on lighter hardware, thus making mobile phone staking a possibility.

Finally, Vitalik skimmed over the Splurge, calling it "all the other fun stuff."

## Completing the Transition

Following Vitalik's summary of each Ethereum development phase, he goes more in-depth on the effects of the PoW to PoS transition. One notable change is a decrease in Ether issuance from a fixed 5M per year to an equation of ~166 * sqrt(total_deposits) per year.

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img20220727053446149327de-3291-4dfa-93ea-b512dc004ed9.jpg)Source: [Grand Amphi Théatre Youtube](https://www.youtube.com/watch?v=kGjFTzRTH3Q)

He also mentions that while PoS allows for greater decentralization, it comes with the tradeoff of *weak subjectivity*. [*Weak subjectivity*](https://academy.binance.com/en/glossary/weak-subjectivity) is a requirement in PoS blockchains where a new node joining the chain must rely on other nodes to determine the system's state. *Weak subjectivity* is a tradeoff compared to *objectivity* applied by PoW blockchains because a node requires a recent state from a trusted source in order to sync with the blockchain. *Weak subjectivity* does not exist on PoW blockchains like Bitcoin, where determining the active chain is as simple as finding the longest chain.

## Ethereum's Growth Trajectory

Continuing, Vitalik discusses his thoughts on Ethereum's growth trajectory and the distinct roles of L1 and L2 in the future.

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img20220727053446826bb270-8fb7-4709-bf65-89eb2cc5f21b.jpg)

Vitalik explains that Ethereum is currently in a stage of rapid iteration, and the capability of the system will grow at a slower rate after the next few development phases. Vitalik believes that Ethereum will have achieved 55% of its intended functionality once it completes the Merge, putting us past the graph's inflection point.

As improvement to the system's capability slows, the development of Ethereum should aim to optimize safety, predictability, and decentralization. This process of scaling back rapid iteration is what he calls "settling down."

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img202207270534466246fe05-61f1-4cc8-b301-fe76548095eb.jpg)

Vitalik views L1 and L2 as serving two distinct roles, one for safety and reliability and the other for rapid iteration, high scalability, and high response times. He seems to imply that, as Ethereum's ecosystem matures, end-users will be interacting with L2 almost by default.

## Short-Term Pain, Long-term Gain

Then, Vitalik talks about some examples of short-term pain resulting in long-term gain. A few notable examples are the switch to Verkle trees, EIP 4444, and the banning of the selfdestruct(address) opcode.

The main issue with the [selfdestruct(address)](https://hackernoon.com/how-to-hack-smart-contracts-self-destruct-and-solidity) function is that it adds unnecessary complexity to the EVM without providing much utility. Banning this opcode will break backward compatibility with only a few applications, and with a long lead time, developers should have no problem working around changes.

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img202207270534473d8b4917-211d-44f8-a450-c7a9e46a6b34.jpg)

These changes are slated to occur during the Verge and Purge stages of development. The general theme with these changes is that they will break backward compatibility for some dapps, forcing developers to rework features. However, in the long term, they will reduce the overall complexity of Ethereum, decreasing the amount of code in an Ethereum client over time.

## What to Focus On? Decentralization

As well, Vitalik discusses his decentralization goals for Ethereum, not before mentioning features he'd be scared of implementing. He is scared of implementing features such as adding support for multiple VMs ([eWASM](https://ewasm.readthedocs.io/) and [Cairo](https://www.cairo-lang.org/)), implementing base layer SNARKs, and surrendering to the mindset of "it's okay if no single person can understand the whole protocol because we can specialize."

The apprehension behind implementing multiple VMs and the mindset above is the same: the aversion to multiplying protocol complexity. And in the case of SNARKs, the current readability of SNARK circuits is poor, making them hard to understand and unfit to implement on the Ethereum base layer.

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img20220727053447d6ab2c71-4ae2-4861-8661-24fcc25eef96.jpg)

Instead of focusing on protocol improvements that may undermine the stability of the network, Ethereum needs to focus on decentralization. As new features implemented in the Merge and Verge stabilize and the protocol's rate of change slows, decentralization will be easier.

Decentralization goals include an easy-to-use light client allowing users to directly access the consensus layer and better support for home stakers and smaller decentralized staking pools. Decentralization will be improved through a gradual decrease in computational complexity and client storage requirements.

## Long-term Goals

At the end of his talk, Vitalik mentions a few of his long-term goals for Ethereum beyond the scope of his 2021 roadmap diagram.

![Vitalik's Speech on EthCC Paris](https://tokeninsight.com/cdn-cgi/image/width=750,fit=cover,quality=85/https://s2.tokeninsight.com/static/research/img202207270534478f620a99-6436-43d8-9f09-8e8f83182a83.jpg)

When quantum computers come in the not-too-distant future, Ethereum will need to upgrade cryptography, as Elliptic curve cryptography is not quantum attack resistant. Also, in the case that zkEVMs work well, there is the possibility of increasing transaction space on the base layer, though that requires good zk-SNARK circuit legibility. Finally, Vitalik emphasizes it's important to keep an open mind, as we don't know what the future will demand.

## Closing Thoughts

Vitalik's panel talk tell us that his vision for Ethereum is for the base layer to be maximally robust and dependable through decentralization and minimizing code complexity. This security and safety are far more important than continually iterating the base layer's functionality, as most future innovations will occur on L2. No matter your role in the Web 3 community, there's a lot of valuable information to extract from Vitalik's Ethereum conference panel talk. Hopefully, upon finishing this article, you now have a much clearer view of the road that Ethereum is headed on.
