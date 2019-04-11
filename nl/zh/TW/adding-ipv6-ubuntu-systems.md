---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

keywords: IPv6

subcollection: software

---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 將 IPv6 新增至 Ubuntu 系統
{: #adding-ipv6-to-ubuntu-systems}

使用此程序，以將 IPv6 IP 位址連結至 Ubuntu 伺服器。

1. 編輯 **/etc/network/interfaces** 檔案，並將下列各行新增至檔案結尾。

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  第一行定義系統在其上使用 IPv6 的介面。</br>
  第二行載入 IPv6 的模組。<br/>
  第三行識別 IPv6 位址。<br/>
  第四行定義 IPv6 子網路的網路遮罩。<br/>
  第五行定義 IPv6 子網路的預設閘道。



2. 使用下列指令重新啟動網路：

	'/etc/init.d/networking restart'

## 驗證 IPv6 連線功能
{: #verifying-ipv6-connectivity}

### 驗證已連結 IPv6 IP
{: #verify-that-ipv6-ip-is-bound}

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### IPv6 鄰接項快取
{: #ipv6-neighbor-cache}

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

如果鄰接項快取顯示 fe80 項目，則可能適用下列其中一個狀況：
- 未設定閘道
- IP 未連結至正確介面
- IP 未正確地連結至公用介面
- 軟體防火牆將封鎖 IPv6 ICMP。

### IPv6 預設閘道
{: #ipv6-default-gateway}

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

如果未列出預設閘道，您可以使用 `ping6` 指令找到預設閘道，然後使用此 IP 指令手動進行新增：

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
