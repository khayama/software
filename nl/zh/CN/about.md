---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 关于软件
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} 与供应商具有战略合作伙伴关系，可提供 32 位和 64 位兼容软件的每月许可证。在订购设备时，选择设备的操作系统类型和软件。在 {{site.data.keyword.slportal_full}} 中，可以为设备添加更多软件，也可以通过在现有设备上重装操作系统，更改为其他操作系统。IBM 自动化系统使用每个供应商的最佳做法准则为服务器供应软件，因而可确保实现最高稳定性和可用性。

请参阅当前支持的软件的列表：[云服务器软件 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}。


如果当前不支持您需要的软件，请使用服务器根访问权来安装和配置您自己的该软件版本。要返回到设备上支持的版本，请重装操作系统。

IBM 包括在 {{site.data.keyword.BluSoftlayer_notm}} 环境中使用产品的指示信息或注意事项。有关软件文档，请参阅制作该软件的供应商的文档。

## IBM Cloud 虚拟服务器支持的操作系统
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

IBM Cloud 虚拟服务器支持以下操作系统。

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) 缺省为 PV 引导方式，但是您可以切换到 HVM 引导方式
- Ubuntu 16 (PV/HVM) 缺省为 PV 引导方式，但是您可以切换到 HVM 引导方式
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**注释：**引导磁盘的大小依据操作系统而有所不同：<br>  
Linux OS 支持 25 GB 和 100 GB。
Windows 仅支持 100 GB。

有关在 PV 和 HVM 引导方式之间切换的更多信息，请参阅以下链接：
* [虚拟访客支持的引导方式
![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [添加引导方式选项 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}

