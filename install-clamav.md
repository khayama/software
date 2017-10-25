---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Installing ClamAV

Use this procedure to install ClamAV.

1. Log into WHM on https://x.x.x.x:2087 (replace x.x.x.x with your server IP)
2. Click on the cPanel icon on the far right side of the screen.
3. Click on the **Manage Plugins** icon to view the list of cPanel plugins.
4. On the **Addon Modules** page, locate **clamavconnector**. Enable **Install and keep Updated** and click **Save** at the end of the page.
The install will take around twenty minutes to complete.

**Notes** 
The lib version checking is disabled by default. However, the server should have zlib 1.2.2 or greater installed.

Licensing is the most common reason that the ClamAV installation fails. The clamav addon is free, however you need to register as a professional license. Refer to https://www.clamav.net/ for more information. After correctly registering your license, return to step 4, uninstall, and reinstall clamavconnector.
