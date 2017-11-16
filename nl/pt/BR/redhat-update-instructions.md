---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# Informações de atualização do RedHat

A IBM fornece serviços de atualização de OS e de software para ambientes do RedHat gratuitamente.

Todos os serviços de atualização na IBM compartilham os recursos a seguir:
* O tráfego de atualização é roteado do servidor (por meio da VLAN privada) para a rede de serviço privado
* O tráfego de atualização faz parte da largura de banda de rede privada ilimitada e não reduz as dotações de largura de banda pública.
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

Sempre teste os upgrades de kernel ou de service pack antes da instalação em ambientes do servidor de produção. É possível localizar informações técnicas que estão relacionadas ao hardware, OS e aplicativos específicos implementados na seção de Perguntas mais Frequentes ou de drivers dentro do Portal da Web do cliente. A IBM testa os upgrades de kernel e de service pack e posta informações relacionadas (incluindo drivers) para ajudar o processo de upgrade.

## Assinatura do RHN

Para sistemas operacionais RedHat, a IBM fornece servidores RedHat Network Satellite para instalar atualizações de segurança críticas e não críticas.

A rede RedHat no SoftLayer inclui os servidores RHN Satellite e Proxy. Quando seu servidor RedHat é provisionado, ele é registrado automaticamente no servidor IBM RHN Satellite usando o servidor proxy apropriado. Esse registro permite usar os comandos **up2date** localmente em seus servidores e puxar atualizações na rede de serviço privado.

Para assegurar a qualidade corporativa de serviço e facilitar técnicas de gerenciamento de mudanças adequadas, os servidores RedHat OS são configurados por padrão para ignorar atualizações de kernel. Para assegurar a estabilidade do sistema, execute upgrades do kernel manualmente depois de concluir o teste de regressão. A IBM usa tecnologias de hardware de última geração que requerem edições de kernel estáveis para desempenho adequado.
