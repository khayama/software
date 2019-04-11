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

# Adición de IPv6 a sistemas Ubuntu
{: #adding-ipv6-to-ubuntu-systems}

Utilice este procedimiento para enlazar direcciones IP IPv6 a su servidor Ubuntu.

1. Edite el archivo **/etc/network/interfaces** y añada las líneas siguientes al final del archivo.

		#IPV6 configuration
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  La primera línea define la interfaz en la que el sistema utiliza IPv6.</br>
  La segunda línea carga el módulo para IPv6.<br/>
  La tercera línea identifica la dirección IPv6.<br/>
  La cuarta línea define la máscara de la subred IPv6.<br/>
  The quinta línea define la pasarela predeterminada para la subred IPv6.

2. Reinicie la red con este mandato:

	'/etc/init.d/networking restart'

## Verificación de conectividad IPv6
{: #verifying-ipv6-connectivity}

### Verifique que la dirección IP de IPv6 está vinculada
{: #verify-that-ipv6-ip-is-bound}

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### Memoria caché de vecinos IPv6
{: #ipv6-neighbor-cache}

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

Si la memoria caché de vecinos muestra una entrada fe80, es posible que se esté produciendo una de las siguientes condiciones:
- La pasarela no está establecida
- La dirección IP no está vinculada a la interfaz correcta
- La dirección IP no está vinculada correctamente a la interfaz pública
- El cortafuegos de software está bloqueando el ICMP de IPv6

### Pasarela predeterminada de IPv6
{: #ipv6-default-gateway}

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

Si la pasarela predeterminada no está en la lista, puede utilizar el mandato `ping6` para encontrarla y a continuación añadirla manualmente utilizando este mandato IP:

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
