---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# RedHat 업데이트 정보

IBM은 RedHat 환경에 맞는 OS 및 소프트웨어 업데이트 서비스를 무료로 제공합니다.

IBM의 모든 업데이트 서비스는 다음 기능을 공유합니다.
* 업데이트 트래픽은 사용자의 서버에서(사설 VLAN을 통해) 개인 서비스 네트워크로 라우트됩니다.
* 업데이트 트랙픽은 무제한 사설 네트워크 대역폭의 일부이며 공용 대역폭 할당을 줄이지 않습니다.
* 업데이트 속도는 공급업체에서 직접 업데이트하는 것보다 빠릅니다(요청 시 업그레이드된 포트 속도 사용 가능)
* 전세계적으로 매우 중요한 업데이트 기간 중에 쉽게 업데이트할 수 있습니다.
* 긴급 상황에서 사설 네트워크를 통해 업데이트를 계속 수행하는 동안 공용 포트가 종료될 수 있습니다. 
* 서버는 배치 시 자동으로 업데이트되도록 사전 구성되어 있으며 요청 시 수동으로 업데이트할 수 있습니다.

IBM 업데이트 서버는 개인 서비스 네트워크에 있으며 다음과 같은 위치 ID를 사용합니다. 

|데이터 센터|서비스 호스트 주소|
|---|---|
|암스테르담|rhnproxyams0101.service.softlayer.com|
|달라스|rhnproxy101.service.softlayer.com|
|휴스턴|rhnproxy421.service.softlayer.com|
|산호세|rhnproxy501.service.softlayer.com|
|시애틀|rhnproxy201.service.softlayer.com|
|싱가포르|rhnproxysng0101.service.softlayer.com|
|워싱턴 D.C.|rhnproxy301.service.softlayer.com|

프로덕션 서버 환경에 설치하기 전에 항상 커널 또는 서비스 팩 업그레이드를 테스트하십시오. 특정 하드웨어, OS 및 배치된 애플리케이션과 관련된 기술 정보는 고객 웹 포털 내의 FAQ 또는 드라이버 섹션에서 찾을 수 있습니다. IBM은 커널 및 서비스 팩 업그레이드를 테스트하고 관련 정보(드라이버 포함)를 게시하여 업그레이드 프로세스를 지원합니다.

## RHN 등록

RedHat 운영 체제에서 IBM은 RedHat Network Satellite 서버를 제공하여 중요한 보안 업데이트와 중요하지 않은 보안 업데이트를 설치합니다.

SoftLayer의 RedHat Network에는 RHN Satellite 및 프록시 서버가 포함됩니다. RedHat 서버가 프로비저닝되는 경우 적절한 프록시 서버를 사용하여 IBM RHN Satellite 서버에 자동으로 등록됩니다. 이 등록을 통해 서버에서 로컬로 **up2date** 명령을 사용하고 개인 서비스 네트워크에서 업데이트를 가져올 수 있습니다. 

엔터프라이즈 서비스 품질(QoS)을 보장하고 적절한 변경 관리 기술을 사용하기 위해 RedHat OS 서버는 기본적으로 커널 업데이트를 건너뛰도록 구성되어 있습니다. 시스템 안전성을 보장하려면 회귀 테스트를 완료한 후 커널 업그레이드를 수동으로 수행하십시오. IBM은 적절한 성능을 위해 안정적인 커널 에디션을 필요로 하는 첨단 하드웨어 기술을 사용합니다.
