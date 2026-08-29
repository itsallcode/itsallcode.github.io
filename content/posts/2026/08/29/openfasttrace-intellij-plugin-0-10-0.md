---
title: "OpenFastTrace IntelliJ Plugin 0.10.0"
date: 2026-08-29
draft: false
author: "Sebastian"
---

The [OpenFastTrace IntelliJ Plugin 0.10.0](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.10.0) is now available. This release introduces specification item status filtering to OpenFastTrace run configurations, giving teams finer control over which lifecycle states are included during traceability analysis.

## Item Status Filtering

OpenFastTrace supports four specification item lifecycle statuses:

- **Draft**: Work-in-progress items under active drafting.
- **Proposed**: Items that have reached maturity and are ready for approval review.
- **Approved**: Accepted specifications (the default state for items without an explicit status).
- **Rejected**: Discarded or superseded requirements retained for historical completeness.

In standard OpenFastTrace workflows, only approved items are traced against architecture and implementation, while non-approved items are treated as informational. However, depending on review workflows and specification phases, developers and reviewers often need to trace draft or proposed items before formal approval.

Version 0.10.0 adds status checkboxes to the OpenFastTrace run configuration editor:

- **Draft**, **Proposed**, **Approved**, and **Rejected** can now be selected individually or in any combination.
- The selected statuses are persisted with the run configuration and passed directly to the OpenFastTrace core engine as import filter criteria.

## Template Defaults and Configuration Validation

All pre-configured run configuration templates (*User requirements*, *Design and down*, *Typical project*, and *Unfiltered*) default to selecting only **Approved** items.

## Getting the Plugin

You can download the release assets from [GitHub](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.10.0).
