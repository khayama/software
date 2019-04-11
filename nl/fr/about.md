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

# A propos du logiciel
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} entretient des relations stratégiques avec les éditeurs de logiciels pour fournir des licences à facturation sur base mensuelle sur les logiciels 32 bits et 64 bits compatibles.  Lorsque vous commandez un terminal, vous sélectionnez le type de système d'exploitation et les logiciels pour votre terminal. Vous pouvez ajouter d'autres logiciels à votre terminal depuis le {{site.data.keyword.slportal_full}} et changer de système d'exploitation en effectuant un rechargement du système d'exploitation sur votre terminal existant. Le système IBM automatisé provisionne des logiciels sur votre serveur en suivant les pratiques recommandées de chaque éditeur pour garantir une stabilité et une disponibilité maximales.

Consultez la liste suivante dans laquelle sont répertoriés les logiciels actuellement pris en charge : [Cloud server software ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

Si vous avez besoin d'un logiciel qui n'est pas pris en charge actuellement, utilisez vos droits d'accès de l'utilisateur root au serveur pour installer et configurer votre propre version de ce logiciel.  Pour revenir à une version prise en charge sur votre terminal, rechargez le système d'exploitation.

IBM inclut des instructions ou des remarques pour l'utilisation de produits dans l'environnement {{site.data.keyword.BluSoftlayer_notm}}. Pour la documentation des logiciels, reportez-vous à la documentation de l'éditeur concerné.

## Systèmes d'exploitation pris en charge pour les serveurs virtuels IBM Cloud
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

Les serveurs virtuels IBM Cloud prennent en charge les systèmes d'exploitation suivants :

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Le mode d'amorçage PV est défini par défaut pour Ubuntu 14 (PV/HVM), mais vous pouvez basculer vers le mode d'amorçage HVM
- Le mode d'amorçage PV est défini par défaut pour Ubuntu 16 (PV/HVM), mais vous pouvez basculer vers le mode d'amorçage HVM
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**Remarque :** les tailles de disque d'amorçage varient d'un système d'exploitation à l'autre :<br>  
Le système d'exploitation Linux prend en charge 25 Go et 100 Go.
Windows ne prend en charge que 100 Go.

Pour plus d'informations sur le basculement entre le mode d'amorçage PV et le mode d'amorçage HVM, cliquez sur les liens suivants :
* [Virtual guest supported boot modes ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Add boot mode option ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
