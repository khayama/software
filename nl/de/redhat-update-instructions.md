---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# Aktualisierungsinformationen für RedHat

IBM stellt kostenlose Aktualisierungsservices für Betriebssysteme und Software für RedHat-Umgebungen zur Verfügung.

Alle Aktualisierungsservices von IBM weisen die folgenden Funktionen auf:
* Der Datenverkehr für die Aktualisierung wird vom Server (über Ihr privates VLAN) an das private Servicenetz weitergeleitet.
* Der Datenverkehr für die Aktualisierung ist Teil der unbegrenzten Bandbreite Ihres privaten Netzes und hat keine Auswirkungen auf die öffentliche Bandbreitenzuordnungen.
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

Testen Sie Kernel- oder Service-Pack-Upgrades immer vor der Installation in Produktionsserverumgebungen. Technische Informationen in Bezug auf bestimmte Hardware, Betriebssysteme oder bereitgestellte Anwendungen finden Sie in den häufig gestellten Fragen oder im Abschnitt zu Treibern im Webportal für Kunden. IBM testet Kernel- und Service-Pack-Upgrades und postet die entsprechenden Informationen (einschließlich Treiber) zur Unterstützung des Aktualisierungsprozesses.

## RHN-Abonnement

Für RedHat-Betriebssysteme stellt IBM für die Installation von kritischen und nicht kritischen Sicherheitsupdates RedHat Network Satellite-Server bereit.

RedHat Network bei SoftLayer umfasst RHN Satellite- und Proxy-Server. Wenn der RedHat-Server bereitgestellt wird, wird er mithilfe des entsprechenden Proxy-Servers automatisch für den IBM RHN Satellite-Server registriert. Mit dieser Registrierung können Sie Befehle des Typs **up2date** lokal auf den Servern verwenden und Aktualisierungen mit Pull-Operation im gesamten privaten Servicenetz anwenden.

Um die auf das Unternehmen abgestimmte Servicequalität sicherzustellen und ein ordnungsgemäß angewendetes Change-Management-Verfahren zu ermöglichen, sind Server unter RedHat standardmäßig so konfiguriert, dass Kernelaktualisierungen übersprungen werden. Um die Systemstabilität sicherzustellen, führen Sie solche Aktualisierungen manuell nach dem Abschluss von Regressionstests durch. IBM verwendet innovative Hardwaretechnologien, für deren ordnungsgemäßen Einsatz stabile Kernel-Editionen erforderlich sind.
