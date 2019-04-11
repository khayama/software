---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 소프트웨어 정보
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}}는 32비트 및 64비트의 호환 가능 소프트웨어에 월별 라이센스를 제공하는 공급업체와의 전략적 관계를 맺고 있습니다.  디바이스를 주문할 때 디바이스의 운영 체제 및 소프트웨어의 유형을 선택하십시오. {{site.data.keyword.slportal_full}} 내에서 디바이스에 더 많은 소프트웨어를 추가하고 기존 디바이스에서 OS 다시 로드를 통해 다른 운영 체제로 변경할 수 있습니다. IBM 자동화된 시스템은 각 공급업체의 우수 사례 가이드라인을 사용하여 소프트웨어를 사용자의 서버에 프로비저닝하여 최고의 안전성 및 가용성을 보장합니다.

현재 지원되는 소프트웨어 목록은 다음을 참조하십시오. [클라우드 서버 소프트웨어 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

현재 지원되지 않은 소프트웨어가 필요한 경우 서버에 대한 루트 액세스를 사용하여 해당 소프트웨어의 자체 버전을 설치하고 구성하십시오.  디바이스에서 지원되는 버전으로 돌아가려면 OS를 다시 로드하십시오. 

IBM은 {{site.data.keyword.BluSoftlayer_notm}} 환경에서 제품을 사용하기 위한 지시사항 또는 고려사항을 포함합니다. 소프트웨어 문서를 보려면 소프트웨어를 제작한 공급업체의 문서를 참조하십시오.

## IBM Cloud 가상 서버를 위한 지원되는 운영 체제
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

IBM Cloud 가상 서버에서는 다음 운영 체제를 지원합니다. 

- Cent OS 6(PV)
- Cent OS 7(HVM)
- Debian 7(PV)
- Debian 8(HVM)
- Debian 9(HVM)
- RHEL 6(PV)
- RHEL 7(HVM)
- Ubuntu 14(PV/HVM)는 PV 부트 모드로 기본 설정되지만 HVM 부트 모드로 전환할 수 있습니다. 
- Ubuntu 16(PV/HVM)은 PV 부트 모드로 기본 설정되지만 HVM 부트 모드로 전환할 수 있습니다. 
- Windows 2012(HVM)
- Windows 2012 R2(HVM)
- Windows 2016(HVM)

**참고:** 부트 디스크 크기는 운영 체제 별로 다릅니다. <br>  
Linux OS는 25GB 및 100GB를 지원합니다.
Windows는 100GB만 지원합니다.

PV 및 HVM 부트 모드 사이 전환에 대한 자세한 정보는 다음 링크를 참조하십시오. 
* [가상 게스트 지원 부트 모드 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [부트 모드 추가 옵션 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
