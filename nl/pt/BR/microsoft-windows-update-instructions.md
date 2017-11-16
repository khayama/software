---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Informações de atualização do Microsoft Windows
A IBM fornece serviços de atualização de OS e de software para ambientes do Microsoft Windows Server gratuitamente.

Todos os serviços de atualização no SoftLayer compartilham os recursos a seguir:
* O tráfego de atualização é roteado do servidor, por meio da VLAN privada, para a rede de serviço privado
* O tráfego de atualização faz parte da largura de banda de rede privada ilimitada e não reduz as dotações de largura de banda pública.
* As velocidades das atualizações são mais rápidas do que a atualização diretamente de fornecedores (velocidades de portas submetidas a upgrade disponíveis sob demanda)
* As atualizações ficam prontamente disponíveis durante os dias críticos de atualização pesada em todo o mundo.
* Em situações de emergência, as portas públicas podem ser encerradas, embora ainda permitam que as atualizações ocorram na rede privada
* Os servidores são pré-configurados para atualização automática na implementação com atualizações manuais disponíveis sob demanda.


Os servidores de atualização da SoftLayer estão na rede de serviço privado com os identificadores de localização a seguir.

Microsoft: **wsus01.service.softlayer.com**

Sempre teste os upgrades de kernel ou de service pack antes de instalá-los em ambientes do servidor de produção. É possível localizar informações técnicas que estão relacionadas ao hardware, OS e aplicativos específicos implementados pela IBM na seção de Perguntas mais Frequentes ou de drivers dentro do Portal da Web do cliente. Os engenheiros da IBM testam continuamente os upgrades de kernel e de service pack e postam informações relacionadas (incluindo drivers) para ajudar o processo de upgrade.


## WSUS - Windows Server Update Services

Os servidores Microsoft Windows puxam automaticamente atualizações de servidores Windows Server Update Services (WSUS) locais.

Para sistemas operacionais Microsoft Windows, os servidores são configurados por padrão para fazer download e instalar correções assim que elas são disponibilizadas. O servidor será reiniciado automaticamente se for necessário. Essas atualizações são feitas para ajudar a proteger os servidores contra vulnerabilidades importantes. Se preferir planejar suas atualizações de forma diferente, será possível mudar o planejamento de atualização por meio do recurso **Atualizações do Windows** no Painel de controle.
