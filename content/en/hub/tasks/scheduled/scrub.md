---
title: "Configuring Scrub Tasks"
description: "A how-to for configuring scrub tasks."
---

A scrub is the process of ZFS scanning through the data on a pool. Scrubs help
to identify data integrity problems, detect silent data corruptions caused by
transient hardware issues, and provide early alerts of impending disk failures.
TrueNAS makes it easy to schedule automatic scrubs. In order to create scrub
tasks, you must first
<a href="/hub/initial-setup/storage/pools/">create a pool</a>.

By default, TrueNAS creates a scrub task when new pool is created. The scrub
task default schedule is set to run every Sunday at 12:00 AM. To edit the
default scrub, go to **Tasks > Scrub Tasks** and click
<i class="fas fa-ellipsis-v"></i> to edit the task. Otherwise, proceed to
creating a new scrub task.

## Create Scrub Task

To create a scrub task for a pool, go to **Tasks > Scrub Tasks** and click
*ADD*. First, select a pool for the scrub task. Enter a number for the
*Threshhold days*. The *Threshhold days* are the number of days before a completed
scrub is allowed to run again. This controls the task schedule. For example,
scheduling a scrub to run daily and setting *Threshold days* to 7 means the
scrub attempts to run daily. When the scrub is successful, it continues to
check daily but does not run again until seven days have elapsed. Using a
multiple of seven ensures the scrub always occurs on the same weekday. An
optional description can be given. Select a schedule for the scrub task.
If a custom schedule is desired, select *Custom* and fill out the custom
scheduler to meet your needs. The custom scheduler can accept standard
[cron input strings](https://www.freebsd.org/cgi/man.cgi?query=crontab&sektion=5)
for the *Minutes*, *Hours*, and *Days*. Unsetting *Enabled* only
keeps the task from automatically running. You can still save the scrub task and
enable it later.
