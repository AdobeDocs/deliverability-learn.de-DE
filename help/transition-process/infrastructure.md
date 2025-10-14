---
title: Infrastruktur
description: Erfahren Sie, was für den Aufbau einer E-Mail-Infrastruktur erforderlich ist.
topics: Deliverability
jira: KT-7052
thumbnail: kt7052.jpg
doc-type: article
activity: understand
role: Admin, Leader
level: Beginner
team: ACS
exl-id: 4025d95c-cc77-4e0c-9904-aaf60019b18c
source-git-commit: 6b312cdbba496818337c97ec4f42962aea757901
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 2%

---

# Infrastruktur

Eine erfolgreiche Zustellbarkeit hängt von einer soliden Grundlage ab. E-Mail-Infrastruktur ist ein Kernelement. Eine ordnungsgemäß aufgebaute E-Mail-Infrastruktur besteht aus mehreren Komponenten, nämlich Domain(s) und IP-Adresse(n). Diese Komponenten sind wie die Maschinen hinter den E-Mails, die Sie senden, und sie sind oft der Anker für den Versand von Reputation. Berater für Zustellbarkeit stellen sicher, dass diese Elemente während der Implementierung ordnungsgemäß eingerichtet werden. Aufgrund des Reputationselements ist es jedoch wichtig, dass Sie über dieses grundlegende Verständnis verfügen.

## Einrichten und Strategie von Domains {#domain-setup-and-strategy}

Die Zeiten haben sich geändert, und einige ISPs (wie Gmail und Yahoo) integrieren jetzt Domain-Reputation als zusätzlichen Punkt, wenn es darum geht, E-Mail-Reputation an einen Absender anzuhängen. Die Reputation Ihrer Domain basiert auf Ihrer Versand-Domain und nicht auf Ihrer IP-Adresse. Das bedeutet, dass Ihre Marke beim Filtern von ISP-Entscheidungen Vorrang hat.

Zu den Aufgaben beim Onboarding für neue Absender auf Adobe-Plattformen gehören das Einrichten Ihrer Versand-Domains und die Sicherstellung, dass Ihre Infrastruktur ordnungsgemäß eingerichtet ist. Sie sollten mit einem Experten darüber arbeiten, welche Bereiche Sie langfristig verwenden möchten. Im Folgenden finden Sie einige Tipps, die eine gute Domain-Strategie formen:

* Seien Sie bei der gewählten Domain so klar und reflektierend wie möglich, damit Benutzer die E-Mail nicht fälschlicherweise als Spam kennzeichnen. Einige Beispiele sind newsletter.foo.com, receipts.foo.com usw.
* Sie sollten Ihre übergeordnete oder Unternehmens-Domain nicht verwenden, da sich dies auf den Versand von E-Mails von Ihrem Unternehmen an ISPs auswirken könnte.
* Erwägen Sie die Verwendung einer Subdomain Ihrer übergeordneten Domain, um Ihre Versand-Domain zu legitimieren.
* Trennen Sie Ihre Subdomains für Transaktions- und Marketing-Nachrichtenkategorien. Dies wird dazu beitragen, den E-Mail-Traffic zuverlässiger zu gestalten, da ISPs nach dieser Versandmethode suchen. Dies ist eine bekannte Best Practice für E-Mails und wird dringend empfohlen.

## IP-Strategie {#ip-strategy}

Es ist wichtig, eine gut strukturierte IP-Strategie zu entwickeln, um eine positive Reputation aufzubauen. Die Anzahl der IPs und das Setup variieren je nach Ihrem Geschäftsmodell und Ihren Marketing-Zielen. Arbeiten Sie mit einem Experten zusammen, um eine klare Strategie zu entwickeln, um richtig zu beginnen. Beachten Sie dabei Folgendes:

* **Zu viele IPs** können Probleme mit dem Ruf des Triggers verursachen, da es eine gängige Taktik von Spammern ist, **Schneeschuh** zu verwenden. Diese Taktik wird von Spammern verwendet, bei der der Traffic über viele IPs verteilt wird, um den Versand von Spam-Mails zu maximieren. Obwohl Sie kein Spammer sind, können Sie wie einer aussehen, wenn Sie zu viele IPs verwenden, insbesondere wenn diese IPs keinen vorherigen Traffic hatten.
* **Zu wenige IPs** können Durchsatzprobleme und möglicherweise Probleme mit der Reputation des Triggers verursachen. Der Durchsatz variiert je nach ISP. Wie viel und wie schnell ein ISP akzeptieren möchte, hängt in der Regel von seiner Infrastruktur und den Rufschwellen ab.
* Die Trennung des Traffics für Messaging-Typen ist von entscheidender Bedeutung. Es ist wichtig, Marketing- und Transaktions-E-Mails zumindest in separaten IP-Pools zu trennen.
* Abhängig von Ihrer E-Mail-Strategie kann es auch ratsam sein, verschiedene Produkte oder Marketing-Streams in verschiedenen IP-Pools zu trennen, wenn Ihre Reputation drastisch unterschiedlich ist. Einige Marketer segmentieren auch nach Region. Wenn Sie die IP-Adresse für Traffic mit einer niedrigeren Reputation trennen, wird das Reputationsproblem nicht behoben, aber es werden Probleme mit E-Mail-Sendungen mit einer „guten“ Reputation verhindert. Schließlich möchte man sein gutes Publikum nicht einem riskanteren opfern.

## Feedback-Schleifen {#feedback-loops}

Hinter den Kulissen verarbeiten Adobe-Plattformen Daten zu Bounces, Beschwerden, Abmeldungen und mehr. Die Einrichtung dieser Feedback-Schleifen ist ein wichtiger Aspekt der Zustellbarkeit. Beschwerden können eine Reputation beschädigen. Daher sollten Sie E-Mail-Adressen verwenden, an die sich Beschwerden aus Ihrer Zielgruppe richten. Beachten Sie, dass Gmail diese Daten nicht zurückgibt. Abmeldekopfzeilen und Interaktionsfilter sind besonders für Gmail-Abonnenten wichtig, die jetzt die Mehrheit der Abonnentendatenbanken ausmachen.

## Authentifizierung {#authentication}

Authentifizierung ist der Prozess, den ISPs verwenden, um die Identität eines Absenders zu überprüfen. Die beiden gängigsten Authentifizierungsprotokolle sind [!DNL Sender Policy Framework] (SPF) und [!DNL DomainKeys Identified Mail] (DKIM). Diese sind für den Endbenutzer nicht sichtbar, helfen ISPs jedoch beim Filtern von E-Mails von verifizierten Absendern. [!DNL Domain-based Message Authentication Reporting and Conformance] (DMARC) wird immer beliebter, obwohl seine Richtlinien noch nicht von allen ISPs in ihre Reputationssysteme integriert wurden.

### SPF

[!DNL Sender Policy Framework] (SPF) ist eine Authentifizierungsmethode, mit der der Eigentümer einer Domain angeben kann, welche E-Mail-Server er zum Senden von E-Mails von dieser Domain verwendet.

### DKIM

[!DNL Domain Keys Identified Mail] (DKIM) ist eine Authentifizierungsmethode, mit der gefälschte Absenderadressen (häufig als „Spoofing“ bezeichnet) erkannt werden. Wenn DKIM aktiviert ist, kann der Empfänger bestätigen, ob der Absender zum Senden von E-Mails über diese Domain berechtigt ist.

### DMARC

[!DNL Domain-based Message Authentication, Reporting and Conformance] (DMARC) ist eine Authentifizierungsmethode, die es Domain-Inhabern ermöglicht, ihre Domain vor unbefugter Verwendung zu schützen. DMARC verwendet SPF oder DKIM oder beides, damit ein Domain-Inhaber steuern kann, was mit E-Mails passiert, bei denen die Authentifizierung fehlschlägt: zugestellt, unter Quarantäne gestellt oder abgelehnt.

## Produktspezifische Ressourcen

**Campaign**

* Wie Sie eine Subdomain vollständig an Adobe Campaign Classic oder Standard delegieren, erfahren Sie in [diesem Abschnitt](/help/additional-resources/ac-domain-name-setup.md).
* [Control Panel: Vollständige Subdomain-Delegierung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-classic-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html?lang=de) - *Erfahren Sie, wie Sie eine Subdomain vollständig an Adobe Campaign Classic delegieren.*
* [Control Panel: Vollständige Subdomain-Delegierung (Tutorial)](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/subdomains-and-certificates/subdomain-delegation.html?lang=de) - *Erfahren Sie, wie Sie eine Subdomain vollständig an Adobe Campaign Standard delegieren.*
* Weitere Informationen zur Implementierung einer Feedback-Schleife für eine Campaign Classic-Instanz finden Sie [&#x200B; (diesem Abschnitt](/help/additional-resources/acc-technical-recommendations.md#feedback-loop-acc).

## Zusätzliche Ressourcen

* Weitere Informationen zu den Authentifizierungsmethoden von SPF, DKIM und DMARC finden Sie [&#x200B; (diesem Abschnitt](/help/additional-resources/authentication.md).
* Weitere Informationen zur Verbesserung der E-Mail-Reputation mit IP-Warming finden [&#x200B; in diesem Abschnitt](/help/additional-resources/increase-reputation-with-ip-warming.md).
