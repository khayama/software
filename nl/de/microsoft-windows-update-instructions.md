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

# Aktualisierungsinformationen für Microsoft Windows
{: #microsoft-windows-update-information}

IBM stellt kostenlose Aktualisierungsservices für Betriebssysteme und Software für Microsoft Windows Server-Umgebungen zur Verfügung.

Alle Aktualisierungsservices bei {{site.data.keyword.Bluemix_notm}} weisen die folgenden Funktionen auf:
* Der Datenverkehr für die Aktualisierung wird vom Server (über Ihr privates VLAN) an das private Servicenetz weitergeleitet.
* Der Datenverkehr für die Aktualisierung ist Teil der unbegrenzten Bandbreite Ihres privaten Netzes. Dieser Datenverkehr hat keine Auswirkungen auf die Zuordnungen öffentlicher Bandbreite.
* Geschwindigkeiten bei der Aktualisierung sind schneller als eine direkte Aktualisierung über Anbieter (aktualisierte Portgeschwindigkeiten sind bei Bedarf erhältlich).
* Aktualisierungen sind während der datenverkehrintensiven Zeiträume für kritische Aktualisierungen leicht erhältlich.
* In Notfallsituationen können öffentliche Ports beendet werden, während Aktualisierungen über das private Netz weiterhin möglich sind.
* Server sind so vorkonfiguriert, dass sie bei der Bereitstellung automatisch aktualisiert werden; gleichzeitig sind manuelle Aktualisierungen bei Bedarf verfügbar.


{{site.data.keyword.Bluemix_notm}}-Aktualisierungsserver weisen im privaten Servicenetz die folgenden Positionskennungen auf:

Microsoft, **wsus01.service.softlayer.com**

Testen Sie Kernel- oder Service-Pack-Upgrades immer vor der Installation in Produktionsserverumgebungen. Technische Informationen in Bezug auf bestimmte Hardware, Betriebssysteme und von IBM bereitgestellte Anwendungen finden Sie in den häufig gestellten Fragen oder im Abschnitt zu Treibern im Steuerungsportal. IBM testet Kernel- und Service-Pack-Upgrades immer wieder und postet die entsprechenden Informationen (einschließlich der Treiber) zur Unterstützung des Aktualisierungsprozesses.


## WSUS - Windows Server Update Services
{: #wsus-windows-server-update-services}

In vielen Fällen extrahieren Microsoft Windows-Server Aktualisierungen automatisch per Pull-Operation von lokalen WSUS-Servern (WSUS, Windows Server Update Services). Wenn Ihr Server jedoch mit einem cloud-init-fähigen Image bereitgestellt wird, müssen Sie möglicherweise die Windows-Registrierungsdatenbank manuell aktualisieren, um lokale {{site.data.keyword.cloud_notm}}-WSUS-Server (Windows Server Update Services) und nicht die standardmäßigen Microsoft-WSUS-Server verwenden zu können.

Wenn Sie einen virtuellen Server mit einem Windows Server-Betriebssystem ohne Add-ons bestellen, z. B. weitere Software, Bereitstellungsabschlussscripts oder erweiterte Überwachung, wird Ihr Server wahrscheinlich mit einem cloud-init-fähigen Image bereitgestellt. Weitere Informationen dazu, wie Sie Ihre Registrierungsdatenbank so aktualisieren, dass sie auf {{site.data.keyword.cloud_notm}}-WSUS-Server zeigt, finden Sie im Abschnitt zur [Aktualisierung einer Instanz für die Verwendung eines lokalen WSUS-Servers](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server).

Unter Microsoft Windows-Betriebssystemen sind Server standardmäßig so konfiguriert, dass Patches sofort bei ihrer Bereitstellung heruntergeladen und installiert werden. Falls dies erforderlich sein sollte, wird der Server automatisch erneut gestartet. Aktualisierungen werden durchgeführt, um Server vor Angriffen auf Sicherheitslücken zu schützen. Wenn Sie die Aktualisierungen anders planen möchten, können Sie den Plan für die Aktualisierung über die Funktion **Windows-Updates** in der Systemsteuerung ändern.
