---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# FAQ
{: #faqs}

## 디바이스에서 운영 체제(OS)를 변경할 수 있습니까?
{: #can-the-operating-system-os-be-changed-on-the-device-}

OS를 <!--[OS Reload](perform-os-reload-device.html){:new_window}--> 다시 로드하여 설치한 OS 및 소프트웨어를 변경할 수 있습니다. 디바이스에서 OS 다시 로드를 선택하면 시스템은 사용자의 시스템에서 소프트웨어를 업데이트할 수 있도록 페이지에 링크를 표시합니다. 이 페이지에서 OS, 제어판, 안티바이러스 패키지 및 데이터베이스 소프트웨어를 업데이트할 수 있습니다.

## OS 다시 로드를 무료로 제공합니까?
{: #do-you-provide-complimentary-os-reloads-}

운영 체제 변경, 제어판 추가 또는 제거, 파티션 편집 및 기타 옵션과 같은 사용자 정의된 OS 다시 로드를 포함한 자동화된 OS 다시 로드는 무료입니다. 자세한 정보를 보려면 제품 포털을 여십시오.

## OS 다시 로드의 상태를 어떻게 추적할 수 있습니까?
{: #how-can-i-track-the-status-of-the-os-reload-}

고객 포털의 하드웨어에 각 서버에 대한 참고 섹션이 있습니다. 참고 섹션에는 다시 로드의 현재 단계 및 다시 로드의 해당 부분을 완료하기 위한 예상 시간과 관련된 정보에 대한 링크가 포함됩니다.

## OS를 다시 로드하면 보조 디스크가 제거됩니까?
{: #can-an-os-reload-erase-secondary-disks-}

OS 다시 로드는 시스템의 기본 디스크만 포맷합니다. 기타 모든 디스크는 단독으로 남겨집니다. 이는 이미지 템플리트에서 다시 로드할 때와 같은 방식으로 작동합니다. 템플리트에 하나 이상의 디스크가 포함되어 있으면 기본 디스크만 포맷됩니다. 기타 디스크가 변경되지 않습니다.

## 왜 내 cpsrvd 이메일이 실패합니까?
{: #why-did-my-cpsrvd-email-fail-}

대부분의 경우, **cpsrvd 실패**라는 이메일을 받으면 다시 부팅 후 즉시 전송된 것입니다. 이 오류는 chkservd에서 chkservd 프로세스의 유효성 검증을 시도할 때 발생합니다. 프로세스가 시작되지 않았기 때문에 유효성 검증이 실패합니다. 

대부분의 경우, chkservd 서비스에서 cpsrvd가 실패했다는 이메일을 받으면 이 메시지를 무시할 수 있습니다. 그러나 다시 시작 후 이 메시지를 5번 이상 연속해서 받거나 하루에 4번 이상 받으면 지원 티켓을 여십시오. 
