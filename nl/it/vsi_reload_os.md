---



copyright:
  years: 2017
lastupdated: "2017-09-25"

keywords: OS Reload, operating system

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

#  Ricaricamento del SO
{: #reloading-the-os}

Puoi ricaricare il sistema operativo (SO) su un dispositivo in qualsiasi momento per ripristinarlo al suo ordine di lavoro originale o per riconfiguralo con un software differente. Un ricaricamento SO rimuove tutti i dati dal dispositivo e applica una configurazione "come nuova", come specificato durante il processo di configurazione dell'impostazione del ricaricamento del SO. Poiché i ricaricamenti del SO cancellano tutti i dati dal dispositivo, se non era stato eseguito un backup dei dati prima del ricaricamento, essi verranno eliminati in modo permanente e non potranno essere recuperati.
{:shortdesc}

**Importante:** se desideri conservare i tuoi dati, esegui il backup di tutti i dati prima di eseguire un ricaricamento del SO.

## Ricarica il SO
{: #reload-the-os}

1. Da **Device List**, fai clic sul server che ha bisogno di un ricaricamento del SO per visualizzare la pagina Device Details.
2. Dal menu **Actions**, seleziona **OS Reload**.
3. Determina se desideri ricaricare la configurazione esistente o ricaricare il dispositivo con una nuova configurazione.

   <table>
   <CAPTION>Tabella 1. Opzioni di ricaricamento del SO</CAPTION>
   <THEAD>
   <TR>
   <th>Tipo di ricaricamento</th>
   <th>Passi</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Se desideri ricaricare una nuova configurazione...</td>
   <td>
   <ol>
   <li>Fai clic su <b>Edit</b> per la categoria che richiede un aggiornamento.</li>
   <li>Seleziona il nuovo software da applicare al dispositivo dall'elenco a discesa <i>Select Software</i>.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Se desideri ricaricare la configurazione esistente...</td>
   <td>Procedi al passo successivo.</td>
   </tr>
   </TBODY>
   </table>

4. Determina se applicare uno script di post-installazione dopo l'esecuzione del provisioning del dispositivo.

   Se desideri applicare uno script di post-installazione, seleziona lo script dall'elenco a discesa Existing Script oppure immetti l'URL completo per il nuovo script. Altrimenti, procedi al passo successivo.

5. Per i dispositivi fisici, determina se aggiungere o rimuovere le partizioni installate o se devono rimanere invariate.

   <table>
   <CAPTION>Tabella 2. Opzioni di azione di partizione</CAPTION>
   <THEAD>
   <TR>
   <th>Azione di partizione</th>
   <th>Passi</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Per aggiungere le partizioni installate...</td>
   <td>
   <ul>
   <li>Fai clic sul link <b>Add Another Partition</b>.</li>
   <li>Immetti il nome esatto della partizione.</li>
   <li>Immetti la dimensione della partizione (in GB). Se vuoi, puoi selezionare Grow per espandere la partizione per riempire lo spazio su disco rimanente.
   <p><b>Nota:</b> può essere selezionata solo una partizione per l'espansione alla volta. Questa partizione è più grande della dimensione specificata e riempie tutta la capacità disponibile. La capacità della partizione di espansione (Grow) viene calcolata sottraendo la dimensione combinata di tutte le partizioni dal numero di capacità totale (Total Capacity) di cui è stato eseguito il provisioning nella sezione delle partizioni installate (Installed Partitions).</p>
   </li>
   </ul>
   </td>
   </tr>
   <tr>
   <td>Per eliminare le partizioni installate...</td>
   <td>Fai clic su <b>Delete</b> per eliminare la partizione.</td>
   </tr>
   <tr>
   <td>Per non modificare...</td>
   <td>Procedi al passo successivo.</td>
   </tr>
   </TBODY>
   </table>

6. Determina se applicare una o più chiavi SSH al dispositivo.

7. Seleziona le caselle di spunta applicabili per le opzioni che desideri applicare al dispositivo durante o dopo il ricaricamento del SO.

   **Nota:** le opzioni variano in base al dispositivo. Non tutte le opzioni sono disponibili per ogni dispositivo.

8. Fai clic su **Reload Above Configuration** per procedere alla revisione. Fai clic su **Cancel** per annullare le modifiche al dispositivo e uscire dalla schermata.

9. Verifica che tutti i dettagli nella sezione Nuova configurazione siano corretti.  

10. Fai clic su **Confirm OS Reload** per confermare e avviare il ricaricamento del SO. Fai clic su **Cancel** per annullare l'azione.

## Operazioni successive
{: #what-s-next-reloading-the-os}

Dopo che avrai avviato il processo di ricaricamento del SO, il dispositivo verrà portato offline e il processo di ricaricamento del SO inizierà.
Il periodo di durata del ricaricamento SO varia in base alla configurazione nuova o corrente del dispositivo.
Durante il processo di configurazione, il tempo minimo del ricaricamento del SO viene visualizzato in ogni schermata.
Il periodo di tempo visualizzato è una stima generata dal sistema. Se il ricaricamento impiega più di 24 ore, contatta il supporto IBM.

Quando il dispositivo ritorna online, funziona come specificato nella nuova configurazione per il ricaricamento del SO. Tutti i dati precedentemente salvati sul dispositivo vanno perduti ma possono essere ripristinati se avevi creato un backup del dispositivo prima del ricaricamento del SO. Se non era stato eseguito il backup dei dati, non sarà possibile ripristinarli.

Occorrerà eseguire nuovamente la registrazione del tuo dispositivo presso eVault.
