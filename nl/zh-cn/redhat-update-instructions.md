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



# RedHat 更新信息

IBM 为 RedHat 环境提供免费的操作系统和软件更新服务。

IBM 的所有更新服务都具有以下特点：
* 更新流量的路由从服务器开始（经过专用 VLAN），到达专用服务网络
* 更新流量是无限专用网络带宽的一部分，不会减少公共带宽分配。
* 更新速度比直接从供应商更新快（按需提供升级端口速度）
* 即使在全球大量进行重要更新的日子，更新也随时可用。
* 在紧急情况下，可以关闭公共端口，但仍允许通过专用网络进行更新。
* 服务器经过预先配置，可在部署时自动更新，也可按需进行手动更新。

IBM 更新服务器在专用服务网络中的位置标识如下：

|数据中心|服务主机地址|
|---|---|
|阿姆斯特丹|rhnproxyams0101.service.softlayer.com|
|达拉斯|rhnproxy101.service.softlayer.com|
|休斯顿|rhnproxy421.service.softlayer.com|
|圣何塞|rhnproxy501.service.softlayer.com|
|西雅图|rhnproxy201.service.softlayer.com|
|新加坡|rhnproxysng0101.service.softlayer.com|
|华盛顿特区|rhnproxy301.service.softlayer.com|

在生产服务器环境中安装 kernel 或服务包升级之前，总是先进行测试。在常见问题或客户 Web 门户网站的驱动程序部分中，可以找到关于特定硬件、操作系统和已部署的应用程序的技术信息。IBM 测试 kernel 和服务包升级并发布相关信息（包括驱动程序）以帮助您完成升级过程。

## RHN 预订

对于 RedHat 操作系统，IBM 提供 RedHat 网络卫星服务器用于安装关键和非关键安全更新。

SoftLayer 上的 RedHat 网络包括 RHN 卫星和代理服务器。在供应 RedHat 服务器时，会使用相应的代理服务器自动向 IBM RHN 卫星服务器注册。通过此注册，您可以在服务器本地使用 **up2date** 命令，并在专用服务网络中拉取更新。

为了保证企业服务质量，利用合适的变更管理方法，在缺省情况下，RedHat 操作系统服务器配置为跳过 kernel 更新。为了确保系统稳定性，请在完成回归测试后手动执行 kernel 升级。IBM 使用最前沿的硬件技术，因此要求有稳定的 kernel 版本来实现良好的性能。
