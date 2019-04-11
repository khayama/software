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

# Atualizando uma instância para usar um servidor WSUS local
{: #updating-an-instance-to-use-a-local-wsus-server}

Se a instância do servidor virtual que está executando o Microsoft Windows tiver sido provisionada com uma imagem ativada cloud-init, talvez você queira atualizar manualmente o registro do Windows para usar servidores {{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services (WSUS) locais, em vez dos servidores padrão do Microsoft WSUS.
{:shortdesc}

Se você pedir um servidor virtual com um sistema operacional Windows Server sem quaisquer complementos, como mais software, scripts de pós-fornecimento ou monitoramento avançado, será provável que seu servidor seja provisionado com uma imagem cloud-init. Com as provisões cloud-init, o servidor WSUS é padronizado para o servidor Microsoft WSUS.

Se desejar atualizar o servidor virtual para usar o servidor WSUS local do {{site.data.keyword.cloud_notm}}, use o arquivo .reg a seguir depois que o servidor for provisionado. Faça as mudanças a seguir antes de usar esse arquivo.
- Mude *wsusdal0102* para o data center local no qual seu servidor virtual está provisionado.  
- A linha que inclui *"DoNotConnectToWindowsUpdateInternetLocations"* força o servidor a usar o servidor WSUS. É possível deixá-lo fora se você quiser verificar com relação ao Windows Update e ao WSUS.

```
 Windows Registry Editor Versão 5.00

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
