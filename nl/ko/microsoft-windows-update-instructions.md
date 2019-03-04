---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Microsoft Windows 업데이트 정보
IBM은 Microsoft Windows 서버 환경에 맞는 OS 및 소프트웨어 업데이트 서비스를 무료로 제공합니다.

SoftLayer의 모든 업데이트 서비스는 다음 기능을 공유합니다.
* 업데이트 트래픽은 사설 VLAN을 통해 사용자의 서버에서 개인 서비스 네트워크로 라우트됩니다.
* 업데이트 트랙픽은 무제한 사설 네트워크 대역폭의 일부이며 공용 대역폭 할당을 줄이지 않습니다.
* 업데이트 속도는 공급업체에서 직접 업데이트하는 것보다 빠릅니다(요청 시 업그레이드된 포트 속도 사용 가능)
* 전세계적으로 매우 중요한 업데이트 기간 중에 쉽게 업데이트할 수 있습니다.
* 긴급 상황에서 사설 네트워크를 통해 업데이트를 계속 수행하는 동안 공용 포트가 종료될 수 있습니다. 
* 서버는 배치 시 자동으로 업데이트되도록 사전 구성되어 있으며 요청 시 수동으로 업데이트할 수 있습니다.


SoftLayer 업데이트 서버는 개인 서비스 네트워크에 있으며 다음과 같은 위치 ID를 사용합니다. 

Microsoft: **wsus01.service.softlayer.com**

프로덕션 서버 환경에 설치하기 전에 항상 커널 또는 서비스 팩 업그레이드를 테스트하십시오. 특정 하드웨어, OS 및 IBM에서 배치한 애플리케이션과 관련된 기술 정보는 고객 웹 포털 내의 FAQ 또는 드라이버 섹션에서 찾을 수 있습니다. IBM 엔지니어는 커널 및 서비스 팩 업그레이드를 지속적으로 테스트하고 관련 정보(드라이버 포함)를 게시하여 업그레이드 프로세스를 지원합니다.


## WSUS - Windows Server Update Services

Microsoft Windows 서버는 로컬 WSUS(Windows Server Update Services) 서버에서 업데이트를 자동으로 가져옵니다.

Microsoft Windows 운영 체제에서 서버는 기본적으로 패치가 사용 가능하면 즉시 패치를 다운로드하고 설치하도록 구성되어 있습니다. 서버는 필요 시 자동으로 다시 시작합니다. 이 업데이트는 중요 취약점으로부터 서버를 보호하기 위해 수행됩니다. 업데이트를 다른 시간으로 스케줄링하려면 제어 패널에서 **Windows 업데이트** 기능을 통해 업데이트 스케줄을 변경할 수 있습니다.
