---
title: Authentifizierung
description: Erfahren Sie mehr über Authentifizierungsmethoden für SPF, DKIM und DMARC.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 03609139-b39b-4051-bcde-9ac7c5358b87
source-git-commit: d6094cd2ef0a8a7741e7d8aa4db15499fad08f90
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 42%

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

Bitte beachten Sie, dass es bis zu 48 Stunden in Anspruch nehmen kann, bis in der Umgebung von DNS-Servern gemachte Einträge berücksichtigt werden. Die Dauer hängt davon ab, mit welcher Häufigkeit die DNS-Caches der Empfangs-Server aktualisiert werden.

## DKIM {#dkim}

Die DKIM-Authentifizierung (DomainKeys Identified Mail) ist eine Nachfolgeauthentifizierung von SPF. Sie verwendet eine Verschlüsselung mit öffentlichem Schlüssel, mit der der empfangende E-Mail-Server überprüfen kann, ob eine Nachricht tatsächlich von der Person oder Entität gesendet wurde, von der sie behauptet, dass sie gesendet wurde, und ob der Nachrichteninhalt zwischen dem ursprünglichen Versand (und DKIM „signiert„) und dem Empfang geändert wurde. Bei diesem Standard wird in der Regel die Domain im &quot;Von&quot;- oder &quot;Absender&quot;-Header genutzt.

DKIM geht auf eine Kombination der Authentifizierungsprinzipien DomainKeys von Yahoo! und Identified Internet Mail von Cisco zurück und dient der Prüfung der Authentizität von Absender-Domains sowie der Sicherstellung der Integrität von Nachrichten.

DKIM hat sozusagen die **DomainKeys**-Authentifizierung ersetzt.

Für die Verwendung von DKIM müssen folgende Voraussetzungen gegeben sein:

* **Sicherheit**: Verschlüsselung ist ein Schlüsselelement der DKIM. Um das Sicherheitsniveau der DKIM zu gewährleisten, ist 1024b die empfohlene Verschlüsselungsgröße. Niedrigere DKIM-Schlüssel werden von den meisten Zugriffsanbietern nicht als gültig erachtet.
* **Reputation**: Die Reputation basiert auf der IP-Adresse und/oder der Domain, aber der weniger transparente DKIM-Selektor ist auch ein Schlüsselelement, das berücksichtigt werden muss. Die Auswahl des Selektors ist wichtig: Vermeiden Sie es, den „Standard“ beizubehalten, der von jedem verwendet werden könnte und daher eine schwache Reputation hat. Sie müssen einen anderen Selektor für **Aufbewahrungs- vs. Akquise-Kommunikation** und für die Authentifizierung implementieren.

Weitere Informationen zu den Voraussetzungen für die Verwendung von DKIM beim Campaign Classic finden [ in diesem Abschnitt](/help/additional-resources/acc-technical-recommendations.md#dkim-acc).

## DMARC {#dmarc}

DMARC (Domain-based Message Authentication, Reporting and Conformance) ist die neueste Art der E-Mail-Authentifizierung. Bei der Entscheidung, ob eine E-Mail weitergeleitet wird oder fehlschlägt, kommt sowohl SPF- als auch DKIM-Authentifizierung zum Einsatz. DMARC ist in zweierlei Hinsicht einzigartig und leistungsstark:

* Konformität - Auf diese Weise kann der Absender die ISPs anweisen, was mit jeder Nachricht zu tun ist, die sich nicht authentifizieren kann (zum Beispiel: akzeptieren Sie sie nicht).
* Reporting - liefert dem Absender einen detaillierten Bericht mit allen Nachrichten, bei denen die DMARC-Authentifizierung fehlgeschlagen ist, sowie der jeweils verwendeten Absender-Domain und IP-Adresse. Auf diese Weise kann ein Unternehmen legitime E-Mails identifizieren, bei denen die Authentifizierung fehlschlägt und die eine Art von „Fehlerbehebung“ erfordern (z. B. Hinzufügen von IP-Adressen zu seinem SPF-Eintrag). Außerdem können die Quellen und die Prävalenz von Phishing-Versuchen in ihren E-Mail-Domains identifiziert werden.

>[!NOTE]
>
>DMARC kann die von [250ok](https://250ok.com/) erstellten Berichte nutzen.
