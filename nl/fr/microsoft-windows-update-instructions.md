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

# Informations de mise à jour pour Microsoft Windows
IBM fournit à titre gracieux des services de mise à jour du système d'exploitation et des logiciels pour les environnements Microsoft Windows Server.

Tous les services de mise à jour de SoftLayer partagent les caractéristiques suivantes : 
* Le trafic de mise à jour est acheminé de votre serveur, sur votre VLAN privé, vers le réseau de service privé
* Le trafic de mise à jour fait partie de votre bande passante illimitée sur le réseau privé et ne réduit pas les allocations de bande passante publique.
* Les vitesses de mises à jour sont plus rapides qu'une mise à jour directe à partir des fournisseurs (vitesses de ports mises à niveau disponibles sur demande)
* Les mises à jour sont immédiatement disponibles en cas de lourdes mises à jour critiques déployées au niveau mondial.
* Dans les situations d'urgence, les ports publics peuvent être fermés tout en autorisant des mises à jour sur le réseau privé. 
*  Les serveurs sont préconfigurés pour une mise à jour automatique lors du déploiement, des mises à jour manuelles étant disponibles sur demande. 


Les serveurs de mise à jour SoftLayer sont situés sur le réseau de service privé avec les identificateurs d'emplacement suivants.

Microsoft : **wsus01.service.softlayer.com**

Testez toujours les mises à niveau du noyau ou de service pack avant de les installer sur les environnements de serveurs de production. Vous pouvez trouver des informations techniques relatives à des matériels, systèmes d'exploitation et applications spécifiques déployés par IBM dans la section Foire aux questions (FAQ) ou consacrée aux pilotes dans le portail Web client. Les ingénieurs IBM testent systématiquement les mises à niveau du noyau et des service packs et publient les informations pertinentes (y-compris les pilotes) afin de faciliter le processus de mise à niveau.


## WSUS - Windows Server Update Services

Les serveurs Microsoft Windows extraient automatiquement les mises à jour depuis les serveurs WSUS (Windows Server Update Services) locaux.

Pour les systèmes d'exploitation Microsoft Windows, les serveurs sont configurés par défaut pour télécharger et installer les correctifs dès lors qu'ils sont disponibles. Le serveur redémarre automatiquement si ceci est requis. Ces mises à jour sont destinées à immuniser vos serveurs contre des vulnérabilités cruciales. Si vous préférez planifier différemment vos mises à jour, vous pouvez modifier le planning de mise à jour via la fonction **Mises à jour Windows** dans le Panneau de configuration.
