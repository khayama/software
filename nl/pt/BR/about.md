---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Sobre o software
{: #about-software}

O {{site.data.keyword.BluSoftlayer_full}} possui relacionamentos estratégicos com fornecedores para fornecer licenças mensais para software compatível com 32 e 64 bits.  Ao pedir um dispositivo, você seleciona o tipo de sistema operacional e software para seu dispositivo. É possível incluir mais software em seu dispositivo no {{site.data.keyword.slportal_full}} e mudar para outro sistema operacional recarregando o S.O. em seu dispositivo existente. O sistema IBM automatizado provisiona software em seu servidor usando as diretrizes de melhores práticas de cada fornecedor para assegurar máxima estabilidade e disponibilidade.

Consulte a lista a seguir de software suportado atualmente: [Software do servidor em nuvem ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

Se você precisar de software não suportado atualmente, use seu acesso raiz ao servidor para instalar e configurar sua própria versão desse software.  Para retornar para uma versão suportada em seu dispositivo, recarregue o S.O.

A IBM inclui instruções ou considerações para o uso de produtos no ambiente do {{site.data.keyword.BluSoftlayer_notm}}. Para obter a documentação do software, consulte a documentação do fornecedor que produz o software.

## Sistemas operacionais suportados para servidores virtuais IBM Cloud
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

Os servidores virtuais do IBM Cloud suportam os sistemas operacionais a seguir.

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) é padronizado para o modo de inicialização PV, mas é possível alternar para o modo de inicialização HVM
- Ubuntu 16 (PV/HVM) é padronizado para o modo de inicialização PV, mas é possível alternar para o modo de inicialização HVM
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**Nota:** os tamanhos de disco de inicialização variam por sistema operacional:<br>  
O S.O. Linux suporta 25 GB e 100 GB.
O Windows suporta apenas 100 GB.

Para obter mais informações sobre como alternar entre os modos de inicialização PV e HVM, consulte os links a seguir:
* [Modos de inicialização suportados pelo guest virtual ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Incluir a opção de modo de inicialização ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
