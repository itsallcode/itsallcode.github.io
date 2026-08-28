---
title: "OpenFastTrace IntelliJ Plugin 0.9.0"
date: 2026-08-28
draft: false
author: "Sebastian"
---

The [OpenFastTrace IntelliJ Plugin 0.9.0](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.9.0) is now available. Following the Test Runner UI introduced in version 0.8.0, this release streamlines project setup with specialized run configuration templates, clarifies defect reporting by distinguishing direct and transitive defects, and upgrades the bundled OpenFastTrace core to 4.9.0.

## Run Configuration Templates

To simplify setting up traceability, version 0.9.0 comes with specialized run configuration templates.

When creating a new OpenFastTrace run configuration (`Run | Edit Configurations... | + | OpenFastTrace`), you can now choose from four pre-configured templates:

- **User requirements**: Scans `doc/`, excludes source directories, and filters for high-level artifact types (`feat, req, scn, bconstr`). This setup is tailored for validating stakeholder-level requirements and business specifications without noise from implementation artifacts.
- **Design and down**: Scans `doc/`, excludes source directories, and filters for specification artifacts down to design (`feat, req, scn, bconstr, arch, dsn, constr, bld`). Useful during architecture and system design phases.
- **Typical project**: Scans `doc/` and all project source directories with no artifact type filtering. This is the default setup for end-to-end requirement-to-code traceability across the entire codebase.
- **Unfiltered**: Scans the entire project root (`.`) with no directory exclusions or artifact filters, suitable for custom project structures.

Each template can be customized with additional path includes, exclusions, and report options.

## Direct and Transitive Defect Presentation

When resolving traceability issues in a multi-tier specification, downstream items often fail simply because an upstream requirement has an unresolved defect. These follow-up failures are *transitive defects*, whereas the actionable root cause is the *direct defect*.

Version 0.9.0 improves how these defects are presented in the IntelliJ Test Runner UI:

- **Transitive Indicator**: Specification items with transitive failures are prefixed with a `↳` symbol in the result tree, distinguishing them from direct defects at a glance.
- **Transitive Defect Filter**: Run configurations now include a "Show transitive defects" option (enabled by default). Disabling this toggle hides secondary defects, allowing you to focus exclusively on fixing root causes.
- 
## Accurate Item Counting in the Test Runner

In previous versions, the Test Runner mixed specification items and trace link sub-nodes in its overall test count. This inflated the total count and could cause the progress bar to remain below 100% even on completely clean runs.

The Test Runner now counts specification items exclusively. Source file suites and trace link details remain fully navigable in the tree view for deep inspection, but they no longer inflate item counts or distort progress reporting.

## Bundled OpenFastTrace 4.9.0 and Other Improvements

This release bundles the latest **OpenFastTrace 4.9.0** core engine, bringing updated importer capabilities and performance enhancements.

Additional improvements include:
- **Refined Markdown Completion**: Auto-completion for specification item IDs in Markdown files is now restricted to relevant contexts, avoiding intrusive suggestions while typing regular text.
- **Marketplace Metadata**: Updated plugin description and release notes for clearer presentation on the JetBrains Marketplace.
- **Automated Verification**: Integrated JetBrains plugin verification into the release workflow to ensure compatibility and stability before publication.

## Getting the Plugin

You can download the release assets from [GitHub](https://github.com/itsallcode/openfasttrace-intellij-plugin/releases/tag/0.9.0).
