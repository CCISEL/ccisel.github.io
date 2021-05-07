---
layout: post
title: Towards unopinionated Web templates
image: 2021-05-07-miguel-towards-unopinionated-web-templates.png
date: 2021-05-07
type: post
published: true
status: publish
category: java
tags: [java, kotlin]
author:
  login: miguelgamboa
  email: 
  display_name: Miguel Gamboa
  image: miguel.jpg
  role: Software Developer
---

In this article, Miguel Gamboa et al. argue against the use of an external DSL
to implement HTML templates, such as using JSP, handlebars, Thymeleaf, Vue, or
others, that introduce new dialects such as `th:each`, `th:with`, `v-for`,
`v-if`, `v-bind`, etc… On the other hand, an internal DSL like React JSX,
KotlinX.html, or HtmlFlow, let you fluently interleave constructs from the host
language (i.e. JavaScript, Kotlin, or Java, respectively) with the use of HTML.

Providing templating features through specific dialects incur the following drawbacks:
1. weak or absent compile-time validation.
2. idiomatic mix between HTML, template dialects and the host programming language.
3. restricted suite of control flow features leveraged by template dialects.
4. opinionated templating idioms.
5. lack of asynchronous rendering support, according to asynchronous view models.

This work shows how an internal domain-specific language (DSL) for HTML (such as
HtmlFlow, Kotlinx.html, or React JSX) can suppress the aforementioned
limitations.
To that end, this work uses the Spring Framework and the well-known sample
application PetClinic to show how an internal DSL for HTML provides
unopinionated web templates with boundless resolving features only ruled by the
host programming language (such as Java, Kotlin, or JavaScript).

<a href="https://gamboa.pt/img/my-papers/lnbip2020-unopinionated-templates.pdf">
  <img src="/assets/blog/2021-05-07-miguel-towards-unopinionated-web-templates.png" width="650px">
</a>