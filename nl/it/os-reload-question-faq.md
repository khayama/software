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

# Domande frequenti (FAQ, Frequently Asked Questions)
{: #faqs}

## Il sistema operativo (SO) può essere modificato sul dispositivo?
{: #can-the-operating-system-os-be-changed-on-the-device-}

Puoi modificare il tuo SO e il software che hai installato ricaricando un SO <!--[OS Reload](perform-os-reload-device.html){:new_window}-->. Dopo che hai selezionato il ricaricamento del SO sul dispositivo, il sistema visualizza un link a una pagina che ti consente di aggiornare il software sul tuo sistema. Da questa pagina, puoi aggiornare il SO, il pannello di controllo, i pacchetti antivirus e il software di database.

## Fornite dei ricaricamenti del sistema operativo gratuiti?
{: #do-you-provide-complimentary-os-reloads-}

I ricaricamenti del SO automatizzati sono gratuiti, compresi i ricaricamenti del SO personalizzati quali la modifica dei sistemi operativi, l'aggiunta o la rimozione di pannelli di controllo, la modifica delle partizioni e altre opzioni. Per ulteriori informazioni, apri il portale del cliente.

## Come posso tenere traccia dello stato del ricaricamento del SO?
{: #how-can-i-track-the-status-of-the-os-reload-}

In Hardware nel portale del cliente, c'è una sezione Notes per ciascuno dei tuoi server. La sezione Notes include dei link a informazioni relative al passo corrente del ricaricamento e il tempo stimato per completare quella parte del ricaricamento.

## Un ricaricamento del SO può cancellare i dischi secondari?
{: #can-an-os-reload-erase-secondary-disks-}

Un ricaricamento del SO formatta solo il disco primario sul sistema. Tutti gli altri dischi non subiscono alcuna variazione. Lo stesso vale quando viene eseguito un ricaricamento da un template di immagine. Se il template contiene più di un disco, viene formattato solo il disco primario. Agli altri dischi non viene apportata alcuna modifica.

## Perché la mia email cpsrvd non è riuscita?
{: #why-did-my-cpsrvd-email-fail-}

Nella maggior parte dei casi, quando ricevi una email che indica **cpsrvd failed**, essa è stata inviata immediatamente dopo un riavvio. Questo errore si verifica quando chkservd prova a convalidare il processo cpsrvd. La convalida non riesce perché il processo non è stato avviato.

Se ricevi una email dal servizio chkservd che indica la mancata riuscita di cpsrvd, nella maggior parte dei casi puoi ignorare il messaggio. Tuttavia, se ricevi 5 o più di questi messaggi di seguito o se ne ricevi più di 4 in un giorno dopo i riavvii, apri un ticket di supporto
