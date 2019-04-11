---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

keywords: Red Hat, RedHat

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Istruzioni di aggiornamento di Red Hat
{: #red-hat-update-instructions}

IBM fornisce dei servizi di aggiornamento del SO e del software per gli ambienti Red Hat gratuitamente.

Tutti i servizi di aggiornamento a IBM condividono le seguenti funzioni:
* Il traffico di aggiornamento viene instradato dal tuo server (sulla tua VLAN privata) alla rete del servizio privata
* Il traffico di aggiornamento fa parte della tua larghezza di banda privata illimitata. Questo traffico non riduce le quote di larghezza di banda pubblica.
* Le velocità degli aggiornamenti sono superiori a quelle direttamente dai fornitori (velocità delle porte aggiornate disponibili su richiesta)
* Gli aggiornamenti sono immediatamente disponibili durante i giorni di aggiornamento critici intensi a livello globale.
* In situazioni di emergenza, le porte pubbliche possono essere arrestate pur consentendo il verificarsi degli aggiornamenti sulla rete privata.
* I server sono preconfigurati per l'esecuzione dell'aggiornamento in modo automatico al momento della distribuzione, con aggiornamenti manuali disponibili su richiesta.

I server di aggiornamento IBM si trovano sulla rete del servizio privato con i seguenti identificativi di ubicazione:

|Data center|Indirizzo host del servizio|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San Jose|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapore|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Esegui sempre un test degli upgrade di kernel o service pack prima di installarli negli ambienti di produzione. Puoi trovare informazioni tecniche per hardware, SO e applicazioni specifici distribuiti nella sezione delle domande frequenti o in quella relativa ai driver all'interno del portale di controllo. 

IBM esegue dei test degli upgrade di kernel e service pack e pubblica le informazioni e i driver correlati per fornire un ausilio al tuo processo di upgrade.

## Sottoscrizione RHN
{: #rhn-subscription}

Per i sistemi operativi Red Hat, IBM fornisce i server Red Hat Network Satellite per installare aggiornamenti della sicurezza critici e non critici.

La Red Hat Network in {{site.data.keyword.Bluemix_notm}} include i server RHN Satellite e Proxy. Quando viene eseguito il provisioning del tuo server Red Hat, ne viene eseguita automaticamente la registrazione presso il server IBM RHN Satellite utilizzando il server proxy appropriato. Con questa registrazione, puoi utilizzare i comandi **up2date** in locale sui tuoi server per estrarre gli aggiornamenti nella rete del servizio privato.

Per garantire una QoS (Quality of Service) aziendale e facilitare delle tecniche di gestione delle modifiche appropriate, i server del SO Red Hat sono configurati per impostazione predefinita per ignorare gli aggiornamenti del kernel. Per garantire la stabilità del sistema, completa i tuoi upgrade del kernel manualmente dopo che hai completato l'esecuzione del test di regressione. IBM utilizza tecnologie hardware all'avanguardia che richiedono delle edizioni del kernel stabili per un corretto funzionamento.
