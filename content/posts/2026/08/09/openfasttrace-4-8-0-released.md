---
title: "OpenFastTrace 4.8.0 released: Transitive Defect Distinction"
date: 2026-08-09
draft: false
author: "sebastian"
---

OpenFastTrace 4.8.0 is now available! Codenamed "Transitive Defect Distinction", this release introduces a crucial improvement for analyzing trace results by distinguishing between direct and transitive defects.

## Direct vs. Transitive Defects

Previously, a defect in a specification item was reported without indicating whether the defect originated in the item itself or was inherited from the items it covers. In version 4.8.0, OpenFastTrace now makes this distinction clear in both the HTML and plain-text reports.

*   **Direct Defect:** A failure of the item itself (e.g., a missing trace link or a failed check).
*   **Transitive Defect:** A defect inherited from covered items that have failed.

This improvement helps developers and quality engineers to quickly identify and focus on the root causes of failures in the requirement matrix, rather than wading through inherited defects.

## Plugin Updates

Please note that we haven't had the time yet to update the **Maven** and **Gradle** plugins to this new version. They will be updated in the coming weeks. Until then, you can use the OpenFastTrace CLI to take advantage of the new features.

For a complete list of changes, please see the [official release notes](https://github.com/itsallcode/openfasttrace/releases/tag/4.8.0).

