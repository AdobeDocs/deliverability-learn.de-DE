---
title: Lautstärke - Tipps für einen reibungslosen Übergang
description: Das Volumen der gesendeten E-Mails ist entscheidend für einen positiven Ruf. Erfahren Sie, was Sie für einen reibungslosen Übergang tun können.
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

Das Volumen der gesendeten E-Mails ist entscheidend für einen positiven Ruf. Setzen Sie sich in die Schuhe eines ISPs - wenn Sie eine Menge Traffic von jemandem sehen, den Sie nicht kennen, wäre das alarmierend. Der sofortige Versand großer Mengen von E-Mails ist riskant und verursacht sicher Reputationsprobleme, die häufig schwer zu lösen sind. Es kann frustrierend, zeitaufwendig und kostspielig sein, sich aus der schlechten Reputation zu befreien und Probleme zu schüren und zu blockieren, die sich aus dem Versand zu viel zu früh ergeben.

Die Volumenschwellen variieren je nach ISP und können abhängig von Ihren durchschnittlichen Interaktionsmetriken variieren. Einige Absender benötigen eine sehr geringe und langsame Rampe, während andere eine stärkere Rampe ermöglichen können. Wir empfehlen, mit einem Experten wie einem Adobe-Zustellbarkeits-Berater zusammenzuarbeiten, um einen kundenspezifischen Volumenplan zu entwickeln.

Im Folgenden finden Sie eine Liste mit Hinweisen und Tipps für einen reibungslosen Übergang:

* **Permission** ist die Grundlage jedes erfolgreichen E-Mail-Programms.
* **Niedrig und langsam** - Beginnen Sie mit geringen Versandvolumen und erhöhen Sie dann, wenn Sie Ihre Reputation als Absender feststellen.
* Eine **Tandem-Mailing-Strategie** ermöglicht es Ihnen, das Volumen in Campaign zu erhöhen, während Sie mit Ihrem aktuellen ESP abschließen, ohne Ihren E-Mail-Kalender zu stören.
* **Interaktion zählt** - Beginnen Sie mit den Abonnenten, die Ihre E-Mails regelmäßig öffnen und klicken.
* **Befolgen Sie den Plan** - Unsere Empfehlungen haben Hunderten von Campaign-Kunden dabei geholfen, ihre E-Mail-Programme erfolgreich auf den Weg zu bringen.
* **Überwachen Sie Ihr E-Mail-Konto für die Antwort**. Es ist ein schlechtes Erlebnis für Ihren Kunden, noreply@xyz.com zu verwenden oder nicht zu antworten.
* Inaktive Adressen können sich negativ auf die Zustellbarkeit auswirken. **Reaktivieren und erneuern Sie die Berechtigung auf Ihrer aktuellen Plattform**, nicht auf Ihren neuen IPs.
* **Domänen** - Verwenden Sie eine sendende Domäne, die eine Subdomäne der tatsächlichen Domäne Ihres Unternehmens ist.
   * Wenn Ihre Unternehmensdomäne beispielsweise xyz.com lautet, bietet email.xyz.com mehr Glaubwürdigkeit für die ISPs als xyzemail.com.
* **Transparenz** - Registrierungsdetails für Ihre E-Mail-Domäne sollten öffentlich verfügbar sein und nicht privat sein.

Unter vielen Umständen folgen Transaktionsnachrichten nicht dem herkömmlichen Ansatz zur Förderung der Erwärmung. Die Lautstärke von Transaktionsnachrichten lässt sich aufgrund ihrer Beschaffenheit nur schwer kontrollieren, da im Allgemeinen eine Benutzerinteraktion erforderlich ist, um den E-Mail-Kontakt Trigger. In einigen Fällen kann die Transition von Transaktionsnachrichten einfach ohne formellen Plan erfolgen. In anderen Fällen kann es besser sein, jeden Nachrichtentyp im Laufe der Zeit zu übergehen, um das Volumen langsam zu erhöhen. Sie können beispielsweise eine Transition wie folgt durchführen:

1. Kaufbestätigungen — hohe Interaktion im Allgemeinen
2. Warenkorbabbruch - mittel - hohe Interaktion im Allgemeinen
3. Willkommens-E-Mails - hohe Interaktion, können aber je nach den Erfassungsmethoden Ihrer Liste fehlerhafte Adressen enthalten
4. Winback-E-Mails - niedrigere Interaktion im Allgemeinen

## Produktspezifische Ressourcen

**Campaign**

* Weitere Informationen zum Verwalten der Zustellbarkeit beim Start einer neuen Plattform mit Adobe Campaign finden Sie in [diesem Abschnitt](/help/additional-resources/ac-starting-new-platform.md).
* In [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-waves) erfahren Sie, wie Sie mit mehreren Schüben mit Adobe Campaign Classic senden.
* In [diesem Abschnitt](/help/additional-resources/ac-domain-name-setup.md) erfahren Sie, wie Sie eine Subdomain vollständig Adobe Campaign Classic oder Standard zuweisen.
* [Control Panel: Vollständige Subdomain-Zuweisung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-classic-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html) - *Erfahren Sie, wie Sie eine Subdomain vollständig Adobe Campaign Classic zuweisen.*
* [Control Panel: Vollständige Subdomain-Zuweisung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html) - *Erfahren Sie, wie Sie eine Subdomain vollständig Adobe Campaign Standard zuweisen.*

## Zusätzliche Ressourcen

* In [diesem Abschnitt](/help/additional-resources/increase-reputation-with-ip-warming.md) erfahren Sie mehr über die Verbesserung der Reputation Ihrer E-Mail mit IP-Warming.
