---
title: Einrichten einer neuen Plattform
description: Erfahren Sie mehr über die Verwaltung der Zustellbarkeit, wenn Sie eine neue Plattform mit Adobe Campaign starten.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 6c9ade01-3052-4311-af80-888294820024
TQID: https://experienceleague.adobe.com/cQa5nOTSJwxDGX-QkXGez5dpm5N-8I7QZ-LsEW0FRLo
product_v2:
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
  - id: c5f60233-d5ea-4453-a799-0ad258b4d399
  - id: d1d0a9cd-295d-4976-8c39-ddae266f240e
  - id: e2290edd-b061-4880-9d79-dee306cf5aa9
  - id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 680
ht-degree: 41%

---

# Einrichten einer neuen Plattform {#starting-new-platform}

Die Aufrechterhaltung der Reputation Ihrer Domain und IP-Adresse ist beim Einrichten einer neuen Plattform für die Verwendung mit Adobe Campaign von entscheidender Bedeutung.

## Ein sensibler Schritt

Sie sollten sehr vorsichtig sein, wenn Sie mit dem Versand von E-Mails auf einer neuen Plattform beginnen, da die Plattform keine Nutzungsgeschichte hat und keine Reputation hat, wenn die sendenden IPs nie für diesen Zweck verwendet wurden.

ISPs sind naturgemäß argwöhnisch gegenüber IP-Adressen, die noch nie zum Senden von E-Mails verwendet wurden und plötzlich große Mengen von E-Mail-Traffic verursachen. Tatsächlich nutzen Spammer im Allgemeinen &quot;unbekannte&quot; IP-Adressen (Adressen, die noch nie auf Blockierungslisten standen), um vor der Erkennung eine maximale Anzahl von Nachrichten zu senden.

Es ist nicht zu erwarten, dass die Betriebsgeschwindigkeit in Bezug auf die Leistung gleich zu Beginn der Produktionsphase erreicht wird. Außerdem sollten Sie nicht versuchen, Nachrichten in diesem Tempo zu senden, da dies dazu führen kann, dass die ISPs die Versandadressen blockieren und den Rest der Startphase erheblich beeinträchtigen.

## Grundprinzipien

Nachfolgend sind die wichtigsten Grundsätze aufgeführt, die beim Start einer neuen Plattform befolgt werden müssen.

* Konfigurieren Sie eine dedizierte Subdomain, die spezifisch für E-Mail-Kampagnen ist, die von Adobe gesendet werden.

* Wenn Sie über solche Daten verfügen, **importieren Sie ungültige Adressen in die Quarantänetabelle**.
Der Start einer Plattform erfolgt häufig, wenn eine Liste von Adressen zum ersten Mal verwendet wird und diese möglicherweise nicht vollständig qualifiziert sind. Wenn Sie an ungültige Adressen oder an Honigtopf-Adressen senden, trägt dies dazu bei, die Reputation der Plattform zu verringern.

   * Wenn Sie eine Liste ungültiger Adressen haben, ist es in Ihrem Interesse, diese in die Quarantänetabelle zu importieren, bevor Sie sie zum ersten Mal senden. Die Quarantänetabelle ist über die Menüs **[!UICONTROL Administration > Kampagnenverwaltung > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]** (Campaign Classic) und **[!UICONTROL Administration > Kanäle > Quarantänen > Adressen]** (Campaign Standard) verfügbar.

   * Wenn Sie die ungültigen Adressen trotzdem erneut qualifizieren möchten, ist es viel besser, dies zu tun, sobald die Reputation der Plattform etabliert ist – und zwar nach und nach, um die Verwendung schlechter Adressen im Laufe der Zeit zu &quot;verwässern&quot;.

* **Begrenzen Sie die Durchsatzrate**, indem Sie die Anzahl der &quot;mtachilds&quot; einschränken. Wenden Sie sich für weitere Informationen zum Anpassen dieser technischen Einstellung an Ihren Adobe Campaign-Administrator.

* **Erhöhen Sie die gesendeten Volumen schrittweise**, damit diese nicht als Spam gekennzeichnet werden. Senden Sie nicht gleich an die gesamte Datenbank, sondern fügen Sie bei jedem Senden einen weiteren Anteil der Liste hinzu. So sollten Sie das Volumen bei jedem Schritt erhöhen und gleichzeitig die Gesamtrate ungültiger Adressen reduzieren können. Um eine reibungslose Entwicklung der Startphase zu gewährleisten, können Wellen verwendet werden.

* **Senden Sie regelmäßig**. Bis zu einem gewissen Grad ist es besser, regelmäßig kleine Aufnahmen zu machen als sporadisch große Kampagnen durchzuführen.
* **Beachten Sie dabei die Versandberichte**. Hohe Fehlerindikatoren können bedeuten, dass eine technische Einstellung schlecht konfiguriert ist.

## Weitere Ressourcen

Weitere Informationen zu den oben aufgeführten Prinzipien und deren Implementierung in Adobe Campaign finden Sie in den folgenden Abschnitten:

* [E-Mail-Reputation mit IP-Warming verbessern](../../help/additional-resources/increase-reputation-with-ip-warming.md)
* [Alles über Spam-Fallen](../../help/additional-resources/all-about-spam-traps.md)

**Adobe Campaign Classic**

* [Optimieren des Versands durch Quarantänen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html#optimizing-your-delivery-through-quarantines)
* [Identifizieren von für die gesamte Plattform in Quarantäne befindlichen Adressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html#identifying-quarantined-addresses-for-the-entire-platform)
* [In mehreren Schüben versenden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-waves)
* [Versand-Monitoring](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de#sending-messages)

**Adobe Campaign Standard**

* [Optimieren des Versands durch Quarantänen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-quarantine-management.html#optimizing-your-delivery-through-quarantines)
* [Identifizieren von für die gesamte Plattform in Quarantäne befindlichen Adressen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-quarantine-management.html?lang=de)
* [Sendungen überwachen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/monitoring-a-delivery.html?lang=de)
