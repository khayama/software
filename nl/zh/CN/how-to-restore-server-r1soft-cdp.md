---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 使用 R1Soft Tivoli Continuous Data Protection for Files 复原服务器

使用此过程，在服务器发生导致数据或操作系统受损的故障时完成 {{site.data.keyword.BluSoftlayer_full}} 公共或私有虚拟服务器 (VSI) 的[裸机复原](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window}。

将复原已备份的所有文件系统块，包括操作系统和未从备份中排除的任何文件。如果您想要复原一部分文件，请不要遵循此流程。要仅复原文件，请参阅 [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}。

## 准备 R1Soft Tivoli Continuous Data Protection for Files 服务器

1. 打开浏览器窗口并登录到 R1Soft Tivoli Continuous Data Protection for Files 服务器（IP 和管理员密码在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中提供）。
2. 单击 R1Soft Tivoli Continuous Data Protection for Files 管理门户网站上的**恢复点**。
3. 选择您想要复原的**服务器**和您想要从中复原的**磁盘保险箱**。
4. 从恢复点列表中，找到您想要从中复原的点。
5. 单击**裸机复原**（盾牌图标）以启动**复原向导**。
6. 单击**复原向导**上的**下一步**。
7. 选择要复原的文件系统，并单击**下一步**。
8. 选择要复原到的主机。可以为原始主机或者其他主机。（注：此过程中的步骤恢复到同一个服务器。）
9. 单击**下一步**。
10. 选择要使用的存储配置（使用服务器上的存储配置或者根据备份选择一个配置）。
11. 如果您选择文件系统布局，那么选择您想要使用的**分区表**。
12. 将您的文件系统映射到正确的块设备（例如 C:\ = /dev/sda1）并单击**下一步**。
13. 选择复原选项（例如**复原后重新引导**、**复原后检查文件系统**），并单击**下一步**。
14. 验证选项，并单击**复原**或者返回更改复原选项。

此时将出现一个窗口，显示当前复原的状态

## 准备设备以进行复原

1. 打开浏览器窗口，并访问 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 单击**设备**、**设备列表**并选择要复原的设备。
3. 单击**操作**并选择**从映像引导**以显示私有映像的列表。
4. 从菜单中选择**公共映像**。
4. 针对您的 R1Soft 服务器版本 (*r1soft-cdp-bootcd-server-4.0.0.iso*) 选择相应的 R1Soft 代理程序引导映像，并且单击**从此映像引导**。
5. 从您正在复原的服务器的“设备详细信息”页面，单击**操作** > **KVM 控制台**。控制台正常运行并且映像启动后，您将看到 Debian 引导装入程序屏幕及一些选项。
6. 使用缺省选项，按 **Enter** 进行引导。
7. 启动操作系统之后，在 r1soft-recovery 提示符处键入 netconfig，并按 **Enter** 键。
8. 选择**是**以配置联网。
9. 在**设备详细信息**页面中输入网络配置详细信息。
10. 当提示您重新启动联网时，单击**是**。
11. **可选**：键入 `passwd root` 以设置 SSH 登录的 root 用户密码，键入 `service ssh start` 以允许 SSH 登录（在您的 KVM 控制台响应缓慢时可能很有用）。
12. 键入 `service cdp-agent restart`。此命令启动 Tivoli Continuous Data Protection for Files 代理程序（如果尚未运行）。
13. 选择**从映像引导**。此时将显示一个框架，说明设备已配置为从 *r1soft-cdp-bootcd-agent-4.0.0.iso* 映像引导。将提示您回答有关卸载映像并返回到正常引导的问题。
14. 单击**是**，服务器将从系统磁盘重新引导。

服务器将通过 chkdsk 或 fsck 流程运行，以验证磁盘，并且可能再次重新启动。流程完成后，您的服务器或 VM 可正常运行并且包含从所选复原点复原的数据。
