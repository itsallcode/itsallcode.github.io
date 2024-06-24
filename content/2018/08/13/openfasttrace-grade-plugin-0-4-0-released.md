---
title: "OpenFastTrace Gradle plugin 0.4.0 released"
date: 2018-10-13T20:21:32+02:00
draft: false
params:
    author: Sebastian
---

Today we released version 0.4.0 of the OpenFastTrace Gradle plugin. This is the first version that can be considered production ready. It was successfully integrated into a real life commercial project using the following features:

- Software architecture design (Swad) imported as a dependency from a maven repository
- Software detailed design (Swdd) written in MarkDown
- Coverage tags in code (long format) for item types src, utest and stest
- Filter requirements from Swad, Swdd and Code using a artifact type filter
- Filter Swad requirements relevant for the project using a tag filter
- Generate a tracing report in text format containing failure details
- Additionally, to the report we export the requirements in Specobject format that can be delivered to integration for creating an overall tracing report

Only minor adaptions were required and OFT works in parallel to the proprietary tracing tool. It is just must faster! 😉

To see how you can integrate the OFT Gradle plugin into your project have a look at the [example projects](https://github.com/itsallcode/openfasttrace-gradle/tree/v0.4.0/example-projects/).