---
title: "Recovering Jpgs From a Broken File System on a Flash Disk"
date: 2018-11-25T20:36:13+02:00
draft: true
params:
    author: Sebastian
---

Today I want to thank the author of [recoverjpg](http://manpages.ubuntu.com/manpages/bionic/man1/recoverjpeg.1.html), Samuel Tardieu. This tool is proof that “do one thing, do it well” results in the most useful software.

A family member brought an SD card back from a vacation trip abroad and the filesystem broke when she plugged the card into her Mac. Needless to say that this is not the usual scenario, because many times before everything went well.

Having (partially) restored broken filesystems or at least files, I knew the drill. First rule: don’t attempt to restore on the volume that failed directly. So I created a 1:1 copy of the broken filesystem with the `dd` command that comes with any Linux installation.

Attempts to restore the filesystem itself failed. The structure was so broken, that `fsck.vfat` did not succeed. At that point I already pictured myself trying to repair parts with a hex editor. But then I found `recoverjpg` and it looks for typical structures that look like a JPG file without caring about the filesystem itself too much. That did the trick.

Thanks Samuel!