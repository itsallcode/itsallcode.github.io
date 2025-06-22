---
title: "4.2.0, the release to Maven central that drove us mad"
date: "2025-06-22T14:26:00+01:00"
draft: false
author: Sebastian
---

Although the feature set change for version 4.2.0 is not that big, that was the most painful release we had sofar.

To understand the rant that is about to follow, one must know that this year Sonatype changed the way releases are deployed to the Central repository (formerly known as Maven Central).

Nothing wrong with doing that per se, since the old mechanism was quite clunky, and I imagine, also caused some trouble on Sonatype's side. The announcement came around the end of 2024, and the deadline for the migration was the last of May 2025. So far so fair.

Trouble starts with the fact that the new Maven plugin for the deployment has a zero in front, which is not what you would expect when you are supposed to use it for production. At the time of the release we had 0.7.0, which had a lot of its kinks already smoothed out, but the documentation was quite thin.

Especially, it was not clear how the new plugin played together with the existing `maven-deploy-plugin`. And let me tell you, the setup is not straight forward.

To give you an example, with the Maven Central deployment plugin it should be clear what the server URL of the central repository is. That could very well be hard-coded into the plugin as a default value. Unfortunately, while the `maven-deploy-plugin` doest not do the actual deployment anymore, it still requires configuring the repo URLs.

To make things worse, OFT is a pretty complicated multi-module Maven project, where most modules should be on the Central repository but at least one — namely the `testutils` — does not belong there.

Excluding that one module turned out to be super finicky. Like jumping through a set of burning hoops while being blindfolded and having frozen turkey being fired at you from a dozen catapults.

It took the combined efforts of Christoph and me, and a lot of exploring dead ends until we finally got it right.  If you are interested in the solution, check [PR #464](https://github.com/itsallcode/openfasttrace/pull/464/files).

I added a section about the [module structure](https://github.com/itsallcode/openfasttrace/blob/main/doc/developer_guide.md#module-overview) and what that means for the deployment to the developer guide, and Christoph contributed a section about [debugging the new Central deployment](https://github.com/itsallcode/openfasttrace/blob/main/doc/developer_guide.md#debugging-maven-central-deployment.

In total, that release took us around a month until we had it ready. We improved a lot of documentation, updated dependencies, added support for new JavaScript extensions and added a feature that allows ignoring specification items inside Markdown code blocks. In the course of that last feature, we also added markers `oft:on|off` that allow excluding OFT parsing for selected text passages.

For more information, please check the [release letter of 4.2.0](https://github.com/itsallcode/openfasttrace/releases/tag/4.2.0).