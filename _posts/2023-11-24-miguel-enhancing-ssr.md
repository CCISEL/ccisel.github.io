---
layout: post
title: Enhancing SSR in Low-Thread Web Servers
image: 2023-11-24-miguel-enhancing-ssr.png
date: 2023-11-24
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

Naive server-side rendering (SSR) techniques require a dedicated server thread
per HTTP request, thereby limiting the number of concurrent requests to the
available server threads.
Furthermore, this approach proves impractical for modern low-thread servers like
WebFlux, VertX, and Express Node.js.
To achieve progressive rendering, asynchronous data models provided by
non-blocking APIs must be utilized. 
Nevertheless, this method can introduce undesirable interleaving between
template view processing and data access, potentially resulting in malformed
HTML documents.
Some template engines offer partial remedies through specific templating
dialects, but they encounter two limitations.
Firstly, their compatibility is confined to specific types of asynchronous APIs,
such as the reactive stream Publisher API. 
Secondly, they typically support only a single asynchronous data model at a
time. In this research, we propose an alternative web templating approach that
embraces any asynchronous AP I (e.g., Publisher, promises, suspend functions,
flow, etc.) and allows for multiple asynchronous data sources. 
Our approach is implemented on top of HtmlFlow, a Java-based DSL for writing
type-safe HTML. We evaluated against state-of-the-art reactive servers,
specifically WebFlux, and compared it with popular templating idioms like
Thymeleaf and KotlinX.html. 
Our proposal effectively overcomes the limitations of existing approaches.

<a href="https://www.scitepress.org/Link.aspx?doi=10.5220/0012165300003584" target="_blank">
  <img src="/assets/blog/2023-11-24-miguel-enhancing-ssr.png" width="100%">
</a>
