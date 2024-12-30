---
title: Adressensammlung und Listenwachstum
description: Erfahren Sie, welche Quellen am besten für neue E-Mail-Adressen geeignet sind, wie Sie eine hohe Datenqualität sicherstellen und wie Sie sich an den rechtlichen Richtlinien ausrichten können.
topics: Deliverability
jira: KT-7063
thumbnail: kt7063.jpg
doc-type: article
activity: understand
team: TM
exl-id: 350950dc-4703-402a-8e22-3862f4e21d52
source-git-commit: 9444f8601f2f349398ee5deb9d5f4d4f7abb44f5
workflow-type: tm+mt
source-wordcount: '1594'
ht-degree: 3%

---

# Adressensammlung und Listenwachstum

Die besten Quellen für neue E-Mail-Adressen sind direkte Quellen wie Anmeldungen auf Ihrer Website oder in physischen Geschäften. In diesen Situationen können Sie das Erlebnis steuern, um sicherzustellen, dass es positiv ist und dass der Abonnent daran interessiert ist, E-Mails von Ihrer Marke zu erhalten.

Einige Hinweise zu diesen Anmeldemethoden:

**Physischer Store** Die Listensammlung kann aufgrund mündlicher oder schriftlicher Adresseingaben zu Problemen führen, die eine Rechtschreibfehler in den Adressen verursachen. Es wird empfohlen, nach der Anmeldung im Geschäft so schnell wie möglich eine Bestätigungs-E-Mail zu senden.

Die häufigste Form der **Website-Anmeldung** ist „Single Opt-in“. Dies ist der absolute Mindeststandard, den Sie zum Erfassen von E-Mail-Adressen verwenden sollten. Ein Single-Opt-in liegt vor, wenn der Inhaber einer bestimmten E-Mail-Adresse einem Absender die Berechtigung zum Senden von Marketing-E-Mails erteilt, normalerweise durch Senden der Adresse über ein Web-Formular oder In-Store-Anmeldungen. Mit dieser Methode kann zwar eine erfolgreiche E-Mail-Kampagne ausgeführt werden, sie kann jedoch die Ursache einiger Probleme sein.

* Unbestätigte E-Mail-Adressen können Rechtschreibfehler aufweisen, fehlerhaft, falsch sein oder böswillig verwendet werden. Tippfehler und falsch formatierte Adressen verursachen hohe Absprungraten, was zu Sperren durch ISPs oder IP-Reputationsverlust führen kann und dies auch tut.

* Die böswillige Übermittlung bekannter Spam-Fallen (manchmal auch als „Listen-Vergiftung“ bezeichnet) kann zu großen Problemen bei der Zustellung und Reputation führen, wenn der Besitzer dieser Falle Maßnahmen ergreift. Es ist unmöglich zu wissen, ob der Empfänger wirklich ohne Bestätigung zu einer Marketing-Liste hinzugefügt werden möchte. Dies macht es ebenso unmöglich, die Erwartungen der Empfängerin bzw. des Empfängers festzulegen, und kann zu vermehrten Spam-Beschwerden führen - und manchmal zu einer Blockierungsauflistung, wenn die gesammelten E-Mails eine Spam-Falle sind.

Anleitungen dazu, wie Sie die Probleme minimieren können, die sowohl im physischen Speicher als auch beim einmaligen Opt-in auftreten, finden Sie im Abschnitt [Datenqualität und -hygiene](#data-quality-and-hygiene) in diesem Handbuch die Details und Vorteile des doppelten Opt-ins.

>[!NOTE]
>
>Abonnentinnen und Abonnenten verwenden oft Wegwerf-Adressen, abgelaufene Adressen oder Adressen, die nicht zu ihren gehören, um von einer Website zu erhalten, was sie möchten, aber auch um zu vermeiden, zu Marketing-Listen hinzugefügt zu werden. In diesem Fall führen die Listen von Marketing-Fachleuten zu einer hohen Anzahl von Hardbounces, hohen Spam-Beschwerderaten und Abonnentinnen und Abonnenten, die E-Mails nicht anklicken, öffnen oder positiv mit ihnen interagieren. Dies kann als Warnsignal für Postfachanbieter und ISPs dienen.

## Anmeldeformulare

Zusätzlich zum Hinzufügen der Felder für die Daten möchten Sie Daten über Ihre neuen Abonnenten erfassen. Es gibt einige andere Dinge, die Sie mit Ihrem Anmeldeformular auf der Website tun sollten.

* Geben Sie dem Abonnenten klare Erwartungen, dass er mit dem Empfang von E-Mails einverstanden ist, was er erhalten wird und wie oft er die E-Mails erhalten wird.
* Fügen Sie Optionen hinzu, mit denen Abonnentinnen und Abonnenten die Häufigkeit oder den Typ der Nachrichten auswählen können, die sie erhalten. Mit diesen Optionen können Sie die Voreinstellungen des Abonnenten von Anfang an kennen, damit Sie Ihrem neuen Kunden das bestmögliche Erlebnis bieten können.
* Abwägen Sie das Risiko, das Interesse des Abonnenten während des Anmeldevorgangs zu verlieren, indem Sie so viele Informationen wie möglich anfordern. Dinge wie Geburtstag, Ort oder Interessen helfen Ihnen, mehr personalisierte Inhalte zu senden. Die Abonnentinnen und Abonnenten jeder Marke haben unterschiedliche Erwartungen und Toleranzschwellen. Daher ist es wichtig, zu testen, um das richtige Gleichgewicht für Ihre Situation zu finden.

>[!NOTE]
>
> Verwenden Sie während des Anmeldevorgangs keine vorab markierten Kästchen. Es kann Sie zwar legal in Schwierigkeiten bringen, aber es ist auch ein negatives Kundenerlebnis.

## Datenqualität und -hygiene

Das Sammeln von Daten ist nur ein Teil der Herausforderung. Außerdem müssen Sie sicherstellen, dass die Daten sowohl korrekt als auch verwendbar sind. Sie sollten über grundlegende Formatfilter verfügen. Eine E-Mail-Adresse ist ungültig, wenn sie kein &quot;@&quot; oder &quot;.“ enthält. Beispiel. Achten Sie darauf, keine allgemeinen Alias-Adressen zuzulassen, die auch als Rollenkonten bezeichnet werden (z. B. „info“, „admin“, „sales“, „support“ ). Rollenkonten können ein Risiko darstellen, da der Empfänger naturgemäß eine Gruppe von Personen anstelle eines einzelnen Abonnenten enthält. Erwartungen und Toleranz können innerhalb einer Gruppe variieren, was das Risiko von Beschwerden, unterschiedlicher Interaktion, Abmeldungen und allgemeiner Verwirrung birgt.

Im Folgenden finden Sie einige Lösungen für häufige Probleme, auf die Sie mit Ihren E-Mail-Adressdaten stoßen können:

**[!DNL Double opt-in (DOI)]**
[!DNL Double opt-in (DOI)] gilt für die meisten E-Mail-Experten als Best Practice für die Zustellbarkeit. Wenn Sie Probleme mit Spam-Fallen oder Beschwerden bei Ihren Begrüßungs-E-Mails haben, stellt DOI sicher, dass sich der Abonnent, der Ihre E-Mails erhält, tatsächlich für Ihr E-Mail-Programm angemeldet hat und Ihre E-Mails erhalten möchte.

DOI besteht darin, eine Bestätigungs-E-Mail an die E-Mail-Adresse des Abonnenten zu senden, der sich bei Ihrem E-Mail-Programm angemeldet hat. Diese enthält einen Link, auf den geklickt werden muss, um die Zustimmung zu bestätigen. Bei dieser Akquise-Methode würde der Absender, wenn der Abonnent es nicht bestätigt, ihm keine weiteren E-Mails senden. Teilen Sie neuen Abonnentinnen und Abonnenten mit, dass Sie dies auf der Website tun, und ermutigen Sie sie, die Anmeldung abzuschließen, bevor Sie fortfahren. Bei dieser Methode sinkt zwar die Anzahl der Anmeldungen, aber die Personen, die sich anmelden, sind meist sehr engagiert und bleiben langfristig. Dies führt in der Regel zu einem viel höheren ROI für den Absender.

**Ausgeblendetes Feld**
Das Anwenden eines ausgeblendeten Felds auf Ihrem Anmeldeformular ist eine hervorragende Möglichkeit, automatische Bot-Anmeldungen von echten menschlichen Abonnenten zu unterscheiden. Da das Datenfeld nicht sichtbar und im HTML-Code ausgeblendet ist, gibt ein Bot Daten ein, wo ein Mensch dies nicht tun würde. Mit dieser Methode können Sie Regeln erstellen, um alle Anmeldungen zu unterdrücken, die Daten enthalten, die in dieses ausgeblendete Feld eingetragen wurden.

**[!DNL re-CAPTCHA] ist eine Validierungsmethode, mit der Sie die Wahrscheinlichkeit verringern können, dass der Abonnent ein Bot und keine reale Person ist. Es gibt verschiedene Versionen, von denen einige Schlüsselwortidentifizierung oder Bilder enthalten. Einige Versionen sind effektiver als andere, und was Sie an Sicherheit und Zustellbarkeit gewinnen, ist wesentlich höher als jede negative Auswirkung auf Konversionen.

## Rechtliche Leitlinien

Wenden Sie sich an Ihre Rechtsanwälte, um lokale und nationale Gesetze bezüglich E-Mails zu interpretieren. Denken Sie daran, dass E-Mail-Gesetze in verschiedenen Ländern und manchmal in verschiedenen lokalen Regionen innerhalb eines Landes sehr unterschiedlich sind.

* Stellen Sie sicher, dass Sie die Standortdaten eines Abonnenten erfassen, damit Sie die nationalen Gesetze des Abonnenten einhalten. Ohne dieses Detail können Sie sich darauf beschränken, wie Sie an Abonnenten vermarkten können.
* Alle relevanten Gesetze werden durch den Standort des Empfängers bestimmt, nicht durch den Absender. Daher müssen Sie die Gesetze jedes Landes kennen und befolgen, in dem Sie einen Abonnenten haben könnten.
* Oft ist es schwierig, mit absoluter Sicherheit das Land zu kennen, in dem der Abonnent seinen Wohnsitz hat. Die vom Kunden bereitgestellten Daten können veraltet sein, und die Pixelortdaten können aufgrund von VPN oder Image-Warehousing, wie bei Gmail und Yahoo, ungenau sein. Im Zweifelsfall ist es am sichersten, die strengsten Gesetze und Richtlinien anzuwenden.

## Andere nicht empfohlene Methoden zur Listenerfassung

Es gibt viele andere Möglichkeiten, Adressen zu sammeln, jede mit ihren eigenen Chancen, Herausforderungen und Nachteilen. Adobe empfiehlt diese im Allgemeinen nicht, da die Verwendung oft durch vom Anbieter akzeptable Nutzungsrichtlinien eingeschränkt wird. Wir werden uns einige gängige Beispiele ansehen, damit Sie die Gefahren kennenlernen können, die Ihnen helfen, die Risiken zu begrenzen oder zu vermeiden:

**Liste kaufen oder mieten**
Es gibt viele Arten von E-Mail-Adressen. Primäre E-Mails, geschäftliche E-Mails, Schul-E-Mails, sekundäre E-Mails und inaktive E-Mails, um nur einige zu nennen. Die Arten von Adressen, die über gekaufte oder gemietete Listen erfasst und verteilt werden, sind selten primäre E-Mail-Konten, in denen nahezu alle Interaktionen und Kaufaktivitäten stattfinden.

Wenn Sie Glück haben, erhalten Sie sekundäre Konten, in denen Personen nach Angeboten suchen, wenn sie bereit sind, etwas zu kaufen. Dies führt in der Regel zu niedrigen Interaktionsniveaus - falls vorhanden. Wenn Sie kein Glück haben, ist die Liste voll mit inaktiven E-Mails, die jetzt Spam-Fallen sein könnten. Häufig erhält man eine Mischung aus sekundären und inaktiven E-Mails. Im Allgemeinen schadet die Qualität dieser Listentypen einem E-Mail-Programm mehr als sie nützt. Diese Vorgehensweise ist gemäß der [Adobe Campaign Acceptable Use Policy](https://www.adobe.com/de/legal/terms/aup.html) verboten.

**Listen anhängen**
Dies sind Kunden, die sich dafür entschieden haben, mit Ihrer Marke zu interagieren, was großartig ist. Sie haben sich jedoch dafür entschieden, eine andere Methode als E-Mail anzuwenden (In-Store, soziale Medien usw.). Sie waren nicht empfänglich für eine nicht angeforderte E-Mail von Ihnen und könnten auch besorgt darüber sein, wie Sie ihre E-Mail-Adresse erhalten haben, da sie sie nicht bereitgestellt haben. Bei dieser Methode besteht die Gefahr, dass ein Kunde oder potenzieller Kunde, der mit Ihrer Marke interagiert hat, zu einem Kritiker wird, der Ihrer Marke nicht mehr vertraut und stattdessen zu Ihrer Konkurrenz wechselt. Diese Vorgehensweise ist gemäß der [Adobe Campaign Acceptable Use Policy](https://www.adobe.com/de/legal/terms/aup.html) verboten.

**Handelsmesse oder andere Veranstaltungskollektion**
Das Erfassen von Adressen an einem Stand oder über eine andere offizielle, klar gekennzeichnete Methode kann nützlich sein. Das Risiko besteht darin, dass viele Ereignisse wie diese alle Adressen erfassen und über den Ereignispromotor oder -host verteilen. Das bedeutet, dass die Besitzer dieser E-Mail-Adressen nie angefordert haben, E-Mails von Ihrer Marke zu erhalten. Diese Abonnentinnen und Abonnenten beschweren sich häufig und markieren Ihre E-Mails als Spam. Möglicherweise haben sie keine korrekten Kontaktinformationen angegeben.

**Gewinnspiele**

Gewinnspiele liefern schnell eine große Anzahl von E-Mail-Adressen. Aber diese Abonnenten wollen den Preis, nicht Ihre E-Mails. Vielleicht haben sie nicht einmal darauf geachtet, wer mit ihnen in Kontakt treten würde. Diese Personen beschweren sich häufig und markieren Ihre E-Mails als Spam. Es ist unwahrscheinlich, dass sie jemals mit Ihren E-Mails interagieren oder etwas kaufen.

## Produktspezifische Ressourcen

**Adobe Campaign Classic**

* [Abonnement-Formular mit doppeltem Opt-in erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=de#create-a-subscription--form-with-double-opt-in)

**Adobe Campaign Standard**

* [Doppeltes Opt-in-Verfahren](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/landing-pages/setting-up-a-double-opt-in-process.html?lang=de#communication-channels)
