---
title: "How I Taught My Computer To Cater to My Wife's iPhone (With the help of the Unix Philosophy)"
date: 2025-03-31
author: "Sebastian"
---

Emphraim Kishon always called his wife the "best wife of all of them". We have that in common. What he probably did not have was one with an iPhone and a Linux laptop.

She loves her adorable iPhone mini. But her current photo management software, Shotwell, was putting quite a damper on the photo-syncing operation. A sigh emerged from her one evening, "Can't this be automatic?"

Being a Linux nerd, and a good husband indeed, it was time to use some good old Unix philosophy, roll up the sleeves and get some Bash magic working.

> Rule of Modularity: Write simple parts connected by clean interfaces.

Check.

The quartet of software utilities that I used were `iFuse`, `rsync`, `ImageMagick`, and `Bash`.

> Rule of Clarity: Clarity is better than cleverness.

OK, that one is admittedly tricky. Writing clean Bash code is like trying to create a sculpture out of half-dried vomit. Sure it will hold together, but it's not very pretty.

> Rule of Composition: Design programs to be connected to other programs.

Another big checkmark. This is where the combination of CLI and Bash scripting really shines.

> Rule of Separation: Separate policy from mechanism; separate interfaces from engines.

In a 125 lines script there is not so much "engine" going on. Still the parts are separated into functions by concern.

> Rule of Simplicity: Design for simplicity; add complexity only where you must.

I resisted the urge to make the script configurable and opted for auto-magick where possible. The target user profile does not care about customization so much as for full automation.

> Rule of Parsimony: Write a big program only when it is clear by demonstration that nothing else will do.

No frills, no unnecessary features. Mount iPhone, incrementally sync photos, unmount iPhone then incrementally turn the HEIC photos into JPG. Done.

> Rule of Transparency: Design for visibility to make inspection and debugging easier.

What should I say? It's a Bash script. At least it has meaningful log output.

> Rule of Robustness: Robustness is the child of transparency and simplicity.

Well, I resisted the urge to over-complicate things. I let `rsync` do its job. When I found out that `rsync` could not produce an overall progress bar, I tried some variants with `pv`, but they all added complexity and cost a lot of performance, so I sighed and lived without indicator.

> Rule of Representation: Fold knowledge into data so program logic can be stupid and robust.

Not much data structure going on in this use case. Sorry.

> Rule of Least Surprise: In interface design, always do the least surprising thing.

Both the user interface and the functions are designed to be easy to understand, free of unexpected side effects.

> Rule of Silence: When a program has nothing surprising to say, it should say nothing.

That is my favorite rule. And, the one a lot of programmers seem to have big problems with. Don't flood your logs with trivialities. Keep the output and logs lean and users might actually read them!

> Rule of Repair: When you must fail, fail noisily and as soon as possible.

I built fail safes in where applicable for everything else there is an appropriate non-zero exit code.

> Rule of Economy: Programmer time is expensive; conserve it in preference to machine time.

I had my trusty AI coding companion running in IDEA. As always, the results varied from "wow, that's neat" to "I can see from a mile everything that will go wrong with this code". Ultimately, I was a bit faster than handwriting all the code. Mainly because I can't remember all the horrible Bash syntax for the life of me.

That being said, I actually optimized the script for runtime efficiency. Incremental and fast automation was the whole point of the endeavor.

> Rule of Extensibility: Design for the future, because it will be here sooner than you think.

I put this script on GitHub with user requirements, design and user guide. All the while hoping that on one will ask me to add new features. Let's see how that goes.

https://github.com/itsallcode/linux-iphone-photo-sync

Pull requests on the other hand are welcome. :-)

My wife's happy, I’m relieved, and she's at peace with her Linux machine again. And there's nothing more satisfying than that.