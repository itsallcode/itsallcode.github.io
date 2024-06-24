---
title: "New Project Structure for OpenFastTrace"
date: 2024-06-23T20:53:01+02:00
draft: false
params:
    author: Christoph
---

We are happy to announce the latest release 2.3.5 of OpenFastTrace.

In this release we split the source code into sub-modules for api, importers, exporters etc. This has some advantages:

- The dependencies of plugins are now enforced by the compiler. It is not possible that e.g. the specobject exporter depends on the specobject importer.
- Developers who want to extend OFT with custom importers or exporters only need add a dependency for the stable API module without all the other internal code.
- A stable API simplifies internal refactoring of the code because third party plugins only depend on the API module. All other modules are internal and can be changed without breaking third party plugins.

I also should mention some caveats. Building the project now takes around 3 minutes, deployment to JCenter even 9 minutes.

Currently the API module contains some plugin specific classes for configuration. We plan to clean this up in one of the next releases.

To make it easier for users and third party developers we also maintain a [changelog](https://github.com/itsallcode/openfasttrace/blob/develop/doc/CHANGELOG.md) with all the important changes in each release. The changelog follows the structure of [Keep a changelog](https://keepachangelog.com/en/1.0.0/).

Of course we also released version 0.6.2 of the [gradle plugin](https://github.com/itsallcode/openfasttrace-gradle) which uses the new OpenFastTrace 2.3.5. The gradle plugin now also contains a [changelog](https://github.com/itsallcode/openfasttrace-gradle/blob/develop/CHANGELOG.md).

Please upgrade to the new versions and share your experience.

Happy Tracing!