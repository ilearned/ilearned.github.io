---
layout: post
title: Cron and it's rules
date: 2017-9-14
author: sabino
---

Today we had a problem with one of our servers.

The server runs some cron jobs at night but something went wrong and no jobs ran at all.
Turns out that the cron file was set wrong. The hour was set to **45** making the cron unrunnable:
```
0 45 * * *        root exec_job.sh

```

Fixed to this:
```
45 0 * * *        root exec_job.sh

```
