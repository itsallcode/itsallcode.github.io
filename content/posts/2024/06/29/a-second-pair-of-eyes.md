---
title: "A Second pair of Eyes"
date: "2024-06-29T13:53:22+02:00"
draft: false
params:
    author: Sebastian 
---

Which developer does not know this situation: you debug like a mad person and form all sorts of crazy theories my the code in front of you does not work. Especially if you are new to a topic — like we are with our shiny new Hugo blog.

When I created the blog, I intended to keep the directory structure identical to the old WordPress blog:

    <domain>/<year>/<month>/<day>/<post>

All good and well, until I updated to a different theme, because the [minimal theme](https://github.com/calintat/minimal) by Calin Tataru that I originally chose — and which I still find stunningly beautiful in its clean simplicity — is apparently not maintained anymore. At least the last commit dates four years back.

But this story was not supposed to be about the challenges of supply chain management. That's a whole different story.

It's about your thoughts going in circles and ending up in a cargo cult[^1]. I had all sorts of crazy theories, why we only get the year 2018 in the index with the new theme. I even hypothesized that a kind of hidden cache in Hugo held pre-built pages.

Turns out, I couldn't have been more off. Christoph, whom I called for help debugged the current template and found out that Hugo has a concept of main sections. And 2018 simply got auto-picked because it had the most entries.

So here's the fix:

1. Put your posts under the top level directory `posts`
     ```
    <domain>/posts/<year>/<month>/<day>/<post>
    ```
2. List it in the configuration
   ```yaml
   params:
     mainSections: ['posts']

Big thanks to Christoph for saving my sanity.

[^1]: The term "[Cargo cult](https://en.wikipedia.org/wiki/Cargo_cult)" refers to the practice of primitive civilizations believing that one factually unconnected thing influences the other, because the mechanism behind the correlation is not understood by the observer. First appearance of the term "cargo cult" in print Norris Mervyn Bird, *Pacific Islands Monthly*, November 1945.