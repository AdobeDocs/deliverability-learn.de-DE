---
title: Bounces
description: Erfahren Sie mehr über die verschiedenen Arten von Bounces.
topics: Deliverability
jira: KT-7047
thumbnail: kt7047.jpg
doc-type: article
activity: understand
team: ACS
exl-id: 6338eb67-3efd-476e-8b26-97bbb6a1d35f
TQID: https://experienceleague.adobe.com/0Gly4dAgTpfrmnFD3N-RphZf9vmctJ57fMi1hSmfMTg
product_v2: id: b27e5950-9033-45ac-9f86-eb22e567f615id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: ea90ebee-5c84-42d9-8b21-006bdabc95a3id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 100%

---

# Bounces

Bounces sind das Ergebnis eines Zustellversuchs und -fehlers, bei dem der ISP Fehlermeldungen zurückgibt. Die Bounce-Verarbeitung ist ein wichtiger Bestandteil der Listenhygiene. Nachdem eine E-Mail mehrmals hintereinander abgewiesen wurde, wird sie durch diesen Prozess markiert und unterdrückt. Die Anzahl und die Art der Bounces, die erforderlich sind, um die Unterdrückung auszulösen, variieren je nach System. Dieser Prozess verhindert, dass Systeme weiterhin ungültige E-Mail-Adressen senden. Bounces gehören zu den wichtigsten Daten, mit denen ISPs die IP-Reputation bestimmen. Es ist sehr wichtig, diese Metrik im Auge zu behalten. &quot;Zugestellt&quot; versus &quot;Bounces&quot; ist wahrscheinlich die gebräuchlichste Art, die Zustellung von Marketing-Nachrichten zu messen: je höher der zugestellte Prozentsatz ist, desto besser.

Hier werden zwei verschiedene Arten von Bounces beschrieben .

## Hardbounces

Hardbounces sind permanente Fehler, die generiert werden, nachdem ein ISP einen Mailing-Versuch an eine Abonnentenadresse als nicht zustellbar eingestuft hat. In Adobe Campaign werden der Quarantäne Hartbounces hinzugefügt, die als nicht zustellbar eingestuft werden. Dies bedeutet, dass ihre Zustellung nicht erneut versucht wird. Es gibt einige Fälle, in denen ein Hardbounce ignoriert wird, wenn die Ursache für den Fehler unbekannt ist.
Hier finden Sie einige gängige Beispiele für Hardbounces:

* Adresse existiert nicht
* Konto deaktiviert
* Fehlerhafte Syntax
* Fehlerhafte Domain

## Softbounces

Softbounces sind vorübergehende Fehler, die ISPs generieren, wenn sie Schwierigkeiten haben, E-Mails zuzustellen. Bei Softbounce-Fehlschlägen wird der Zustellversuch mehrmals wiederholt (mit Abweichungen in Abhängigkeit von der Verwendung benutzerdefinierter oder nativen Versandeinstellungen). Adressen, die ständig einen Softbounce verursachen, werden erst dann in die Quarantäne aufgenommen, wenn die maximale Anzahl von Wiederholungsversuchen erreicht ist (die wiederum von den Einstellungen abhängt). Einige häufige Ursachen für Softbounces sind:

* Postfach voll
* E-Mail-Empfangs-Server ausgefallen
* Probleme mit der Reputation des Absenders

![Bounce-Typen](../assets/bounce-types.png)

>[!NOTE]
>
>Bounces sind ein wichtiger Indikator für ein Problem, da sie auf eine schlechte Datenquelle (Hardbounce) oder ein Reputationsproblem mit einem ISP (Softbounce) hinweisen können.
>
>Softbounces treten oft im Zuge des E-Mail-Versands auf und sollten die Möglichkeit erhalten, durch Wiederholungen behoben zu werden, bevor sie als echtes Zustellbarkeitsproblem eingestuft werden. Wenn Ihre Softbounce-Rate bei einem einzelnen ISP mehr als 30 Prozent beträgt und nicht innerhalb von 24 Stunden behoben wird, sollten Sie Ihren Zustellbarkeitsberater für Adobe Campaign auf das Problem aufmerksam machen.

## Produktspezifische Ressourcen

**Adobe Campaign Classic**

* [Typen und Ursachen für fehlgeschlagene Sendungen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=de#delivery-failure-types-and-reasons)
* [Bounce-E-Mail-Verwaltung](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=de#bounce-mail-management)
* [Bericht über unzustellbare Nachrichten und Bounces](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/global-reports.html?lang=de#non-deliverables-and-bounces)

**Adobe Campaign Standard**

* [Typen und Ursachen für fehlgeschlagene Sendungen](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-delivery-failures.html?lang=de#delivery-failure-types-and-reasons)
* [Bounce-Message-Qualifizierung](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-delivery-failures.html?lang=de#bounce-mail-qualification)
* [Zusammenfassender Bericht über Bounces](https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/list-of-reports/bounce-summary.html?lang=de#reporting)
