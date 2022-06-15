---
layout:   post
title:    Apple from Catalina to Monterey upgrade
author:   flex
category: 2022
tags:     [compúter, Apple, Catalina, Monterey, English]
comments: false

headerSIZE:       '0px'
headerBGimagex:   ''
headerBGposition: 'background-position: center;'

contentLEFT: '<p style="padding: 20px;"><img src="images/Apple_MBP16Touch-Silver-2019_nobg.png"></p>'
---

Knowing that I'm going to lose my current daily job, the next thing I planed to do on our home computer infrastructure after the [DSM 7 upgrade](Synology_DSM7_upgrade) was to also upgrade the macOS operating system on my MacBook Pro from Catalina to the latest version of Monterey as soon as I could.

## Starting point

Here's how it happened:

<pre class="terminal">
07:13:18 Wed Jun 15 [flex@MBP16:[~/Downloads] [0]
$ <strong>df -h</strong>
Filesystem      Size   Used  Avail Capacity     iused      ifree %iused  Mounted on
/dev/disk1s1   466Gi   11Gi   36Gi    23%      488454 4881964426    0%   /
devfs          379Ki  379Ki    0Bi   100%        1311          0  100%   /dev
/dev/disk1s2   466Gi  414Gi   36Gi    93%     4155629 4878297251    0%   /System/Volumes/Data
/dev/disk1s5   466Gi  4.0Gi   36Gi    11%           4 4882452876    0%   /private/var/vm
map auto_home    0Bi    0Bi    0Bi   100%           0          0  100%   /System/Volumes/Data/home
drivefs        466Gi  431Gi   34Gi    93% 18446744069414584742 4294967295 4381649422663796736%   /Volumes/GoogleDrive

07:15:08 Wed Jun 15 [flex@MBP16:[~/Downloads] [0]
</pre>

<img src="images/Screenshot_2022-06-15_at_7.14.52.png">

<hr>

## Checklist after the upgrade process:

- VPN CHECK: ✅
- VMware Fusion upgrade + CHECK: ✅
- brew upgrade + CHECK: ✅
- Time Machine backup CHECK: ✅
- Apple Xcode upgrade + CHECK: ✅
- so far incompatible Apps upgrade + CHECK: ✅
- printer CHECK: ✅
- Steam CHECK: ✅

After a little more than an hour, all the expected functions are working fine again. 🤞