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

# Anweisungen zur Aktualisierung von Red Hat
{: #red-hat-update-instructions}

IBM stellt kostenlose Aktualisierungsservices für Betriebssysteme und Software für Red Hat-Umgebungen zur Verfügung.

Alle Aktualisierungsservices von IBM weisen die folgenden Funktionen auf:
* Der Datenverkehr für die Aktualisierung wird vom Server (über Ihr privates VLAN) an das private Servicenetz weitergeleitet.
* Der Datenverkehr für die Aktualisierung ist Teil der unbegrenzten Bandbreite Ihres privaten Netzes. Dieser Datenverkehr hat keine Auswirkungen auf die Zuordnungen öffentlicher Bandbreite.
* Geschwindigkeiten bei der Aktualisierung sind schneller als eine direkte Aktualisierung über Anbieter (aktualisierte Portgeschwindigkeiten sind bei Bedarf erhältlich).
* Aktualisierungen sind während der datenverkehrintensiven Zeiträume für kritische Aktualisierungen leicht erhältlich.
* In Notfallsituationen können öffentliche Ports beendet werden, während Aktualisierungen über das private Netz weiterhin möglich sind.
* Server sind so vorkonfiguriert, dass sie bei der Bereitstellung automatisch aktualisiert werden; gleichzeitig sind manuelle Aktualisierungen bei Bedarf verfügbar.

IBM Aktualisierungsserver weisen im privaten Servicenetz die folgenden Positionskennungen auf:

|Rechenzentrum|Hostadresse des Service|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San Jose|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapur|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Testen Sie Kernel- oder Service-Pack-Upgrades immer vor der Installation in Produktionsumgebungen. Technische Informationen in Bezug auf bestimmte Hardware, Betriebssysteme und bereitgestellte Anwendungen finden Sie in den häufig gestellten Fragen oder im Abschnitt zu Treibern im Steuerungsportal.

IBM testet Kernel- und Service-Pack-Upgrades und postet die entsprechenden Informationen und Treiber zur Unterstützung des Aktualisierungsprozesses.

## RHN-Abonnement
{: #rhn-subscription}

Für Red Hat-Betriebssysteme stellt IBM für die Installation von kritischen und nicht kritischen Sicherheitsupdates Red Hat Network Satellite-Server bereit.

Red Hat Network bei {{site.data.keyword.Bluemix_notm}} umfasst RHN Satellite- und Proxy-Server. Wenn der Red Hat-Server bereitgestellt wird, wird er mithilfe des entsprechenden Proxy-Servers automatisch für den IBM RHN Satellite-Server registriert. Mit dieser Registrierung können Sie Befehle des Typs **up2date** lokal auf den Servern verwenden und Aktualisierungen mit Pull-Operation im gesamten privaten Servicenetz anwenden.

Um die auf das Unternehmen abgestimmte Servicequalität sicherzustellen und ein ordnungsgemäß angewendetes Change-Management-Verfahren zu ermöglichen, sind Red Hat-Betriebssystemserver standardmäßig so konfiguriert, dass Kernelaktualisierungen übersprungen werden. Um die Systemstabilität sicherzustellen, führen Sie Ihre Kernelaktualisierungen manuell nach dem Abschluss der Regressionstests durch. IBM verwendet innovative Hardwaretechnologien, für deren ordnungsgemäßen Einsatz stabile Kernel-Editionen erforderlich sind.
