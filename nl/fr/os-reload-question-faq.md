---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# Foire aux questions
{: #faqs}

## Peut-on changer le système d'exploitation (SE) sur le terminal ?
{: #can-the-operating-system-os-be-changed-on-the-device-}

Vous pouvez changer votre système d'exploitation et les logiciels que vous avez installés en rechargeant un système d'exploitation<!--[OS Reload](perform-os-reload-device.html){:new_window}-->. Après que vous sélectionnez Rechargement du système d'exploitation sur le terminal, le système affiche un lien vers une page qui vous permettra de mettre à jour les logiciels sur votre système. Vous pouvez mettre à jour le système d'exploitation, le Panneau de configuration, les packages antivirus et le logiciel de base de données depuis cette page.

## Mettez-vous à disposition des rechargements du système d'exploitation ?
{: #do-you-provide-complimentary-os-reloads-}

Les rechargements automatiques de système d'exploitation sont gratuits, y-compris les rechargements de système d'exploitation personnalisés comme le changement de systèmes d'exploitation, l'ajout ou le retrait de panneaux de commande, l'édition de partitions, et d'autres options. Ouvrez le Portail client pour plus d'informations.

## Commet suivre le statut du rechargement du système d'exploitation ?
{: #how-can-i-track-the-status-of-the-os-reload-}

Dans le Portail client, Sous Matériel, figure une section Notes pour chacun de vos serveurs. Cette section inclut des liens vers des informations sur l'étape en cours du rechargement et l'heure estimée de l'achèvement de cette étape.

## Un rechargement du système d'exploitation peut-il effacer les disques secondaires ?
{: #can-an-os-reload-erase-secondary-disks-}

Un rechargement du système d'exploitation ne formate que le disque principal du système. Tous les autres disques sont ignorés. Le comportement est identique lors du rechargement à partir d'un modèle d'image. Si le modèle contient plusieurs disques, seul le disque principal est formaté. Aucune modification n'est apportée aux autres disques.

## Pour quelle raison le message indiquant que cpsrvd a échoué m'est-il envoyé ?
{: #why-did-my-cpsrvd-email-fail-}

Dans la plupart des cas, lorsque vous recevez un courrier électronique indiquant **cpsrvd a échoué**, il est envoyé immédiatement après un réamorçage. Cette erreur se produit lorsque chkservd tente de valider le processus cpsrvd. La validation échoue car le processus n'a pas encore commencé.

Si vous recevez un courrier électronique du service chkservd vous indiquant que cpsrvd a échoué, vous pouvez ignorer ce message dans la plupart des cas. Toutefois, si vous recevez successivement au moins 5 de ces messages, ou si vous en recevez plus de 4 le jour qui suit le réamorçage, ouvrez un ticket de demande de service.
