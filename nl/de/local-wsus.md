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

# Aktualisierung einer Instanz für die Verwendung eines lokalen WSUS-Servers
{: #updating-an-instance-to-use-a-local-wsus-server}

Wenn die Instanz Ihres virtuellen Servers, die mit Microsoft Windows ausgeführt wird, mit einem cloud-init-fähigen Image bereitgestellt wird, müssen Sie möglicherweise die Windows-Registrierungsdatenbank manuell aktualisieren, um lokale {{site.data.keyword.BluSoftlayer_full}}-WSUS-Server (Windows Server Update Services) und nicht die standardmäßigen Microsoft-WSUS-Server verwenden zu können.
{:shortdesc}

Wenn Sie einen virtuellen Server mit einem Windows Server-Betriebssystem ohne Add-ons bestellen, z. B. weitere Software, Bereitstellungsabschlussscripts oder erweiterte Überwachung, wird Ihr Server wahrscheinlich mit einem cloud-init-fähigen Image bereitgestellt. Mit der Bereitstellung von cloud-init-fähigen Images ist der WSUS-Server standardmäßig der Microsoft-WSUS-Server.

Wenn Sie den virtuellen Server dahingehend aktualisieren möchten, dass er den lokalen {{site.data.keyword.cloud_notm}}-WSUS-Server nutzt, verwenden Sie nach der Bereitstellung Ihres Servers die folgende REG-Datei (.reg). Nehmen Sie vor der Verwendung dieser Datei die folgenden Änderungen vor.
- Ändern Sie *wsusdal0102* in das lokale Rechenzentrum, in dem Ihr virtueller Server bereitgestellt wird.  
- Durch die Zeile mit *"DoNotConnectToWindowsUpdateInternetLocations"* wird der Server zur Verwendung des WSUS-Servers gezwungen. Sie können die Zeile weglassen, wenn die Überprüfung auf Windows-Updates und WSUS durchgeführt werden soll.

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
