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

# Incluindo IPv6 em sistemas Ubuntu

Use este procedimento para ligar endereços IP IPv6 ao servidor Ubuntu. 

1. Edite o arquivo **/etc/network/interfaces** e inclua as linhas a seguir no final do arquivo.

		#Configuração de IPV6
	    iface eth1 inet6 static
	    pre-up modprobe ipv6 </br>
	    address 2607:f0d0:2001:0000:0000:0000:0000:0010</br>
	    netmask 64</br>
		gateway 2607:f0d0:2001:0000:0000:0000:0000:0001</br>
  A primeira linha define a interface na qual o sistema usa IPv6. </br>
  A segunda linha carrega o módulo para IPv6.<br/>
  A terceira linha identifica o endereço IPv6.<br/>
  A quarta linha define a máscara de rede para a sub-rede IPv6.<br/>
  A quinta linha define o gateway padrão para a sub-rede IPv6.

2. Reinicie a rede:

	'/etc/init.d/networking restart'

## Verificando a conectividade de IPv6

### Verifique se o IP IPv6 está ligado

    root@server:~# ip -6 address show eth1
    3: eth1: mtu 1500 qlen 1000
        inet6 2607:f0d0:2001::/64 scope global
           valid_lft forever preferred_lft forever
        inet6 fe80::230:48ff:fe7e:330a/64 scope link
           valid_lft forever preferred_lft forever
    root@server:~#


### Cache vizinho IPv6

    root@server:~# ip -6 neighbor show dev eth1
    2607:f0d0:2001::1 lladdr 00:1b:0d:e6:57:c0 router REACHABLE
    root@server:~#

Se o cache vizinho mostrar uma entrada fe80, um das condições a seguir poderão se aplicar:
- O gateway não está configurado
- O IP não está ligado à interface correta
- O IP não está ligado corretamente à interface pública
- O firewall de software está bloqueando o ICMP de IPv6.


### Gateway padrão IPv6

    root@server:~# ip -6 route show dev eth1
    2607:f0d0:2001::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    fe80::/64  proto kernel  metric 256  mtu 1500 advmss 1440 hoplimit 4294967295
    default via 2607:f0d0:2001::1  metric 1024  mtu 1500 advmss 1440 hoplimit 4294967295
    root@server:~#

Se o gateway padrão não estiver listado, será possível usar o comando `ping6` para localizar seu gateway padrão e, em seguida, inclui-lo manualmente usando este comando IP:

    root@server:~# ip -6 route add default via 2607:f0d0:2001::1
    root@server:~#
