---
title: Alternatives
author: Gleb N
date: 2022-02-07
category: Jekyll
layout: post
---

Second-layer payment pools could be made with another Bitcoin Script primitives.

[OP_TLUV](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html),
as it was proposed, has to be tweaked to allow CoinPool as it is. The issue is that
the original OP_TLUV is not restrictive enough. The tweak could potenitally be replaced with
something else, although we are not aware of any alternative.

[OP_CTV](https://utxos.org/) could be [used](https://utxos.org/uses/batch-channels/) to build Payment Pools, although different than CoinPool.
We believe that CoinPool is advantageous because it allows any-time non-cooperative exits.
