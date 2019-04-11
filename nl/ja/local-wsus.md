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

# ローカル WSUS サーバーを使用するようにインスタンスを更新する
{: #updating-an-instance-to-use-a-local-wsus-server}

Microsoft Windows を稼働している仮想サーバー・インスタンスが cloud-init 対応イメージを使用してプロビジョンされた場合、デフォルトの Microsoft WSUS (Windows Server Update Services) サーバーではなくローカルの {{site.data.keyword.BluSoftlayer_full}} WSUS サーバーを使用するように、手動で Windows レジストリーを更新することをお勧めします。
{:shortdesc}

仮想サーバーを、追加のソフトウェア、プロビジョン後スクリプト、拡張モニタリングなどのアドオンなしで Windows Server オペレーティング・システムとともに注文した場合、サーバーは cloud-init イメージでプロビジョンされる可能性があります。cloud-init プロビジョンでは、WSUS サーバーのデフォルトは Microsoft WSUS サーバーになります。

{{site.data.keyword.cloud_notm}} のローカル WSUS サーバーを使用するように仮想サーバーを更新する場合は、サーバーがプロビジョンされた後、以下の .reg ファイルを使用します。このファイルを使用する前に、以下の変更を行ってください。
- *wsusdal0102* を、仮想サーバーがプロビジョンされるローカル・データ・センターに変更します。  
- *"DoNotConnectToWindowsUpdateInternetLocations"* が含まれた行により、サーバーは WSUS サーバーを使用することを強制されます。Windows Update および WSUS に対して検査できるようにする場合は、その行を省くことができます。

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
