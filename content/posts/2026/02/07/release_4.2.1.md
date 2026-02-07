---
title: "Release 4.2.1"
date: "2026-02-07T13:31:41+01:00"
draft: false
author: sebastian
---

> Everything that can go wrong will go wrong.

— *Ed Murphy* (not really, the original quote was a bit different)

## Release 4.2.2 (or the moment we found out 4.2.1 was not on Maven Central)

Finally, we managed to get a new release of OFT out of the door.

While [4.2.2](https://github.com/itsallcode/openfasttrace/releases/tag/4.2.2) is only a bugfix and security release, it also inherits a new feature from 4.2.1. Why do I mention that?

Because it turns out that we had a problem with our Maven Central deployment and 4.2.0 was never properly released.

Generally, my observation is that release pipelines have become more and more complex over time. Some of that we owe to repeated supply chain attacks on package repositories. This is why we can't have nice things. But I digress.

The new feature is peeking into XML files before treating them as OFT input. Only if the header looks like a ReqM2 file, OFT will process it. This speeds up scanning of larger projects and removes warnings that came up when OFT tried to read a non-ReqM2 file.
