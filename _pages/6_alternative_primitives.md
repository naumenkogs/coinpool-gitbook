---
title: 6. Alternative design primitives
author: Gleb N
date: 2022-11-02
category: Jekyll
layout: post
---

In Bitcoin smart contract design, the tools restricting the ways a UTXO could be spent are called
covenants. These tools, among other things, enable new off-chain protocols, including CoinPool.
Even though different covenant constructions have been discussed for years, none were activated
on Bitcoin mainnet.

CoinPool requires one of the following covenants:

- [TAPROOT_LEAF_UPDATE_VERIFY](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html)
enables dynamic editing of the Taproot tree. For CoinPool, it allows non-interactive withdrawals:
a user prunes their own balance from the pool while being unable to touch other users' balances.

- [MERKELSUB](https://github.com/ariard/bips/blob/coinpool-bips/bip-merklesub.mediawiki) is a
more restrictive alternative to TLUV. It allows slightly more straightforward CoinPool design,
although the opcode itself could be less powerful for other use-cases.

We encourage the community to continue the exploration of constructions enabling CoinPool.

Additionally, CoinPool requires the following modifications to Bitcoin Script:

- [SIGHASH_ANYPREVOUT](http://anyprevout.xyz/) is a new sighash flag to omit the spent
outpoints from the inputs and thus allowing dynamic rebinding of transactions. It enables
[Eltoo](https://blockstream.com/eltoo.pdf), an off-chain update mechanism.

- [SIGHASH_GROUP](https://github.com/ariard/bips/blob/coinpool-bips/bip-group.mediawiki)
is a new sighash malleability to outputs in an arbitrary way..

- [SIGHASH_ANYPUBKEY and SIGHASH_ANYAMOUNT](https://www.mail-archive.com/bitcoin-dev@lists.linuxfoundation.org/msg10456.html)
are new sighash flags to remove the commitment to the outputs amounts and scriptPubkey
in the transaction digest. For CoinPools, they allow linking the exact value to
be a function of previous pool withdrawals.
