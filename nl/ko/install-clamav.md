---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

keywords: ClamAV

subcollection: software
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# ClamAV 설치
{: #installing-clamav}

ClamAV를 설치하려면 이 프로시저를 사용하십시오.

1. `https://x.x.x.x:2087`에서 WHM에 로그인하십시오(x.x.x.x를 사용자 서버 IP로 대체)
2. 화면의 오른쪽에 있는 cPanel 아이콘을 클릭하십시오. 
3. cPanel 플러그인의 목록을 보려면 **플러그인 관리** 아이콘을 클릭하십시오. 
4. **추가 기능 모듈** 페이지에서 **clamavconnector**를 찾으십시오. **업데이트 항목 설치 및 유지**를 사용으로 설정하고 페이지 끝에 있는 **저장**을 클릭하십시오.
설치를 완료하려면 약 20분이 소요됩니다.

**참고**
기본적으로 lib 버전 확인이 사용 안함으로 설정됩니다. 그러나 서버에는 zlib 1.2.2 이상이 설치되어 있습니다.

라이센싱은 ClamAV 설치가 실패하는 가장 공통된 이유입니다. clamav 추가 기능은 무료로 제공되지만 전문가용 라이센스로 등록해야 합니다. 자세한 정보는 https://www.clamav.net/의 내용을 참조하십시오. 라이센스를 올바르게 등록한 후 단계 4로 돌아가서 clamavconnector를 설치 제거한 후 다시 설치하십시오.
