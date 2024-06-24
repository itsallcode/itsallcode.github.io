---
title: "Long time, no see"
date: 2020-05-23T20:54:20+02:00
draft: false
params:
    author: Christoph
---

The previous blog post was published more than one year ago. That’s why it’s high time for an update. We where busy in the last weeks preparing some new releases for you!

## OpenFastTrace 3.0.2

This major release contains these changes:

- The project now requires Java 11 for building and running.
- We re-structured the packages to have unique package names for each submodule. This is a precondition for Java 9 modules which we will introduce later.
- The tag importer now supports many more file types, e.g. for C, C++, SQL and many more.

## OpenFastTrace Maven Plugin 0.1.0

This is the first release we recommend for production use as we added integration tests for real use cases. We upgraded to the latest OFT release and introduced a feature to optionally fail the build when tracing finds an error.