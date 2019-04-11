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

# Informationen zu Software
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} hat strategische Beziehungen zu Anbietern, um Lizenzen auf Monatsbasis für mit 32-Bit und 64-Bit kompatibler Software zur Verfügung zu stellen.  Bei der Bestellung eines Geräts wählen Sie das Betriebssystem und die Software für das Gerät aus. Sie können im {{site.data.keyword.slportal_full}} weitere Software zum Gerät hinzufügen und zu einem anderen Betriebssystem wechseln, indem Sie das Betriebssystem auf dem vorhandenen Gerät erneut laden. Das automatisierte IBM System stellt unter Verwendung von Best Practices-Richtlinien der entsprechenden Anbieter Software auf dem Server bereit, um maximale Stabilität und Verfügbarkeit sicherzustellen.

Ziehen Sie die Liste der derzeit unterstützten Software zurate: [Cloud server software ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

Wenn Sie Software benötigen, die aktuell nicht unterstützt wird, installieren und konfigurieren Sie mithilfe des Rootzugriffs für den Server Ihre eigene Version dieser Software.  Um zu einer unterstützten Version auf dem Gerät zurückzukehren, laden Sie das Betriebssystem erneut.

IBM stellt Anweisungen bzw. Hinweise zur Verwendung von Produkten in der {{site.data.keyword.BluSoftlayer_notm}}-Umgebung bereit. Informationen zur Software finden Sie in der Dokumentation des Software-Herstellers.

## Unterstützte Betriebssysteme für virtuelle IBM Cloud-Server
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

Die virtuellen IBM Cloud-Server unterstützen die folgenden Betriebssysteme.

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) verwendet standardmäßig den PV-Bootmodus, Sie können aber zum HVM-Bootmodus umschalten
- Ubuntu 16 (PV/HVM) verwendet standardmäßig den PV-Bootmodus, Sie können aber zum HVM-Bootmodus umschalten
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**Hinweis:** Die Größen der Bootplatten variieren nach Betriebssystem:<br>  
Linux OS unterstützt 25 GB und 100 GB.
Windows unterstützt nur 100 GB.

Für weitere Informationen zum Umschalten zwischen dem PV- und dem HVM-Bootmodus verwenden Sie die folgenden Links:
* [Virtual guest supported boot modes ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Add boot mode option ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
