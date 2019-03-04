---



copyright:
  years: 2017
lastupdated: "2017-09-25"

subcollection: software


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Betriebssystem mithilfe einer Imagevorlage neu laden

## Unterschiede zwischen dem erneuten Laden des Betriebssystems als Standardverhalten und dem erneuten Laden über eine Imagevorlage
Während des erneuten Ladens des Betriebssystems als Standardverhalten können Sie einzelne Konfigurationsoptionen für das Gerät auswählen. Beim Laden über eine Imagevorlage wird die Konfiguration genau so geladen, wie sie in der Imagevorlage gespeichert ist. 

Bei einem erneuten Laden über eine Imagevorlage können Sie noch Funktionen hinzufügen, bevor Sie das Betriebssystem erneut laden.

Laden Sie anhand der folgenden Schritte ein Betriebssystem von einer Imagevorlage erneut, indem Sie die Funktion zum Laden von einem Image im Kundenportal verwenden.

**Wichtig:** Wenn Sie alle Daten beibehalten möchten, sichern Sie die Daten vor dem erneuten Laden des Betriebssystems. Da bei diesem Ladevorgang alle Daten vom Gerät gelöscht werden, werden die Daten permanent entfernt und können nicht mehr abgerufen werden, falls die Daten vor dem erneuten Laden nicht gesichert wurden.
{:shortdesc}

##Betriebssystem erneut laden
1. Klicken Sie in der **Geräteliste** auf den Server, für den das Betriebssystem erneut geladen werden muss, um die Seite mit den Gerätedetails anzuzeigen.
2. Wählen Sie aus dem Menü **Aktionen** die Option **Von Image laden** aus.
3. Wählen Sie das Kontrollkästchen für die Imagevorlage aus, die auf das Gerät geladen werden soll.

   **Hinweis:** Vor dem Abschluss des erneuten Ladens wird die Imagevorlage, falls sie sich nicht bereits dort befindet, in das Rechenzentrum kopiert, in dem sich das Gerät befindet. Wenn die Imagevorlage in das Rechenzentrum kopiert werden muss, kann eine Gebühr anfallen, falls die Vorlage nach dem erneuten Laden des Betriebssystems nicht aus der Speicherposition gelöscht wird.
  
4. Legen Sie fest, ob Sie Funktionen hinzufügen möchten. Alle von Ihnen ausgewählten Funktionen werden im Rahmen des erneuten Ladeprozesses zum Gerät hinzugefügt.
   
   <table>
   <CAPTION>Tabelle 1. Optionale Funktionen</CAPTION>
   <THEAD>
   <TR>
   <th>Optionale Funktionen</th>
   <th>Schritte</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   </tr>
   <tr>
   <td>Ja, ich möchte optionale Funktionen hinzufügen.</td>
   <td>
   <ol>
   <li>Klicken Sie auf <b>Ausgewähltes Image laden</b>.</li>
   <li>Überprüfen Sie die Imagekonfiguration und fahren Sie entweder fort oder brechen Sie den Vorgang ab.</li>
   <li>Klicken Sie auf <b>Erneutes Laden des Betriebssystems bestätigen</b>, um die Aktion zu bestätigen und den Vorgang zu starten.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Nein, ich möchte keine zusätzlichen Funktionen hinzufügen.</td>
   <td>Klicken Sie auf <b>Optionale Funktionen anzeigen</b>.</td>
   </tr>
   </TBODY>
   </table>

5. Konfigurieren Sie die Optionen wie gewünscht. Nachfolgend finden Sie hierzu weitere Details.
   
   <dl>
   <dt>Script nach Installationsabschluss</dt>
   <dd>Fügt ein vorhandenes oder neues Script nach Installationsabschluss hinzu.</dd>
   <dt>SSH-Schlüssel</dt>
   <dd>Fügt beim erneuten Laden einen SSH-Schlüssel zum Gerät hinzu. </dd>
   <dt>IPMI-Kennwort zurücksetzen</dt>
   <dd> Diese Option ist nur für physische Geräte verfügbar. </dd>
   <dt>BIOS-Upgrades für Systemplatine anwenden</dt>
   <dd>Diese Option ist nur für physische Geräte verfügbar. </dd>
   <dt>Firmware-Updates für alle Festplatten anwenden</dt>
   <dd>Diese Option ist nur für physische Geräte verfügbar. </dd>
   <dt>Ersatzpool nach erneutem Laden des Betriebssystems hinzufügen</dt>
   <dd>Diese Option ist nur für physische Geräte verfügbar und bedarf einer internen Genehmigung, bevor sie für ein Konto verfügbar ist.</dd>
   <dt>Alle Festplatten löschen</dt>
   <dd> Diese Option ist nur für physische Geräte verfügbar und bedarf besonderer Benutzerberechtigungen, die durch den Administrator des entsprechenden Kontos festgelegt werden.</dd>
   <dt>Erneutes Laden des Betriebssystems mit Beibehaltung auf Platte</dt>
   <dd>Behält alle Daten auf der aktuellen primären Platte während des erneuten Ladens des Betriebssystems bei. Bei dieser Beibehaltung wird das primäre Laufwerk in eine portierbare Speichereinheit umgewandelt. Diese Option steht nur auf virtuellen Einheiten zur Verfügung und basierend auf den Berechnungsmustern (stündlich oder monatlich) für das Gerät fallen entsprechende Gebühren an. Diese Gebühren müssen an dem Punkt nicht weiter gezahlt werden, an dem Sie die portierbare Speichereinheit nicht weiter verwenden möchten.</dd>
   </dl>

6. Klicken Sie auf **Ausgewähltes Image laden**.

7. Überprüfen Sie die Imagekonfiguration und klicken Sie auf **Weiter**, um die nächste Anzeige aufzurufen, oder auf **Abbrechen**, um die Aktion abzubrechen.

   **Hinweis:** Nachdem Sie auf **Weiter** geklickt haben, werden alle Netzports für das Gerät systematisch beendet und das Gerät ist für bis zu 15 Minuten nicht verfügbar. Während dieser Zeit kann die Aktion jederzeit durch Klicken auf **Abbrechen** abgebrochen werden. Der nächste Schritt muss innerhalb von 15 Minuten nach dem Klicken auf **Weiter** erfolgen oder die vorherigen Schritte müssen erneut durchgeführt werden. Dieser Prozess fungiert als Absicherung, um sicherzustellen, dass zwischen dem Bestätigen der Konfiguration und dem erneuten Laden des Betriebssystems keine zusätzlichen Daten zum Gerät hinzugefügt werden.

8. Klicken Sie auf **Erneutes Laden des Betriebssystems bestätigen**, um die Aktion zu bestätigen und den Vorgang zu starten. Klicken Sie auf **Abbrechen**, um die Aktion abzubrechen.


## Weitere Schritte
Nachdem Sie das erneute Laden des Betriebssystems eingeleitet haben, geht das System offline und der Ladeprozess wird gestartet.
Der Zeitraum für das erneute Laden unterscheidet sich je nach aktueller und neuer Konfiguration des Geräts.
Während des Konfigurationsprozesses wird die Mindestzeit für den Ladevorgang auf dem Bildschirm angezeigt.
Der angezeigte Zeitrahmen ist ein vom System generierter Schätzwert und wird als unverbindlicher Service bereitgestellt. Falls das erneute Laden länger als 24 Stunden dauern sollte, wenden Sie sich an IBM Support.

Wenn das Gerät wieder online gestellt wird, funktioniert es entsprechend der neuen Konfiguration des Ladevorgangs. Alle zuvor auf dem Gerät gespeicherten Daten gehen verloren, sie können jedoch wiederhergestellt werden, falls Sie vor dem erneuten Laden eine Sicherung des Geräts durchgeführt haben. Falls keine Sicherung durchgeführt wurde, können die Daten nicht abgerufen werden. 

Sie müssen das Gerät erneut mit eVault registrieren. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
