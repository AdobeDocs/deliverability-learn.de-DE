---
title: Einrichten einer neuen Plattform
description: Erfahren Sie mehr über die Verwaltung der Zustellbarkeit, wenn Sie eine neue Plattform mit Adobe Campaign starten.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 6c9ade01-3052-4311-af80-888294820024
source-git-commit: d6094cd2ef0a8a7741e7d8aa4db15499fad08f90
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 56%

---

# Einrichten einer neuen Plattform {#starting-new-platform}

Die Aufrechterhaltung der Reputation Ihrer Domain und IP-Adresse ist beim Einrichten einer neuen Plattform für die Verwendung mit Adobe Campaign von entscheidender Bedeutung.

## Ein sensibler Schritt

Sie sollten sehr vorsichtig sein, wenn Sie mit dem Versand von E-Mails auf einer neuen Plattform beginnen, da die Plattform keine Nutzungsgeschichte hat und keine Reputation hat, wenn die sendenden IPs nie für diesen Zweck verwendet wurden.

ISPs sind naturgemäß argwöhnisch gegenüber IP-Adressen, die noch nie zum Senden von E-Mails verwendet wurden und plötzlich große Mengen von E-Mail-Traffic verursachen. Tatsächlich nutzen Spammer im Allgemeinen &quot;unbekannte&quot; IP-Adressen (Adressen, die noch nie auf Blockierungslisten standen), um vor der Erkennung eine maximale Anzahl von Nachrichten zu senden.

Erwarten Sie nicht, dass der Versand gleich zu Beginn der Produktionsphase in der gewünschten Geschwindigkeit durchgeführt werden kann. Sie sollten auch nicht versuchen, Nachrichten in dieser Geschwindigkeit zu versenden, da dies ISPs veranlassen könnte, die Absenderadresse zu blockieren, was die Anfangsphase erheblich beeinträchtigen würde.

## Grundprinzipien

Nachfolgend sind die wichtigsten Grundsätze aufgeführt, die beim Start einer neuen Plattform befolgt werden müssen.

* Konfigurieren Sie eine dedizierte Subdomain, die spezifisch für E-Mail-Kampagnen ist, die von Adobe gesendet werden.

* Wenn Sie über solche Daten verfügen, **importieren Sie ungültige Adressen in die Quarantänetabelle**.
Oft werden Plattformen gestartet, wenn eine Adressliste zum ersten Mal verwendet wird; diese ist möglicherweise nicht vollständig qualifiziert. Wenn Sie an ungültige Adressen oder Honeypot-Adressen senden, verschlechtert sich die Reputation der Plattform.

   * Wenn Sie eine Liste ungültiger Adressen haben, ist es in Ihrem Interesse, diese in die Quarantänetabelle zu importieren, bevor Sie sie zum ersten Mal senden. Die Quarantänetabelle ist über die Menüs **[!UICONTROL Administration > Campaign Management > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]** (Campaign Classic) und **[!UICONTROL Administration > Kanäle > Quarantänen > Adressen]** (Campaign Standard) verfügbar.

   * Wenn Sie die ungültigen Adressen trotzdem erneut qualifizieren möchten, ist es viel besser, dies zu tun, sobald die Reputation der Plattform etabliert ist – und zwar nach und nach, um die Verwendung schlechter Adressen im Laufe der Zeit zu &quot;verwässern&quot;.

* **Begrenzen Sie die Durchsatzrate**, indem Sie die Anzahl der &quot;mtachilds&quot; einschränken. Wenden Sie sich für weitere Informationen zum Anpassen dieser technischen Einstellung an Ihren Adobe Campaign-Administrator.

* **Erhöhen Sie die gesendeten Volumen schrittweise**, damit diese nicht als Spam gekennzeichnet werden. Senden Sie nicht gleich an die gesamte Datenbank, sondern fügen Sie bei jedem Senden einen weiteren Anteil der Liste hinzu. So sollten Sie das Volumen bei jedem Schritt erhöhen und gleichzeitig die Gesamtrate ungültiger Adressen reduzieren können. Um eine reibungslose Entwicklung der Startphase zu gewährleisten, können Wellen verwendet werden.

* **Senden Sie regelmäßig**. Bis zu einem gewissen Grad ist es besser, regelmäßig kleine Aufnahmen zu machen als sporadisch große Kampagnen durchzuführen.
* **Beachten Sie dabei die Versandberichte**. Hohe Fehlerindikatoren können bedeuten, dass eine technische Einstellung schlecht konfiguriert ist.

## Zusätzliche Ressourcen

Weitere Informationen zu den oben aufgeführten Prinzipien und deren Implementierung in Adobe Campaign finden Sie in den folgenden Abschnitten:

* [E-Mail-Reputation mit IP-Warming verbessern](../../help/additional-resources/increase-reputation-with-ip-warming.md)
* [Alles über Spam-Fallen](../../help/additional-resources/all-about-spam-traps.md)

**Adobe Campaign Classic**

* [Optimieren Sie Ihren Versand durch Quarantänen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=de#optimizing-your-delivery-through-quarantines)
* [Identifizieren von für die gesamte Plattform in Quarantäne befindlichen Adressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=de#identifying-quarantined-addresses-for-the-entire-platform)
* [Versand in mehreren Schüben](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-waves)
* [Überwachen des Versands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de#sending-messages)

**Adobe Campaign Standard**

* [Optimieren Sie Ihren Versand durch Quarantänen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-quarantine-management.html?lang=de#optimizing-your-delivery-through-quarantines)
* [Identifizieren von für die gesamte Plattform in Quarantäne befindlichen Adressen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-quarantine-management.html?lang=de)
* [Überwachen eines Versands](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/monitoring-a-delivery.html?lang=de)
