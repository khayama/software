---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restauration d'un serveur avec R1Soft Tivoli Continuous Data Protection for Files

Utilisez ce processus pour effectuer une [restauration bare metal](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} sur un serveur virtuel privé ou public {{site.data.keyword.BluSoftlayer_full}} si une panne de serveur entraîne une perte de données ou de système d'exploitation. 

Tous les blocs de système de fichiers sauvegardés sont restaurés, y compris le système d'exploitation et les fichiers qui n'ont pas été exclus des sauvegardes. Ne suivez pas cette procédure si vous souhaitez restaurer un sous-ensemble de fichiers. Pour restaurer uniquement les fichiers, voir [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Préparation du serveur R1Soft Tivoli Continuous Data Protection for Files

1. Ouvrez une fenêtre de navigateur et connectez-vous au serveur R1Soft Tivoli Continuous Data Protection for Files (l'adresse IP et le mot de passe administrateur sont disponibles dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Cliquez sur **Recovery Points** sur le portail de gestion R1Soft Tivoli Continuous Data Protection for Files. 
3. Sélectionnez le **serveur** que vous souhaitez restaurer et le **disque sécurisé** à partir duquel vous souhaitez effectuer la restauration. 
4. Localisez le point à partir duquel vous souhaitez restaurer dans la liste des points de récupération. 
5. Cliquez sur **Bare Metal Restore** (icône en forme de bouclier) pour démarrer l'**assistant de restauration**.
6. Cliquez sur **Next** dans l'**assistant de restauration**.
7. Sélectionnez les systèmes de fichiers à restaurer et cliquez sur **Next**.
8. Sélectionnez l'hôte sur lequel vous souhaitez effectuer la restauration. Il peut s'agir de l'hôte d'origine ou d'un autre hôte. (Remarque : les étapes de cette procédure permettent d'effectuer une restauration sur le même serveur.) 
9. Cliquez sur **Next**.
10. Choisissez la configuration de stockage à utiliser (utilisez celle qui est en place sur le serveur ou choisissez-en une basée sur les sauvegardes).
11. Sélectionnez les **tables de partition** que vous souhaitez utiliser si vous avez opté pour le choix de la disposition de système de fichiers 
12. Mappez vos systèmes de fichiers aux unités par bloc appropriées (par exemple, C:\ = /dev/sda1) et cliquez sur **Next**.
13. Sélectionnez vos options de restauration, par exemple, **Reboot after restore**, **Check file system after restore**, puis cliquez sur **Next**.
14. Vérifiez vos options et cliquez sur **Restore** ou revenez en arrière pour modifier vos options de restauration. 

Une fenêtre s'affiche avec l'état de la restauration en cours. 

## Préparation de l'unité pour la restauration

1. Ouvrez une fenêtre de navigateur et accédez au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Unités**, **Liste d'unités** et sélectionnez l'unité à restaurer. 
3. Cliquez sur **Actions** et choisissez **Initialiser à partir d'une image** pour afficher une liste d'images privées. 
4. Choisissez **Images publiques** dans le menu.
4. Choisissez l'image d'initialisation d'agent R1Soft appropriée pour votre version de serveur R1Soft (*r1soft-cdp-bootcd-server-4.0.0.iso*) et cliquez sur **Initialiser à partir de cette image**.
5. Cliquez sur **Actions**, **Console KVM** sur la page Détails d'unités pour le serveur que vous restaurez. Une fois la console active et l'image démarrée, un écran relatif au chargeur de démarrage Debian s'affiche avec certaines options. 
6. Appuyez sur **Entrée** pour amorcer le système avec l'option par défaut. 
7. Tapez netconfig à l'invite r1soft-recovery une fois le système d'exploitation démarré et appuyez sur **Entrée**.
8. Choisissez **Oui** pour configurer la mise en réseau.
9. Entrez les détails de configuration réseau provenant de la page **Détails d'unité**. 
10. Cliquez sur **Oui** lorsque vous êtes invité à redémarrer la mise en réseau. 
11. **Facultatif** : tapez `passwd root` pour définir un mot de passe root pour les connexions SSH et tapez `service ssh start` pour autoriser la connexion SSH, ce qui peut s'avérer utile si les temps de réponse de votre console KVM sont lents. 
12. Tapez `service cdp-agent restart`. Cette commande permet de démarrer l'agent Tivoli Continuous Data Protection for Files même s'il n'est pas actif. 
13. Sélectionnez **Initialiser à partir d'une image**. Un cadre s'affiche pour indiquer que l'unité est configurée pour un amorçage à partir de l'image *r1soft-cdp-bootcd-agent-4.0.0.iso*. Vous êtes invité à indiquer si vous souhaitez décharger l'image et revenir à un amorçage normal. 
14. Cliquez sur **Oui** pour que le serveur soit réamorcé à partir du disque système. 

Le serveur s'exécutera via un processus chkdsk ou fsck afin de vérifier le disque et pourra éventuellement redémarrer lui-même. Une fois le processus terminé, votre serveur ou machine virtuelle est opérationnel avec des données qui ont été restaurées à partir du point de restauration que vous avez choisi. 
