---
title: "OpenFastTrace 4.9.0 released: Item ID Location"
date: 2026-08-09
draft: false
author: "sebastian"
---

OpenFastTrace 4.9.0, codenamed "Item ID Location", is now available! This release lays the groundwork for much better IDE integration by tracking the exact location of specification item IDs in source files and documentation.

## Tracking ID Locations

The importers for long coverage tags, Markdown, and reStructuredText (RST) have been updated to collect the precise source code location of every specification item ID they encounter. 

This is a key requirement for upcoming IDE plugin features, such as:
*   **Syntax Highlighting:** Accurately coloring item IDs in your editor.
*   **Navigation:** Jumping directly from a reference to the declaration.
*   **Find Occurrences:** Listing all places where a requirement is covered or mentioned.
*   **Auto-complete:** Providing suggestions for existing item IDs.

By integrating this tracking into the core of OpenFastTrace, we avoid code duplication in plugins and ensure a more reliable and consistent experience across different tools.

## API Changes and Deprecations

For developers using the OpenFastTrace API or writing custom plugins, please note that several methods in the `ImportEventListener` interface have been deprecated in favor of new variants that include location information:

*   `setId(SpecificationItemId id)`
*   `addCoveredId(SpecificationItemId id)`
*   `addDependsOnId(SpecificationItemId id)`

We recommend migrating to the new methods to ensure your plugins can take advantage of the new location tracking capabilities.

## Plugin Updates

The work on 4.9.0 is a prerequisite for major updates to our IDE plugins. We are still working on updating the **Maven** and **Gradle** plugins to support the latest versions (4.8.x and 4.9.x). We appreciate your patience as we work through these updates.

For a complete list of changes, please see the [official release notes](https://github.com/itsallcode/openfasttrace/releases/tag/4.9.0).

