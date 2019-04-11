---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# Häufig gestellte Fragen
{: #faqs}

## Kann das Betriebssystem auf dem Gerät geändert werden?
{: #can-the-operating-system-os-be-changed-on-the-device-}

Sie können das Betriebssystem und die von Ihnen installierte Software ändern, indem Sie ein Betriebssystem erneut laden <!--[OS Reload](perform-os-reload-device.html){:new_window}-->. Nachdem Sie das erneute Laden des Betriebssystems auf dem Gerät ausgewählt haben, wird ein Link zu einer Seite angezeigt, auf der Sie die Software auf dem System aktualisieren können. Über diese Seite können Sie beispielsweise das Betriebssystem, die Systemsteuerung, Virenschutzpakete und die Datenbanksoftware aktualisieren.

## Ist das erneute Laden des Betriebssystems kostenlos?
{: #do-you-provide-complimentary-os-reloads-}

Das automatisierte erneute Laden von Betriebssystemen ist kostenlos. Dazu zählen auch angepasste Ladevorgänge, wie das Ändern von Betriebssystemen, das Hinzufügen oder Entfernen von Systemsteuerungen, das Bearbeiten von Partitionen und andere Optionen. Weitere Informationen hierzu finden Sie im Kundenportal.

## Wie kann ich den Status des erneuten Ladens des Betriebssystems verfolgen?
{: #how-can-i-track-the-status-of-the-os-reload-}

Im Kundenportal unter 'Hardware' finden Sie einen Abschnitt mit Hinweisen für jeden Ihrer Server. Dieser Abschnitt enthält Links zu Informationen zum aktuellen Schritt des Ladevorgangs und zur geschätzten Zeit bis zum Abschluss dieses Teils des Vorgangs.

## Können durch das erneute Laden des Betriebssystems sekundäre Platten gelöscht werden?
{: #can-an-os-reload-erase-secondary-disks-}

Durch ein erneutes Laden des Betriebssystems wird nur die primäre Platte auf dem System formatiert. Alle anderen Platten bleiben unverändert. Genauso funktioniert es auch beim erneuten Laden über eine Imagevorlage. Wenn die Vorlage mehr als eine Platte enthält, wird nur die primäre Platte formatiert. An den anderen Platten werden keine Änderungen vorgenommen.

## Weshalb ist 'cpsrvd' fehlgeschlagen?
{: #why-did-my-cpsrvd-email-fail-}

Wenn Sie eine E-Mail mit der Nachricht **cpsrvd failed** erhalten, wird diese in den meisten Fällen sofort nach einem Neustart gesendet. Dieser Fehler tritt auf, wenn 'chkservd' versucht, den cpsrvd-Prozess zu validieren. Die Validierung schlägt fehl, da der Prozess nicht gestartet wurde.

Wenn Sie eine E-Mail vom chkservd-Service erhalten, die darauf hinweist, dass 'cpsrvd' fehlgeschlagen ist, können Sie die Nachricht in den meisten Fällen ignorieren. Wenn Sie jedoch mindestens fünf dieser Nachrichten hintereinander oder mehr als vier an einem Tag nach einem Neustart erhalten, öffnen Sie ein Support-Ticket.
