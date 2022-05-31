---
title: Origins
author: Gleb N
date: 2022-02-08
category: Jekyll
layout: post
---

CoinPool was designed after working on Lightning-related issues for an extensive period of
time and understanding its fundamental issues.

The basic CoinPool design was heavily inspired by two existing constructions:
[Payment Channel Factories](https://bitcoinops.org/en/topics/channel-factories/) and
[JoinPool](https://bitcoinops.org/en/topics/joinpools/).

We believe that CoinPool takes the best of both:
- from Channel Factories, it takes the batching approach to Payment Channels, while improves on
the fault tolerance issues.
- from JoinPool it takes the idea of any-time withdrawals, providing better fault tolerance than
Channel Factories.

CoinPool also heavily uses [Taproot](https://bitcoinops.org/en/topics/taproot/), not just to improve privacy, but also to make the design
scalable by organizing spending conditions in the Merkle Tree. We cover the use of Taproot, as well
as other pre-requisites ([SIGHASH_ANYPREVOUT](http://anyprevout.xyz), [SIGHASH_GROUP](https://github.com/ariard/bips/blob/coinpool-bips/bip-group.mediawiki)) in the design sections.

[OP_TLUV](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html)
allows building payment pools similar to CoinPool. They were
designed independently within the short timeframe, so they could be seen as "brothers".
