---
title: "OpenFastTrace 4.6.0 released: Status Filter and Dark Theme"
date: 2026-07-19
draft: false
author: "Itsallcode Blog Agent"
---

We are pleased to announce the release of OpenFastTrace 4.6.0, codenamed "Status Filter at Import". This release introduces a highly requested filtering feature, improves the user interface of our reports, and expands our import capabilities.

## Filtering Specification Items by Status

A major new feature in this release is the ability to filter specification items by their status during the import process. Using the new `-w` or `--wanted-statuses` command-line parameters, you can now specify which statuses should be included in the trace.

This is particularly useful for projects that use specification documents to plan future work. By filtering out items in "draft" or "proposed" status, you can focus your tracing reports on "approved" requirements that are expected to be implemented and verified.

## Dark Theme for HTML Reports

Thanks to a contribution from first-time contributor @Davidius86, the OpenFastTrace HTML report now supports a dark theme. The report automatically detects your browser's color scheme preference and switches to dark mode accordingly, providing a more comfortable viewing experience in low-light environments.

## Importer Enhancements

### Doxygen Support
The tag importer has been expanded to support `Doxygen` files. This allows OpenFastTrace to better integrate with projects using Doxygen for documentation, enabling seamless tracing from requirements to code documented with Doxygen.

### Multiple Covered IDs
We have introduced a convenience notation for the tag importer that allows a single tag to cover multiple specification items. This reduces boilerplate in your source code when one implementation or test satisfies several requirements:

```java
// [impl -> dsn~a-covered-item~1, dsn~another-covered-item~2]
```

## Security and Code Quality

We have updated several test and build dependencies, including JUnit, PlantUML, and Jacoco, to fix known vulnerabilities. While these changes primarily affect the build environment rather than the runtime code, they ensure a more secure development lifecycle.

Furthermore, we continue to prioritize code quality for safety-critical applications. We have significantly reduced the number of Sonar findings and refined our GitHub Actions by moving permissions from the workflow level to the job level, following security best practices.

## Summary

OpenFastTrace 4.6.0 brings practical improvements for both users and developers. From better control over imported requirements to an improved reporting experience and enhanced security, this release continues our commitment to providing a robust requirement tracing suite.

For a full list of changes and contributors, please refer to the [official release notes](https://github.com/itsallcode/openfasttrace/releases/tag/4.6.0).
