---
title: "OpenFastTrace IntelliJ Plugin 0.8.0"
date: "2026-06-10T19:25:40+02:00"
draft: false
author: "sebastian"
---

The [OpenFastTrace IntelliJ Plugin 0.8.0](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.8.0) is out. While version 0.7.0 made OFT runs configurable, this release focuses on how you interact with the results.

## Test Runner UI Integration

The most significant change is that OpenFastTrace results now integrate directly with IntelliJ's built-in Test Runner UI. Instead of scanning a text report, you get a structured tree of results.

This integration provides several benefits:
- **Visual Feedback**: Results are grouped by source file, specification item, and trace link. Clean items show as passed, while defects appear as failures.
- **Deep Inspection**: You can expand source files to see affected items and inspect incoming/outgoing trace links as sub-tests.
- **Contextual Information**: Item IDs, link status, and defect explanations are visible in the test details.
- **Easy Navigation**: You can jump from result nodes directly to the source files, specification declarations, or coverage tags.

The global `Tools | OpenFastTrace | Trace Project` action and new run configurations use this UI by default. If you prefer the raw report, you can still opt into the plain text output in the run configuration.

## Improved Identity

We have also added JetBrains-compliant icon assets. This means the plugin is now easier to identify in the IDE and on the JetBrains Marketplace. OpenFastTrace run configurations now use a dedicated icon instead of the generic execution icon.

## Documentation and Maintenance

This release also includes a new use-case-centric user guide to help you get the most out of the plugin. On the build side, we have added dependency locks and improved our version checking to ensure a more stable build process.

If you are using IntelliJ, give it a try. You can find the release and the full changelog on [GitHub](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.8.0).

