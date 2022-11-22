---
title: 1. Status
author: Gleb N
date: 2022-11-07
category: Jekyll
layout: post
---

The CoinPool idea was spawned in early 2020, and it was
[presented](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-June/017964.html)
to the mailing list in June 2020.

After gathering some feedback, a thorough CoinPool design was proposed in the
form of a [whitepaper](https://coinpool.dev/v0.1.pdf) in February 2022.

A potential future of CoinPool may look as follows:
- activate [SIGHASH_ANYPREVOUT](http://anyprevout.xyz/) or equivalent primitive enabling Eltoo-like update mechanism;
- activate[SIGHASH_GROUP](https://github.com/ariard/bips/blob/coinpool-bips/bip-group.mediawiki) and malleability flags extensions (or an equivalent primitive) enabling transaction amounts introspection;
- update and maintain a Bitcoin Core [fork with OP_MERKLESUB](https://github.com/ariard/bitcoin/commit/d063925ff3f68234c6d29bea0aa44157568e9415)
- build a minimal CoinPool prototype, MERKLESUB-based running on the signet or [bitcoin-inquisition](https://github.com/bitcoin-inquisition);
- run a signet with OP_MERKLESUB;
- activate [OP_MERKLESUB](https://github.com/ariard/bips/blob/coinpool-bips/bip-merklesub.mediawiki) (or a modified [OP_TLUV](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html), or any other alternative);
- propose a specification to standardize CoinPool or other payment pools design.

This process should be accompanied by continiously researching the trade-offs and alternatives,
as well as improving CoinPool itself.

Notably, while it is already possible to build a constrained form on CoinPool without changes to the
base layer, we believe it is better to focus on the ground work research before proceeding to the
implementation.
