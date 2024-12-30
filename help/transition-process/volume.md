---
title: Lautstärke - Tipps für einen reibungslosen Übergang
description: Die Menge der versendeten E-Mails ist entscheidend für eine positive Reputation. Erfahren Sie, was Sie für einen reibungslosen Übergang tun können.
topics: Deliverability
jira: KT-7055
thumbnail: kt7055.jpg
doc-type: article
activity: understand
role: Admin,User
level: Beginner
team: ACS
exl-id: 1bc56061-0c64-4033-b49c-66618916bca6
source-git-commit: 6b312cdbba496818337c97ec4f42962aea757901
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 1%

---

# Volumen

Die Menge der versendeten E-Mails ist entscheidend für eine positive Reputation. Stecken Sie sich in die Lage eines ISPs - wenn Sie eine Menge Verkehr von jemandem sehen, den Sie nicht kennen, wäre es alarmierend. Große Mengen von E-Mails sofort zu versenden ist riskant und verursacht mit Sicherheit Reputationsprobleme, die oft schwer zu beheben sind. Es kann frustrierend, zeitaufwendig und kostspielig sein, sich selbst aus dem schlechten Ruf zu befreien und Probleme zu stapeln und zu blockieren, die daraus resultieren, dass zu viel zu früh versendet wird.

Die Mengenschwellen variieren je nach ISP und können auch je nach Ihrer durchschnittlichen Interaktionsmetrik variieren. Einige Absender benötigen eine sehr niedrige und langsame Rampe des Volumens, während andere eine steilere Rampe des Volumens ermöglichen können. Wir empfehlen die Zusammenarbeit mit einem Experten, z. B. einem Adobe-Zustellbarkeitsberater, um einen individuellen Volumenplan zu erstellen.

Hier finden Sie eine Liste von Hinweisen und Tipps für einen reibungslosen Übergang:

* **Permission** ist die Grundlage jedes erfolgreichen E-Mail-Programms.
* **Niedrig und langsam** - Beginnen Sie mit niedrigen Versandvolumen und erhöhen Sie dann Ihre Absenderreputation.
* Eine **Tandem-** ermöglicht es Ihnen, die Menge in Campaign zu erhöhen und gleichzeitig Ihren aktuellen ESP zu nutzen, ohne Ihren E-Mail-Kalender zu stören.
* **Interaktion ist wichtig** — Beginnen Sie mit den Abonnentinnen und Abonnenten, die Ihre E-Mails regelmäßig öffnen und klicken.
* **Plan befolgen** - Unsere Empfehlungen haben Hunderten von Campaign-Kunden dabei geholfen, ihre E-Mail-Programme erfolgreich zu optimieren.
* **Überwachen Sie Ihr Antwort-E-Mail-Konto**. Es ist eine schlechte Erfahrung für Ihren Kunden, noreply@xyz.com zu verwenden oder nicht zu reagieren.
* Inaktive Adressen können die Zustellbarkeit beeinträchtigen. **Erneutes Aktivieren und erneutes Zulassen für Ihre aktuelle Plattform**, nicht für Ihre neuen IPs.
* **Domains** - Verwendet eine Versand-Domain, die eine Subdomain der tatsächlichen Domain Ihres Unternehmens ist
   * Wenn Ihre Unternehmens-Domain beispielsweise xyz.com lautet, bietet email.xyz.com den ISPs mehr Glaubwürdigkeit als xyzemail.com
* **Transparenz** - Registrierungsdetails für Ihre E-Mail-Domain sollten öffentlich verfügbar und nicht privat sein.

In vielen Fällen folgen Transaktions-E-Mails nicht dem herkömmlichen Ansatz des Werbe-Warmings. Es ist offensichtlich schwierig, das Volumen von Transaktions-E-Mails zu kontrollieren, da es im Allgemeinen eine Benutzerinteraktion erfordert, um den E-Mail-Touch-Trigger zu steuern. In einigen Fällen können Transaktions-E-Mails einfach ohne einen formellen Plan übertragen werden. In anderen Fällen ist es möglicherweise besser, jeden Nachrichtentyp im Laufe der Zeit umzustellen, um das Volumen langsam zu erhöhen. Beispielsweise können Sie wie folgt umstellen:

1. Kaufbestätigungen - hohes Engagement im Allgemeinen
2. Warenkorbabbruch - mittel - allgemein hohes Engagement
3. Begrüßungs-E-Mails - hohe Interaktion, kann jedoch je nach den Methoden der Listenerfassung fehlerhafte Adressen enthalten
4. Winback-E-Mails - generell geringere Interaktion

## Produktspezifische Ressourcen

**Campaign**

* Weitere Informationen zur Verwaltung der Zustellbarkeit beim Starten einer neuen Plattform mit Adobe Campaign finden [ in diesem Abschnitt](/help/additional-resources/ac-starting-new-platform.md).
* In diesem Abschnitt erfahren Sie, wie Sie mit Adobe Campaign Classic [ mehreren Schüben versenden ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-waves).
* Wie Sie eine Subdomain vollständig an Adobe Campaign Classic oder Standard delegieren, erfahren Sie in [diesem Abschnitt](/help/additional-resources/ac-domain-name-setup.md).
* [Control Panel: Vollständige Subdomain-Delegierung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-classic-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html) - *Erfahren Sie, wie Sie eine Subdomain vollständig an Adobe Campaign Classic delegieren.*
* [Control Panel: Vollständige Subdomain-Delegierung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html) - *Erfahren Sie, wie Sie eine Subdomain vollständig an Adobe Campaign Standard delegieren.*

## Zusätzliche Ressourcen

* Weitere Informationen zur Verbesserung der E-Mail-Reputation mit IP-Warming finden [ in diesem Abschnitt](/help/additional-resources/increase-reputation-with-ip-warming.md).
