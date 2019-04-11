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

# 로컬 WSUS 서버를 사용하도록 인스턴스 업데이트
{: #updating-an-instance-to-use-a-local-wsus-server}

Microsoft Windows를 실행하는 가상 서버 인스턴스가 클라우드 시작 사용 이미지로 프로비저닝된 경우 기본 Microsoft WSUS 서버가 아닌 로컬 {{site.data.keyword.BluSoftlayer_full}} Windows Server Update Services(WSUS) 서버를 사용하도록 Windows 레지스트리를 수동으로 업데이트할 수 있습니다. {:shortdesc}

추가 소프트웨어, 프로비저닝 후 스크립트 또는 고급 모니터링과 같은 추가 기능 없이 Windows Server 운영 체제가 설치된 가상 서버를 주문하는 경우 서버가 클라우드 시작 이미지로 프로비저닝될 가능성이 높습니다. 클라우드 시작 프로비저닝의 경우 WSUS 서버는 기본적으로 Microsoft WSUS 서버로 설정됩니다. 

가상 서버를 업데이트하여 {{site.data.keyword.cloud_notm}} 로컬 WSUS 서버를 사용하려면 서버가 프로비저닝된 후 다음 .reg 파일을 사용하십시오. 이 파일을 사용하기 전에 다음과 같이 변경합니다. 
- *wsusdal0102*를 가상 서버가 프로비저닝된 로컬 데이터 센터로 변경합니다.   
- *"DoNotConnectToWindowsUpdateInternetLocations"*를 포함하는 라인은 WSUS 서버를 사용하도록 서버를 강제 실행합니다. Windows 업데이트 및 WSUSWSUS를 확인하려는 경우에는 제외할 수 있습니다. 

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
