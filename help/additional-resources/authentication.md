---
title: Authentifizierung
description: Erfahren Sie mehr über Authentifizierungsmethoden für SPF, DKIM und DMARC.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 03609139-b39b-4051-bcde-9ac7c5358b87
TQID: https://experienceleague.adobe.com/zuhBmNWmF8CoCSNofsg3FKCcQFLOFfZmRutB2P1L4-U
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
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 769
ht-degree: 33%

---

# Authentifizierung

## SPF {#spf}

: SPF (Sender Policy Framework) ist ein Standard für die E-Mail-Authentifizierung, mit dem der Inhaber einer Domain angeben kann, welche E-Mail-Server E-Mails im Namen dieser Domain senden dürfen. Bei diesem Standard wird die Domain in der Kopfzeile &quot;Return-Path&quot; der E-Mail (auch als &quot;Envelope From&quot;-Adresse bezeichnet) genutzt.

>[!NOTE]
>
>Sie können [dieses externe Tool) verwenden](https://www.kitterman.com/spf/validate.html) um einen SPF-Eintrag zu überprüfen.

SPF ist eine Technik, mit der Sie in gewissem Umfang sicherstellen können, dass der in einer E-Mail verwendete Domain-Name nicht gefälscht wird. Wenn eine Nachricht von einer Domain empfangen wird, wird der DNS-Server der Domain abgefragt. Die Antwort ist ein kurzer Datensatz (der SPF-Datensatz), der angibt, welche Server für das Senden von E-Mails von dieser Domain autorisiert sind. Wenn wir davon ausgehen, dass nur der Eigentümer der Domain über die Mittel verfügt, um diesen Datensatz zu ändern, können wir davon ausgehen, dass mit dieser Technik die Absenderadresse nicht gefälscht werden kann, zumindest nicht der Teil rechts von „@“.

In der endgültigen [RFC 4408-Spezifikation](https://www.rfc-editor.org/info/rfc4408) werden zwei Elemente der Nachricht verwendet, um die als Absender betrachtete Domain zu bestimmen: die vom SMTP-Befehl „HELO“ (oder „EHLO„) angegebene Domain und die von der Adresse des „Return-Path“-Headers (oder „MAIL FROM„) angegebene Domain, die auch die Bounce-Adresse ist. Verschiedene Überlegungen ermöglichen es, nur einen dieser Werte zu berücksichtigen. Wir empfehlen, dass beide Quellen dieselbe Domain angeben.

Durch die Überprüfung des SPF ist eine Auswertung der Gültigkeit der Absender-Domain gewährleistet.

* **None**: Es konnte keine Auswertung durchgeführt werden.
* **Neutral**: Die abgefragte Domain ermöglicht keine Auswertung.
* **Pass**: Die Domain wird als authentisch betrachtet.
* **Fehler**: Die Domain ist gefälscht und die Nachricht sollte abgelehnt werden.
* **SoftFail**: Die Domain ist wahrscheinlich gefälscht, aber die Nachricht sollte nicht nur aufgrund dieses Ergebnisses abgelehnt werden.
* **TempError**: Ein temporärer Fehler hat die Auswertung angehalten. Die Nachricht kann abgelehnt werden.
* **PermError**: Die SPF-Einträge der Domain sind ungültig.

Beachten Sie, dass es bis zu 48 Stunden dauern kann, bis Einträge auf der Ebene der DNS-Server berücksichtigt werden. Diese Verzögerung hängt davon ab, wie oft die DNS-Caches der empfangenden Server aktualisiert werden.

## DKIM {#dkim}

Die DKIM-Authentifizierung (DomainKeys Identified Mail) ist eine Nachfolgeauthentifizierung von SPF. Sie verwendet eine Verschlüsselung mit öffentlichem Schlüssel, mit der der empfangende E-Mail-Server überprüfen kann, ob eine Nachricht tatsächlich von der Person oder Entität gesendet wurde, von der sie behauptet, dass sie gesendet wurde, und ob der Nachrichteninhalt zwischen dem ursprünglichen Versand (und DKIM „signiert„) und dem Empfang geändert wurde. Bei diesem Standard wird in der Regel die Domain im &quot;Von&quot;- oder &quot;Absender&quot;-Header genutzt.

DKIM kommt aus einer Kombination der DomainKeys, Yahoo! Cisco und IDENTIFIZIERTE INTERNET-MAIL-AUTHENTIFIZIERUNGSPRINZIPIEN UND WIRD VERWENDET, UM DIE AUTHENTIZITÄT DER ABSENDER-DOMAIN ZU ÜBERPRÜFEN UND DIE INTEGRITÄT DER NACHRICHT ZU GARANTIEREN.

DKIM hat sozusagen die **DomainKeys**-Authentifizierung ersetzt.

Für die Verwendung von DKIM müssen folgende Voraussetzungen gegeben sein:

* **Sicherheit**: Verschlüsselung ist ein Schlüsselelement der DKIM. Um das Sicherheitsniveau der DKIM zu gewährleisten, ist 1024b die empfohlene Verschlüsselungsgröße. Niedrigere DKIM-Schlüssel werden von den meisten Zugriffsanbietern nicht als gültig erachtet.
* **Reputation**: Die Reputation basiert auf der IP-Adresse und/oder der Domain, aber der weniger transparente DKIM-Selektor ist auch ein Schlüsselelement, das berücksichtigt werden muss. Die Auswahl des Selektors ist wichtig: Vermeiden Sie es, den „Standard“ beizubehalten, der von jedem verwendet werden könnte und daher eine schwache Reputation hat. Sie müssen einen anderen Selektor für **Aufbewahrungs- vs. Akquise-Kommunikation** und für die Authentifizierung implementieren.

Weitere Informationen zu den Voraussetzungen für die Verwendung von DKIM finden Sie in [diesem Abschnitt](/help/additional-resources/acc-technical-recommendations.md#dkim-acc).

## DMARC {#dmarc}

DMARC (Domain-based Message Authentication, Reporting and Conformance) ist die neueste Art der E-Mail-Authentifizierung. Bei der Entscheidung, ob eine E-Mail weitergeleitet wird oder fehlschlägt, kommt sowohl SPF- als auch DKIM-Authentifizierung zum Einsatz. DMARC ist in zweierlei Hinsicht einzigartig und leistungsstark:

* Konformität - Auf diese Weise kann der Absender die ISPs anweisen, was mit jeder Nachricht zu tun ist, die sich nicht authentifizieren kann (zum Beispiel: akzeptieren Sie sie nicht).
* Reporting - liefert dem Absender einen detaillierten Bericht mit allen Nachrichten, bei denen die DMARC-Authentifizierung fehlgeschlagen ist, sowie der jeweils verwendeten Absender-Domain und IP-Adresse. Auf diese Weise kann ein Unternehmen legitime E-Mails identifizieren, bei denen die Authentifizierung fehlschlägt und die eine Art von „Fehlerbehebung“ erfordern (z. B. Hinzufügen von IP-Adressen zu seinem SPF-Eintrag). Außerdem können die Quellen und die Prävalenz von Phishing-Versuchen in ihren E-Mail-Domains identifiziert werden.

>[!NOTE]
>
>DMARC kann die von [250ok](https://250ok.com/) erstellten Berichte nutzen.
