---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

keywords: Microsoft Windows Update, software update services

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Informazioni sull'aggiornamento di Microsoft Windows
{: #microsoft-windows-update-information}

IBM fornisce dei servizi di aggiornamento del SO e del software per gli ambienti Microsoft Windows Server gratuitamente.

Tutti i servizi di aggiornamento a {{site.data.keyword.Bluemix_notm}} condividono le seguenti funzioni:
* Il traffico di aggiornamento viene instradato dal tuo server (sulla tua VLAN privata) alla rete del servizio privata
* Il traffico di aggiornamento fa parte della tua larghezza di banda privata illimitata. Questo traffico non riduce le quote di larghezza di banda pubblica.
* Le velocità degli aggiornamenti sono superiori a quelle direttamente dai fornitori (velocità delle porte aggiornate disponibili su richiesta)
* Gli aggiornamenti sono immediatamente disponibili durante i giorni di aggiornamento critici intensi a livello globale.
* In situazioni di emergenza, le porte pubbliche possono essere arrestate pur consentendo il verificarsi degli aggiornamenti sulla rete privata.
* I server sono preconfigurati per l'esecuzione dell'aggiornamento in modo automatico al momento della distribuzione, con aggiornamenti manuali disponibili su richiesta.


I server di aggiornamento {{site.data.keyword.Bluemix_notm}} si trovano sulla rete del servizio privato con i seguenti identificativi di ubicazione.

Microsoft, **wsus01.service.softlayer.com**

Esegui sempre un test degli upgrade di kernel o service pack prima di installarli negli ambienti server di produzione. Puoi trovare le informazioni tecniche correlate a hardware, SO e applicazioni specifici distribuiti da IBM nella sezione delle domande frequenti o in quella relativa ai driver all'interno del portale di controllo. IBM esegue costantemente dei test degli upgrade di kernel e service pack e pubblica le informazioni correlate (compresi i driver) per assistere nel processo di upgrade.


## Servizi di aggiornamento del server Windows WSUS
{: #wsus-windows-server-update-services}

In molti casi, i server Microsoft Windows estraggono automaticamente gli aggiornamenti dai server WSUS (Windows Server Update Services) locali. Tuttavia, se per il tuo server è necessario eseguire il provisioning di un'immagine abilitata a cloud-init, potresti dover aggiornare manualmente il registro Windows per utilizzare i server WSUS (Windows Server Update Services) {{site.data.keyword.cloud_notm}} locali invece dei server Microsoft WSUS predefiniti.

Se ordini un server virtuale con un sistema operativo Windows Server senza alcun componente aggiuntivo, come ad esempio dell'altro software, degli script di post-provisioning o un monitoraggio avanzato, è probabile che il provisioning del tuo server venga eseguito con un'immagine cloud-init. Per ulteriori informazioni sull'aggiornamento del tuo registro perché punti ai server WSUS {{site.data.keyword.cloud_notm}}, vedi [Aggiornamento di un'istanza per utilizzare un server WSUS locale](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server).

Per i sistemi operativi Microsoft Windows, i server sono configurati per impostazione predefinita per scaricare e installare le patch appena diventano disponibili. Il server viene riavviato automaticamente, se è necessario un riavvio. Gli aggiornamenti vengono completati per proteggere i server da vulnerabilità cruciali. Se preferisci pianificare i tuoi aggiornamenti diversamente, puoi modificare la pianificazione degli aggiornamenti mediante la funzione **Aggiornamenti di Windows** nel pannello di controllo.
