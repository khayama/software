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

# 將實例更新為使用本端 WSUS 伺服器
{: #updating-an-instance-to-use-a-local-wsus-server}

如果您的虛擬伺服器實例執行 Microsoft Windows 並已佈建已啟用 cloud-init 的映像檔，您可能要手動更新 Windows 登錄，改成使用本端 {{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services (WSUS) 伺服器，而不是預設 Microsoft WSUS 伺服器。{:shortdesc}

如果您訂購具有 Windows Server 作業系統但不含任何附加程式（例如，更多軟體、佈建後 Script，或進階監視）的虛擬伺服器，則您的伺服器有可能已佈建有 cloud-init 映像檔。藉由 cloud-init 佈建，WSUS 伺服器預設為 Microsoft WSUS 伺服器。

如果您要更新虛擬伺服器以便使用 {{site.data.keyword.cloud_notm}} 本端 WSUS 伺服器，請在佈建伺服器之後使用下列 .reg 檔案。請在使用此檔案之前進行下列變更。
- 將 *wsusdal0102* 變更為其中已佈建您的虛擬伺服器的本端資料中心。  
- 包含 *"DoNotConnectToWindowsUpdateInternetLocations"* 的行會強制伺服器使用 WSUS 伺服器。如果您想要依據 Windows Update 和 WSUS 進行檢查，您可以忽略該行。

```
 Windows 登錄編輯程式 5.00 版

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
