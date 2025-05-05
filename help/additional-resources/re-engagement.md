---
title: Best Practices zur Rückgewinnung
description: Erfahren Sie, wie Sie die Zustellbarkeit durch Rückgewinnungsstrategien verbessern können.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 30118706-d4c0-4bd8-8c9b-50c26b8374ef
source-git-commit: d6094cd2ef0a8a7741e7d8aa4db15499fad08f90
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 24%

---

# Best Practices zur Rückgewinnung {#re-engagement}

Bei der Implementierung der Zustellbarkeit bestehen einige der Best Practices darin, einen intakten Abonnentenstamm beizubehalten und die Zustellbarkeit durch Rückgewinnungsstrategien (oder Win-Back-Strategien) zu verbessern.

* Die Aufrechterhaltung eines gesunden Abonnentenstamms ist einer der Hauptaspekte für einen guten und konsistenten Versand. Viele Zustellbarkeitsprobleme entstehen durch schlechte Datenpraxis und Wartung.
* Eines der häufigsten Probleme, mit denen Marketing-Experten heutzutage konfrontiert sind, ist die Inaktivität von Abonnenten (auch als „niedrige“ oder „fehlende Interaktion“ bezeichnet), die sich negativ auf den Versand von E-Mails auswirken und einen niedrigen ROI verursachen kann.

>[!NOTE]
>
>Weitere Informationen zu Wiedergewinnungsstrategien und Zustellbarkeitsdiensten von Adobe erhalten sie von Ihrem Zustellbarkeitsberater oder Ihrem Adobe-Vertreter.

## Wie sehen ISPs Nicht-Interaktionsaktivitäten? {#how-do-isps-view-non-engagement-activity-}

Seit Jahren verwenden ISPs Feedback-Metriken von ihren Benutzern, um zu entscheiden, wo Nachrichten platziert werden sollen oder ob sie überhaupt gesendet werden sollen. Die [Interaktion](/help/engagement.md) besteht aus positivem und negativem Feedback, und die ISPs überwachen beide kontinuierlich. Sich nicht einzubringen, ist vielleicht einer der Hauptverursacher negativen Engagements. Aus Sicht der Zustellbarkeit kann das konsistente Senden von Kampagnen an Benutzende, die keine Interaktion zeigen, auch die allgemeine Reputation Ihrer IP-Adresse und Domains beeinträchtigen.

ISPs wie Gmail, Microsoft® und OATH betrachten die Abwesenheit von Interaktionen als unerwünschte E-Mails und leiten Nachrichten an den Spam-Ordner weiter. Außerdem ist es möglich, dass diese Abonnenten nicht mehr der Eigentümer des E-Mail-Kontos sind und dies als „recycelte“ Spam-Falle verwendet werden kann. Dies bedeutet, dass die Adresse einige Zeit ungültig war und alle Nachrichten zurückgewiesen wurden. Wenn Ihr Abonnentenverwaltungssystem keine „Hardbounce“-Adressen entfernt, ist es wahrscheinlich, dass E-Mails an Spam-Fallen gesendet werden, was zu erheblichen Versandproblemen führen kann.

## Wie sollte man an Inaktivität herangehen? {#how-should-you-approach-inactivity-}

Kunden und Kundinnen, die die Adobe-Plattform verwenden, können Inaktivität in ihrer Instanz anzeigen, indem sie die Daten zum Öffnen und Klicken entsprechend dem Segment überprüfen. Da die Nichtinteraktion den Versand behindern kann, besteht der erste Gedanke darin, Abonnentinnen und Abonnenten aus der Datenbank zu entfernen. Dies kann sich jedoch manchmal als falsche Option erweisen. Daher ist eine Rückgewinnungsstrategie (auch als „Win-back-Strategie“ bezeichnet) die beste Empfehlung, Abonnentinnen und Abonnenten, die am Erhalt von E-Mails interessiert sind, beizubehalten und diejenigen, die keine Aktivität mehr zeigen, schrittweise auszuschließen.

## Funktionieren Rückgewinnungskampagnen wirklich? {#do-re-engagement-campaigns-really-work-}

Laut einer Studie von Return Path erzielten Rückgewinnungskampagnen eine Öffnungsrate von 12 % verglichen mit einer durchschnittlichen Öffnungsrate von 14 % bei normalen Kampagnen. Obwohl nur 24 % der Abonnenten die Rückgewinnungskampagne gelesen hatten, lasen ca. 45 % von ihnen die darauf folgenden Nachrichten.

![](../../help/assets/deliverability_implementation_1.png)

## Wie erstelle ich eine Rückgewinnungskampagne? {#how-do-you-create-a-re-engagement-campaign-}

### Phase 1 {#phase-1}

* Der erste Schritt besteht darin, Abonnentinnen und Abonnenten zu identifizieren, die wenig oder gar keine Öffnungs- oder Klickaktivität haben, und diese Gruppe dementsprechend basierend auf einem bestimmten Zeitrahmen zu segmentieren. Die Faustregel lautet, Abonnentinnen und Abonnenten zu überprüfen, die in den letzten 90 Tagen keine E-Mail geöffnet oder geklickt haben. Dies variiert jedoch je nach Art des Geschäfts (z. B. saisonaler Versand).
* Außerdem sollten Sie bei der Festlegung von Zeitrahmen bedenken, dass ISPs und Anbieter von Blockierungslisten bei der Interaktion von zwischen 1,5 und 1,8 Jahren ausgehen. Auch Verhaltensaktivitäten wie Käufe und Website-Aktivitäten oder andere Touchpoints, wie z. B. Voreinstellungen während der Anmeldungsphase oder des ersten Kontaktpunkts.

### Phase 2 {#phase-2}

* Sobald ein Segment definiert ist, besteht der nächste Schritt darin, eine Rückgewinnungskampagne zu erstellen, die den Abonnenten entsprechend den identifizierten Metriken anspricht. Das Erstellen einer Betreffzeile trägt dazu bei, das Interesse der Abonnentinnen und Abonnenten zu erhöhen. Laut einer Studie zum Return Path generieren Betreffzeilen und Inhalte, die „Wir vermissen euch“ ausdrücken, höhere Antwortraten als „Wir wollen euch zurück“.
* Es kann auch ein Anreiz für eine erneute Interaktion mit der E-Mail angeboten werden. Bei der Berücksichtigung von Angeboten mit Rabatten ist es am besten, Dollarbeträge versus Prozentsätze zu verwenden. Return Path schlägt auch vor, dies zu tun, da es höhere Antwortraten verursacht. Schließlich ist auch die Durchführung von A/B-Split-Tests zur Überprüfung der Antwort- und Erfolgsraten eine nützliche Option.

### Phase 3 {#phase-3}

Als Nächstes muss die Frequenz der Rückgewinnungskampagne bestimmt werden. Im Gegensatz zu einfachen Bestätigungsnachrichten sollen Rückgewinnungskampagnen die Abonnenten langfristig mit mehreren E-Mails zurückgewinnen. Im Folgenden wird ein Beispiel für die Ermittlung der Frequenz beschrieben.

![](../../help/assets/deliverability_implementation_2.png)

Abonnenten, die in der Kampagne durch Öffnen oder Anklicken erneut aktiv werden, werden wieder auf die Liste aktiver Abonnenten gesetzt.

### Phase 4 {#phase-4}

* In der nächsten Phase werden Abonnentinnen und Abonnenten identifiziert, die kontinuierlich keine Aktivität zeigen, und der Versand von E-Mails an sie über einen bestimmten Zeitraum wird schrittweise reduziert. Wenn im letzten Jahr keine Aktivität verzeichnet wurde, empfiehlt es sich, das E-Mail-Abonnement der Abonnenten auf „Zurückgestellt“ zu setzen. Obwohl sie kein Interesse am E-Mail-Inhalt gezeigt haben, gibt es immer eine letzte Chance, dass sie ihr Abonnement durch eine einmalige Bestätigungskampagne reaktivieren.
* Bestätigungskampagnen sind eine gute Möglichkeit, Abonnentinnen und Abonnenten, die lange Zeit inaktiv sind, zu fragen, ob sie auf der Abonnement-Liste bleiben möchten. Bei der Erstellung der Kampagne ist es vorzuziehen, einen Link „Hier klicken“ hinzuzufügen, damit der Benutzer die Aktion bestätigen und seine Adresse überprüfen kann. Auf diese Weise kann die Aktion in der Datenbank aufgezeichnet werden. Nachfolgend finden Sie ein Beispiel für eine Bestätigungs-E-Mail:

  ![](../../help/assets/deliverability_implementation_3.png)

  Sobald der Abonnent eine Aktion durchgeführt hat, kann eine Landingpage mit der Bestätigung seiner Wiederabmeldung angeboten werden. Nachfolgend finden Sie ein Beispiel für die Landingpage:

  ![](../../help/assets/deliverability_implementation_4.png)

## Produktspezifische Ressourcen

**Adobe Campaign**

* [Trackinglogs in Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=de#tracking-logs)
* [Trackinglogs im Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/sending-and-tracking-messages/tracking-messages.html?lang=de#tracking-logs)

**Adobe Customer Journey Management**

* [Nachrichten-Tracking](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/message-tracking.html?lang=de)
