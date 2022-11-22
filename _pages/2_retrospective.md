---
title: 2. Retrospective of constructions
author: Gleb N
date: 2022-11-06
category: Jekyll
layout: post
---

The CoinPool design builds on the research of Bitcoin Protocol Development community.

[Lightning Network](https://lightning.network/lightning-network-paper.pdf)
demonstrated the capabilities of Bitcoin off-chain protocols: it's a network of interconnected
bi-directional payment channels. The disadvantage of the LN is the complexity of routing payments
and resulting low funds velocity.

[Channel Factories](https://tik-old.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20(1).pdf) were proposed to optimize establishing/closing the payment channels by batching them across
many users and channels. The downside is substantial on-chain footprint every time a single
channel is closed.

[Joinpool](https://gist.github.com/harding/a30864d0315a0cebd7de3732f5bd88f0) utilizes Taproot tree
to encode withdraw capabilities of several participants owning a single UTXO, although balance
changes have to happen on-chain.

[Radixpool](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-June/017968.html)
allowed off-chain balances changes in a pooled construction. It assumes collocating participants
in radix branches, which restricts the computational space. The disadvantage is requiring users of
the same radix to rely on each other for leaving the pool.

[CoinPool](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-June/017964.html)
was proposed in mid-2020 resulting from discussions at Chaincode Labs and around.
