---
title: "Itsallcode gets a new blog"
date: 2024-06-23T14:58:47+02:00
draft: true
params:
    author: Sebastian
---
 Today I had a good opportunity to reflect on how I select software. Of course there are rational criteria like whether it is open source, has regular releases, gets good reviews and so on.

But then there is also the matter of taste.

<!--more-->

I simply can't bring myself to like anything that has to do with JavaScript. Try as I might, I can't. The whole dependency management in JS already gives me nightmares.

But I also wanted something that has a low entry barrier — after all I want to spend time on writing post — not on fiddling around with the infrastructure. So it had to be something that is available as a Debian package. This allows me to install it on my local machine and on the GitHub CI runner without any hassle — and, what's more important without installing from some random website.

After some quick research the choice was down to three candidates:

* Hugo (Go)
* Jekyll (Ruby)
* Pelican (Python)

I read a little bit about all of them, and I am sure, all would fit our need at itsallcode.org. But since I am a speed fanatic, the prospect of having near-instant feedback with Hugo was just too tempting not to try it out.

The installation went fairly uneventful, except for stumbling over a command in the Hugo documentation that I copied and didn't run. Quick internet search brought up the right variant luckily. And here we are, with a shiny new blog running on the [mini](https://themes.gohugo.io/themes/hugo-theme-cactus-plus/) theme. Just the way we like it.

