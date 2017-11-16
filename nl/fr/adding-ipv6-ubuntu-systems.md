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

# Ajout d'IPv6 à des systèmes Ubuntu

Suivez cette procédure pour lier des adresses IP IPv6 à votre serveur Ubuntu. 

1. Ouvrez votre fichier **/etc/network/interfaces** et ajoutez les lignes suivantes à la fin du fichier.

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  La première ligne définit l'interface sur laquelle le système utilise IPv6. </br>
  La seconde ligne charge le module pour IPv6.<br/>
  La troisième ligne identifie l'adresse IPv6.<br/>
  La quatrième ligne définit le masque de réseau pour le sous-réseau IPv6.<br/>
  La cinquième ligne définit la passerelle par défaut pour le sous-réseau IPv6.

2. Redémarrez l'opération réseau :

	'/etc/init.d/networking restart'

## Vérification de la connectivité IPv6

### Vérifiez que l'adresse IP IPv6 est liée

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### Cache des voisins IPv6

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

Si le cache des voisins comporte une entrée fe80, l'une des conditions suivantes peut être en cause :
- La passerelle n'a pas été définie
- L'adresse IP n'est pas liée à l'interface correcte
- L'adresse IP n'est pas liée correctement à l'interface publique
- Le pare-feu logiciel bloque le protocole IPv6 ICMP.


### Passerelle par défaut IPv6

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

Si la passerelle par défaut n'est pas répertoriée, vous pouvez utiliser la commande `ping6` pour identifier votre passerelle par défaut, puis l'ajouter manuellement via cette commande IP :

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
