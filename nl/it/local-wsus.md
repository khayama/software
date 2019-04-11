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

# Aggiornamento di un'istanza per utilizzare un server WSUS locale
{: #updating-an-instance-to-use-a-local-wsus-server}

Se il provisioning della tua VSI (virtual server instance) che sta eseguendo Microsoft Windows era stato eseguito con un'immagine abilitata a cloud-init, potresti volere aggiornare manualmente il registro Windows per utilizzare i server WSUS (Windows Server Update Services) {{site.data.keyword.BluSoftlayer_full}} locali invece dei server Microsoft WSUS predefiniti.
{:shortdesc}

Se ordini un server virtuale con un sistema operativo Windows Server senza alcun componente aggiuntivo, come ad esempio dell'altro software, degli script di post-provisioning o un monitoraggio avanzato, è probabile che il provisioning del tuo server venga eseguito con un'immagine cloud-init. Con i provisioning cloud-init, il server WSUS viene automaticamente impostato sul server Microsoft WSUS.

Se desideri aggiornare il server virtuale per utilizzare il server WSUS {{site.data.keyword.cloud_notm}} locale, utilizza il seguente file di registro dopo che è stato eseguito il provisioning del tuo server. Prima di utilizzare questo file, apporta le seguenti modifiche.
- Modifica *wsusdal0102* impostandolo sul data center locale dove viene eseguito il provisioning del tuo server virtuale.  
- La riga che include *"DoNotConnectToWindowsUpdateInternetLocations"* forza il server a utilizzare il server WSUS. Puoi lasciarla fuori se desideri poter eseguire un controllo rispetto a Windows Update e WSUS.

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
