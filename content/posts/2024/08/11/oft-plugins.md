---
title: "Plugins for OpenFastTrace"
date: "2024-08-11T10:30:00+02:00"
draft: false
author: "Christoph"
---

We are very happy to announce a new feature for OpenFastTrace in [version 4.1.0](https://github.com/itsallcode/openfasttrace/releases/tag/4.1.0): You can now create and use third party plugins!

Using plugins you can extend OFT with new imports and exports without modifying the core product. The very first plugin [openfasttrace-asciidoc-plugin](https://github.com/itsallcode/openfasttrace-asciidoc-plugin) was contributed by [@sophokles73](https://github.com/sophokles73) and is available in [version 0.2.0](https://github.com/itsallcode/openfasttrace-asciidoc-plugin/releases/tag/0.2.0).

We also have good news for Maven users: It's very easy to use OFT plugins with our [openfasttrace-maven-plugin](https://github.com/itsallcode/openfasttrace-maven-plugin) if they are published to a Maven repository, see the [documentation](https://github.com/itsallcode/openfasttrace-maven-plugin/blob/main/README.md#openfasttrace-plugins) for details. The latest version [2.1.0](https://github.com/itsallcode/openfasttrace-maven-plugin/releases/tag/2.1.0) contains OFT 4.1.0.

If you want to use plugins with standalone OFT, please check [how to install plugins](https://github.com/itsallcode/openfasttrace/blob/main/doc/plugins.md), and if you are a developer and want to build a new plugin, please check out our new [Plugin Developer Guide](https://github.com/itsallcode/openfasttrace/blob/main/doc/plugin_developer_guide.md).
