---
copyright:
  years: 2018
lastupdated: "2018-05-16"

keywords: WSUS, Microsoft Windows

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 更新实例以使用本地 WSUS 服务器
{: #updating-an-instance-to-use-a-local-wsus-server}

如果您的运行 Microsoft Windows 的虚拟服务器实例是使用启用 cloud-init 的映像供应的，那么您可能想要手动更新 Windows 注册表以使用本地
{{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services (WSUS) 服务器，而不是缺省的 Microsoft WSUS 服务器。
{:shortdesc}

如果您订购的虚拟服务器使用 Windows Server 操作系统，没有任何附加组件（例如更多软件、供应后脚本或高级监视），那么您的服务器可能是使用 cloud-init 映像供应的。使用 cloud-init 供应，WSUS 服务器缺省为 Microsoft WSUS 服务器。

如果您想要更新虚拟服务器以使用 {{site.data.keyword.cloud_notm}} 本地 WSUS 服务器，请在供应服务器后使用以下 .reg 文件。使用此文件前，进行以下更改。
- 将 *wsusdal0102* 更改为供应虚拟服务器的本地数据中心。  
- 包含 *"DoNotConnectToWindowsUpdateInternetLocations"* 的行将强制服务器使用 WSUS 服务器。如果您希望可以检查 Windows 更新和 WSUS，您可以不包含该行。

```
 Windows Registry Editor Version 5.00

    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate]
    "ElevateNonAdmins"=dword:00000000
    "WUServer"="http://wsusdal0102.service.softlayer.com"
    "WUStatusServer"="http://wsusdal0102.service.softlayer.com"
    "DoNotConnectToWindowsUpdateInternetLocations"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU]
    "AUOptions"=dword:00000005
    "NoAutoRebootWithLoggedonUsers"=dword:00000001
    "NoAutoUpdate"=dword:00000000
    "RebootReLaunchTimeout"=dword:000000f0
    "RebootReLaunchTimeoutEnabled"=dword:00000001
    "RebootWarningTimeout"=dword:0000000a
    "RebootWarningTimeoutEnabled"=dword:00000001
    "RescheduleWaitTime"=dword:0000000a
    "RescheduleWaitTimeEnabled"=dword:00000001
    "ScheduledInstallDay"=dword:00000000
    "ScheduledInstallTime"=dword:00000002
    "UseWUServer"=dword:00000001
```
{: codeblock}
