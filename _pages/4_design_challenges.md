---
title: 4. Design challenges
author: Gleb N
date: 2022-11-04
category: Jekyll
layout: post
---

Current CoinPool design would have much better usability if the following challenges are addressed:

Lowering interactivity: every off-chain pool update touching 2+ balances requires
a real-time authorization from all pool participants (some thoughts [here](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-April/020370.html)).
This puts a strong availability burden on the users.

Efficient onboarding: adding a new user to the existing CoinPool instance requires an on-chain
transaction, which takes time (to mine confirmation blocks) and money (transaction fee).

Non-interactive withdraw aggregation: users withdrawing at the same time currently have to
create one transaction per withdrawal, and arrange their withdrawals spending one another. Ideally,
users should be able to easily combine their withdrawals in one transaction.
