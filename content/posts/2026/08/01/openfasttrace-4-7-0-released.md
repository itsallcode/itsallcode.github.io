---
title: "OpenFastTrace 4.7.0 released: Gherkin Importer"
date: 2026-08-01
draft: false
author: "sebastian"
---

OpenFastTrace 4.7.0, codenamed "Gherkin Importer", is now available. This release introduces direct support for Gherkin `.feature` files as specification sources and enables requirement coverage within Markdown and reStructuredText (RST) comments.

## Gherkin Specification Import

The most significant addition in this release is the ability to import specification items directly from Gherkin `.feature` files. This allows teams using Behavior-Driven Development (BDD) to integrate their executable specifications directly into their traceability matrix.

OpenFastTrace now recognizes `Scenario` and `Scenario Outline` blocks as specification items when they are annotated with an OFT ID tag. You can also specify "coverage" and "needs" metadata using comments immediately following the tags.

Example of an annotated Gherkin scenario:

```gherkin
@id:scn~user-login~1
# Covers: req~authentication~1
# Needs: dsn, itest
Scenario: Successful login with valid credentials
  Given the login page is open
  When the user enters valid credentials
  Then the user should be redirected to the dashboard
```

## Coverage in Documentation Comments

This release expands the Tag Importer to support native comments in Markdown and reStructuredText (RST) files. This allows documentation to cover specification items without the coverage tags being visible in the rendered output.

In Markdown, you can now use standard HTML comments for coverage:

```markdown
<!-- [impl -> req~user-manual-updated~1] -->
```

Similarly, in reStructuredText, native comments are supported:

```rst
.. [impl -> req~user-manual-updated~1]
```

This feature is useful for maintaining traceability in user manuals, architectural decision records, and other documentation where explicit coverage tags might disrupt the flow for the reader.

For a detailed list of changes, please see the [official release notes](https://github.com/itsallcode/openfasttrace/releases/tag/4.7.0).
