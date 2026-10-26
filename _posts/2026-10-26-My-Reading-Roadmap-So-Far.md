---
layout: post
title: "My Reading Roadmap So Far"
date: 2026-10-26
---

I want to share some of the papers I have read or studied so far, along with a few topics I have explored. I hope this list can help others who are interested in similar topics.

This is not a complete roadmap, and I am not saying that everyone should follow the same order. It is simply a look at the path I have taken so far.


## 1. Blockchain protocols

I think the Bitcoin Backbone paper is a good place to start if you want to understand how blockchain protocols can be studied and how their security can be proved.

### The Bitcoin Backbone Protocol

[The Bitcoin Backbone Protocol: Analysis and Applications (EUROCRYPT 2015)](https://eprint.iacr.org/2014/765.pdf)

This paper studies the security of Bitcoin-like systems. It introduces some important ideas that are useful for understanding how blockchains work and what makes them secure.

When reading it, try to understand the main security goals and the assumptions behind the protocol. You do not need to understand every proof on your first try.

### A different version of the Bitcoin Backbone

[The Bitcoin Backbone Protocol with Chains of Variable Difficulty (CRYPTO 2017)](https://eprint.iacr.org/2016/1048.pdf)

This paper builds on the Bitcoin Backbone model and studies what happens when the difficulty of the chain can change.

Reading it after the original paper can help you understand how researchers change an existing model and study its security under new conditions.

### Proof of Stake

[Ouroboros: A Provably Secure Proof-of-Stake Blockchain Protocol (CRYPTO 2017)](https://eprint.iacr.org/2016/889.pdf)

Ouroboros is about building a secure blockchain using Proof of Stake instead of Proof of Work.

While reading it, try to compare its main ideas with the Bitcoin Backbone paper. What changes when the system uses stake instead of computational work? What assumptions does the protocol need?

### Privacy in blockchain systems

[Proof-of-Stake Protocols for Privacy-Aware Blockchains (EUROCRYPT 2019)](https://eprint.iacr.org/2018/1105.pdf)

This paper looks at privacy in Proof-of-Stake blockchains. It is a useful direction if you want to learn more about the connection between blockchain protocols and privacy.

[Can a Public Blockchain Keep a Secret? (TCC 2020)](https://eprint.iacr.org/2020/464.pdf)

The title asks an interesting question: can a public blockchain keep information secret? While reading this paper, focus on the exact problem it tries to solve and the conditions under which its solution works.

### Privacy-preserving payments

[Privacy-preserving auditable token payments in a permissioned blockchain system](https://eprint.iacr.org/2019/1058.pdf)

This paper studies how a blockchain payment system can protect privacy while still allowing payments to be checked when needed.

It is a useful example of how researchers try to balance different goals when designing a system.


## 2. A few things I have learned so far

Reading research papers takes time. Sometimes you understand the general idea but cannot follow the proofs. Sometimes a single definition can take hours to understand.

I think this is a normal part of the process. You do not have to understand everything on your first try.

It also helps to keep notes. I write down useful definitions, questions, and papers that I may need to read later. These notes make it easier to return to a topic after some time.

Another useful thing is to compare papers. When two papers study similar problems, try to understand what is different between them and why the newer paper was needed.

Most importantly, do not treat reading papers as a race. Reading ten papers without understanding them is not necessarily better than understanding one paper well.

This is the path I have taken so far, and I still have a lot to learn. I will update this list as I read more papers and explore new topics.

I hope it helps someone who is following a similar path.