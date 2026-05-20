---
title: Bulking und Blockieren von E-Mails
description: Erfahren Sie, warum ISPs E-Mail-Nachrichten in Bulk-Ordnern platzieren oder blockieren.
topics: Deliverability
jira: KT-7051
thumbnail: kt7051.jpg
doc-type: article
activity: understand
team: ACS
exl-id: 4b280f90-73b9-4b88-adb8-57b6a46ddad7
TQID: https://experienceleague.adobe.com/mNz7Z6yQjlK7-NShGkgXNR8hp9kKUXDl9nHzMG4j3Q4
product_v2: id: b27e5950-9033-45ac-9f86-eb22e567f615id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: c5f60233-d5ea-4453-a799-0ad258b4d399id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 100%

---

# Bulking und Blockieren

## Bulking

Beim Bulking landen E-Mails bei deren Versand im Spam- oder Junk-Ordner eines ISP. Sie erkennen Bulking daran, dass eine ungewöhnlich niedrige Öffnungsrate (und manchmal auch Klickrate) mit einer hohen Zustellrate einhergeht. Die Ursachen dafür, warum E-Mails in diese Ordner verschoben werden, variieren je nach ISP. Generell gilt jedoch: Wenn Nachrichten im Bulk-Ordner landen, muss ein Merkmal, das die Versandreputation beeinflusst (z. B. Listenhygiene), neu ausgewertet werden. Bulking ist ein Zeichen dafür, dass die Reputation abnimmt, was ein Problem ist, das sofort behoben werden muss, bevor es weitere Kampagnen beeinträchtigt. Wenden Sie sich an Ihren Adobe-Zustellbarkeitsberater, um eventuelle Probleme mit dem Bulking zu beheben.

## Blockieren

Eine Blockierung tritt auf, wenn Spam-Indikatoren ISP-Schwellen erreichen und der ISP beginnt, E-Mails von einem Absender zu blockieren (erkennbar durch zurückgewiesene Zustellversuche). Es gibt verschiedene Arten von Blockierungen. Im Allgemeinen werden einzelne IP-Adressen blockiert. Blockierungen können aber auch auf der Ebene der sendenden Domain oder Entität auftreten. Das Auflösen einer Blockierung erfordert spezielles Fachwissen. Wenden Sie sich daher an Ihren Adobe-Zustellbarkeitsberater.

## Blockierungsauflistung

Eine Blockierungsauflistung tritt auf, wenn ein Blockierungslistenverwalter eines Drittanbieters ein Spammer-ähnliches Verhalten in Verbindung mit einem Absender feststellt. Der Grund für eine Blockierungsauflistung wird manchmal von der verantwortlichen Partei veröffentlicht. Eine Auflistung basiert in der Regel auf der IP-Adresse, in schwerwiegenderen Fällen kann sie aber auch nach IP-Bereich oder sogar nach einer Absender-Domain erfolgen. Holen Sie sich zur Behebung einer Blockierungsauflistung die Unterstützung Ihres Adobe-Zustellbarkeitsberaters, um die Auflistung vollständig zu beheben und weitere Auflistungen zu verhindern. Einige Auflistungen sind besonders schwerwiegend und können lang anhaltende Reputationsprobleme verursachen, die nur schwer zu beheben sind. Das Ergebnis einer Blockierungsauflistung variiert je nach Blockierungsliste, kann aber möglicherweise die Zustellung aller E-Mails beeinträchtigen.

## Weitere Ressourcen

* Erfahren Sie mehr über [Echtzeit-Blackhole-Listen](/help/additional-resources/blocklist-databases.md), die Datenbanken mit IP-Adressen und Domains verwalten, die oft von Spammern verwendet werden.
