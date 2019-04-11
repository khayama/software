---



copyright:
  years: 2017
lastupdated: "2017-09-25"

keywords: OS Reload, operating system

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

#  Betriebssystem erneut laden
{: #reloading-the-os}

Sie können das Betriebssystem auf einem Gerät jederzeit neu laden, um die ursprüngliche Funktionsfähigkeit eines Geräts wiederherzustellen oder ein Gerät mit einer anderen Software neu zu konfigurieren. Bei einem erneuten Laden des Betriebssystems werden alle Daten von dem Gerät entfernt und es wird eine 'neuwertige' Konfiguration gemäß den Angaben angewendet, die im Rahmen des Konfigurationsprozesses während des erneuten Ladens des Betriebssystems festgelegt wurden. Da bei diesem Vorgang alle Daten vom Gerät gelöscht werden, werden die Daten permanent entfernt und können nicht mehr abgerufen werden, falls die Daten vor dem erneuten Laden nicht gesichert wurden.
{:shortdesc}

**Wichtig:** Wenn Sie die Daten beibehalten möchten, sichern Sie vor dem erneuten Laden des Betriebssystems alle Daten.

## Betriebssystem erneut laden
{: #reload-the-os}

1. Klicken Sie in der **Geräteliste** auf den Server, für den das Betriebssystem erneut geladen werden muss, um die Seite mit den Gerätedetails anzuzeigen.
2. Wählen Sie aus dem Menü **Aktionen** die Option zum erneuten Laden des Betriebssystems aus.
3. Legen Sie fest, ob Sie die vorhandene Konfiguration oder aber das Gerät mit der neuen Konfiguration erneut laden möchten.

   <table>
   <CAPTION>Tabelle 1. Optionen für das erneute Laden des Betriebssystems</CAPTION>
   <THEAD>
   <TR>
   <th>Typen für erneutes Laden</th>
   <th>Schritte</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Wenn Sie eine neue Konfiguration erneut laden möchten...</td>
   <td>
   <ol>
   <li>Klicken Sie für die Kategorie auf <b>Bearbeiten</b>, die aktualisiert werden muss.</li>
   <li>Wählen Sie die neue Software, die auf das Gerät angewendet werden soll, aus der Dropdown-Liste <i>Software auswählen</i> aus.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Wenn Sie die vorhandene Konfiguration erneut laden möchten...</td>
   <td>Fahren Sie mit dem nächsten Schritt fort.</td>
   </tr>
   </TBODY>
   </table>

4. Legen Sie fest, ob das Script für den Installationsabschluss nach der Bereitstellung des Geräts angewendet werden soll.

   Wenn Sie ein Script für den Installationsabschluss anwenden möchten, wählen Sie das Script aus der Dropdown-Liste mit den vorhandenen Scripts aus oder geben Sie die qualifizierte URL für das neue Script ein.  Andernfalls fahren Sie mit dem nächsten Schritt fort.

5. Legen Sie für physische Geräte fest, ob installierte Partitionen hinzugefügt oder entfernt oder ob sie nicht geändert werden sollen.

   <table>
   <CAPTION>Tabelle 2. Optionen für Partitionsaktionen</CAPTION>
   <THEAD>
   <TR>
   <th>Partitionsaktion</th>
   <th>Schritte</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Um installierte Partitionen hinzuzufügen...</td>
   <td>
   <ul>
   <li>Klicken Sie auf den Link <b>Weitere Partition hinzufügen</b>.</li>
   <li>Geben Sie den genauen Namen der Partition ein.</li>
   <li>Geben Sie die Partitionsgröße (in GB) ein. Wenn Sie möchten, können Sie die Option zum Vergrößern wählen, um die Partition so zu vergrößern, dass der verbleibende Plattenspeicher gefüllt wird.
   <p><b>Hinweis:</b> Es kann immer nur eine Partition für diesen Vorgang ausgewählt werden. Diese Partition ist größer als die angegebene Größe und füllt die gesamte verfügbare Kapazität aus. Die Kapazität der Partition, die zum Vergrößern ausgewählt wurde, wird berechnet, indem die zusammengefasste Größe aller anderen Partitionen von der Gesamtanzahl der Gesamtkapazität abgezogen wird, die im Abschnitt mit den installierten Partitionen angegeben ist.</p>
   </li>
   </ul>
   </td>
   </tr>
   <tr>
   <td>Um installierte Partitionen zu löschen...</td>
   <td>Klicken Sie auf <b>Löschen</b>, um die Partition zu löschen.</td>
   </tr>
   <tr>
   <td>Um keine Änderungen vorzunehmen...</td>
   <td>Fahren Sie mit dem nächsten Schritt fort.</td>
   </tr>
   </TBODY>
   </table>

6. Stellen Sie fest, ob Sie einen oder mehrere SSH-Schlüssel auf das Gerät anwenden sollen.

7. Wählen Sie die entsprechenden Kontrollkästchen für die Optionen aus, die während oder nach dem erneuten Laden des Betriebssystems auf das Gerät angewendet werden sollen.

   **Hinweis:** Je nach Gerät stehen andere Optionen zur Verfügung. Nicht alle Optionen sind für jedes Gerät verfügbar.

8. Klicken Sie auf die Option zum erneuten Laden der obigen Konfiguration, um zur Überprüfung überzugehen. Klicken Sie auf **Abbrechen**, um die am Gerät vorgenommenen Änderungen zu verwerfen und die Anzeige zu beenden.

9. Stellen Sie sicher, dass alle Details im Abschnitt 'Neue Konfiguration' richtig sind.  

10. Klicken Sie auf **Erneutes Laden des Betriebssystems bestätigen**, um das erneute Laden des Betriebssystems zu bestätigen und einzuleiten. Klicken Sie auf **Abbrechen**, um die Aktion abzubrechen.

## Weitere Schritte
{: #what-s-next-reloading-the-os}

Nachdem Sie das erneute Laden des Betriebssystems eingeleitet haben, geht das System offline und der Ladeprozess wird gestartet.
Der Zeitraum für das erneute Laden unterscheidet sich je nach aktueller und neuer Konfiguration des Geräts.
Während des Konfigurationsprozesses wird die Mindestzeit für den Ladevorgang auf dem Bildschirm angezeigt.
Der angezeigte Zeitrahmen ist ein vom System generierter Schätzwert. Falls das erneute Laden länger als 24 Stunden dauern sollte, wenden Sie sich an IBM Support.

Wenn das Gerät wieder online gestellt wird, funktioniert es entsprechend der neuen Konfiguration des Ladevorgangs. Alle zuvor auf dem Gerät gespeicherten Daten gehen verloren, sie können jedoch wiederhergestellt werden, falls Sie vor dem erneuten Laden des Betriebssystems eine Sicherung des Geräts durchgeführt haben. Falls keine Sicherung durchgeführt wurde, können die Daten nicht abgerufen werden.

Sie müssen das Gerät mit eVault erneut registrieren.
