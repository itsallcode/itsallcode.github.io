---
title: "OpenFastTrace 4.5.0 released: 10 years of OFT"
date: 2026-06-06
draft: false
author: "Itsallcode Blog Agent"
---

We are pleased to announce the release of OpenFastTrace 4.5.0. This release is particularly special as it marks the 10th anniversary of OpenFastTrace on GitHub.

## New Mastodon Presence

As part of our community outreach, OpenFastTrace is now on Mastodon. You can follow us for updates and discussions at [@OpenFastTrace@mastodon.social](https://mastodon.social/@OpenFastTrace).

## CLI Improvements

The command-line interface has been improved with standard help options. You can now use `-h` or `--help` to display usage information. Additionally, the help message now includes the version of OpenFastTrace, making it easier to verify the environment you are running in.

## Importer Enhancements

### FXML Support
The tag importer now supports `FXML` files. This allows for better integration with JavaFX projects where requirements might be referenced within UI definitions.

### Importer Delegation and Priority
We have improved how OpenFastTrace handles file extensions. Multiple importers can now be registered for the same extension, governed by a priority system. The first importer that claims it can handle a specific file is used. 

A key benefit is seen with the XML importer: it now uses its "peek" function to detect if an XML file actually contains SpecObjects. If it doesn't, it can decline handling the file, allowing the tag importer to process it instead.

## Robustness and Developer Experience

### Better Error Messages for Importers
When using OpenFastTrace as a library, particularly with custom classloaders, it was previously sometimes difficult to diagnose why an importer factory could not be found. We have added more descriptive exceptions that explain the likely cause when an importer factory loader fails.

### Guidance for AI Agents
Reflecting the modern development landscape, we have added an `AGENTS.md` file to the repository. This file serves as a central entry point for LLM-based agents, providing them with the necessary context and rules to interact effectively with the project.

## Summary

This release combines a decade of stability with modern refinements. For a full list of changes, please refer to the [official release notes](https://github.com/itsallcode/openfasttrace/releases/tag/4.5.0).
