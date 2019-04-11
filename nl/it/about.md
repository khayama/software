---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Informazioni sul software
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} ha una relazione strategica con i fornitori per fornire delle licenze mese dopo mese su software compatibile a 32 bit e 64 bit. Quando ordini un dispositivo, selezioni il tipo di sistema operativo e il software per il tuo dispositivo. Puoi aggiungere ulteriore software al tuo dispositivo nel {{site.data.keyword.slportal_full}} e passare a un altro sistema operativo ricaricando il SO sul tuo dispositivo esistente. Il sistema automatizzato IBM esegue il provisioning del software sul tuo server utilizzando le linee guida delle prassi ottimali di ciascun fornitore per garantire stabilità e disponibilità massime.

Vedi il seguente elenco di software correntemente supportato: [Cloud server software ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

Se hai bisogno di software che non è correntemente supportato, utilizza il tuo accesso root al server per installare e configurare la tua versione di tale software. Per ritornare a una versione supportata sul tuo dispositivo, ricarica il SO.

IBM include istruzioni o considerazioni per l'utilizzo dei prodotti nell'ambiente {{site.data.keyword.BluSoftlayer_notm}}. Per la documentazione del software, vedi la documentazione del fornitore che produce il software.

## Sistemi operativi supportati per i server virtuali IBM Cloud
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

I server virtuali IBM Cloud supportano i seguenti sistemi operativi.

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) - la modalità di avvio predefinita è PV ma puoi passare alla modalità di avvio HVM
- Ubuntu 16 (PV/HVM) - la modalità di avvio predefinita è PV ma puoi passare alla modalità di avvio HVM
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**Nota:** le dimensioni del disco di avvio variano in base al sistema operativo:<br>  
Il SO Linux supporta 25 GB e 100 GB.
Windows supporta solo 100 GB.

Per ulteriori informazioni su come passare dalla modalità di avvio PV a quella HVM e viceversa, vedi i seguenti link:
* [Modalità di avvio supportate dai guest virtuali![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Opzione di aggiunta di una modalità di avvio![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
