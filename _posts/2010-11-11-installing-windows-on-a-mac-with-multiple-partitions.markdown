---
comments: true
date: 2010-11-11 22:33:02
layout: post
slug: installing-windows-on-a-mac-with-multiple-partitions
title: Installing Windows on a Mac with Multiple Partitions
wordpress_id: 30
categories:
- Computing
tags:
- apple
- computing
- linkedin
- mac
- tutorial
---

### Update: July 2011


Recently the new version of Mac OS X, Lion, was released to the public. This version features a new recovery partition which cannot be setup if you have multiple HFS partitions as described in this tutorial. I will look into this in August, but for now, be cautious if you want to upgrade to Lion.


### Prelude


When I ordered my iMac I chose the 2TB hard disk option, planning to contain my entire photo dataset and my digital music and TV recordings on this main drive. For the past few years I've always separated my data from applications and settings using partitions. On the Windows side this has made reinstalling the operating system and restoring from backups far easier. So naturally when I received my iMac I immediately created a Data volume and started copying in my photos and media.


### The problem


Fast forward a few weeks, and I decided to try installing Windows to try the few games I do play on my shiny new quad core computer. To my dismay, the Boot Camp Assistant immediately said I had to delete my extra partition. That would not do - I could not see any reason why I should not have multiple HFS+ partitions as well as an NTFS partition for Windows. It turns out that the GPT scheme that Apple use (and increasingly many PCs will start using as hard disks grow above 2TB) does not have a limit on the number of primary partitions, and does not support extended ("logical") partitions. The system used by older PCs uses the MBR (Master Boot Record) scheme which allows 4 primary partitions only. Boot Camp Assistant sets the partition layout to have 3 partitions - a compulsory EFI partition, the Macintosh HD partition, and the Bootcamp partition, which is set up with a hybrid GPT/MBR scheme that allows Windows versions later than XP to boot. Since you are forced to use the MBR scheme, there is room for 1 more primary partition. Some may wish to use it as a shared FAT32 volume, but that is less practical when you have large files. I already used this slot for my Mac data (which is at least readable in Windows), so there was no need to do anything with it other than shrink it to allow room for a further partition.<!-- more -->


### How I then installed Windows





	
  1. The first step in my case was to resize the large Data partition to make room for my new NTFS partition. I used Apple's Disk Utility, which was not as intuitive as I expected. To resize a partition, you need to select the disk drive itself, then go to the "Partition" tab. There you can select a partition and either drag its corner to resize, or type in a new size after selecting it. I resized my data partition to leave 80GB for Windows 7 (which is more than enough when it isn't the primary OS on the machine).

	
  2. I then created a new partition in the empty space for Windows itself. To do this, you click a little "+" and then choose to format as MS_DOS (FAT). I wish Apple would natively support NTFS writing and formatting, but there is [Tuxera](http://www.tuxera.com/) for that. Make sure you label the partition to aid finding it in the Windows installer.

	
  3. Next, I had to prepare the MBR record for the disk so that Windows would 'see' it. The most important tool in the whole process is [rEFIt](http://refit.sourceforge.net/). This tool can be installed on a USB stick or your main Mac partition. I chose the former, and rebooted, holding down Option to bring up the boot selector. Once in rEFIt, the shell can be used (run gptsync.efi) or choose the partition editor. This basically sets the MBR up so Windows will be happy.

	
  4. At this point, it's time to install Windows. I tried booting a USB stick that normally installs my custom Windows 7 ISO, but that didn't work on the Mac. I tried a DVD of the same image, and that worked fine. The only real manual step was to format the partition I had created as NTFS.

	
  5. Once Windows was installed (note that when the installer reboots you need to hold down Option to allow you to boot from the Windows partition) and hopefully working, the final step is to insert the Snow Leopard installation DVD to install drivers (to enable reading of HFS partitions amongst other useful things like graphics drivers). I used the DVD that came with my iMac (so it's reasonably up to date (July 2010)), and if you have an older version then there is an updated download from the Apple site.

	
  6. That was basically it. Windows 7 is awesome on such a big screen, but I still prefer OS X for getting things done (excluding gaming and .NET programming).


I hope Google indexes this and somebody else finds it useful ;).
