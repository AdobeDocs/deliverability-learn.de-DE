---
title: Implementieren der Markenindikatoren von Gmail zur Nachrichtenidentifizierung (BIMI)
description: Informationen zur Implementierung von BIMI
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

[!DNL Brand Indicators for Message Identification] (BIMI) ist ein Industriestandard, der es ermöglicht, dass in teilnehmenden Plattformen neben der E-Mail eines Absenders ein genehmigtes Logo angezeigt wird.

Mit diesem Standard kann eine Marke ein Logo bestimmen, das in den Posteingängen der Postfachanbieter angezeigt werden soll. Nach der Veröffentlichung in einem so genannten BIMI-DNS (Domain Name System)-Eintrag kann ein Postfachanbieter dieses Logo abrufen und im Posteingang anzeigen, wenn bestimmte Kriterien erfüllt sind.

Unterschiedliche Anbieter implementieren die Lösung unterschiedlich, aber die Vorteile liegen auf der Hand: im Posteingang austreten, Vertrauen aufbauen und Kontrolle über das haben, was gezeigt wird.

BIMI verbessert nicht direkt die Zustellbarkeit oder Ihre Reputation. Es kann dabei helfen, mehr Vertrauen zu Ihren Empfängern aufzubauen und so die Interaktion mit ihnen zu fördern.

## Wie sieht es aus?

Auf der Seite der BIMI Gruppe finden Sie einige Beispiele für Implementierungen verschiedener Anbieter und weitere Details, bei welchen Anbietern das Logo [&#x200B; wird](https://bimigroup.org/where-is-my-bimi-logo-displayed/){target="_blank"}.

## Wer ist die BIMI Group?

Die BIMI-Gruppe ist eine Arbeitsgruppe, die das BIMI entwickelt, da es nicht nur das Logo, sondern auch die technischen, rechtlichen und Compliance-Anforderungen abdeckt.

Die BIMI Group besteht aus mehreren Stakeholdern aus verschiedenen Bereichen der Branche: Google, Yahoo, Fastmail, Proofpoint, Mailchimp, Sendgrid, Valimail und Validity.

## Wer unterstützt BIMI?

Die Mailbox-Anbieterliste, die BIMI unterstützt, wächst stetig. Eine aktuelle Liste finden Sie [hier](https://bimigroup.org/bimi-infographic/){target="_blank"} sowohl für unterstützende Anbieter als auch für Anbieter, die BIMI in Betracht ziehen.

Seit April 2023 umfasst die Liste Gmail, Yahoo, La Poste, Fastmail, Onet.pl und Zone, Proofpoint als Anti-Spam-Appliance und Apple Mail (ab iOS 16).

Die prominentesten Namen auf dieser Liste sind offensichtlich Yahoo, Gmail und ein kürzlich eingesetzter Nutzer: Apple mit iOS 16. Apple nimmt eine besondere Rolle in dem Mix ein, da es kein Postfachanbieter ist, aber es hat BIMI-Unterstützung zu seiner nativen E-Mail-App hinzugefügt. E-Mails, die mit BIMI konform sind, werden als „digital zertifizierte E-Mails“ angezeigt, was das Vertrauen in die Marke stärkt.

## Implementierung

Die Implementierung von BIMI erfolgt in mehreren Schritten:

1. Implementierung von DMARC (Domain-basierte Nachrichtenauthentifizierung, Reporting und Konformität) auf Durchsetzungsebene für die Versand-Domain und die Organisations-Domain - [Weitere Informationen](#dmarc)

1. Erstellung Ihres Markenlogos im SVG TinyPS-Format - [Mehr erfahren](#create-brand-logo)

1. Anmeldung für ein Verified Mark Zertifikat (nur bei einigen Anbietern erforderlich) - [Weitere Informationen](#vmc)

1. Publish einen BIMI-DNS-Eintrag mit dem Logo und dem Zertifikat - [Weitere Informationen](#publish-bimi-record)

1. Einen guten Ruf haben - [Mehr erfahren](#good-reputation)

>[!NOTE]
>
>Beachten Sie, dass alle Schritte deaktiviert sein müssen.


### DMARC {#dmarc}

DMARC ist ein Standard, der es der Marke ermöglicht zu entscheiden, was ein Postfachanbieter mit einer E-Mail tun soll, die fehlschlägt [Authentifizierung](../additional-resources/authentication.md). Die so genannten Policies reichen von „none“ über „quarantine“ (Spam-Ordner-Platzierung) bis „ject“ (die E-Mail direkt blockieren). Nur die beiden letztgenannten Richtlinien werden als „Durchsetzung“ bezeichnet und sind für das BIMI qualifiziert. E-Mails, die per Adobe versendet werden, bestehen die Authentifizierung, da SPF (Sender Policy Framework) und DKIM (Domain Keys Identified Mail) standardmäßig eingerichtet sind. Adobe richtet auf Anfrage DMARC auf Ihrer Versand-Domain ein.

Zusätzlich zu DMARC auf der Versand-Domain muss DMARC auch auf der Durchsetzungsebene für die Organisations-Domain verwendet werden (wenn die Versand-Domain news.example.com ist, ist example.com die Organisations-Domain).

### Erstellung Ihres Markenlogos {#create-brand-logo}

Die Erstellung des Logos muss den Anforderungen zu 100 % entsprechen. Bitte beachten Sie immer die [Richtlinien der BIMI Group](https://bimigroup.org/creating-bimi-svg-logo-files/){target="_blank"}.

Das Logo muss an einem sicheren Speicherort (HTTPS) gespeichert werden. Falls ein Content Delivery Network (CDN) verwendet wird, muss ein Schutz deaktiviert werden, der Postfachanbieter daran hindert, das Logo abzurufen (z. B. Bot-Schutz).

Neben den technischen Anforderungen gibt es einige praktische Empfehlungen wie ein quadratisches Logo, eine einfarbige Hintergrundfarbe und andere. Diese Empfehlungen eignen sich am besten zur Visualisierung. Einige Anbieter haben eigene Anforderungen, die zusätzlich zu denen der BIMI-Arbeitsgruppe bestehen. [Gmail](https://support.google.com/a/answer/10911027?sjid=903725605955621707-EU){target="_blank"} erfordert beispielsweise, dass das Logo mindestens 96 x 96 Pixel groß ist.
Bitte beachten Sie, dass eine Nichteinhaltung dazu führen kann, dass das Logo nicht angezeigt wird.

### Verifiziertes Prüfzeichen-Zertifikat (VMC) {#vmc}

Ein Verified Mark Certificate (VMC) ist nur für einige Postfachanbieter wie Gmail und Apple erforderlich und daher optional. Wir empfehlen jedoch, einen VMC zu erhalten, um BIMI wirklich zu nutzen.

Ein Verifiziertes Prüfzeichen-Zertifikat ist eine rechtliche Bestätigung, dass die Marke das Logo verwenden kann. Eine Zertifizierungsstelle prüft dies über das Markenamt, bei dem das Markenlogo eingetragen ist. Dieser Prozess umfasst mehrere rechtliche Validierungen und Prüfungen und kann einige Zeit in Anspruch nehmen. Derzeit stellen zwei CAs (Zertifizierungsstellen) VMCs aus: DigiCert und Entrust. Die erste Gruppe von Markenämtern sind die USA, Kanada, die EU, Großbritannien, Deutschland, Japan, Australien und Spanien.

In der Regel benötigen Sie einen VMC pro Logo. Ein VMC für Ihre Unternehmens-Domain deckt Subdomains ab, und mit einer zusätzlichen Funktion sogar verschiedene Domains. Wenn Sie über verschiedene Logos verfügen, ist mehr als ein VMC erforderlich. Die Zertifizierungsstelle oder der Partner, mit der bzw. dem Sie zusammenarbeiten möchten, unterstützt Sie bei der Einrichtung.

>[!NOTE]
>
>Beachten Sie, dass für VMCs eine jährliche Gebühr erhoben wird.

### Veröffentlichen des BIMI-Datensatzes {#publish-bimi-record}

Sobald die anderen Schritte abgeschlossen sind, kann der BIMI-DNS-Eintrag veröffentlicht werden. Der Datensatz sieht wie folgt aus:

```
default._bimi.[domain] IN TXT "v=BIMI1; l=[SVG URL]; a=[PEM URL]
```

„PEM URL“ ist der Dateispeicherort des Zertifikats mit verifizierter Markierung.

Für Ihre Versand-Domain muss dies per Adobe geschehen.

### Guter Ruf {#good-reputation}

Vertrauen ist der Schlüssel zum BIMI. Der Benutzer vertraut darauf, dass sein Postfachanbieter das Logo nur für rechtmäßige Absender anzeigt. Daher muss der Postfachanbieter der Marke vertrauen. Dies geschieht durch Ihre Absenderreputation. Wenn Sie einen guten Ruf haben, ist alles gut, aber wenn nicht, wird das Logo nicht angezeigt. Leider gibt es keine Informationen oder Metriken, anhand derer wir herausfinden könnten, ob die Reputation hoch genug ist.

Selbst der Aufwand und die Kosten für einen VMC nehmen diesen Teil nicht weg. Wenn der Postfachanbieter der Marke nicht vertraut, wird das Logo nicht angezeigt.

## Tipps und Tricks

* Die BIMI Group bietet ein praktisches Validierungstool für BIMI. Wenn Sie überprüfen möchten, ob alles eingerichtet und bereit ist, oder nur sehen möchten, ob das Logo konform ist, gehen Sie zu [diesem Link](https://bimigroup.org/bimi-generator/){target="_blank"}. Für letztere klicken Sie einfach auf **[!UICONTROL BIMI generieren]** und geben eine Platzhalter-Domain, aber die richtige Logo-URL ein. Der Inspektor wird Ihnen sagen, ob das Logo konform ist.

* Sie können sicher ohne VMC starten, es schadet Ihrer Reputation nicht, wenn Ihr BIMI-Eintrag keine VMC-URL enthält, aber das Logo kann bereits in Yahoo angezeigt werden.

* Die Implementierung von DMARC auf Unternehmensebene ist ein großes Unterfangen. Einige Unternehmen haben sich darauf spezialisiert, Marken dabei zu unterstützen, eine vollständige DMARC-Akzeptanz zu erreichen.

* Eine umfangreiche Liste häufig gestellter Fragen wird [hier](https://bimigroup.org/faqs-for-senders-esps/){target="_blank"} veröffentlicht.
