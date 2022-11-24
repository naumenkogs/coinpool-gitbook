---
title: 3. Protocol design
author: Gleb N
date: 2022-11-05
category: Jekyll
layout: post
---

CoinPool enables UTXO-sharing among many (from 2 to hundreds) participants.
It improves Bitcoin onboarding and transactional scaling by orders of magnitude. CoinPool instances
could be deployed standalone, as well as to enhance the Lightning Network.

Let's say Alice, Bob, Carol and Dave construct a CoinPool instance, each committing some BTC.
Once the pool is confirmed on-chain, they can pay each other off-chain, or leave the pool
non-interactively.

![coinpool-tree](/assets/coinpool-tree.png)

CoinPool v0.1 offers the following features:
- scalable non-interactive withdraw: a participant can withdraw their balance on-chain
without asking anyone for authorization. To execute this right, a user have to store a set of
pre-signed transactions.

- French leave: once one user withdraws, the remaining pool remains fully operational, at the cost
of only two on-chain transactions (as opposed to Channel Factories).

- lazy user kick-out: an irresponsive participant could be kicked out by the remaining parties,
ensuring both reasonable fault-tolerance and the safety of the lazy user's funds.

- protocol uplifting: pool balances could be used for high-level protocols, e.g. Payment Channels or
Swaps, or could be even connected to the LN. This could become a special zone for high-frequency
financial contracts and native routing of CoinPool funds through the Lightning Network.

Read the v0.1 protocol whitepaper [here](https://coinpool.dev/v0.1.pdf).
