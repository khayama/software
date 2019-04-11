---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Server mit R1Soft Tivoli Continuous Data Protection for Files wiederherstellen

Verwenden Sie diesen Prozess, um eine [Bare-Metal-Wiederherstellung](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} auf einen virtuellen öffentlichen oder privaten {{site.data.keyword.BluSoftlayer_full}}-Server (VSI) durchzuführen, wenn ein Serverfehler zu Daten- oder Betriebssystemverlust führt.

Alle Dateisystemblöcke, die gesichert werden, werden wiederhergestellt, einschließlich des Betriebssystems und aller Dateien, die nicht von den Sicherungen ausgeschlossen wurden. Führen Sie diesen Prozess nicht aus, wenn Sie nur eine Teilmenge von Dateien wiederherstellen möchten. Informationen zum Wiederherstellen lediglich der Dateien finden Sie unter [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## R1Soft Tivoli Continuous Data Protection for Files-Server vorbereiten

1. Öffnen Sie ein Browserfenster und melden Sie sich beim R1Soft Tivoli Continuous Data Protection for Files-Server an (IP und Administratorkennwörter sind im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} verfügbar).
2. Klicken Sie im Managementportal von R1Soft Tivoli Continuous Data Protection for Files auf **Wiederherstellungspunkte**.
3. Wählen Sie den **Server** aus, den Sie wiederherstellen möchten, sowie den **Plattentresor**, von dem aus Sie die Wiederherstellung durchführen möchten.
4. Suchen Sie in der Liste der Wiederherstellungspunkte den Punkt, von dem aus Sie die Wiederherstellung durchführen möchten.
5. Klicken Sie auf **Bare-Metal-Wiederherstellung** (Schildsymbol), um den **Wiederherstellungsassistenten** zu starten.
6. Klicken Sie im **Wiederherstellungsassistenten** auf **Weiter**.
7. Wählen Sie die Dateisysteme aus, die wiederhergestellt werden sollen, und klicken Sie auf **Weiter**.
8. Wählen Sie den Host für die Wiederherstellung aus. Es kann sich um den ursprünglichen Host oder um einen anderen Host handeln. (Hinweis: Wenn Sie die Schritte in dieser Prozedur ausführen, wird die Wiederherstellung für den jeweils selben Server durchgeführt.)
9. Klicken Sie auf **Weiter**.
10. Wählen Sie die zu verwendende Speicherkonfiguration aus (auf dem Server oder vom Backup).
11. Wählen Sie die **Partitionstabellen** aus, die Sie verwenden möchten, wenn Sie sich für das Dateisystemlayout entschieden haben.
12. Ordnen Sie Ihre Dateisysteme den richtigen Blockeinheiten zu (z. B. C:\ = /dev/sda1) und klicken Sie auf **Weiter**.
13. Wählen Sie die Wiederherstellungsoptionen wie z. B. **Warmstart nach Wiederherstellung** und **Dateisystem nach der Wiederherstellung überprüfen** aus und klicken Sie auf **Weiter**.
14. Überprüfen Sie Ihre Optionen und klicken Sie auf **Wiederherstellen** oder gehen Sie zurück, um Ihre Wiederherstellungsoptionen zu ändern.

Es wird ein Fenster mit dem Status der aktuellen Wiederherstellung angezeigt.

## Gerät zur Wiederherstellung vorbereiten

1. Öffnen Sie ein Browserfenster und navigieren Sie zum [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Klicken Sie auf **Geräte**, **Geräteliste** und wählen Sie das Gerät aus, das wiederhergestellt werden soll.
3. Klicken Sie auf **Aktionen** und wählen Sie **Aus Image starten** aus, um eine Liste der privaten Images anzuzeigen.
4. Wählen Sie **Öffentliche Images** im Menü aus.
4. Wählen Sie das entsprechende Boot-Image des R1Soft-Agenten für Ihre Version des R1Soft-Servers (*r1soft-cdp-bootcd-server-4.0.0.iso*) aus und klicken Sie auf **Aus diesem Image starten**.
5. Klicken Sie auf der Seite mit den Gerätedetails für den Server, den Sie wiederherstellen, auf **Aktionen** und **KVM-Konsole**. Wenn die Konsole aktiviert ist und das Image gestartet wird, ist eine Anzeige für das Debian-Bootladeprogramm mit einigen Optionen zu sehen.
6. Drücken Sie die Eingabetaste, um mithilfe der Standardoption einen Boot durchzuführen.
7. Geben Sie in der Eingabeaufforderung für die R1soft-Wiederherstellung 'netconfig' ein, sobald das Betriebssystem gestartet wurde, und drücken Sie die Eingabetaste.
8. Wählen Sie **Ja** aus, um den Netzbetrieb zu konfigurieren.
9. Geben Sie die Details zur Netzkonfiguration auf der Seite mit den **Gerätedetails** ein.
10. Klicken Sie auf **Ja**, wenn Sie dazu aufgefordert werden, den Netzbetrieb erneut zu starten.
11. **Optional**: Geben Sie `passwd root` ein, um ein Rootkennwort für SSH-Anmeldungen festzulegen, und geben Sie `service ssh start` ein, um die SSH-Anmeldung zu ermöglichen. Dies kann nützlich sein, wenn Ihre KVM-Konsole langsam reagiert.
12. Geben Sie `service cdp-agent restart` ein. Mit diesem Befehl wird der Tivoli Continuous Data Protection for Files-Agent gestartet, auch wenn er noch nicht aktiv ist.
13. Wählen Sie **Aus Image starten** aus. Es wird ein Rahmen angezeigt, in dem angegeben wird, dass das Gerät so konfiguriert ist, dass es von dem Image *r1soft-cdp-bootcd-agent-4.0.0.iso* aus gestartet wird. Sie werden gefragt, ob Sie das Image entladen und zum herkömmlichen Bootprozess zurückkehren möchten.
14. Klicken Sie auf **Ja**; der Server wird von der Systemplatte aus neu gestartet.

Für den Server wird ein Prozess des Typs chkdsk oder fsck durchgeführt, um die Platte zu überprüfen; der Server wird nach der Überprüfung möglicherweise neu gestartet. Nach Abschluss des Prozesses ist der Server oder die VM mit den Daten betriebsbereit, die von Ihrem ausgewählten Wiederherstellungspunkt aus wiederhergestellt wurden.
