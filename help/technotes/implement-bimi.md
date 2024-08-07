---
title: Implementieren von Gmail's Brand Indicators for Message Identification (BIMI)
description: Erfahren Sie, wie Sie BIMI implementieren
topics: Deliverability
role: Admin
level: Beginner
jira: KT-14079
exl-id: 6b911bcc-a531-466a-8bd3-7fa469b96cc7
source-git-commit: b96539608acd51ce76ef5bdaf5afd07b5a4208b7
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Implementieren von [!DNL Brand Indicators for Message Identification] (BIMI)

[!DNL Brand Indicators for Message Identification] (BIMI) ist ein Branchenstandard, der es ermöglicht, auf teilnehmenden Plattformen neben der E-Mail eines Absenders ein genehmigtes Logo anzuzeigen.

Mit diesem Standard kann eine Marke ein Logo bestimmen, das in den Postfächern der Postfächer angezeigt werden soll. Nach der Veröffentlichung in einem so genannten BIMI DNS (Domain Name System)-Datensatz kann ein Postfachanbieter dieses Logo abrufen und im Posteingang anzeigen, wenn bestimmte Kriterien erfüllt sind.

Verschiedene Anbieter führen unterschiedliche Implementierungen durch, aber die Vorteile sind klar: das Hervorheben im Posteingang, das Aufbauen von Vertrauen und die Kontrolle darüber, was gezeigt wird.

BIMI verbessert nicht direkt die Zustellbarkeit oder Ihre Reputation. Dies kann dazu beitragen, mehr Vertrauen in Ihre Empfänger zu schaffen und so die Interaktion zu steigern.

## Wie sieht es aus?

Sie finden einige Beispiele für Implementierungen von verschiedenen Anbietern und weitere Details darüber, welche Anbieter das Logo auf der Seite [BIMI Group](https://bimigroup.org/where-is-my-bimi-logo-displayed/){target="_blank"} anzeigen.

## Wer ist die BIMI-Gruppe?

Die BIMI-Gruppe ist eine Arbeitsgruppe, die BIMI entwickelt, da sie nicht nur das Logo, sondern auch die technischen, rechtlichen und Compliance-Anforderungen abdeckt.

Die BIMI-Gruppe besteht aus mehreren Akteuren aus verschiedenen Branchen: Google, Yahoo, Fastmail, Proofpoint, Mailchimp, Sendgrid, Valimail und Validity.

## Wer unterstützt BIMI?

Die Liste der Postfachanbieter, die BIMI unterstützen, wächst stetig. Eine aktuelle Liste finden Sie [hier](https://bimigroup.org/bimi-infographic/){target="_blank"} sowohl für unterstützende Anbieter als auch für Anbieter, die BIMI in Erwägung ziehen.

Seit April 2023 enthält die Liste Gmail, Yahoo, La Poste, Fastmail, Onet.pl und Zone, Proofpoint als Anti-Spam-Gerät und Apple Mail (ab iOS 16).

Die bekanntesten Namen auf dieser Liste sind offensichtlich Yahoo, Gmail und ein aktueller Anwender: Apple mit iOS 16. Apple spielt eine besondere Rolle in diesem Mix, da es kein Postfachanbieter ist, doch hat es BIMI-Unterstützung zu seiner nativen E-Mail-App hinzugefügt. E-Mails, die mit BIMI konform sind, werden als &quot;digital zertifizierte E-Mail&quot;angezeigt, was das Vertrauen in die Marke stärkt.

## Implementierung

Die Implementierung von BIMI erfolgt in mehreren Schritten:

1. Implementierung von DMARC (Domain based Message Authentication, Reporting and Conformance) auf Durchsetzungsebene für die sendende Domain und ihre Organisationsdomäne - [Weitere Informationen](#dmarc)

1. Erstellung Ihres Markenlogos im SVG TinyPS-Format - [Mehr erfahren](#create-brand-logo)

1. Anmeldung für ein Verified Mark Certificate (nur bei einigen Providern erforderlich) - [Weitere Informationen](#vmc)

1. Publish einen BIMI-DNS-Eintrag mit dem Logo und dem Zertifikat - [Weitere Informationen](#publish-bimi-record)

1. Gute Reputation - [Mehr erfahren](#good-reputation)

>[!NOTE]
>
>Beachten Sie, dass alle Schritte ausgecheckt werden müssen.


### DMARC {#dmarc}

DMARC ist ein Standard, der es der Marke ermöglicht zu entscheiden, was ein Postfachanbieter mit einer E-Mail tun soll, bei der [Authentifizierung](../additional-resources/authentication.md) fehlschlägt. Die so genannten Richtlinien reichen von &quot;Keine&quot; über &quot;Quarantäne&quot;(Platzierung von Spam-Ordnern) bis &quot;Zurückweisen&quot;(Blockieren der E-Mail). Nur die beiden letztgenannten Richtlinien werden als &quot;Durchsetzung&quot;bezeichnet und sind für BIMI qualifiziert. Durch Adobe gesendete Nachrichten übergeben die Authentifizierung, da SPF (Sender Policy Framework) und DKIM (Domain Keys Identified Mail) standardmäßig eingerichtet sind. Adobe richtet DMARC auf Anfrage für Ihre Versanddomäne ein.

Zusätzlich zu DMARC in der sendenden Domäne muss DMARC auch auf Durchsetzungsebene für die Organisationsdomäne verwendet werden (wenn die sendende Domäne news.example.com ist, ist example.com die Organisationsdomäne).

### Erstellung des Markenlogos {#create-brand-logo}

Die Erstellung des Logos muss den Anforderungen von 100 % entsprechen. Beachten Sie immer die Richtlinien der [BIMI-Gruppe](https://bimigroup.org/creating-bimi-svg-logo-files/){target="_blank"}.

Das Logo muss an einem sicheren Speicherort (HTTPS) gespeichert werden. Wenn ein Content Delivery Network (CDN) verwendet wird, muss jeder Schutz deaktiviert werden, der verhindert, dass Posteingangsanbieter das Logo abrufen (z. B. Bot Protection).

Neben den technischen Anforderungen gibt es einige praktische Empfehlungen wie ein quadratisches Logo, eine solide Farbe als Hintergrund und andere. Diese Empfehlungen dienen der optimalen Visualisierung. Einige Provider haben ihre eigenen Anforderungen, die zusätzlich zu denen der BIMI-Arbeitsgruppe gestellt werden. Für [Gmail](https://support.google.com/a/answer/10911027?sjid=903725605955621707-EU){target="_blank"} muss das Logo beispielsweise mindestens 96 x 96 Pixel groß sein.
Beachten Sie bitte, dass die Nichteinhaltung dazu führen kann, dass das Logo nicht angezeigt wird.

### Überprüftes Mark-Zertifikat (VMC) {#vmc}

Ein Verified Mark Certificate (VMC) ist nur für einige Postfachanbieter wie Gmail und Apple erforderlich und ist daher optional. Wir empfehlen, einen VMC zu erhalten, um BIMI wirklich zu nutzen.

Ein Verified Mark Certificate ist eine gültige Bestätigung dafür, dass die Marke das Logo verwenden kann. Eine Zertifizierungsstelle prüft dies über die Markenbehörde, bei der das Markenlogo registriert ist. Dieser Prozess umfasst mehrere Validierungen und Prüfungen, die einige Zeit in Anspruch nehmen können. Derzeit stellen zwei Zertifizierungsstellen (Zertifizierungsstellen) VMCs aus: Digicert und Entrust. Die ersten Markenbüros sind die USA, Kanada, die EU, Großbritannien, Deutschland, Japan, Australien und Spanien.

In der Regel benötigen Sie einen VMC pro Logo. Eine VMC für Ihre Organisationsdomäne deckt Unterdomänen ab und verfügt über eine zusätzliche Funktion auch für verschiedene Domänen. Falls Sie unterschiedliche Logos haben, benötigen Sie mehr als einen VMC. Die Zertifizierungsstelle oder der Partner, mit dem Sie zusammenarbeiten, hilft Ihnen bei der Einrichtung.

>[!NOTE]
>
>Beachten Sie, dass VMCs eine jährliche Gebühr haben.

### Veröffentlichen des BIMI-Datensatzes {#publish-bimi-record}

Sobald die anderen Schritte abgeschlossen sind, kann der BIMI DNS-Eintrag veröffentlicht werden. Der Datensatz sieht wie folgt aus:

```
default._bimi.[domain] IN TXT "v=BIMI1; l=[SVG URL]; a=[PEM URL]
```

&quot;PEM-URL&quot;ist der Dateispeicherort des Verified Mark Certificate.

Für Ihre Versanddomäne muss dies über Adobe erfolgen.

### Gute Reputation {#good-reputation}

Vertrauen ist der Schlüssel zu BIMI. Der Benutzer vertraut seinem Postfachanbieter, dass er das Logo nur für rechtmäßige Absender anzeigt, sodass der Postfachanbieter der Marke vertrauen muss. Dies geschieht durch Ihre Reputation als Absender. Wenn Sie einen hohen Ruf haben, ist alles gut, aber wenn Sie es nicht sind, wird das Logo nicht angezeigt. Leider gibt es keine Informationen oder Metriken, mit denen wir herausfinden können, ob die Reputation hoch genug ist.

Selbst wenn man den Aufwand und die Kosten für einen VMC durchläuft, nimmt man diesen Teil nicht weg. Wenn der Postfachanbieter der Marke nicht vertraut, wird das Logo nicht angezeigt.

## Tipps und Tricks

* Die BIMI Gruppe bietet ein praktisches Validierungstool für BIMI. Wenn Sie überprüfen möchten, ob alles eingerichtet ist und bereit ist, oder nur prüfen möchten, ob das Logo kompatibel ist, gehen Sie zu [diesem Link](https://bimigroup.org/bimi-generator/){target="_blank"}. Klicken Sie für letztere einfach auf **[!UICONTROL BIMI generieren]** und geben Sie eine Platzhalterdomäne ein, aber die richtige Logo-URL. Der Inspektor wird Ihnen mitteilen, ob das Logo konform ist.

* Sie können sicher ohne VMC starten, es gibt keinen Schaden für Ihre Reputation, wenn Ihr BIMI-Datensatz keine VMC-URL enthält, aber das Logo kann bereits in Yahoo angezeigt werden.

* Die organisatorische Umsetzung von DMARC ist ein großes Unternehmen. Einige Unternehmen sind spezialisiert, um Marken bei der vollständigen Einführung von DMARC zu helfen.

* Eine umfassende Liste häufig gestellter Fragen wird [hier](https://bimigroup.org/faqs-for-senders-esps/){target="_blank"} veröffentlicht.
