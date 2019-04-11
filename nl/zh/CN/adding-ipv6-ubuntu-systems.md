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

# 将 IPv6 添加到 Ubuntu 系统
{: #adding-ipv6-to-ubuntu-systems}

使用此过程将 IPv6 IP 地址绑定到 Ubuntu 服务器。

1. 编辑 **/etc/network/interfaces** 文件并将以下各行添加到文件末尾。

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  第一行定义系统使用 IPv6 的接口。</br>
  第二行装入 IPv6 的模块。<br/>
  第三行识别 IPv6 地址。<br/>
  第四行定义 IPv6 子网的子网掩码。<br/>
  第五行定义 IPv6 子网的缺省网关。



2. 使用以下命令重新启动联网：

	'/etc/init.d/networking restart'

## 验证 IPv6 连接
{: #verifying-ipv6-connectivity}

### 验证 IPv6 IP 是否已绑定
{: #verify-that-ipv6-ip-is-bound}

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### IPv6 邻居缓存
{: #ipv6-neighbor-cache}

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

如果邻居缓存显示 fe80 条目，那么可能存在以下某种情况：
- 未设置网关
- IP 未绑定到正确的接口
- IP 未正确绑定到公共接口
- 软件防火墙阻止 IPv6 ICMP。

### IPv6 缺省网关
{: #ipv6-default-gateway}

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

如果未列出该缺省网关，那么可以使用 `ping6` 命令来查找缺省网关，然后使用此 IP 命令进行手动添加：

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
