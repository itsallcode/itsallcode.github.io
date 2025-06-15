---
title: "4.2.0, the release to Maven central that drove us mad"
date: "2025-06-15T15:14:00+01:00"
draft: false
author: Sebastian
---

To understand the rant that is about to follow, one must know that this year Sonatype changed the way releases are deployed to the Central repository (formerly known as Maven Central).

Nothing wrong with doing that per se, since the old mechanism was quite clunky and I imagine, also caused some trouble on Sonatype's side. The announcement came end of 2024, and the deadline for the migration was the last of May 2025. So far so fair.

Trouble starts with the fact that the new Maven plugin for the deployment has a zero in front, which is not what you would expect when you are supposed to use it for production. At the time of the release we had 0.7.0, which had a lot of its kinks already smoothed out, but the documentation was quite thin.

Especially, it was not clear how the new plugin played together with the existing `maven-deploy-plugin`. And let me tell you, the setup is not straight forward.

To make things worse, OFT is a pretty complicated multi-module Maven project, where most modules should be on the Central repository but at least one — namely the `testutils` — does not belong there.

Excluding that one module turned out to be super finicky. Like jumping through a set of burning hoops while being blindfolded and having frozen turkey being fired at you from a dozen catapults.

At the time I am writing this article, we still did not find a configuration that passes all Maven checks. It is a long and painful series of trial-and-error with long roundtrips.

Anyway, we will keep pushing through. Stay tuned.
