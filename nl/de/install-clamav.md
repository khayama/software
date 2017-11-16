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

# ClamAV installieren

Führen Sie für die Installation von ClamAV die folgenden Schritte aus.

1. Melden Sie sich über 'https://x.x.x.x:2087' (ersetzen Sie x.x.x.x mit der Server-IP) bei WHM an.
2. Klicken Sie ganz rechts in der Anzeige auf das Symbol für cPanel.
3. Klicken Sie auf das Symbol **Plug-ins verwalten**, um eine Liste der cPanel-Plug-ins anzuzeigen.
4. Suchen Sie auf der Seite mit den Add-on-Modulen nach dem Modul **clamavconnector**. Aktivieren Sie die Option zum Installieren und ständigen Aktualisieren und klicken Sie unten auf der Seite auf **Speichern**.
Die Installation dauert etwas 20 Minuten.

**Hinweise**
Das Überprüfen der Bibliotheksversion ist standardmäßig inaktiviert. Auf dem Server sollte jedoch mindestens zlib Version 1.2.2 installiert sein.

Probleme bei der Lizenzierung ist einer der häufigsten Gründe, warum die ClamAV-Installation fehlschlägt. Das Add-on 'clamav' ist zwar kostenlos, Sie müssen das Programm jedoch als professionelle Lizenz registrieren. Weitere Informationen finden Sie unter 'https://www.clamav.net/'. Kehren Sie nach der ordnungsgemäßen Registrierung der Lizenz zu Schritt 4 zurück, deinstallieren Sie 'clamavconnector' und installieren Sie das Programm dann erneut.
