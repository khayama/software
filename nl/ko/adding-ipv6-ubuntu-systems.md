---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Ubuntu 시스템에 IPv6 추가

이 프로시저를 사용하여 Ubuntu 서버에 IPv6 IP 주소를 바인드합니다. 

1. **/etc/network/interfaces** 파일을 편집하고 다음 행을 파일 끝에 추가하십시오.

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  첫 번째 행은 시스템에서 IPv6을 사용하는 인터페이스를 정의합니다.</br>
  두 번째 행은 IPv6의 모듈을 로드합니다.<br/>
  세 번째 행은 IPv6 주소를 식별합니다.<br/>
  네 번째 행은 IPv6 서브넷의 넷마스크를 정의합니다.<br/>
  다섯 번째 행은 IPv6 서브넷의 기본 게이트웨이를 정의합니다.

2. 네트워킹 다시 시작:

	'/etc/init.d/networking restart'

## IPv6 연결 확인

### IPv6 IP가 바인드되어 있는지 확인합니다.

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### IPv6 인접 항목 캐시

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

인접 항목 캐시에서 fe80 항목이 표시된 경우 다음 조건이 적용될 수 있습니다.
- 게이트웨이가 설정되지 않습니다.
- IP가 올바른 인터페이스에 바인드되어 있지 않습니다.
- IP가 올바른 공용 인터페이스에 바인드되어 있지 않습니다.
- 소프트웨어 방화벽은 IPv6 ICMP를 차단하고 있습니다.


### IPv6 기본 게이트웨이

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

기본 게이트웨이가 나열되지 않은 경우 `ping6` 명령을 사용하여 기본 게이트웨이를 찾은 후 이 IP 명령을 통해 수동으로 이를 추가할 수 있습니다.

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
