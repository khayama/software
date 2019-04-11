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

# Informations de mise à jour pour Microsoft Windows
{: #microsoft-windows-update-information}

IBM fournit à titre gracieux des services de mise à jour du système d'exploitation et des logiciels pour les environnements Microsoft Windows Server.

Tous les services de mise à jour {{site.data.keyword.Bluemix_notm}} partagent les caractéristiques suivantes :
* Le trafic de mise à jour est acheminé de votre serveur (sur votre VLAN privé) vers le réseau de service privé
* Le trafic de mise à jour fait partie de votre bande passante illimitée sur le réseau privé. Ce trafic ne réduit pas les allocations de bande passante publique. 
* Les vitesses de mises à jour sont plus rapides qu'une mise à jour directe à partir des fournisseurs (vitesses de ports mises à niveau disponibles sur demande)
* Les mises à jour sont immédiatement disponibles en cas de lourdes mises à jour critiques déployées au niveau mondial.
* Dans les situations d'urgence, les ports publics peuvent être fermés tout en autorisant des mises à jour sur le réseau privé.
* Les serveurs sont préconfigurés pour une mise à jour automatique lors du déploiement, des mises à jour manuelles étant disponibles sur demande.


Les serveurs de mise à jour {{site.data.keyword.Bluemix_notm}} sont situés sur le réseau de service privé avec les identificateurs d'emplacement suivants. 

Microsoft, **wsus01.service.softlayer.com**

Testez toujours les mises à niveau du noyau ou de service pack avant de les installer sur les environnements de serveurs de production. Vous trouverez des informations techniques relatives à des matériels, systèmes d'exploitation et applications spécifiques déployés par IBM dans la rubrique Foire aux questions (FAQ) ou la section consacrée aux pilotes dans le portail de contrôle. IBM teste en continu les mises à niveau du noyau et des service packs et publie les informations pertinentes et les pilotes afin de faciliter le processus de mise à niveau.


## WSUS Windows Server Update Services
{: #wsus-windows-server-update-services}

Dans de nombreux cas, les serveurs Microsoft Windows extraient automatiquement les mises à jour depuis les serveurs WSUS (Windows Server Update Services) locaux. Toutefois, si votre serveur est mis à disposition avec une image cloud-init activée, vous devrez peut-être mettre à jour manuellement le registre Windows afin d'utiliser des serveurs {{site.data.keyword.cloud_notm}} Windows Server Update Services (WSUS) locaux au lieu des serveurs Microsoft WSUS par défaut. 

Si vous commandez un serveur virtuel avec un système d'exploitation Windows Server sans module complémentaire, tel que des logiciels supplémentaires, des scripts de mise à disposition postérieure ou des fonctions de surveillance avancées, il est probable que votre serveur soit mis à disposition avec une image cloud-init. Pour plus d'informations sur la mise à jour de votre registre pour qu'il pointe vers des serveurs {{site.data.keyword.cloud_notm}} WSUS, voir [Mise à jour d'une instance pour qu'elle utilise un serveur WSUS local](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server).

Pour les systèmes d'exploitation Microsoft Windows, les serveurs sont configurés par défaut pour télécharger et installer les correctifs dès lors qu'ils sont disponibles. Le serveur redémarre automatiquement si cette opération est requise. Les mises à jour sont destinées à protéger vos serveurs contre des vulnérabilités cruciales. Si vous préférez planifier différemment vos mises à jour, vous pouvez modifier le planning de mise à jour via la fonction **Mises à jour Windows** dans le Panneau de configuration.
