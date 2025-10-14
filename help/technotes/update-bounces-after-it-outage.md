---
title: Aktualisierung der Bounce-Qualifizierung nach Ausfall von Italia Online
description: Erfahren Sie, wie Sie die Bounce-Qualifizierung nach einem Ausfall von Italia Online aktualisieren können
feature: Deliverability
exl-id: a11e88cf-bf37-42cc-9c09-1d58360459b7
hide: true
hidefromtoc: true
role: Admin
level: Beginner
source-git-commit: 6b312cdbba496818337c97ec4f42962aea757901
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 51%

---

# Aktualisieren falscher Hardbounces nach einem Ausfall von Italia Online {#update-bounce-italia}

## Kontext{#outage-context}

Seit dem 22. Januar (Ortszeit) gibt es bei Italia Online einen Ausfall, der zu mehreren Verzögerungen und zurückgewiesenen E-Mails geführt hat. Der Service wurde am 26. Januar mit begrenzter Kapazität wieder aufgenommen.

Betroffene Domains sind: **libero.it**, **virgilio.it**, **inwind.it**, **iol.it** und **blu.it**.

Dieses Problem trat vom 22.1.2023 bis zum 26.1.2023 auf, aber die meisten falschen Quarantänemaßnahmen erfolgten am 26. Januar.

Weitere Informationen finden Sie in der offiziellen Mitteilung [hier](https://tecnologia.libero.it/avviato-il-ritorno-online-di-libero-mail-e-virgilio-mail-66832){_blank}.


## Wirkung{#outage-impact}

Wie in den meisten Fällen, in denen ein Internet Service Provider (ISP) ausfällt, wurden einige über Campaign oder Journey Optimizer gesendete E-Mails fälschlicherweise als Bounces markiert. Dies hatte nicht nur Auswirkungen auf Adobe, sondern auf alle, die während des Ausfalls versuchten, E-Mails an Italia Online zu senden.

Die Symptome waren:

* **Softbounces** mit der Nachricht `452 requested action aborted: try again later` - diese wurden automatisch wiederholt, und es sind keine Aktionen erforderlich.

* **Hardbounces** mit der Nachricht `550 <email address> recipient rejected` wurden von dem ISP am 26. Januar zwischen 8:00 und 14:00 Uhr Ortszeit zurückgeschickt, um zu verhindern, dass seine Server weiter überlastet werden. Wie vom Italia Online-Postmaster bestätigt, handelt es sich hierbei nicht um echte Hardbounces. Daher empfehlen wir, die Quarantäne für alle E-Mail-Adressen aufzuheben, die am 26. Januar 2023 aufgrund dieser Nachricht ausgeschlossen wurden.

## Aktualisierungsprozess{#outage-update}

### Adobe Campaign{#ac-update}

Gemäß der Standardlogik für die Behandlung von Bounces hat Adobe Campaign diese Empfänger automatisch der Quarantäneliste mit dem **[!UICONTROL Status]** **[!UICONTROL Quarantäne]** hinzugefügt. Um dies zu korrigieren, müssen Sie Ihre Quarantänetabelle in Campaign aktualisieren, indem Sie diese Empfänger finden und entfernen oder ihren **[!UICONTROL Status]** auf **[!UICONTROL Gültig]** ändern, damit der nächtliche Bereinigungs-Workflow sie entfernt.

Um die Empfängerinnen und Empfänger zu finden, die von diesem Problem betroffen waren, oder für den Fall, dass dies bei einem anderen ISP erneut auftritt, lesen Sie bitte die folgenden Anweisungen:

* Informationen zu Campaign Classic v7 und Campaign v8 finden Sie [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=de#unquarantine-bulk){_blank}.
* Weitere Campaign Standards finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-quarantine-management.html?lang=de#unquarantine-bulk){_blank}.

### Adobe Journey Optimizer{#ajo-update}

Gemäß der Standardlogik zur Handhabung von Bounces hat Adobe Journey Optimizer diese E-Mail-Adressen automatisch zur Unterdrückungsliste hinzugefügt, wobei die Einstellung **[!UICONTROL Grund]** auf &quot;**[!UICONTROL Empfänger“]**. Um dies zu korrigieren, müssen Sie die Unterdrückungsliste aktualisieren, indem Sie diese E-Mail-Adressen suchen und entfernen.

Nach der Identifizierung können diese Adressen manuell mithilfe der Schaltfläche **[!UICONTROL Löschen“ aus der]** entfernt werden. Diese Adressen können dann in zukünftige E-Mail-Kampagnen aufgenommen werden.

Weitere Informationen finden Sie [&#x200B; (diesem Abschnitt](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/monitor-reputation/manage-suppression-list.html?lang=de#remove-from-suppression-list){_blank}.

