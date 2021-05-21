---
id: 482fd4a7-3fb6-45f4-8052-84eec393e1b1
title: Dev
desc: ''
updated: 1621033185262
created: 1611518371709
stub: false
---




### Managing code
- source: https://www.notion.so/fdffac12a8b54a1bbdf8a0e2058ed4d0?v=dc313dcc7e4d4e30bcd680c403d05c2f

- priority
    1. reducing state
    1. coupling
    1. complexity
    1. code

- other factors <!-- MW -->
    - performance
    - scalability
    - durability

One of my all-time favorite HN comments is from the original discussion of this article:

> Dependencies (coupling) is an important concern to address, but it's only 1 of 4 criteria that I consider and it's not the most important one. I try to optimize my code around reducing state, coupling, complexity and code, in that order. I'm willing to add increased coupling if it makes my code more stateless. I'm willing to make it more complex if it reduces coupling. And I'm willing to duplicate code if it makes the code less complex. Only if it doesn't increase state, coupling or complexity do I dedup code.

> The reason I put stateless code as the highest priority is it's the easiest to reason about. Stateless logic functions the same whether run normally, in parallel or distributed. It's the easiest to test, since it requires very little setup code. And it's the easiest to scale up, since you just run another copy of it. Once you introduce state, your life gets significantly harder.

> I think the reason that novice programmers optimize around code reduction is that it's the easiest of the 4 to spot. The other 3 are much more subtle and subjective and so will require greater experience to spot. But learning those priorities, in that order, has made me a significantly better developer.