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

# Actualización de una instancia para que utilice un servidor WSUS local
{: #updating-an-instance-to-use-a-local-wsus-server}

Si su instancia de servidor virtual que ejecuta Microsoft Windows se suministra con una imagen habilitada para cloud-init, es posible que desee actualizar manualmente el registro de Windows para que utilice servidores {{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services (WSUS) locales en lugar de los servidores Microsoft WSUS predeterminados.
{:shortdesc}

Si solicita un servidor virtual con un sistema operativo Windows Server sin ningún complemento, como más software, scripts post suministro o supervisión avanzada, es probable que el servidor se suministre con una imagen de cloud-init. Con suministros de cloud-init, el servidor WSUS es de forma predeterminada el servidor WSUS de Microsoft.

Si desea actualizar el servidor virtual para que utilice el servidor WSUS local de {{site.data.keyword.cloud_notm}}, utilice el siguiente archivo .reg después de que se suministre el servidor. Realice los siguientes cambios antes de utilizar este archivo.
- Cambie *wsusdal0102* por el centro de datos local en el que desea que se suministre el servidor virtual.  
- La línea que incluye *"DoNotConnectToWindowsUpdateInternetLocations"* obliga al servidor a utilizar el servidor WSUS. Puede dejarlo fuera si desea realizar las comprobaciones mediante Windows Update y WSUS.

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
