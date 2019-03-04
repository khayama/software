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

# IPv6 zu Ubuntu-Systemen hinzufügen

Verwenden Sie dieses Verfahren zum Binden von IPv6-IP-Adressen an den Ubuntu-Server. 

1. Bearbeiten Sie die Datei **/etc/network/interfaces** und fügen Sie am Ende der Datei die folgenden Zeilen ein.

		#IPV6-Konfiguration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  Die erste Zeile definiert die Schnittstelle, auf der das System IPv6 verwendet. </br>
  Die zweite Zeile lädt das Modul für IPv6.<br/>
  Die dritte Zeile gibt die IPv6-Adresse an.<br/>
  Die vierte Zeile definiert die Netzmaske für das IPv6-Teilnetz.<br/>
  Die fünfte Zeile definiert das Standardgateway für das IPv6-Teilnetz.

2. Starten Sie die Vernetzung erneut:

	'/etc/init.d/networking restart'

## IPv6-Anbindung überprüfen

### Überprüfen, dass die IPv6-IP gebunden ist

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### IPv6-Nachbarcache

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

Wenn der Nachbarcache einen Eintrag des Typs 'fe80' aufweist, kann eine der folgenden Bedingungen vorliegen:
- Das Gateway ist nicht festgelegt.
- Die IP ist nicht an die richtige Schnittstelle gebunden.
- Die IP ist nicht ordnungsgemäß an die öffentliche Schnittstelle gebunden.
- Die Software-Firewall blockiert das IPv6-ICMP (ICMP, Internet Control Message Protocol.


### IPv6-Standardgateway

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

Wenn das Standardgateway nicht aufgeführt ist, können Sie mithilfe des Befehls `ping6` nach dem Standardgateway suchen und dieses dann mit dem folgenden IP-Befehl manuell hinzufügen:

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
