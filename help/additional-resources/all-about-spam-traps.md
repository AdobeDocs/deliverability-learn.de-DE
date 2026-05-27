---
title: Alles über Spam-Fallen
description: Erfahren Sie, wie Sie bei der Verwaltung der Zustellbarkeit Spam-Fallen identifizieren und vermeiden können.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 45cdcda0-70e4-47f4-8713-a834500e7881
TQID: https://experienceleague.adobe.com/NsX4YXwncyoIMoPbzNY2YA0bwTmOccNt19GaBFVT4qk
product_v2: id: b27e5950-9033-45ac-9f86-eb22e567f615id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5f60233-d5ea-4453-a799-0ad258b4d399id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 100%

---

# Alles über Spam-Fallen

Eine [Spam-Falle](/help/metrics/spam-traps.md) ist eine technisch gültige Adresse, die keine Fehlermeldung auslöst, wenn E-Mails an sie gesendet werden. Die Hauptaufgabe von Spam-Fallen ist, Spammer oder Absender zu identifizieren, die über keine Verfahren zur Datenbereinigung verfügen.

## Wer verwaltet die Adressen für Spam-Fallen?

Eine Art von Spam-Fallen-Adressen basiert auf IP- und Domain-Blockierungslisten von Unternehmen wie SpamHaus, Sorbs und SpamCop. Diese Firmen besitzen ein riesiges Netzwerk von Adressen, die auf verschiedenen Internet-Seiten wie Websites, Blogs und Foren platziert werden, sodass Spammer diese Adressen sammeln.

Die andere Art von Spam-Fallen basiert auf alten aktiven ISP-Adressen. Diese ISPs haben ihr eigenes Spam-Fallen-Netzwerk, das auf inaktiven Adressen beruht, die in Fallen umgewandelt werden. Jeder Versand an diese Adresse wirkt sich negativ auf die Reputation der Absender-IP und -Domain aus.

## Funktionsweise

**Eine E-Mail-Adresse ohne Endbenutzer**: Diese Adressen haben keinen Endbenutzer, der sich für Newsletter oder andere Arten von Kommunikation registrieren könnte, und werden auch nie an einen vergeben.

**Eine von einem Benutzer nicht mehr verwendete E-Mail-Adresse**: Nach einer gewissen Zeit der Inaktivität werden Adressen von den ISPs deaktiviert. Bounce-Nachrichten werden an die Absender gesendet, um sie über diesen neuen Status zu informieren. Absender müssen diese Adressen in Quarantäne verschieben oder sie aus zukünftigen Aussendungen entfernen. ISPs verwenden diese in „Spam-Fallen“ umgewandelten Adressen, um Absender mit unzulässigen Praktiken zu überwachen.

## Wie erkennt man eine Spam-Falle?

Spam-Fallen zu identifizieren ist schwierig. Diese Adressen müssen anonym bleiben, da sie zur Identifizierung unzulässiger Absender verwendet werden. Der Großteil der ISPs verfügt über kein vollautomatisches System zur Überwachung von E-Mails von unzulässigen Absendern. Anhand von früheren Definitionen ist es jedoch möglich, eine Gruppe verdächtiger Adressen zu bestimmen und die Effizienz dieser Auswahl zu testen.

## Warum ist Ihre Datenbank mit Spam-Fallen infiziert?

Ihre Adressdatenbank enthält Spam-Fallen. Wie konnte das passieren? Die beiden Hauptgründe sind ein mangelhaftes Datenbereinigungsverfahren oder eine Fehlfunktion bei der Erfassung.

Anhand dieser Fragen können Sie Ihre Verfahren überprüfen:

* Fehlfunktion bei der Erfassung:
   * Woher kommen Ihre E-Mail-Adressen? Wie viele Quellen werden zur Erfassung dieser Adressen verwendet? Können Sie sie identifizieren? Interne/Co-Registrierung?
   * Funktioniert Ihr Opt-in-System ordnungsgemäß?
   * Haben Sie die Domains und den Alias Ihrer Adressen überprüft? Sie können dies mit der Tabelle unten tun.
* Verfahren zur Datenbereinigung:
   * Wie sieht Ihr Verfahren bei inaktiven Adressen der letzten 12 Monate aus?
   * Verhängen Sie eine Quarantäne bei Softbounces, indem Sie sie als „inaktive Benutzer“ kennzeichnen?
   * Wann haben Sie das letzte Mal Ihre Datenbank gepflegt und versucht, sie zu bereinigen? Machen Sie es regelmäßig.

## Zu vermeidende Aliase und Domains

**Aliase**

![](../../help/assets/aliases.png)

**Domains**

![](../../help/assets/domains.png)
