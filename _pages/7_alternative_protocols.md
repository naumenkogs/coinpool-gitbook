---
title: 7. Alternative Protocols
author: Gleb N
date: 2022-11-01
category: Jekyll
layout: post
---

Since implementing CoinPool properly requires substantial efforts,
it should be compared to other Bitcoin scalability solutions.

[Sidechains](https://www.blockstream.com/sidechains.pdf) assume moving activities to a parallel
blockchain anchored to Bitcoin, either via a multi-sig federated wallet, a cross-chain smart
contract, or sophisticated incentive mechanisms.

[Chaumian Banks](http://www.hit.bme.hu/~buttyan/courses/BMEVIHIM219/2009/Chaum.BlindSigForPayment.1982.PDF)
assume a timestamping server authorizing asset transfers (possibly blinded).
The idea is currently being revisited by the Bitcoin community within [Fedimint](https://fedimint.org/)

Digital Cash enables oblivious payments across participants, where the state does not have to be
monitored.
The idea is currently being revisited by the Bitcoin community within
[PathCoin](https://gist.github.com/AdamISZ/b462838cbc8cc06aae0c15610502e4da)

[Statechains](https://github.com/RubenSomsen/rubensomsen.github.io/blob/master/img/statechains.pdf)
allow transfering UTXOs off-chain, and doublespending is prevented by a trusted server.

[Proof-of-UTXOs](https://lists.linuxfoundation.org/pipermail/lightning-dev/2020-November/002884.html)
suggested using UTXO ownership to bootstrap other systems.

Establishing a quantitive framework for ranking these solutions (mempool utilization, velocity of
funds, fault tolerance, etc.) could help making an informed decision for picking a research
direction.

![genealogy](/assets/genealogy.jpg)
