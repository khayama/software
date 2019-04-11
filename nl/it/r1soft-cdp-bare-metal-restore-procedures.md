---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Ripristino del tuo server da un'immagine R1Soft
{: #restoring-your-server-from-an-r1soft-image}

Utilizza questa procedura per completare un ripristino a {{site.data.keyword.BluVirtServers_full}} o {{site.data.keyword.BluBareMetServers_full}} pubblici o privati. Utilizza questo processo se un errore del server causa una perdita di dati o del sistema operativo. Questo processo ripristina tutti i blocchi del file system di cui era stato eseguito il backup (compresi il sistema operativo e gli eventuali file che non erano stati esclusi dai backup).

Non utilizzare questo processo se l'obiettivo è il ripristino di un sottoinsieme di file. Per ripristinare solo i file, vedi il [wiki di R1Soft](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Ripristino del tuo dispositivo virtuale
{: #restoring-your-virtual-device}

1. Fai clic sul dispositivo che desideri ripristinare nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic sul menu **Actions** e scegli **Boot from image**; ottieni un elenco delle immagini private.
3. Scegli **Public Images** dal menu.
4. Scegli l'immagine di avvio dell'agent R1Soft appropriata per la tua versione del server R1Soft (serverbackup-centos-bootcd-agent.iso) e fai clic sul link **Boot From This Image** sulla destra.
5. Dalla pagina **Device Details** per il server che stai ripristinando, fai clic su **Actions** > **KVM Console**.
6. Quando la console è attiva e l'immagine è avviata, vedrai una schermata del bootloader Debian con alcune opzioni.Premere il tasto Invio per eseguire l'avvio dall'opzione predefinita.
7. Dopo che il SO è stato avviato, immetti `netconfig` e premi **Invio**.
8. Scegli **Yes** per configurare la rete.
9. Immetti i dettagli di configurazione della rete dai dettagli del dispositivo nel portale di controllo.
10. Scegli **Yes** quando ti viene richiesto di riavviare la rete.
11. Facoltativamente, immetti `passed root` per impostare una password root per gli accessi SSH e immetti service ssh start per consentire l'accesso SSH. Questo passo potrebbe essere utile se la tua console KVM è lenta.
12. Immetti `service cdp-agent restart` (questo comando avvia l'agent Tivoli Continuous Data Protection for Files se non è già in esecuzione).

## Ripristino del tuo dispositivo bare metal
{: #restoring-your-bare-metal-device}

1. Apri un ticket nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e richiedici di avviare il tuo server bare metal in **modalità R1Soft Bare Metal Restore**.
2. Utilizzando la pagina **Device Details** per il server che stai ripristinando, esegui l'accesso alla **console IPMI KVM**.
3. Quando la console è attiva e l'immagine è avviata, vedrai una schermata del bootloader Debian con alcune opzioni.Premere il tasto Invio per eseguire l'avvio dall'opzione predefinita.
4. Dopo che il SO è stato avviato, immetti `netconfig` e premi **Invio**.
5. Scegli **Yes** per configurare la rete.
6. Immetti i dettagli di configurazione della rete dai dettagli del dispositivo nel portale di controllo.
7. Scegli **Yes** quando ti viene richiesto di riavviare la rete.
8. Facoltativamente, immetti `passed root` per impostare una password root per gli accessi SSH e immetti service ssh start per consentire l'accesso SSH. Questo passo potrebbe essere utile se la tua console KVM è lenta.
9. Immetti `service cdp-agent restart` (questo comando avvia l'agent Tivoli Continuous Data Protection for Files se non è già in esecuzione).

## Selezione del server R1Soft e altri parametri e opzioni di ripristino
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

Fai riferimento alla documentazione diR1Soft per [eseguire un Bare Metal Restore](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)
Devi selezionare il server da ripristinare e selezionare il file system, le tabelle di porzione e altre opzioni di ripristino.
