---
title: Spam-Fallen
description: Erfahren Sie mehr über die verschiedenen Arten von Spam-Fallen.
topics: Deliverability
jira: KT-7050
thumbnail: kt7050.jpg
doc-type: article
activity: understand
team: ACS
exl-id: ffacc1b1-bf3f-466e-9a1d-63aad4d2ec45
TQID: https://experienceleague.adobe.com/qandgsfuAA4E9uHfZ0jrgpkjs-kt9Izs8k-HvtgDF7A
product_v2: id: b27e5950-9033-45ac-9f86-eb22e567f615id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: b0bb9048-d951-48d8-8232-45cf248a7e27id: e64968b2-4ee5-47f9-8cae-0588f184b9ebid: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: beb7a3c1-66ab-4786-b879-7621375b3c40
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 100%

---

# Spam-Fallen

Spam-Fallen dienen dazu, E-Mails von betrügerischen Absendern oder solchen, die sich nicht an Best Practices für E-Mails halten, zu identifizieren. Die E-Mail-Adresse der Spam-Falle wird im Allgemeinen nicht veröffentlicht und ist kaum zu identifizieren. Die Zustellung von E-Mails an Spam-Fallen kann Ihre Reputation abhängig von der Art der Falle und dem ISP unterschiedlich stark beeinträchtigen. Weitere Informationen zu den verschiedenen Arten von Spam-Fallen finden Sie in den folgenden Abschnitten.

## Recycelt

Recycelte Spam-Fallen sind Adressen, die einmal gültig waren, aber nicht mehr verwendet werden. Eine wichtige Möglichkeit, Listen so sauber wie möglich zu halten, besteht darin, regelmäßig E-Mails an Ihre gesamte Liste zu senden und abgewiesene E-Mails entsprechend zu unterdrücken. Auf diese Weise können ungültige E-Mail-Adressen unter Quarantäne gestellt und der weiteren Verwendung entzogen werden.

In einigen Fällen kann eine Adresse innerhalb von 30 Tagen den Status &quot;Recycelt&quot; erhalten. Regelmäßiges Senden ist ein wichtiger Aspekt guter Listenhygiene, ebenso wie das regelmäßige Unterdrücken inaktiver Benutzer. **Kampagnen zur Rückgewinnung** werden typischerweise im Rahmen von anspruchsvollen E-Mail-Marketing-Programmen durchgeführt. Mit dieser Kampagnenart kann der Absender versuchen, Benutzer zurückzugewinnen, die sonst nicht mehr angeschrieben werden würden.

## Tippfehler

Eine Tippfehler-Spam-Falle ist eine Adresse, die einen Rechtschreib- oder Formatfehler enthält. Dies ist häufig der Fall bei bekannten Rechtschreibfehlern von großen Domains wie Gmail (z. B.: gmial ist ein häufiger Tippfehler). ISPs und andere Betreiber von Blockierungslisten registrieren bekannte fehlerhafte Domains, die als Spam-Falle verwendet werden, um Spammer zu identifizieren und die Integrität des Absenders zu bestimmen. Der beste Weg, um Tippfehler-Spam-Fallen zu verhindern, ist die Verwendung eines **doppelten Anmeldeverfahrens** für die Erfassung in einer Liste.

## Pristine

Eine &quot;pristine&quot; Spam-Falle ist eine Adresse, die keinen Endbenutzer hat und auch nie einen hatte. Es handelt sich dabei um eine Adresse, die ausschließlich zur Identifizierung von Spam-E-Mails erstellt wurde. Dies ist die wirkungsvollste Art einer Spam-Falle, da es praktisch unmöglich ist, sie zu identifizieren, und es einen erheblichen Aufwand erfordern würde, sie aus Ihrer Liste zu entfernen. Die meisten Blockierungslisten nutzen &quot;pristine&quot; Spam-Fallen, um unseriöse Absender zu identifizieren. Die einzige Möglichkeit zu verhindern, dass &quot;pristine&quot; Spam-Fallen Ihre Marketing-E-Mail-Liste infizieren, besteht darin, ein **doppeltes Anmeldeverfahren** für die Aufnahme in Ihre Liste zu verwenden.

## Weitere Ressourcen

* Weitere Informationen zum Identifizieren und Vermeiden von Spam-Fallen finden Sie in [diesem Abschnitt](/help/additional-resources/all-about-spam-traps.md).
* In [diesem Abschnitt](/help/additional-resources/re-engagement.md) erfahren Sie, wie Sie die Zustellbarkeit durch Rückgewinnungsstrategien verbessern können.

## Produktspezifische Ressourcen

**Adobe Campaign Classic**

* [SpamAssassin](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/deliverability-management/spamassassin.html?lang=de#sending-messages)
* [Abonnement-Formular mit zweifacher Bestätigung erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=de#create-a-subscription--form-with-double-opt-in)

**Adobe Campaign Standard**

* [Vorschau der E-Mail- und Anti-Spam-Analyse](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/email-designer/preview-your-email.html?lang=de#designing-content)
* [Double-Opt-in-Verfahren](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/landing-pages/setting-up-a-double-opt-in-process.html?lang=de#communication-channels)
