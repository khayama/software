---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Installation de ClamAV

Suivez cette procédure pour installer ClamAV.

1. Connectez-vous à WHM à l'adresse https://x.x.x.x:2087 (remplacez x.x.x.x par l'adresse IP de votre serveur)
2. Cliquez sur l'icône cPanel sur le coin droit de l'écran.
3. Cliquez sur l'icône **Manage Plugins** pour afficher la liste des plug-in cPanel.
4. Sur la page **Addon Modules**, localisez l'entrée **clamavconnector**. Activez l'option **Install and keep Updated** et cliquez sur **Save** en bas de la page.
L'installation devrait prendre environ vingt minutes.

**Remarques :**
la vérification de la version de bibliothèque est désactivée par défaut. Toutefois, la version zlib 1.2.2 (ou ultérieure) devrait être installée sur le serveur.

Une question de licence est la raison la plus fréquente de l'échec de l'installation de ClamAV. Le module clamav est gratuit, toutefois vous devez vous enregistrer pour une licence professionnelle. Pour plus d'informations, reportez-vous au site https://www.clamav.net/. Après avoir enregistré correctement votre licence, revenez à l'étape 4, désinstallez, puis réinstallez clamavconnector.
