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
TQID: https://experienceleague.adobe.com/pbp5vbHUIHSL9zL9gQf4LpIhEYZI1umEesy3czbJx-4
product_v2: id: b27e5950-9033-45ac-9f86-eb22e567f615id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: ea90ebee-5c84-42d9-8b21-006bdabc95a3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 335
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
