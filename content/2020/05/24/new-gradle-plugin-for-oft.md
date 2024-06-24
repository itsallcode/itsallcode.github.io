---
title: "New Gradle Plugin for Oft"
date: 2020-05-24T20:56:01+02:00
draft: false
params:
    author: Christoph
---

It took a while, but now we finally released version 0.7.0 containing the Gradle plugin for OpenFastTrace 3.0.2.

There were some issues that delayed the release:

- The configuration of plugins changed in Gradle 6.0. The old API is deprecated and will be removed in Gradle 7.0, so we had to migrate to the new API.
- Calculating the test coverage of Gradle plugin integration tests requires plugin [jacoco-gradle-testkit-plugin](https://github.com/koral--/jacoco-gradle-testkit-plugin). With new Gradle versions the test task fails under Windows with exception message `Failed to create MD5 hash for file content`. This is a [known issue](https://github.com/koral--/jacoco-gradle-testkit-plugin/issues/9) caused by a gradle background process locking the Jacoco coverage result file `build/jacoco/test.exec`. Fortunately there is a workaround described in the issue. Now [Sonarcloud](https://sonarcloud.io/dashboard?id=org.itsallcode%3Aopenfasttrace-gradle) reports a test coverage of 90% for the plugin.

The new Gradle plugin requires Java 11 and Gradle 6.0. We ensure compatibility with versions 6.0 and 6.4.1 with additional integration tests.