---
title: "Named vs. Numeric Requirement IDs"
date: 2018-07-06T20:02:12+02:00
draft: false
params:
    author: Sebastian
---

With every new project there will be a discussion whether requirement IDs should have a unique name or simply a numbering scheme.
<!--more-->

If you look at [OFT](https://github.com/itsallcode/openfasttrace)‘s [specification document](https://github.com/itsallcode/openfasttrace/blob/develop/doc/system_requirements.md), you will see that we chose named IDs. The reason in our case is quite simple: we use the ID as reference in OFT’s native specification format (aka. “requirement-enhanced Markdown”) and it is a lot simpler to understand the connections between the specification items in different artifact types if you can tell by the name what the requirement ID is about. It also helps debugging.

That being said there are major drawbacks with this approach:

1. You have to think of and type an ID for every requirement
2. In large collections of requirements you might need hierarchical ID parts to make the IDs unique (like `req~import.full-coverage-tag-format~1`)
3. Sometimes you pick bad names and are forced to decide whether to bulk-change all documents or live with the name
4. Some tools (like [Doors](https://www.ibm.com/us-en/marketplace/rational-doors) for example) enforce numeric IDs.

Bottom line: deciding between named and numeric IDs a task that you should think long and hard about before you start your project.

Good news is OFT supports both flavors.
