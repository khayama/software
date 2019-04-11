---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 从 R1Soft 映像复原服务器
{: #restoring-your-server-from-an-r1soft-image}

使用此过程可完成复原到公共或专用 {{site.data.keyword.BluVirtServers_full}} 或 {{site.data.keyword.BluBareMetServers_full}} 的过程。如果服务器发生导致数据或操作系统受损的故障，请使用此过程。此过程将复原已备份的所有文件系统块（包括操作系统和未从备份中排除的任何文件）。

如果目标是复原一部分文件，那么不要使用此过程。要仅复原文件，请参阅 [R1Soft Wiki](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}。

## 复原虚拟设备
{: #restoring-your-virtual-device}

1. 在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中单击您想要复原的设备。
2. 单击**操作**菜单，并选择**从映像引导**，您将获得私有映像的列表。
3. 从菜单中选择**公共映像**。
4. 针对您的 R1Soft 服务器版本 (serverbackup-centos-bootcd-agent.iso) 选择相应的 R1Soft 代理程序引导映像，并单击右侧的**从此映像引导**链接。
5. 从要复原的服务器的**设备详细信息**页面，单击**操作** > **KVM 控制台**。
6. 控制台正常运行并且映像引导后，您将看到 Debian 引导装入程序屏幕及一些选项。按 Enter 键以使用缺省选项进行引导。
7. 引导操作系统之后，键入 `netconfig` 并按 **Enter** 键。
8. 选择**是**以配置联网。
9. 在控制门户网站中，输入设备详细信息中的联网配置详细信息。
10. 当提示您重新启动联网时，选择**是**。
11. （可选）键入 `passed root` 以设置 SSH 登录的 root 用户密码，键入 service ssh start 以允许 SSH 登录。如果您的 KVM 控制台响应缓慢，此步骤可能很有用。
12. 键入 `service cdp-agent restart`（如果 Tivoli Continuous Data Protection for Files 代理程序尚未运行，此命令会将其启动）。

## 复原裸机设备
{: #restoring-your-bare-metal-device}

1. 在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中开具凭证，请求在 **R1Soft 裸机复原模式**下引导裸机服务器。
2. 使用要复原的服务器的**设备详细信息**页面，登录到 **IPMI KVM 控制台**。
3. 控制台正常运行并且映像引导后，您将看到 Debian 引导装入程序屏幕及一些选项。按 Enter 键以使用缺省选项进行引导。
4. 引导操作系统之后，键入 `netconfig` 并按 **Enter** 键。
5. 选择**是**以配置联网。
6. 在控制门户网站中，输入设备详细信息中的联网配置详细信息。
7. 当提示您重新启动联网时，选择**是**。
8. （可选）键入 `passed root` 以设置 SSH 登录的 root 用户密码，键入 service ssh start 以允许 SSH 登录。如果您的 KVM 控制台响应缓慢，此步骤可能很有用。
9. 键入 `service cdp-agent restart`（如果 Tivoli Continuous Data Protection for Files 代理程序尚未运行，此命令会将其启动）。

## 选择 R1Soft 服务器以及其他复原参数和选项
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

请参阅[执行裸机复原](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)的 R1Soft 文档。
您需要选择要复原的服务器，并选择文件系统、分区表以及其他复原选项。
