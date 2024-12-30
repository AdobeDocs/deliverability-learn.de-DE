---
title: Microsoft (Hotmail, Outlook, Windows Live usw.)
description: Microsoft ist in der Regel der zweit- oder drittgrößte Anbieter, je nach Zusammensetzung Ihrer Liste, und sie handhaben Traffic geringfügig anders als andere ISPs.
topics: Deliverability
jira: KT-5319
doc-type: article
activity: understand
role: Admin, Leader, User
level: Beginner
team: TM
exl-id: d706cb90-828a-4ab3-8f93-c9bd71553d63
source-git-commit: 6b312cdbba496818337c97ec4f42962aea757901
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# [!DNL Microsoft] ([!DNL Hotmail], [!DNL Outlook], [!DNL Windows Live] usw.)

[!DNL Microsoft] ist in der Regel der zweit- oder drittgrößte Anbieter, je nach Zusammensetzung Ihrer Liste, und sie handhaben Traffic geringfügig anders als andere ISPs.

Im Folgenden finden Sie einige Highlights:

## Welche Daten sind wichtig?

[!DNL Microsoft] konzentriert sich auf die Reputation des Absenders, Beschwerden, Benutzerinteraktionen und die eigene Gruppe vertrauenswürdiger Benutzer (auch als Sender Reputation Data oder SRD bekannt), die sie nach Feedback abfragen.

## Welche Daten stellen sie zur Verfügung?

Mit dem proprietären Sender Reporting Tool von [!DNL Microsoft], [!DNL Smart Network Data Services] (SNDS), können Sie Metriken zur Anzahl der versendeten E-Mails und der akzeptierten E-Mails sowie Beschwerden und Spam-Fallen anzeigen. Beachten Sie, dass es sich bei den freigegebenen Daten um ein Beispiel handelt und nicht um exakte Zahlen. Sie stellen jedoch am besten dar, wie [!DNL Microsoft] Sie als Absender wahrnimmt. [!DNL Microsoft] gibt keine Informationen über die vertrauenswürdige Benutzergruppe öffentlich bekannt, aber diese Daten sind über das [!DNL Return Path Certification] gegen eine zusätzliche Gebühr verfügbar.

## Reputation des Absenders

[!DNL Microsoft] hat sich traditionell auf die Übermittlung von IP-Adressen bei der Bewertung der Reputation und bei Filterentscheidungen konzentriert. Sie arbeiten aktiv daran, auch ihre Fähigkeiten im Bereich der Versand-Domains zu erweitern. Beides ist weitgehend auf die traditionellen Reputations-Influencer zurückzuführen, wie Beschwerden und Spam-Fallen. Die Zustellbarkeit kann auch stark durch das Rückkehrpfad-Zertifizierungsprogramm beeinflusst werden, das spezifische quantitative und qualitative Programmanforderungen hat.

## Insights

[!DNL Microsoft] kombiniert alle Empfangs-Domains, um die Reputation des Versands zu etablieren und zu verfolgen. Dazu gehören [!DNL Hotmail], [!DNL Outlook], MSN, [!DNL Windows Live] usw. sowie alle von Office 365 gehosteten E-Mails des Unternehmens. [!DNL Microsoft] können besonders empfindlich auf Volumenschwankungen reagieren. Ziehen Sie daher in Betracht, spezifische Strategien anzuwenden, um von großen Sendungen aus auf- und abzurufen, anstatt volumenbasierte plötzliche Änderungen zuzulassen.

[!DNL Microsoft] ist auch besonders streng während der ersten Tage des IP-Warming, was in der Regel bedeutet, dass die meisten E-Mails anfänglich gefiltert werden. Die meisten ISPs halten Absender bis zum Beweis ihrer Schuld für unschuldig. [!DNL Microsoft] ist das Gegenteil und hält dich für schuldig, bis du dir selbst die Unschuld beweist.
