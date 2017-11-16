---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Microsoft Windows 更新信息
IBM 为 Microsoft Windows 服务器环境提供免费的操作系统和软件更新服务。

SoftLayer 的所有更新服务都具有以下特点：
* 更新流量的路由从服务器开始，经过专用 VLAN，到达专用服务网络。
* 更新流量是无限专用网络带宽的一部分，不会减少公共带宽分配。
* 更新速度比直接从供应商更新快（按需提供升级端口速度）
* 即使在全球大量进行重要更新的日子，更新也随时可用。
* 在紧急情况下，可以关闭公共端口，但仍允许通过专用网络进行更新。
* 服务器经过预先配置，可在部署时自动更新，也可按需进行手动更新。


SoftLayer 更新服务器在专用服务网络中的位置标识如下。

Microsoft：**wsus01.service.softlayer.com**

在生产服务器环境中安装 kernel 或服务包升级之前，总是先进行测试。在常见问题或客户 Web 门户网站的驱动程序部分中，可以找到关于特定硬件、操作系统和 IBM 部署的应用程序的技术信息。IBM 工程师不断测试 kernel 和服务包升级并发布相关信息（包括驱动程序）以帮助您完成升级过程。


## WSUS - Windows 服务器更新服务

Microsoft Windows 服务器自动从本地 Windows 服务器更新服务 (WSUS) 服务器中拉取更新。

对于 Microsoft Windows 操作系统，缺省情况下，服务器配置为有补丁时立即下载和安装。如有需要，服务器会自动重新启动。安装这些更新有助于保护服务器避免重大漏洞。如果您更愿意安排不同的更新计划，那么可以通过控制面板中的 **Windows 更新**功能部件来更改更新计划。
