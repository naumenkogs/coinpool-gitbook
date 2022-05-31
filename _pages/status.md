---
title: Status
author: Gleb N
date: 2022-02-09
category: Jekyll
layout: post
---

Gleb and Antoine started first discussed CoinPool in early 2020, and [presented](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-June/017964.html)
the idea to the mailing list in June 2020.

After gathering some feedback, Gleb and Antoine presented a thorough CoinPool design
in the form of a [whitepaper](https://coinpool.dev/v0.1.pdf).

According to our personal intution, the next steps in bringing CoinPool to reality should be:
- bring [SIGHASH_ANYPREVOUT](http://anyprevout.xyz/) (and, ideally, [SIGHASH_GROUP](https://github.com/ariard/bips/blob/coinpool-bips/bip-group.mediawiki)) to Bitcoin mainnet
- update and maintain a Bitcoin Core [fork with OP_MERKLESUB](https://github.com/ariard/bitcoin/commit/d063925ff3f68234c6d29bea0aa44157568e9415)
- build OP_MERKLESUB use-cases running on the signet
- run a signet with OP_MERKLESUB
- bring [OP_MERKLESUB](https://github.com/ariard/bips/blob/coinpool-bips/bip-merklesub.mediawiki) (or a modified [OP_TLUV](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html), or any other alternative) to Bitcoin maiinet
- continue building the software for OP_MERKLESUB support

This process should be accompanied by a constant research on the trade-offs and alternatives for
building payment pools. We should also continue to research the ways to improve CoinPool, e.g.
the high coordination requirement.

While it's possible to build CoinPool on the existing Bitcoin, we believe it's better
to allocate the efforts towards the ground work first, especially considering the scarcity of
research and review time. A today's version of CoinPool would be limited in scalability is
usability.
