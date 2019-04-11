---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restauration de votre serveur à partir d'une image R1Soft
{: #restoring-your-server-from-an-r1soft-image}

Cette procédure permet de restaurer des serveurs {{site.data.keyword.BluVirtServers_full}} ou {{site.data.keyword.BluBareMetServers_full}} publics ou privés. Suivez cette procédure si une panne de serveur entraîne une perte de données ou de système d'exploitation. Cette procédure restaure tous les blocs de système de fichiers qui sont sauvegardés (y compris le système d'exploitation et les fichiers qui n'ont pas été exclus des sauvegardes). 

N'utilisez pas cette procédure si vous souhaitez restaurer un sous-ensemble de fichiers. Pour restaurer uniquement les fichiers, voir le [wiki R1Soft](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Restauration de votre unité virtuelle
{: #restoring-your-virtual-device}

1. Cliquez sur l'unité que vous souhaitez restaurer dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur le menu **Actions** et choisissez **Initialiser à partir d'une image** pour afficher une liste d'images privées. 
3. Choisissez **Images publiques** dans le menu.
4. Choisissez l'image d'initialisation d'agent R1Soft appropriée pour votre version de serveur R1Soft (serverbackup-centos-bootcd-agent.iso) et cliquez sur le lien **Initialiser à partir de cette image** situé à droite.
5. Sur la page **Détails d'unité** du serveur que vous restaurez, cliquez sur **Actions** > **Console KVM**.
6. Une fois la console active et l'image démarrée, un écran relatif au chargeur de démarrage Debian s'affiche avec certaines options. Appuyez sur Entrée pour amorcer le système avec l'option par défaut. 
7. Une fois le système d'exploitation initialisé, tapez `netconfig` et appuyez sur **Entrée**.
8. Choisissez **Oui** pour configurer la mise en réseau.
9. Entrez les détails de configuration de la mise en réseau à partir de la page Détails d'unités sur le portail de contrôle. 
10. Cliquez sur **Oui** lorsque vous êtes invité à redémarrer la mise en réseau. 
11. Vous pouvez éventuellement taper `passed root` pour définir un mot de passe root pour les connexions SSH et taper service ssh start pour autoriser la connexion SSH. Cela peut s'avérer utile si les temps de réponse de votre console KVM sont lents.
12. Tapez `service cdp-agent restart` (cette commande permet de démarrer l'agent Tivoli Continuous Data Protection for Files s'il n'est pas actif). 

## Restauration de votre unité bare metal
{: #restoring-your-bare-metal-device}

1. Ouvrez un ticket dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et demandez à ce que votre serveur bare metal soit initialisé en **mode restauration bare metal R1Soft**.
2. Sur la page **Détails d'unité** du serveur que vous restaurez, connectez-vous à la **Console KVM IPMI**.
3. Une fois la console active et l'image démarrée, un écran relatif au chargeur de démarrage Debian s'affiche avec certaines options. Appuyez sur Entrée pour amorcer le système avec l'option par défaut. 
4. Une fois le système d'exploitation initialisé, tapez `netconfig` et appuyez sur **Entrée**.
5. Choisissez **Oui** pour configurer la mise en réseau.
6. Entrez les détails de configuration de la mise en réseau à partir de la page Détails d'unités sur le portail de contrôle. 
7. Cliquez sur **Oui** lorsque vous êtes invité à redémarrer la mise en réseau. 
8. Vous pouvez éventuellement taper `passed root` pour définir un mot de passe root pour les connexions SSH et taper service ssh start pour autoriser la connexion SSH. Cela peut s'avérer utile si les temps de réponse de votre console KVM sont lents.
9. Tapez `service cdp-agent restart` (cette commande permet de démarrer l'agent Tivoli Continuous Data Protection for Files s'il n'est pas actif). 

## Sélection du serveur R1Soft et d'autres paramètres et options de restauration
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

Reportez-vous à la rubrique [Perform a bare-metal Restore](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore) dans la documentation R1Soft. Vous devez sélectionner le serveur à restaurer et choisir le système de fichiers, les tables de portions, ainsi que d'autres options de restauration.

