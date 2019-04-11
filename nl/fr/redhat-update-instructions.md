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

# Instructions de mise à jour de Red Hat
{: #red-hat-update-instructions}

IBM fournit à titre gracieux des services de mise à jour du système d'exploitation et des logiciels pour les environnements Red Hat.

Tous les services de mise à jour IBM partagent les caractéristiques suivantes :
* Le trafic de mise à jour est acheminé de votre serveur (sur votre VLAN privé) vers le réseau de service privé
* Le trafic de mise à jour fait partie de votre bande passante illimitée sur le réseau privé. Ce trafic ne réduit pas les allocations de bande passante publique. 
* Les vitesses de mises à jour sont plus rapides qu'une mise à jour directe à partir des fournisseurs (vitesses de ports mises à niveau disponibles sur demande)
* Les mises à jour sont immédiatement disponibles en cas de lourdes mises à jour critiques déployées au niveau mondial.
* Dans les situations d'urgence, les ports publics peuvent être fermés tout en autorisant des mises à jour sur le réseau privé.
* Les serveurs sont préconfigurés pour une mise à jour automatique lors du déploiement, des mises à jour manuelles étant disponibles sur demande.

Les serveurs de mise à jour IBM sont situés sur le réseau de service privé avec les identificateurs d'emplacement suivants :

|Centre de données|Adresse du système hôte de service|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San Jose|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapour|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Testez toujours les mises à niveau du noyau ou de service pack avant de les installer dans des environnements de production. Vous trouverez des informations techniques relatives à des matériels, systèmes d'exploitation et applications spécifiques déployés dans la rubrique Foire aux questions (FAQ) ou la section consacrée aux pilotes dans le portail de contrôle. 

IBM teste les mises à niveau du noyau et des service packs et publie les informations pertinentes et les pilotes afin de faciliter le processus de mise à niveau.

## Abonnement RHN
{: #rhn-subscription}

Pour les systèmes d'exploitation Red Hat, IBM fournit des serveurs Red Hat Network Satellite pour installer les mises à jour de sécurité critiques et ordinaires. 

Le réseau Red Hat sur {{site.data.keyword.Bluemix_notm}} comprend des serveurs RHN Satellite et Proxy. Lorsque votre serveur Red Hat mis à disposition, il est automatiquement enregistré sur le serveur IBM RHN Satellite via le serveur proxy approprié. Cet enregistrement vous permet d'utiliser des commandes **up2date** en local sur vos serveurs et de déployer les mises à jour à travers le réseau de service privé. 

Pour assurer une qualité de service de niveau entreprise et favoriser les techniques de gestion des changements idoines, les serveurs Red Hat OS sont configurés par défaut pour ignorer les mises à jour de noyau. Pour assurer la stabilité du système, effectuez manuellement les mises à jour du noyau après avoir procédé à un test de régression. IBM utilise des technologies matérielles de pointe qui exigent des éditions de noyau stables pour assurer des performances correctes.
