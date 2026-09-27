---
title: "OpenFastTrace 4.10.0"
date: 2026-09-20
draft: false
author: "sebastian"
---

A lot happened in the world of OpenFastTrace in the last few weeks. OFT finally got its own website: https://openfasttrace.itsallcode.org. We use Jekyll to generate the site from the documentation in the OpenFastTrace repository.

We also have a draft for OFT's own exchange and report format that will eventually replace the SpecObject format inherited from ReqM2.

Oh, and of course we have a fresh new release with [4.10.0](https://openfasttrace.itsallcode.org/releases/4.10.0).

But the biggest change is that we now also publish to [Homebrew](https://formulae.brew.sh/formula/openfasttrace) and have our own [Debian repository](https://apt.itsallcode.org) so installing and updating OFT got a lot easier.

We further improved supply chain management and deliver an SPDX SBOM with every release now.

4.10.0 comes with a new `overview` verbosity level that shows all specification items sans the detail text. And for good measure, we also threw in a couple of bug fixes.