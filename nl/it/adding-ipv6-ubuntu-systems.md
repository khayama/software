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

# Aggiunta di IPv6 ai sistemi Ubuntu
{: #adding-ipv6-to-ubuntu-systems}

Utilizza questa procedura per associare gli indirizzi IP IPv6 al tuo server Ubuntu.

1. Modifica il tuo file **/etc/network/interfaces** e aggiungi le seguenti righe alla fine del file.

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  La prima riga definisce l'interfaccia su cui il sistema utilizza IPv6.</br>
  La seconda riga carica il modulo per IPv6.<br/>
  La terza riga identifica l'indirizzo IPv6.<br/>
  La quarta riga definisce la netmask per la subnet IPv6.<br/>
  La quinta riga definisce il gateway predefinito per la subnet IPv6.

2. Riavvia la rete con il seguente comando:

	'/etc/init.d/networking restart'

## Verifica della connettività IPv6
{: #verifying-ipv6-connectivity}

### Verifica che l'IP IPv6 sia associato
{: #verify-that-ipv6-ip-is-bound}

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### Cache del router adiacente IPv6
{: #ipv6-neighbor-cache}

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

Se la cache del router adiacente mostra una voce fe80, può applicarsi una delle seguenti condizioni:
- Il gateway non è impostato
- L'IP non è associato all'interfaccia corretta
- L'IP non è associato correttamente all'interfaccia pubblica
- Il firewall software sta bloccando l'ICMP IPv6.

### Gateway predefinito IPv6
{: #ipv6-default-gateway}

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

Se il gateway predefinito non è elencato, puoi utilizzare il comando `ping6` per trovare il tuo gateway predefinito e aggiungerlo manualmente utilizzando questo comando IP:

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
