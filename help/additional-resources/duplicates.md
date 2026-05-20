---
title: Duplikate
description: Erfahren Sie, wie Sie Duplikate identifizieren und begrenzen können, um die Zustellbarkeit zu verbessern.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: f89dbb38-a8d4-4294-b017-6fed72591593
TQID: https://experienceleague.adobe.com/7KlDe-wQmAih6L4bl4xrw-lVS35-wNzyyxneyFbSo0A
product_v2:
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b0bb9048-d951-48d8-8232-45cf248a7e27
  - id: c5f60233-d5ea-4453-a799-0ad258b4d399
  - id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 413
ht-degree: 28%

---

# Duplikate {#duplicates}

Das Vorhandensein doppelter E-Mail-Adressen kann unterschiedliche Konsequenzen haben:

* Dieselbe Nachricht wird mehrmals gesendet. Selbst wenn Adobe vor dem Versand standardmäßig ein Deduplizierungsverfahren durchführt, gibt es nichts, was das Senden derselben Nachricht durch verschiedene Aktionen mit demselben Inhalt beim Aufteilen einer Zielgruppe verhindern könnte.
* Abmeldeanfragen wurden nicht berücksichtigt. Wenn sich ein Empfänger abmeldet, nachdem er eine Nachricht erhalten hat, kann sein doppeltes Profil weiterhin für zukünftige Nachrichten verwendet werden.

Von der Umgehung des Anmeldeverfahrens abgesehen, führt dies wahrscheinlich dazu, dass Benutzer diese Nachrichten als Spam betrachten und der ISP die Adresse auf die Blockierungsliste setzt.

Bei der Bearbeitung der Datenbank muss besonders vorsichtig vorgegangen werden:

* Importe müssen sorgfältig konfiguriert werden, insbesondere bei der Auswahl des Abstimmschlüssels.
* Auch geänderte E-Mail-Adressen können zur Duplikatquelle werden. Insbesondere können zwei Adressen mit unterschiedlichen Domains an dasselbe Postfach weitergeleitet werden, z. B. wenn ein Unternehmen den Namen geändert und die frühere Domain eine Zeit lang gepflegt hat: joe.doe@amce-co.com und joe.doe@acme-rebranded.com.
* Automatische Importe, ob aus Listen oder aus anderen Datenbanken, sind Elemente, die bei der Verwaltung von Profilen berücksichtigt werden müssen. Was geschieht, wenn Sie ein Profil löschen oder in eine andere Partition verschieben? Sie kann in der ursprünglichen Partition durch einen automatischen Import neu erstellt werden, z. B. wenn eine Bestellung aufgegeben wird.
* Das Speichern von Profilen in verschiedenen Ordnern kann mithilfe von Ansichten anstelle von Partitionen implementiert werden. Auf diese Weise können Sie sicher sein, dass sich die Profile in derselben physischen Partition befinden, während Sie weiterhin die Anzeige und Verwaltung der entsprechenden Rechte ermöglichen.

Es gibt jedoch Fälle, in denen Duplikate zwischen den verschiedenen Partitionen normal sind. Wenn beispielsweise für Dritte oder verschiedene Unternehmensentitäten gesendet wird, ist es logisch, dass dieselbe Person aus verschiedenen Gründen Empfänger ist. Es ist jedoch selten normal, Duplikate innerhalb derselben Partition zu finden.

## Produktspezifische Ressourcen

Die Deduplizierung von Adressen schützt Ihre Reputation und gewährleistet eine gute Quarantäneverwaltung. Weitere Informationen finden Sie in den folgenden Abschnitten der Produktdokumentation:

**Adobe Campaign Classic**

* [Aktivität „Deduplizierung“](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/deduplication.html?lang=de)
* [Verwenden der Zusammenführungsfunktion der Deduplizierungsaktivität](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=de#automating-with-workflows)

**Adobe Campaign Standard**

* [Daten einer importierten Datei deduplizieren](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-use-case/data-management/deduplicating-data-imported-file.html?lang=de)
