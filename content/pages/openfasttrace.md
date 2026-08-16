---
title: "OpenFastTrace"
date: 2026-08-16
draft: false
---

OpenFastTrace (OFT) is a requirement tracing suite. It keeps track of whether you actually implemented everything you planned in your specifications, identifies obsolete parts of your product, and helps you keep your implementation, tests, and documentation in sync.

![OpenFastTrace HTML Tracing Report](https://raw.githubusercontent.com/itsallcode/openfasttrace/main/doc/images/oft_screenshot_tracing_report.png)

### Why use requirement tracing?

In non-trivial projects, it's easy to lose track of the connection between requirements and their implementation. OpenFastTrace acts as a safety net by:

- Protecting you from forgetting planned parts of your product.
- Finding orphaned code, documents, and resources.
- Helping you track progress towards milestones.
- Allowing you to prove due diligence during quality audits and customer reviews.

### Core Concepts

**Specification Items:** Everything is a specification item—from high-level features (`feat`) and user requirements (`req`) to design decisions (`dsn`) and implementation markers (`impl`).

You can freely define artifact types, so OFT will adapt to the needs of your project.

**Bidirectional Traceability:** OFT allows you to trace from top-level requirements down to implementation and tests, and back up again.

**Deep Coverage:** An item is only considered fully covered if all its detailing items are also correctly covered, ensuring there are no broken links in the chain.

### Technical Capabilities

While OFT's native formats for specifications are **Markdown** and **reStructuredText**, it can import coverage markers from comments in almost any programming language (including Java, C/C++, Python, Rust, Go, Swift, etc.) and configuration formats (YAML, JSON, TOML).

OpenFastTrace is designed to be part of your continuous integration pipeline. It offers dedicated plugins for **Maven** and **Gradle**.

You can generate reports in **HTML** for a high-level overview, **plain text** for console output and debugging, or **XML (aspec)** for integration with other tools.

OFT is a Java application. Version 4.0 and above require **Java 17** or later.

### Agentic Development

OpenFastTrace is a cornerstone for **Agentic Development**—a workflow where AI agents (like LLMs) autonomously or semi-autonomously handle development tasks. OFT provides the necessary structure and safety nets for AI-driven software engineering:

- **AI-Native Specifications:** OFT uses Markdown for requirements and design documentation, which is the natural language of Large Language Models.
- **Spec-Driven Development (SDD):** By treating specifications as the source of truth, agents can derive precise implementation plans (Changesets) from requirements before writing code.
- **Formal Verification of AI Output:** Tracing reports act as a formal gate, ensuring that every requirement is actually implemented and tested, protecting against AI "hallucinations" or omissions.
- **Agent Skills:** Specialized [skill definitions](https://github.com/itsallcode/openfasttrace/tree/main/.agents/skills) allow AI tools to autonomously maintain bidirectional traceability, keeping documentation and code in perfect sync.
- **Contextual Awareness:** Traceability links provide agents with immediate context about *why* a piece of code exists, leading to higher-quality AI-generated contributions.

### Videos

<figure style="display: flex; flex-direction: column; align-items: center; margin: 2rem 0;">
    <div style="width: 100%; margin-bottom: 1rem;">
        {{< youtube tlzMT6RaVWA >}}
    </div>
    <figcaption style="margin-top: 0.5rem; font-size: 0.9rem; color: #666; text-align: center;">Introduction to OpenFastTrace</figcaption>
</figure>

<figure style="display: flex; flex-direction: column; align-items: center; margin: 2rem 0;">
    <div style="width: 100%; margin-bottom: 1rem;">
        {{< youtube P2o_swwQTNE >}}
    </div>
    <figcaption style="margin-top: 0.5rem; font-size: 0.9rem; color: #666; text-align: center;">OpenFastTrace Presentation at Xen Summit</figcaption>
</figure>

### Resources

**Source Code:** [itsallcode/openfasttrace](https://github.com/itsallcode/openfasttrace)

**User Guide:** Detailed documentation is available in the [User Guide](https://github.com/itsallcode/openfasttrace/blob/main/doc/user_guide/user_guide.md).

**AI Agent Guide:** Information for AI agents and [skill definitions](https://github.com/itsallcode/openfasttrace/tree/main/.agents/skills) can be found in [AGENTS.md](https://github.com/itsallcode/openfasttrace/blob/main/AGENTS.md).

**Plugins:** 
    - [Maven Plugin](https://github.com/itsallcode/openfasttrace-maven-plugin)
    - [Gradle Plugin](https://github.com/itsallcode/openfasttrace-gradle)
    - [IntelliJ Plugin](https://github.com/itsallcode/openfasttrace-intellij-plugin)
