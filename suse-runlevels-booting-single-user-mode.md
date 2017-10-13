---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# SUSE Runlevels - Booting into Single User Mode

If you require Single User mode to correct an issue with your server you will need to complete the following procedure: 

1. Login to your VPN.
2. Login to KVM/SOL
3. Reboot the  server
4. When GRUB loads, select the kernel you wish to boot and press the `e` key to edit the line. You can not use `a` to append to the kernel line as can be done in many other distributed versions.
5. Append the runlevel to the end of the kernel line.
6. Press enter.
7. When the kernal configuration of GRUB opens, press `b` to boot.

Following is a list of run levels:

|Runlevel|Description|
|---|---|
|0|System halt|
|S|**Single user mode** with US keyboard mapping|
|1|**Single user mode**|
|2|**Local multiuser mode** without remote network (e.g., NFS)|
|3|**Full multiuser mode** with network|
|4|Not used|
|5|**Full multiuser mode** (not to be used as our installations do not include X)|
|6|System reboot|
