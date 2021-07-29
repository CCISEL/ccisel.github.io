---
layout: post
title: Deconstructing yield Operator to Enhance Streams Processing
image: 2021-07-29-deconstructing-yield.png
date: 2021-7-29
type: post
published: true
status: publish
category: Programming
tags: [yield, iterators, generators]
author:
  login: dpoeira
  email: dpoeira@cc.isel.ipl.pt
  display_name: Diogo Poeira
  image: dpoeira.jpg
  role: Software Engineer
---

The _yield_ keyword is a well-known feature in most programming languages to pause and resume generator functions. 
Yet, what is the performance overhead of interleaving a _yield_-based operation in streams processing?
In this work, we analyze the intrinsic costs of using _yield_ on user-defined operations and we compare it with other state-of-the-art alternatives, including our proposal of a functional and minimalistic yield-based design named [tinyield](https://github.com/tinyield/jayield).

<a href="https://www.scitepress.org/PublicationsDetail.aspx?ID=sFFvNu0PTDs=&t=1" target="_blank">
  <img src="/assets/blog/2021-07-29-deconstructing-yield.png" width="100%">
</a>
