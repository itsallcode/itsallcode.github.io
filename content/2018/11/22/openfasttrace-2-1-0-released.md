---
title: "OpenFastTrace 2.1.0 released"
date: 2018-11-22T20:31:41+02:00
draft: true
params:
    author: Sebastian
---

After two bugfix releases a new feature release. On November 19th Christoph create the Release for [OpenFastTrace 2.1.0](https://github.com/itsallcode/openfasttrace/releases/tag/2.1.0).

Feature-wise we are happy to announce an improved HTML report.

Sonar checks are now up and running again and the last JavaDoc errors have been rooted out.

We also fixed the deep coverage detection which was pointing upwards instead of downwards in the tracing chain. As a consequence we had to rework link loop detection, which acts a lot smarter now than before.

Enjoy this release, which is a huge step forward for OFT!