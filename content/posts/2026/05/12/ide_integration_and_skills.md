---
title: "OFT in the IDE and Teaching AI Agents About Tracing"
date: "2026-05-12"
draft: false
author: sebastian
---

Two things happened recently that I think are worth mentioning: OFT got an IntelliJ plugin, and we added several skill files for AI coding agents.

## The IntelliJ Plugin

Running OFT during development should be as seamless as possible. While we have had build integration for a long time via our [Maven](https://github.com/itsallcode/openfasttrace-maven-plugin) and [Gradle](https://github.com/itsallcode/openfasttrace-gradle) plugins, many developers still found themselves dropping to the command line to check tracing results. That is fine for a final check before a commit, but during active development, it can interrupt your flow.

The [IntelliJ plugin](https://github.com/itsallcode/openfasttrace-intellij-plugin) takes that friction out of the equation. You get the tracing results right in the IDE while you are editing, complementing the existing build-time checks.

Head over to the repository for setup instructions:

https://github.com/itsallcode/openfasttrace-intellij-plugin

## Coding Agent Skills

If you are working with an AI coding agent — and I suspect a growing number of us are — you have probably noticed that they need quite a bit of hand-holding when it comes to project-specific conventions. Explaining what a `dsn~some-feature~2` tag means every time you start a new session gets old fast.

We added skill files to the OFT repository under [`.agents/skills`](https://github.com/itsallcode/openfasttrace/tree/main/.agents/skills). These are structured descriptions of OFT's specification item format, tracing conventions, and reverse-engineering capabilities that an AI agent can pick up as context. Think of it less as "AI magic" and more as a reference sheet you hand to a new team member — except the team member happens to be an LLM.

The practical effect is twofold:
1. **Core Tracing Knowledge**: The agent can read and write spec items, understands the artifact type hierarchy, and knows how coverage tags work without you having to explain it from scratch.
2. **Reverse Engineering**: With the [`openfasttrace-reverse-specs`](https://github.com/itsallcode/openfasttrace/tree/main/.agents/skills/openfasttrace-reverse-specs) skill, the agent can even help you bootstrap your tracing. It can analyze your existing user guides, code, and tests to infer and draft missing system requirements and design specifications, making it much easier to add traceability to an existing project.

## Convenience and Saving Time

These additions boil down to the same thing: reducing friction. OFT is only useful if people actually run it, and the less ceremony involved, the more likely that happens. Whether you are using the build plugins, the command line, or the new IDE integration, the goal is to have tracing integrated into the places where developers actually spend their time. Adding the AI chat window as another interface for OFT just removes one more excuse to skip it.

If you try either of them and run into issues, file a bug. Pull requests are welcome too.
