---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Ripristino di un server con R1Soft Tivoli Continuous Data Protection for Files

Utilizza questo processo per completare un [bare metal restore](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} a un server virtuale (VSI) {{site.data.keyword.BluSoftlayer_full}} pubblico o privato se si verifica un errore del server che causa una perdita di dati o del SO.

Vengono ripristinati tutti i blocchi del file system di cui era stato eseguito il backup, compresi il sistema operativo e gli eventuali file che non erano stati esclusi dai backup. Non seguire questo processo se desideri ripristinare un sottoinsieme di file. Per ripristinare solo i file, vedi [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Preparazione del server R1Soft Tivoli Continuous Data Protection for Files

1. Apri una finestra del browser ed esegui l'accesso al server R1Soft Tivoli Continuous Data Protection for Files (le password di IP e amministratore sono disponibili nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Fai clic su **Recovery Points** nel portale di gestione di R1Soft Tivoli Continuous Data Protection for Files.
3. Seleziona il **Server** che desideri ripristinare e il **Disk Safe** da cui desideri eseguire il ripristino.
4. Individua il punto dal quale desideri eseguire il ripristino dall'elenco dei punti di ripristino.
5. Fai clic su **Bare Metal Restore** (l'icona di scudo) per avviare il **Restoration Wizard**.
6. Fai clic su **Next** nel **Restoration Wizard**.
7. Seleziona i file system da ripristinare e fai clic su **Next**.
8. Seleziona l'host sul quale desideri eseguire il ripristino. Può essere l'host originale oppure un host differente. (Nota: i passi all'interno di questa procedura eseguono il ripristino sullo stesso server).
9. Fai clic su **Next**.
10. Scegli la configurazione di archiviazione da utilizzare (usa quella implementata sul server oppure scegline una basata sui backup).
11. Seleziona le tabelle di partizione (**Partition Tables**) che desideri utilizzare, se hai optato per la scelta del layout di file system.
12. Associa i tuoi file system ai dispositivi a blocchi corretti (come ad esempio C:\ = /dev/sda1) e fai clic su **Next**.
13. Seleziona le tue opzioni di ripristino, come ad esempio **Reboot after restore**, **Check file system after restore** e fai clic su **Next**.
14. Verifica le tue opzioni e fai clic su **Restore** oppure torna indietro per modificare le tue opzioni di ripristino.

Viene visualizzata una finestra con lo stato del ripristino corrente

## Preparazione del dispositivo per il ripristino

1. Apri una finestra del browser e accedi a [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Devices**, **Device List** e seleziona il dispositivo da ripristinare.
3. Fai clic su **Actions** e scegli **Boot from image** per visualizzare un elenco di immagini private.
4. Scegli **Public Images** dal menu.
4. Scegli l'immagine di avvio dell'agent R1Soft appropriata per la tua versione del server R1Soft (*r1soft-cdp-bootcd-server-4.0.0.iso*) e fai clic su **Boot From This Image**.
5. Fai clic su **Actions**, **KVM Console** dalla pagina Device Details per il server che stai ripristinando. Quando la console è attiva e l'immagine è stata avviata, vedi una schermata del bootloader Debian con alcune opzioni.
6. Premi **Invio** per eseguire l'avvio utilizzando l'opzione predefinita.
7. Immetti netconfig dal prompt r1soft-recovery dopo che il SO è stato avviato e premi **Invio**.
8. Scegli **Yes** per configurare la rete.
9. Immetti i dettagli di configurazione della rete dalla pagina **Device Details**.
10. Fai clic su **Yes** quando ti viene richiesto di riavviare la rete.
11. **Facoltativo**: immetti `passwd root` per impostare una password root per gli accessi SSH e immetti `service ssh` start per consentire un accesso SSH, che può essere utile se la console KVM è lenta a rispondere.
12. Immetti `service cdp-agent restart`. Questo comando avvia l'agent Tivoli Continuous Data Protection for Files anche se non è già in esecuzione.
13. Seleziona **Boot From Image**. Compare un riquadro che indica che il dispositivo è configurato per l'avvio dall'immagine *r1soft-cdp-bootcd-agent-4.0.0.iso*. Ti viene presentata una domanda relativa allo scaricamento dell'immagine e al ritorno all'avvio normale.
14. Fai clic su **Yes**; il server verrà riavviato dal disco del sistema

Il server eseguirà un processo chkdsk o fsck per verificare il disco e potrebbe riavviarsi nuovamente. Una volta completato il processo, il tuo server o la tua VM sono operativi con i dati ripristinati dal tuo punto di ripristino scelto.
