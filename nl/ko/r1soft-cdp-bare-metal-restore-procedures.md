---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# R1Soft 이미지에서 서버 복원
{: #restoring-your-server-from-an-r1soft-image}

이 프로시저를 사용하여 퍼블릭 또는 프라이빗 {{site.data.keyword.BluVirtServers_full}} 또는 {{site.data.keyword.BluBareMetServers_full}}로의 복원을 완료하십시오. 서버 장애로 인해 데이터나 OS 손실이 있는 경우 이 프로시저를 사용하십시오. 이 프로세스는 OS 및 백업에서 제외되지 않은 파일을 포함하여 백업된 모든 파일 시스템 블록을 복원합니다. 

파일 서브세트 복원이 목적이라면 이 프로세스를 사용하지 마십시오. 파일만 복원하려면 [R1Soft 위키](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}의 내용을 참조하십시오. 

## 가상 디바이스 복원
{: #restoring-your-virtual-device}

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 복원하려는 디바이스를 클릭하십시오. 
2. **조치**를 클릭하고 **이미지에서 부팅**을 선택하여 개인용 이미지 목록을 가져오십시오. 
3. 메뉴에서 **공용 이미지**를 선택하십시오. 
4. R1Soft 서버 버전에 적합한 R1Soft 에이전트 부트 이미지(serverbackup-centos-bootcd-agent.iso)를 선택하고 오른쪽에 있는 **이 이미지에서 부팅** 링크를 클릭하십시오.
5. 복원 중인 서버에 대해 **디바이스 세부사항** 페이지에서 **조치** > **KVM 콘솔**을 클릭하십시오.
6. 콘솔이 가동되고 이미지가 부팅되면 일부 옵션이 포함된 Debian 부트로더 화면이 표시됩니다. Enter 키를 눌러 기본 옵션을 사용하여 부팅하십시오. 
7. OS가 부팅되면 `netconfig`를 입력하고 **Enter**를 누르십시오. 
8. 네트워킹을 구성하려면 **예**를 선택하십시오. 
9. 제어 포털의 디바이스 세부사항에서 네트워킹 구성 세부사항을 입력하십시오. 
10. 네트워킹을 다시 시작할지 묻는 프롬프트가 표시되면 **예**를 선택하십시오. 
11. 선택적으로 SSH 로그인에 대한 루트 비밀번호를 설정하려면 `passed root`를 입력하고, SSH 로그인을 허용하기 위해 service ssh를 입력하십시오. 이 단계는 KVM 콘솔이 느릴 경우 유용합니다. 
12. `service cdp-agent restart`를 입력하십시오. (이 명령은 Tivoli Continuous Data Protection for Files 에이전트가 아직 실행 중이 아닌 경우 이를 시작합니다.)

## 베어 메탈 디바이스 복원
{: #restoring-your-bare-metal-device}

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 티켓을 열고 **R1Soft 베어 메탈 복원 모드**에 베어 메탈 서버를 부팅하도록 요청하십시오. 
2. 복원 중인 서버에 대해 **디바이스 세부사항** 페이지를 사용하여 **IPMI KVM 콘솔**에 로그인하십시오. 
3. 콘솔이 가동되고 이미지가 부팅되면 일부 옵션이 포함된 Debian 부트로더 화면이 표시됩니다. Enter 키를 눌러 기본 옵션을 사용하여 부팅하십시오. 
4. OS가 부팅되면 `netconfig`를 입력하고 **Enter**를 누르십시오. 
5. 네트워킹을 구성하려면 **예**를 선택하십시오. 
6. 제어 포털의 디바이스 세부사항에서 네트워킹 구성 세부사항을 입력하십시오. 
7. 네트워킹을 다시 시작할지 묻는 프롬프트가 표시되면 **예**를 선택하십시오. 
8. 선택적으로 SSH 로그인에 대한 루트 비밀번호를 설정하려면 `passed root`를 입력하고, SSH 로그인을 허용하기 위해 service ssh를 입력하십시오. 이 단계는 KVM 콘솔이 느릴 경우 유용합니다. 
9. `service cdp-agent restart`를 입력하십시오. (이 명령은 Tivoli Continuous Data Protection for Files 에이전트가 아직 실행 중이 아닌 경우 이를 시작합니다.)

## R1Soft 서버 및 기타 복원 매개변수 및 옵션 선택
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

[베어 메탈 복원 수행](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)에 대해 R1Soft 문서를 참조하십시오. 복원할 서버를 선택하고 파일 시스템, 부분 표 및 기타 복원 옵션을 선택하십시오. 
