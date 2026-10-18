---
title: "OpenFastTrace 4.11.0 and Gradle Plugin 3.5.0: Plugins Everywhere"
date: 2026-10-18
draft: false
author: "christoph"
---

Today we released [OpenFastTrace 4.11.0](https://github.com/itsallcode/openfasttrace/releases/tag/4.11.0) and [OpenFastTrace Gradle Plugin 3.5.0](https://github.com/itsallcode/openfasttrace-gradle/releases/tag/3.5.0). Both releases share one theme: making OFT extension plugins easier to use.

## OpenFastTrace 4.11.0

Until now, extension plugins had to be installed in OFT's predefined plugin directory. With [#610](https://github.com/itsallcode/openfasttrace/issues/610), embedders can now pass plugin JARs to OFT at runtime through the Java API:

```java
Oft.builder().addPlugin("asciidoc", pluginJarFile).build();
```

This means plugins resolved through an external dependency mechanism — a build tool, a container image, or your own classloader — no longer need to touch the plugin directory at all.

Further changes in 4.11.0:

* [#612](https://github.com/itsallcode/openfasttrace/issues/612): The source tag importer now supports Visual Basic (`.vb`) source files.
* [#423](https://github.com/itsallcode/openfasttrace/issues/423): Fixed a tag parsing inconsistency between the Markdown and reStructuredText importers.
* [#574](https://github.com/itsallcode/openfasttrace/issues/574): Fixed invalid HTML when inline code contains underscores.
* [#401](https://github.com/itsallcode/openfasttrace/issues/401): Added a regression test for an RST parser corner case.
* [#605](https://github.com/itsallcode/openfasttrace/issues/605): The user guide now has automatic lateral navigation.

## Gradle Plugin 3.5.0

The Gradle plugin follows up with [#77](https://github.com/itsallcode/openfasttrace-gradle/issues/77): OFT extension plugins can now be declared as build dependencies via the new `pluginDependencies` property. The declared artifacts are added to the classpath used by requirement collection and tracing:

```groovy
plugins {
  id 'org.itsallcode.openfasttrace' version '3.5.0'
}

repositories {
  mavenCentral()
}

requirementTracing {
  pluginDependencies = ['org.itsallcode:openfasttrace-asciidoc-plugin:1.0.0']
}
```

With this in place, a build that traces AsciiDoc requirements is just one dependency away — no manual copying of JARs into a plugin directory.

Note that these are OpenFastTrace extension plugins, not Gradle build plugins. Plugin JARs must provide the appropriate OpenFastTrace service descriptors and should not include a duplicate incompatible `openfasttrace-api` dependency. Plugin discovery remains additive to OFT's built-in plugin directory.

See the [Gradle plugin user guide](https://github.com/itsallcode/openfasttrace-gradle#using-openfasttrace-plugins) for details.

As always, the releases are available on [GitHub](https://github.com/itsallcode/openfasttrace/releases) and the Gradle plugin on the [Gradle Plugin Portal](https://plugins.gradle.org/plugin/org.itsallcode.openfasttrace). Feedback and contributions are welcome.