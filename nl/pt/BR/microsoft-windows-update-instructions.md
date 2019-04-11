---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

keywords: Microsoft Windows Update, software update services

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Informações de atualização do Microsoft Windows
{: #microsoft-windows-update-information}

A IBM fornece serviços de atualização de OS e de software para ambientes do Microsoft Windows Server gratuitamente.

Todos os serviços de atualização no {{site.data.keyword.Bluemix_notm}} compartilham os recursos a seguir:
* O tráfego de atualização é roteado do servidor (por meio da VLAN privada) para a rede de serviço privado
* O tráfego de atualização faz parte de sua largura de banda de rede privada ilimitada. Esse tráfego não reduz as alocações de largura de banda pública.
* As velocidades das atualizações são mais rápidas do que a atualização diretamente de fornecedores (velocidades de portas submetidas a upgrade disponíveis sob demanda)
* As atualizações ficam prontamente disponíveis durante os dias críticos de atualização pesada em todo o mundo.
* Em situações de emergência, as portas públicas podem ser encerradas, embora ainda permitam que as atualizações ocorram na rede privada
* Os servidores são pré-configurados para atualização automática na implementação com atualizações manuais disponíveis sob demanda.


Os servidores de atualização {{site.data.keyword.Bluemix_notm}} estão na rede de serviço privada com os identificadores de localização a seguir.

Microsoft, **wsus01.service.softlayer.com**

Sempre teste os upgrades de kernel ou de service pack antes de instalá-los em ambientes do servidor de produção. É possível localizar informações técnicas que estão relacionadas a hardware, S.O. e aplicativos específicos implementados pela IBM na seção de perguntas mais frequentes ou drivers dentro do portal de controle. A IBM testa continuamente os upgrades do kernel e do service pack e as informações relacionadas a postagem (incluindo drivers) para ajudar o processo de upgrade.


## Serviços de atualização do servidor Windows WSUS
{: #wsus-windows-server-update-services}

Em muitos casos, os servidores Microsoft Windows retiram atualizações automaticamente dos servidores Windows Server Update Services (WSUS) locais. No entanto, se o seu servidor for fornecido com uma imagem ativada cloud-init, talvez seja necessário atualizar manualmente o registro do Windows para usar servidores {{site.data.keyword.cloud_notm}} Windows Server Update Services (WSUS) locais, em vez dos servidores Microsoft WSUS padrão.

Se você pedir um servidor virtual com um sistema operacional Windows Server sem quaisquer complementos, como mais software, scripts de pós-fornecimento ou monitoramento avançado, será provável que seu servidor seja provisionado com uma imagem cloud-init. Para obter mais informações sobre como atualizar seu registro para apontar para servidores WSUS {{site.data.keyword.cloud_notm}}, consulte [Atualizando a instância para usar o servidor WSUS local](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server).

Para sistemas operacionais Microsoft Windows, os servidores são configurados por padrão para fazer download e instalar correções assim que elas são disponibilizadas. O servidor é reiniciado automaticamente se uma reinicialização for necessária. As atualizações são concluídas para proteger servidores de vulnerabilidades cruciais. Se você preferir planejar suas atualizações de forma diferente, será possível mudar o planejamento de atualização por meio do recurso **Atualizações do Windows** no painel de controle.
