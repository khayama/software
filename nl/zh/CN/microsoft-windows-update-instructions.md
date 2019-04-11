---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

keywords: Microsoft Windows Update, software update services

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Microsoft Windows 更新信息
{: #microsoft-windows-update-information}

IBM 为 Microsoft Windows 服务器环境提供免费的操作系统和软件更新服务。

{{site.data.keyword.Bluemix_notm}} 的所有更新服务都共享以下功能：
* 更新流量的路由从服务器开始（经过专用 VLAN），到达专用服务网络
* 更新流量是无限专用网络带宽的一部分。此流量不降低公共带宽分配。
* 更新速度比直接从供应商更新快（按需提供升级端口速度）
* 即使在全球大量进行重要更新的日子，更新也随时可用。
* 在紧急情况下，可以关闭公共端口，但仍允许通过专用网络进行更新。
* 服务器经过预先配置，可在部署时自动更新，也可按需进行手动更新。


{{site.data.keyword.Bluemix_notm}} 更新服务器位于专用服务网络上，带有以下位置标识。

Microsoft：**wsus01.service.softlayer.com**

在生产服务器环境中安装内核或服务包升级之前，总是先进行测试。在控制门户网站内的常见问题或驱动程序部分中，可以找到与 IBM 部署的特定硬件、操作系统和应用程序相关的技术信息。IBM 持续测试内核和服务包升级并发布相关信息（包括驱动程序）以帮助完成升级过程。


## Windows Server Update Services (WSUS) 
{: #wsus-windows-server-update-services}

在大多数情况下，Microsoft Windows 服务器自动从本地 Windows Server Update Services (WSUS) 服务器中拉取更新。但是，如果使用启用 cloud-init 的映像供应服务器，那么您可能需要手动更新 Windows 注册表以使用本地
{{site.data.keyword.cloud_notm}} Windows Server Update Services (WSUS) 服务器，而不是缺省的 Microsoft WSUS 服务器。

如果您订购的虚拟服务器使用 Windows Server 操作系统，没有任何附加组件（例如更多软件、供应后脚本或高级监视），那么您的服务器可能是使用 cloud-init 映像供应的。有关更新注册表指向
{{site.data.keyword.cloud_notm}} WSUS 服务器的更多信息，请参阅[更新实例以使用本地 WSUS 服务器](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server)。

对于 Microsoft Windows 操作系统，缺省情况下，服务器配置为有补丁时立即下载和安装。如果需要重新启动，服务器会自动重新启动。完成这些更新是为了针对重大漏洞保护服务器。如果您更愿意以不同的方式安排更新，那么可以通过控制面板中的 **Windows 更新**功能部件来更改更新安排。
