---
title: Beschwerden
description: Erfahren Sie mehr über Beschwerden, die registriert werden, wenn ein Benutzer angibt, dass eine E-Mail unerwünscht ist oder unerwartet gesendet wurde.
topics: Deliverability
jira: KT-7048
thumbnail: kt7048.jpg
doc-type: article
activity: understand
team: ACS
exl-id: 0343820d-f5af-4b8a-bcab-dbb47ae7aecb
TQID: https://experienceleague.adobe.com/W9G0ZPGeIm5KmVHu5-VuMd-Kb-4x4f7qhBPnpskxqqA
product_v2:
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: ea90ebee-5c84-42d9-8b21-006bdabc95a3
  - id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 307
ht-degree: 100%

---

# Beschwerden

Beschwerden werden registriert, wenn ein Benutzer angibt, dass eine E-Mail unerwünscht ist oder unerwartet gesendet wurde. Diese Aktion des Abonnenten wird in der Regel entweder über den E-Mail-Client des Abonnenten protokolliert, wenn dieser die Spam-Schaltfläche drückt, oder über das Spam-Reporting-System eines Drittanbieters.

## ISP-Beschwerde

Die meisten Tier-1- und einige Tier-2-ISPs bieten ihren Benutzern eine Spam-Reporting-Methode, da Opt-out- und Abmeldeverfahren in der Vergangenheit in böswilliger Absicht zur Validierung einer E-Mail-Adresse verwendet wurden. Adobe Campaign erhält diese Beschwerden über ISP-FBLs. Dies wird während des Einrichtungsprozesses für alle ISPs festgelegt, die FBLs bereitstellen, und ermöglicht Adobe Campaign, automatisch E-Mail-Adressen, die sich beschwert haben, in die Quarantäne-Tabelle zur Unterdrückung aufzunehmen. Spitzen bei ISP-Beschwerden können ein Indikator für eine schlechte Listenqualität, nicht optimale Listenerfassungsmethoden oder unzureichende Interaktionsrichtlinien sein. Beschwerden werden häufig auch dann vermerkt, wenn Inhalte nicht relevant sind.

## Beschwerden von Drittanbietern

Es gibt mehrere Anti-Spam-Gruppen, die Spam-Reporting auf einer breiteren Ebene ermöglichen. Von diesen Drittanbietern verwendete Beschwerdemetriken werden zum Kennzeichnen von E-Mail-Inhalten verwendet, um Spam-E-Mails zu identifizieren. Dieser Prozess wird auch als Fingerabdruck bezeichnet. Benutzer dieser Beschwerdemethoden von Drittanbietern haben im Allgemeinen mehr Erfahrung mit E-Mails, sodass diese Beschwerden größere Auswirkungen haben können als andere Beschwerden, wenn sie unbeantwortet bleiben.

>[!NOTE]
>
>ISPs sammeln die Beschwerden und verwenden sie, um die allgemeine Reputation eines Absenders zu ermitteln. Alle E-Mail-Adressen mit Beschwerden sollten so schnell wie möglich und in Übereinstimmung mit den lokalen Gesetzen und Vorschriften unterdrückt und nicht mehr kontaktiert werden.

## Produktspezifische Ressourcen

**Adobe Campaign Classic**

* [Tracking-Indikatoren](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=de#tracking-indicators)

**Adobe Campaign Standard**

* [Beschwerdenbericht](https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/list-of-reports/complaints.html?lang=de#reporting)
