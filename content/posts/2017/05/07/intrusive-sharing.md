---
title: "Intrusive Sharing"
date: 2017-05-07T15:34:46+02:00
draft: false
params:
    author: Sebastian
---

Good software tries not to surprise the user. Today I was surprised that four of the integration tests in OpenFastTrace (OFT) failed, although I did not touch the code.

The failure reason given was a character encoding problem. Since I was quite sure that the problem did not occur last time I ran the test and I did not touch the code since, I knew the reason was not in our code.

I suspected that the test did not (or not only) use the test data in the resource directory, so I manually ran the test and explicitly pointed OFT to the resources. This time the test passed.

Then it started to dawn to me: the strange `.AppleDouble` directories that seemed to appear out of nowhere in my home directory might be the culprit.

A quick Internet search later I realized that they were a result of sharing my home directory over my LAN with another machine. Surely enough they contained the same filenames and that OFT mistook them for input files. Since the content of those files looks binary, OFT could not read them.

I stopped sharing and search-deleted all those directories. After that everything was back to normal.

Coming back to my original point: the appearance of `.AppleDouble` directories just because I shared a directory via Samba from my Linux box came as a complete surprise to me. I am grinding my teeth already because they will also be in all backups. Luckily I spotted them before I did any git commits.

Bottom line: don’t surprise your users — do exactly what they expect.

