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

# Mise à jour d'une instance pour utiliser un serveur WSUS local
{: #updating-an-instance-to-use-a-local-wsus-server}

Si votre instance de serveur virtuel qui s'exécute sous Microsoft Windows a été mise à disposition avec une image cloud-init activée, vous souhaiterez peut-être mettre à jour manuellement le registre Windows afin d'utiliser des serveurs {{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services (WSUS) locaux au lieu des serveurs Microsoft WSUS par défaut.
{:shortdesc}

Si vous commandez un serveur virtuel avec un système d'exploitation Windows Server sans module complémentaire, tel que des logiciels supplémentaires, des scripts de mise à disposition postérieure ou des fonctions de surveillance avancées, il est probable que votre serveur soit mis à disposition avec une image cloud-init. Avec les mises à disposition cloud-init, le serveur Microsoft WSUS est défini par défaut comme serveur WSUS. 

Si vous souhaitez mettre à jour le serveur virtuel pour utiliser le serveur {{site.data.keyword.cloud_notm}} WSUS local, utilisez le fichier .reg suivant une fois le serveur mis à disposition. Apportez les modifications suivantes à ce fichier avant de l'utiliser :
- Remplacez *wsusdal0102* par le centre de données local sur lequel votre serveur virtuel est mis à disposition.   
- La ligne comportant *"DoNotConnectToWindowsUpdateInternetLocations"* force le serveur à utiliser le serveur WSUS. Vous pouvez omettre cette ligne si vous souhaitez pouvoir effectuer une vérification Windows Update et WSUS.

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
