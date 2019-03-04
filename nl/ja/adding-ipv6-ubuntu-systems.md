---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

subcollection: software
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Ubuntu システムへの IPv6 の追加

Ubuntu サーバーに IPv6 IP アドレスをバインドするには、この手順を使用します。 

1. **/etc/network/interfaces** ファイルを編集し、以下の行をファイルの末尾に追加します。

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
第 1 行は、システムが IPv6 を使用するインターフェースを定義します。</br>
第 2 行は、IPv6 用のモジュールをロードします。<br/>
第 3 行は、IPv6 アドレスを識別します。<br/>
第 4 行は、IPv6 サブネットのネットマスクを定義します。<br/>
第 5 行は、IPv6 サブネットのデフォルト・ゲートウェイを定義します。

2. ネットワーキングを再始動します。

	'/etc/init.d/networking restart'

## IPv6 接続の確認

### IPv6 IP がバインド済みであることの確認

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### IPv6 近隣キャッシュ

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

近隣キャッシュで fe80 項目が表示される場合、以下のいずれかの状態が該当している可能性があります。
- ゲートウェイが設定されていない。
- IP が正しいインターフェースにバインドされていない。
- IP がパブリック・インターフェースに正しくバインドされていない。
- ソフトウェア・ファイアウォールが IPv6 ICMP をブロックしている。


### IPv6 デフォルト・ゲートウェイ

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

デフォルト・ゲートウェイがリストされない場合、`ping6` コマンドを使用してデフォルト・ゲートウェイを検出し、以下の IP コマンドを使用してそれを手動で追加できます。

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
