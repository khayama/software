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

# Installazione di ClamAV
{: #installing-clamav}

Utilizza questa procedura per installare ClamAV.

1. Accedi a WHM su `https://x.x.x.x:2087` (sostituisci x.x.x.x con il tuo IP server)
2. Fai clic sull'icona cPanel sul lato all'estrema destra dello schermo.
3. Fai clic sull'icona **Manage plug-ins** per visualizzare l'elenco di plug-in cPanel.
4. Nella pagina **Addon Modules**, individua **clamavconnector**. Abilita **Install and keep Updated** e fai clic su **Save** alla fine della pagina.
Il completamento dell'installazione richiede circa venti minuti.

**Note**
il controllo della versione della libreria è disabilitato per impostazione predefinita. Tuttavia, il server ha installata la zlib 1.2.2 o superiore.

La licenza è il motivo più comune per cui l'installazione di ClamAV non riesce. Il componente aggiuntivo clamav è gratuito ma devi eseguire la registrazione come una licenza professionale. Per ulteriori informazioni, vedi https://www.clamav.net/. Dopo aver eseguito correttamente la registrazione della tua licenza, ritorna al passo 4 e disinstalla e reinstalla clamavconnector.
