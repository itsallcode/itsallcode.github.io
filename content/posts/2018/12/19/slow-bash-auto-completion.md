---
title: "Slow Bash Auto Completion"
date: 2018-12-19T20:47:08+02:00
draft: false
params:
    author: Sebastian
---

Today I found a nice [hint on a Cygwin forum on how to debug slow Bash auto-completion](http://www.cygwin.com/ml/cygwin/2010-07/msg00516.html):

```bash
set -vx
```

What that does is that it make all the steps visible that the completion uses to come to a result.  No you just have to look if one sticks out especially.
