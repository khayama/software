---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

keywords: ClamAV

subcollection: software
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Installation de ClamAV
{: #installing-clamav}

Suivez cette procédure pour installer ClamAV.

1. Connectez-vous à WHM à l'adresse `https://x.x.x.x:2087` (remplacez x.x.x.x par l'adresse IP de votre serveur)
2. Cliquez sur l'icône cPanel à droite l'écran. 
3. Cliquez sur l'icône **Manage plug-ins** pour afficher la liste des plug-in cPanel. 
4. Sur la page **Addon Modules**, localisez l'entrée **clamavconnector**. Activez l'option **Install and keep Updated** et cliquez sur **Save** en bas de la page.
L'installation dure environ vingt minutes.

**Remarques :**
la vérification de la version de bibliothèque est désactivée par défaut. Toutefois, la version zlib 1.2.2 (ou ultérieure) est installée sur le serveur.

Une question de licence est la raison la plus fréquente de l'échec de l'installation de ClamAV. Le module clamav est gratuit, toutefois, vous devez vous enregistrer pour une licence professionnelle. Pour plus d'informations, voir https://www.clamav.net/. Après avoir enregistré correctement votre licence, revenez à l'étape 4, désinstallez, puis réinstallez clamavconnector.
