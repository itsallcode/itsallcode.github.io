---
title: "OFT Language Server and FlashTrace"
date: 2026-10-11
draft: false
author: "sebastian"
---

Last Sunday, the OpenFastTrace team met with Prof. Oliver Kopp, Felix Gorke and Lennart Solterbeck to talk about the background, history and design of OFT. It was a good opportunity to compare notes on traceability tools and the decisions that shape them.

## A Language Server for OFT

Felix donated the [OpenFastTrace language server](https://github.com/itsallcode/openfasttrace-language-server/) to the itsallcode.org organization. He originally developed it for his bachelor's thesis, and we are very grateful that he is making it available to the community.

The language server brings OFT support to editors that implement the Language Server Protocol. It already includes clients for IntelliJ IDEA and VS Code. Its features range from syntax highlighting, hover documentation, go-to-definition, finding references and symbol search to trace diagnostics and quick fixes. It also provides coverage code lenses and hierarchy views, completion and rename support, trace reports, `.oftignore` support, and traceable architecture decisions. This makes the format more approachable in editors that do not have a dedicated OFT integration yet.

## FlashTrace

Lennart also introduced us to [FlashTrace](https://github.com/flashtrace/flashtrace). He explained why he started the project in JavaScript and why he is currently rewriting it in Rust. We discussed the similarities and differences between FlashTrace and OFT, as well as ways to make the two tools work together more easily.

OpenFastTrace has always been an open-source project. We are happy when our contributions inspire people to build something new. We do not see FlashTrace as competition but as a welcome interaction and a chance to learn from each other. Better interoperability would help users choose the tooling that fits their workflow while keeping traceability information useful across projects.
