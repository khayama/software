---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Server aus einem R1Soft-Image wiederherstellen
{: #restoring-your-server-from-an-r1soft-image}

Mithilfe dieser Prozedur können Sie eine Wiederherstellung für einen öffentlichen oder privaten {{site.data.keyword.BluVirtServers_full}} oder {{site.data.keyword.BluBareMetServers_full}} durchführen. Nutzen Sie diesen Prozess, wenn ein Serverfehler zu Daten- oder Betriebssystemverlust führt. Es werden bei diesem Prozess alle Dateisystemblöcke, die gesichert wurden, wiederhergestellt (einschließlich des Betriebssystems und aller Dateien, die nicht von den Sicherungen ausgeschlossen wurden).

Wenden Sie diesen Prozess nicht an, wenn nur eine Teilmenge der Dateien wiederhergestellt werden soll. Informationen zum Wiederherstellen lediglich der Dateien finden Sie im [R1Soft-Wiki](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Virtuelles Gerät wiederherstellen
{: #restoring-your-virtual-device}

1. Klicken Sie im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} auf das Gerät, das wiederhergestellt werden soll.
2. Klicken Sie auf das Menü **Aktionen** und wählen Sie **Aus Image starten** aus, um eine Liste der privaten Images anzuzeigen.
3. Wählen Sie **Öffentliche Images** im Menü aus.
4. Wählen Sie das entsprechende Boot-Image des R1Soft-Agenten für Ihre Version des R1Soft-Servers (serverbackup-centos-bootcd-agent.iso) aus und klicken Sie auf der rechten Seite auf den Link **Aus diesem Image starten**.
5. Klicken Sie auf der Seite mit den **Gerätedetails** für den Server, den Sie wiederherstellen möchten, auf **Aktionen** > **KVM-Konsole**.
6. Wenn die Konsole aktiviert ist und das Image gestartet wird, ist eine Anzeige für das Debian-Bootladeprogramm mit einigen Optionen zu sehen. Drücken Sie die Eingabetaste, um mithilfe der Standardoption einen Boot durchzuführen.
7. Geben Sie nach dem Booten des Betriebssystems den Befehl `netconfig` ein und drücken Sie die Eingabetaste.
8. Wählen Sie **Ja** aus, um den Netzbetrieb zu konfigurieren.
9. Geben Sie Details zur Netzkonfiguration auf der Seite mit den Gerätedetails im Steuerungsportal ein.
10. Wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden, den Netzbetrieb erneut zu starten.
11. Geben Sie optional `passed root` ein, um ein Rootkennwort für SSH-Anmeldungen festzulegen, und geben Sie 'service ssh start' ein, um die SSH-Anmeldung zu ermöglichen. Dies kann nützlich sein, wenn Ihre KVM-Konsole langsam reagiert.
12. Geben Sie `service cdp-agent restart` ein. (Mit diesem Befehl wird der Tivoli Continuous Data Protection for Files-Agent gestartet, falls er noch nicht ausgeführt wird).

## Bare-Metal-Gerät wiederherstellen
{: #restoring-your-bare-metal-device}

1. Öffnen Sie im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} ein Ticket und fordern Sie das Booten Ihres Bare-Metal-Servers im **R1Soft-Modus für Bare-Metal-Wiederherstellungen** an.
2. Melden Sie sich über die Seite mit den **Gerätedetails** für den Server, den Sie wiederherstellen möchten, bei der **IPMI-KVM-Konsole** an.
3. Wenn die Konsole aktiviert ist und das Image gestartet wird, ist eine Anzeige für das Debian-Bootladeprogramm mit einigen Optionen zu sehen. Drücken Sie die Eingabetaste, um mithilfe der Standardoption einen Boot durchzuführen.
4. Geben Sie nach dem Booten des Betriebssystems den Befehl `netconfig` ein und drücken Sie die Eingabetaste.
5. Wählen Sie **Ja** aus, um den Netzbetrieb zu konfigurieren.
6. Geben Sie Details zur Netzkonfiguration auf der Seite mit den Gerätedetails im Steuerungsportal ein.
7. Wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden, den Netzbetrieb erneut zu starten.
8. Geben Sie optional `passed root` ein, um ein Rootkennwort für SSH-Anmeldungen festzulegen, und geben Sie 'service ssh start' ein, um die SSH-Anmeldung zu ermöglichen. Dies kann nützlich sein, wenn Ihre KVM-Konsole langsam reagiert.
9. Geben Sie `service cdp-agent restart` ein. (Mit diesem Befehl wird der Tivoli Continuous Data Protection for Files-Agent gestartet, falls er noch nicht ausgeführt wird).

## R1Soft-Server und weitere Wiederherstellungsparameter und -optionen auswählen
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

Suchen Sie in der R1Soft-Dokumentation nach dem Abschnitt zum [Durchführen einer Bare-Metal-Wiederherstellung](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore).
Sie müssen den Server für die Wiederherstellung sowie das Dateisystem, Partitionstabellen und weitere Wiederherstellungsoptionen auswählen.
