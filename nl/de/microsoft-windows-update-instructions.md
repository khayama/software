---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Aktualisierungsinformationen für Microsoft Windows
IBM stellt kostenlose Aktualisierungsservices für Betriebssysteme und Software für Microsoft Windows Server-Umgebungen zur Verfügung.

Alle Aktualisierungsservices bei SoftLayer weisen die folgenden Funktionen auf:
* Der Datenverkehr für die Aktualisierung wird vom Server (über Ihr privates VLAN) an das private Servicenetz weitergeleitet.
* Der Datenverkehr für die Aktualisierung ist Teil der unbegrenzten Bandbreite Ihres privaten Netzes und hat keine Auswirkungen auf die öffentliche Bandbreitenzuordnungen.
* Geschwindigkeiten bei der Aktualisierung sind schneller als eine direkte Aktualisierung über Anbieter (aktualisierte Portgeschwindigkeiten sind bei Bedarf erhältlich).
* Aktualisierungen sind während der datenverkehrintensiven Zeiträume für kritische Aktualisierungen leicht erhältlich.
* In Notfallsituationen können öffentliche Ports beendet werden, während Aktualisierungen über das private Netz weiterhin möglich sind.
* Server sind so vorkonfiguriert, dass sie bei der Bereitstellung automatisch aktualisiert werden; gleichzeitig sind manuelle Aktualisierungen bei Bedarf verfügbar.


SoftLayer-Aktualisierungsserver weisen im privaten Servicenetz die folgenden Positionskennungen auf:

Microsoft: **wsus01.service.softlayer.com**

Testen Sie Kernel- oder Service-Pack-Upgrades immer vor der Installation in Produktionsserverumgebungen. Technische Informationen in Bezug auf bestimmte Hardware, Betriebssysteme oder von IBM bereitgestellte Anwendungen finden Sie in den häufig gestellten Fragen oder im Abschnitt zu Treibern im Webportal für Kunden. IBM Entwickler testen Kernel- und Service-Pack-Upgrades immer wieder und posten die entsprechenden Informationen (einschließlich Treiber) zur Unterstützung des Aktualisierungsprozesses.


## WSUS - Windows Server Update Services

Microsoft Windows-Server extrahieren Aktualisierungen automatisch mit Pull-Operation von lokalen WSUS-Servern (WSUS, Windows Server Update Services).

Unter Microsoft Windows-Betriebssystemen sind Server standardmäßig so konfiguriert, dass Patches sofort bei ihrer Bereitstellung heruntergeladen und installiert werden. Falls erforderlich, wird der Server automatisch erneut gestartet. Diese Aktualisierungen schützen Server vor Angriffen auf Sicherheitslücken. Wenn Sie die Aktualisierungen anders planen möchten, können Sie den Plan für die Aktualisierung über die Funktion **Windows-Updates** in der Systemsteuerung ändern.
