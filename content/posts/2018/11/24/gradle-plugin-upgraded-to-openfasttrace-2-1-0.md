---
title: "Gradle Plugin Upgraded to Openfasttrace 2.1.0"
date: 2018-11-24T20:33:37+02:00
draft: false
params:
    author: Christoph
---

After releasing OpenFastTrace 2.1.0 it was high time to release the corresponding [Gradle plugin in version 0.5.0](https://plugins.gradle.org/plugin/org.itsallcode.openfasttrace). This is a drop-in update, just update the version number and benefit from the features and bugfixes of OFT 2.1.0.

During the release process we also fixed the sonar analysis and some sonar warnings.

We also used the opportunity to document (and test) two features that where already implemented but not described:

- [Import requirements from a maven repository](https://github.com/itsallcode/openfasttrace-gradle#importing-external-requirements)  
  This is useful for sharing requirements with other sub-projects.
- [Publish requirements to a maven repository](https://github.com/itsallcode/openfasttrace-gradle#publishing-requirements-to-a-maven-repository)  
  This is useful for tracing against requirements from a higher-level architecture document.