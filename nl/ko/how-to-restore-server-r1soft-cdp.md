---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# R1Soft Tivoli Continuous Data Protection for Files로 서버 복원

이 프로세스를 통해 데이터 또는 OS 손실을 유발하는 서버 장애가 발생한 경우 {{site.data.keyword.BluSoftlayer_full}} 퍼블릭 또는 프라이빗 가상 서버(VSI)로 [베어 메탈 복원](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window}을 완료하십시오. 

OS 및 백업에서 제외되지 않은 파일을 포함하여 백업된 모든 파일 시스템 블록이 복원됩니다. 파일 서브세트를 복원하려면 이 프로세스를 수행하지 마십시오. 파일만 복원하려면 [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}의 내용을 참조하십시오. 

## R1Soft Tivoli Continuous Data Protection for Files 서버 준비

1. 브라우저 창을 열고 R1Soft Tivoli Continuous Data Protection for Files 서버에 로그인하십시오(IP 및 admin 비밀번호는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 참조).
2. R1Soft Tivoli Continuous Data Protection for Files 관리 포털에서 **복구 지점**을 클릭하십시오. 
3. 복원하려는 **서버** 및 복원할 **디스크 세이프**를 선택하십시오. 
4. 복구 지점 목록에서 복원하려는 지점을 찾으십시오. 
5. **베어 메탈 복원**(방패 아이콘)을 클릭하여 **복원 마법사**를 시작하십시오. 
6. **복원 마법사**에서 **다음**을 클릭하십시오. 
7. 복원할 파일 시스템을 선택하고 **다음**을 클릭하십시오. 
8. 복원된 파일을 저장할 호스트를 선택하십시오. 원래 호스트이거나 다른 호스트가 될 수 있습니다. (참고: 이 프로시저 단계에서는 동일한 서버로 복원됩니다. 
9. **다음**을 클릭하십시오. 
10. 사용할 저장소 구성을 선택하십시오(서버에 있는 구성을 사용하거나 백업을 기반으로 하나를 선택합니다.). 
11. 파일 시스템 레이아웃을 선택한 경우 사용할 **파티션 테이블**을 선택하십시오. 
12. 파일 시스템을 올바른 블록 디바이스(예: C:\ = /dev/sda1)에 맵핑하고 **다음**을 클릭하십시오. 
13. **복원 후 다시 부팅**, **복원 후 파일 시스템 확인** 같은 복원 옵션을 선택하고 **다음**을 클릭하십시오.
14. 옵션을 확인하고 **복원**을 클릭하거나 복원 옵션을 변경하려면 되돌아가십시오. 

현재 복원 상태가 있는 창이 표시됩니다. 

## 복원을 위한 디바이스 준비

1. 브라우저 창을 열고 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 액세스하십시오. 
2. **디바이스**, **디바이스 목록**을 클릭하고 복원할 디바이스를 선택하십시오. 
3. **조치**를 클릭하고 **이미지에서 부팅**을 선택하여 개인용 이미지 목록을 표시하십시오. 
4. 메뉴에서 **공용 이미지**를 선택하십시오. 
4. R1Soft 서버 버전에 적합한 R1Soft 에이전트 부트 이미지(*r1soft-cdp-bootcd-server-4.0.0.iso*)를 선택하고 **이 이미지에서 부팅**을 클릭하십시오.
5. 복원 중인 서버의 디바이스 세부사항 페이지에서 **조치** **KVM 콘솔**을 클릭하십시오. 콘솔이 가동되고 이미지가 시작되면 일부 옵션이 포함된 Debian 부트로더 화면이 표시됩니다. 
6. **Enter**를 눌러 기본 옵션을 사용하여 부팅하십시오. 
7. OS가 시작된 후 r1soft 복구 프롬프트에서 netconfig를 입력하고 **Enter**를 누르십시오.
8. 네트워킹을 구성하려면 **예**를 선택하십시오. 
9. **디바이스 세부사항** 페이지에서 네트워크 구성 세부사항을 입력하십시오. 
10. 네트워킹을 다시 시작할지 묻는 프롬프트가 표시되면 **예**를 클릭하십시오. 
11. **선택사항**: SSH 로그인에 대한 루트 비밀번호를 설정하려면 `passwd root`를 입력하고, SSH 로그인을 허용하기 위해 `service ssh`를 입력하십시오. 이 명령은 KVM 콘솔 응답이 느릴 경우 유용합니다. 
12. `service cdp-agent restart`를 입력하십시오. 이 명령은 Tivoli Continuous Data Protection for Files 에이전트가 아직 실행 중이 아닌 경우 이를 시작합니다. 
13. **이미지에서 부팅**을 선택하십시오. 디바이스가 *r1soft-cdp-bootcd-agent-4.0.0.iso*이미지에서 부팅되도록 구성되었다는 프레임이 나타납니다. 이미지 로드 해제 및 일반 부팅과 관련된 질문이 표시됩니다. 
14. **예**를 클릭하면 서버가 시스템 디스크에서 재부팅됩니다. 

서버가 chkdsk 또는 fsck 프로세스를 실행하여 디스크를 확인하고 다시 시작할 수 있습니다. 프로세스가 완료되면 서버 또는 VM이 선택한 복원 지점에서 복원된 데이터로 작동합니다. 
