---

copyright:
  years: 2017
lastupdated: "2017-09-25"

keywords: image template, OS Reload, operating system

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Ricaricamento di un SO utilizzando un template di immagine
{: #reloading-an-os-using-an-image-template}

## Differenze tra un ricaricamento del SO standard e un ricaricamento da un template di immagine
{: #differences-between-a-standard-os-reload-and-a-reload-from-an-image-template}

Durante il processo di ricaricamento del SO standard, selezioni le opzioni di configurazione per il dispositivo singolarmente. Quando esegui il ricaricamento da un template di immagine, la configurazione viene caricata esattamente come si presenta nel template di immagine.

In un ricaricamento da un template di immagine, puoi ancora aggiungere funzioni prima di ricaricare il SO.

Utilizza la seguente procedura per ricaricare un SO da un template di immagine utilizzando la funzione Carica da immagine nel portale del cliente.

**Importante:** se desideri conservare i tuoi dati, esegui il backup di tutti i dati prima di ricaricare il SO. I ricaricamenti del SO cancellano tutti i dati dal dispositivo; pertanto, se non avevi eseguito un backup dei dati prima del ricaricamento, essi verranno eliminati in modo permanente e non potranno essere recuperati.
{:shortdesc}

##Ricarica un SO
{: #reload-an-os}

1. Da **Device List**, fai clic sul server che ha bisogno di un ricaricamento del SO per visualizzare la pagina Device Details.
2. Dal menu **Actions**, seleziona **Load from Image**.
3. Seleziona la casella di spunta relativa al template di immagine da caricare sul dispositivo.

   **Nota:** prima di completare il ricaricamento, il template di immagine viene copiato nel data center che contiene il dispositivo, se non si trova già nello stesso data center. Se il template di immagine deve essere copiato nel data center, potrebbe essere addebitata una tariffa se il template non viene eliminato dall'ubicazione dopo il ricaricamento del SO.

4. Determina se desideri aggiungere delle funzioni. Tutte le funzioni che selezioni vengono aggiunte al dispositivo come parte del processo di ricaricamento.

   <table>
   <CAPTION>Tabella 1. Funzioni facoltative</CAPTION>
   <THEAD>
   <TR>
   <th>Funzioni facoltative</th>
   <th>Passi</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   </tr>
   <tr>
   <td>Sì, voglio aggiungere funzioni facoltative.</td>
   <td>
   <ol>
   <li>Fai clic su <b>Load Selected Image</b>.</li>
   <li>Esamina la configurazione dell'immagine e procedi o annulla.</li>
   <li>Fai clic su <b>Confirm OS Reload</b> per confermare l'azione e avviare il processo di ricaricamento del SO.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>No, non voglio aggiungere funzioni facoltative.</td>
   <td>Fai clic su <b>View Optional Features</b>.</td>
   </tr>
   </TBODY>
   </table>

5. Configura le opzioni, come pertinente. Fai riferimento alla seguenti informazioni per ulteriori dettagli.

   <dl>
   <dt>Post Install script</dt>
   <dd>Aggiunge uno script di post-installazione esistente o nuovo.</dd>
   <dt>SSH key</dt>
   <dd>Aggiunge una chiave SSH al dispositivo al momento dell'azione di ricaricamento.</dd>
   <dt>Reset IPMI Password</dt>
   <dd> Questa opzione è disponibile solo per i dispositivi fisici.</dd>
   <dt>Applica gli upgrade del BIOS della scheda di sistema</dt>
   <dd>Questa opzione è disponibile solo per i dispositivi fisici.</dd>
   <dt>Applica gli aggiornamenti firmware per tutti i dischi rigidi</dt>
   <dd>Questa opzione è disponibile solo per i dispositivi fisici.</dd>
   <dt>Add to Spare Pool after OS Reload</dt>
   <dd>Questa opzione è disponibile solo per i dispositivi fisici e richiede un'approvazione interna prima che sia disponibile su un account.</dd>
   <dt>Erase all hard disks</dt>
   <dd> Questa opzione è disponibile solo per i dispositivi fisici e richiede autorizzazioni utente speciali impostate dall'amministratore dell'account.</dd>
   <dt>OS Reload with Disk Preservation</dt>
   <dd>Conserva tutti i dati sul disco primario corrente durante il processo di ricaricamento del SO. La conservazione del disco converte l'unità primaria in un dispositivo di archiviazione portatile. Questa opzione è disponibile solo sui dispositivi virtuali e comporta degli addebiti basati sui modelli di fatturazione (oraria o mensile) del dispositivo. Gli addebiti potrebbero essere annullati procedendo all'annullamento del dispositivo di archiviazione portatile in qualsiasi momento dopo la sua creazione.</dd>
   </dl>

6. Fai clic su **Load Selected Image**.

7. Esamina la configurazione dell'immagine e fai clic su **Next** per procedere alla schermata successiva o su **Cancel** per annullare l'azione.

   **Nota:** dopo che fai clic su **Next**, tutte le porte di rete per il dispositivo vengono sistematicamente arrestate e il dispositivo non è disponibile per un massimo di 15 minuti. Durante questo tempo, l'azione può venire annullata in qualsiasi momento facendo clic su **Cancel**. Il passo successivo deve essere completato entro 15 minuti facendo clic su **Next**, altrimenti occorrerà completare nuovamente i passi precedenti. Questo processo è implementato come misura di sicurezza per garantire che a un dispositivo non vengano aggiunti ulteriori dati tra la conferma della configurazione e l'avvio del ricaricamento del SO.

8. Fai clic su **Confirm OS Reload** per confermare l'azione e avviare il processo di ricaricamento del SO. Fai clic su **Cancel** per annullare l'azione.

## Operazioni successive
{: #what-s-next-reloading-an-os-using-an-image-template}

Dopo che avrai avviato il processo di ricaricamento del SO, il dispositivo verrà portato offline e il processo di ricaricamento del SO inizierà.
Il periodo di durata del ricaricamento SO varia in base alla configurazione nuova o corrente del dispositivo.
Durante il processo di configurazione, il tempo minimo del ricaricamento del SO viene visualizzato in ogni schermata.
Il periodo di tempo visualizzato è una stima fatta dal sistema e viene fornita a titolo di cortesia. Se il ricaricamento impiega più di 24 ore, contatta il supporto IBM.

Quando il dispositivo ritorna online, funziona come specificato nella nuova configurazione per il ricaricamento del SO. Tutti i dati precedentemente salvati sul dispositivo vanno perduti ma possono essere ripristinati se era stato effettuato un backup del dispositivo prima del suo ricaricamento. Se non era stato eseguito il backup dei dati, non sarà possibile ripristinarli.

Occorrerà eseguire nuovamente la registrazione del tuo dispositivo presso eVault.
