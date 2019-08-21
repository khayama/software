---
copyright:
  years: 2017, 2018
lastupdated: "2019-04-30"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Ordering software
{: #order-software}

{{site.data.keyword.BluSoftlayer_full}} has strategic relationships with vendors to provide month-to-month licenses on 32-bit and 64-bit compatible software.  
{:shortdesc}

When you order a device, you select the type of operating system and software for your device. You can add more software to your device within the {{site.data.keyword.slportal_full}} and change to another operating system by reloading the OS on your existing device. The IBM automated system provisions software onto your server by using best practice guidelines of each vendor to ensure maximum stability and availability.

See the following list of currently supported software: [Cloud server software ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

If you need software that is not currently supported, use your root access to the server to install and configure your own version of that software.  To return to a supported version on your device, reload the OS.

IBM includes instructions or considerations for using products in the {{site.data.keyword.BluSoftlayer_notm}} environment. For software documentation, see the documentation of the vendor who produces the software.

**Note:** Boot disk sizes vary by operating system:<br>  
Linux OS supports 25 GB and 100 GB.
Windows supports only 100 GB.

For more information about toggling between PV and HVM boot modes, see the following links:
* [Virtual guest supported boot modes ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Add boot mode option ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
