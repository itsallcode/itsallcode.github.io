---
title: "On Refactoring an Hidden Technical Dept"
date: 2018-10-30T20:26:53+02:00
draft: true
params:
    author: Sebastian
---

Can you accumulate technical dept, even if you regularly clean up your sources meticulously? A short while ago I would have said that this is possible but unlikely. That was before I started taking on the migration of all of [OpenFastTrace](https://github.com/itsallcode/openfasttrace)‘s unit tests from [JUnit4](https://junit.org/junit4/) to [JUnit5](https://junit.org/junit5/).

Like most non-trivial projects OFT accumulated quite a number of unit tests over the years and although it was always the plan to move to JUnit5 some day, they were all written for JUnit4. With the arrival of [OFT 2.0.0](https://github.com/itsallcode/openfasttrace/releases/tag/2.0.0) — which also was a major refactoring endeavor — I felt now would be the perfect time to make that migration happen. After all I was in the refactoring flow.

## To rule them all…

Shouldn’t take long, right? Boy was I mistaken. The one thing I completely underestimated was how dependent many of our integration tests were on JUnit rules like Stefan Birkner’s “[JUnit System Rules](https://stefanbirkner.github.io/system-rules/)“. While getting the dependencies right in the Maven POM was only slightly harder than anticipated, migrating all parts where rules were used took way longer. I quickly found a replacement for the “[Temporary Folder API](https://junit.org/junit4/javadoc/4.12/org/junit/rules/TemporaryFolder.html)“: JUnit Pioneer’s “[TempDirectory Extension](https://junit-pioneer.org/docs/temp-directory/)“.

## Homebrew extensions

I did not find a suitable replacement of the JUnit System Rules though, so I decided to take matters into my own hands and create the “[JUnit5 System Extensions](https://github.com/itsallcode/junit5-system-extensions)“. At the time of this writing they cover `System.out`, `System.err` and `System.exit` assertions.

It was a good if also painful practice for writing JUnit5 extensions. Only later I realized that Stefan seems to have started a port of his rules, but it did not look finished to me. Anyway this gave me the opportunity to dive deeper into the JUnit 5 life cycle.

## Run baby, run baby, run baby, run!

Christoph was the one who pointed out to me, that the tests I wrote only ran in Eclipse but were silently skipped when triggered by Maven. The culprit was an older version of the [Surefire plugin for Maven](https://maven.apache.org/surefire/maven-surefire-plugin/). Turns out that you need 2.22.1.

## Simply beautiful

Even though the migration turned out to be much more of a pain than anticipated, especially integration tests and test that check for exceptions looks much nicer thanks to JUnit5. It’s about time for this upgrade, and I am sure we won’t regret this when writing new tests.