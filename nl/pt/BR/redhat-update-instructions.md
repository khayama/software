---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

keywords: Red Hat, RedHat

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Instruções de atualização do Red Hat
{: #red-hat-update-instructions}

A IBM fornece serviços de atualização de S.O. e software para ambientes do Red Hat sem encargos.

Todos os serviços de atualização na IBM compartilham os recursos a seguir:
* O tráfego de atualização é roteado do servidor (por meio da VLAN privada) para a rede de serviço privado
* O tráfego de atualização faz parte de sua largura de banda de rede privada ilimitada. Esse tráfego não reduz as alocações de largura de banda pública.
* As velocidades das atualizações são mais rápidas do que a atualização diretamente de fornecedores (velocidades de portas submetidas a upgrade disponíveis sob demanda)
* As atualizações ficam prontamente disponíveis durante os dias críticos de atualização pesada em todo o mundo.
* Em situações de emergência, as portas públicas podem ser encerradas, embora ainda permitam que as atualizações ocorram na rede privada
* Os servidores são pré-configurados para atualização automática na implementação com atualizações manuais disponíveis sob demanda.

Os servidores de atualização da IBM estão na rede de serviço privado com os identificadores de localização a seguir:

|Datacenter|Endereço do host de serviço|
|---|---|
|Amsterdã|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|São José|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapura|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Sempre teste os upgrades do kernel ou do service pack antes de instalá-los em ambientes de produção. É possível localizar informações técnicas para hardware específico, S.O. e aplicativos implementados na seção de perguntas mais frequentes ou drivers dentro do portal de controle.

A IBM testa os upgrades do kernel e do service pack e posta informações relacionadas e drivers para ajudar seu processo de upgrade.

## Assinatura do RHN
{: #rhn-subscription}

Para os sistemas operacionais Red Hat, a IBM fornece servidores Red Hat Network Satellite para instalar atualizações de segurança críticas e não críticas.

O Red Hat Network no {{site.data.keyword.Bluemix_notm}} inclui os servidores RHN Satellite e Proxy. Quando o servidor Red Hat é provisionado, ele é automaticamente registrado no servidor IBM RHN Satellite usando o servidor proxy apropriado. Com esse registro, é possível usar os comandos **up2date** localmente em seus servidores e obter atualizações na rede de serviço privada.

Para assegurar a qualidade de serviço da empresa e facilitar as técnicas de gerenciamento de mudanças apropriadas, os servidores do S.O. Red Hat são configurados por padrão para ignorar as atualizações do kernel. Para assegurar a estabilidade do sistema, conclua os upgrades do kernel manualmente depois de concluir o teste de regressão. A IBM usa tecnologias de hardware de última geração que requerem edições de kernel estáveis para desempenho adequado.
