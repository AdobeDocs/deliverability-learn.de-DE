---
title: SSL-Zertifikatanforderungsprozess
description: Erfahren Sie, wie Sie SSL-Zertifikate auf den Subdomains installieren, die Sie an Adobe delegiert haben.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 8a78abd3-afba-49a7-a2ae-8b2c75326749
source-git-commit: 57016f89df54d5c74755a6a108a92db45153ec18
workflow-type: tm+mt
source-wordcount: '2124'
ht-degree: 1%

---

# SSL-Zertifikatanforderungsvorgang

Nachdem Sie eine Domain zum Senden von E-Mails an Adobe delegiert haben (siehe [Domain-Namen einrichten](/help/additional-resources/ac-domain-name-setup.md)), erstellt und verwendet Adobe bestimmte Subdomains für bestimmte Funktionen.

Wenn Sie beispielsweise &quot;*.example.com“* Adobe für das Senden von E-Mails delegiert haben, erstellt Adobe Subdomains wie die folgenden:
* *t.email.example.com* - für Tracking-Links
* *m.email.example.com* - für Mirrorseiten
* *res.email.example.com* - für gehostete Ressourcen (wie Bilder)

Es wird empfohlen **diese Domains über SSL (HTTPS) zu**. Ungesicherte Links (HTTP) sind in der Tat anfällig für das Abfangen und werden Warnungen auf modernen Browsern anzeigen.

Um SSL-Zertifikate auf diesen Subdomains zu installieren, müssen Sie eine CSR-Datei anfordern und anschließend SSL-Zertifikate zum Installieren oder Verlängern von Adobe erwerben.

>[!CAUTION]
>
>Bevor Sie ein SSL-Zertifikat installieren, stellen Sie sicher, dass Sie über die Voraussetzungen auf [dieser Seite) ](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/renewing-subdomain-certificate.html?lang=de#installing-ssl-certificate).
>
>Adobe unterstützt nur bis zu 2048-Bit-Zertifikate. 4096-Bit-Zertifikate werden noch nicht unterstützt.

## Glossar

| Begriff | Beschreibung |
|--- |--- |
| CA (Zertifizierungsstelle) | Ein SSL-Zertifikatanbieter, der digitale Zertifikate an Organisationen oder Einzelpersonen ausstellt, nachdem diese ihre Identität überprüft haben, z. B. DigiCert, Symantec usw.<ul><li>Eine vertrauenswürdige Zertifizierungsstelle wird in der Regel als Drittanbieter-Zertifizierungsstelle betrachtet, die ein Stammzertifikat ausstellt.</li><li>Wenn das Zertifikat von derselben Organisation/demselben Unternehmen signiert wird, die bzw. das das Zertifikat verwendet, wird es auch dann als nicht vertrauenswürdige Zertifizierungsstelle klassifiziert, wenn es sich um SSL-Zertifikate handelt, z. B. selbstsignierte Zertifikate.</li></ul> |
| Kettenzertifikat | Ein Zertifikat, das ein Stammzertifikat und ein oder mehrere Zwischenzertifikate enthält, wird als Kettenzertifikat (oder verkettetes Zertifikat) bezeichnet. |
| CSR (Certificate Signing Request) | Ein Block mit kodiertem Text, der einer Zertifizierungsstelle bei der Beantragung eines SSL-Zertifikats übergeben wird. Sie wird normalerweise auf dem Server generiert, auf dem das Zertifikat installiert ist. |
| DER (Distinguished Encoding Rules) | Ein Typ der Zertifikaterweiterung. Die Erweiterung .der wird für binäre DER-codierte Zertifikate verwendet. Diese Dateien können auch die Erweiterung .cer oder .crt unterstützen. |
| EV-Zertifikat (Extended Validation) | Ein EV-Zertifikat ist ein neuer Zertifikatstyp, der Phishing-Angriffen vorbeugen soll. Dies erfordert eine erweiterte Validierung Ihres Unternehmens und der Person, die das Zertifikat bestellt. |
| Hochsicherheitszeugnis | Die Zertifizierungsstelle stellt Hochsicherheitszertifikate aus, nachdem sie sich vergewissert hat, dass der Domainname und die gültige Unternehmensregistrierung in ihrem Besitz sind. |
| Mittlere Zertifizierungsstelle | Eine Zertifizierungsstelle von Zwischenzertifikaten, die in einem Kettenzertifikat enthalten sind. |
| Zwischenzertifikat | Eine Zertifizierungsstelle stellt Zertifikate in Form einer Baumstruktur aus. Das Stammzertifikat ist das oberste Zertifikat der Baumstruktur. Jedes Zertifikat zwischen Ihrem Zertifikat und dem Stammzertifikat wird als Kette oder Zwischenzertifikat bezeichnet. |
| Low Assurance-Zertifikat | Ein Low Assurance-Zertifikat, auch als Domain-validiertes Zertifikat bezeichnet, enthält nur den Domain-Namen im Zertifikat (und nicht den Geschäfts-/Organisationsnamen). |
| PEM (Privacy Enhanced Mail) | Ein Zertifikat mit der Erweiterung .pem, das ASCII (Base64)-Daten enthält. Solche Zertifikate beginnen mit einer &quot; - - - - - - BEGIN CERTIFICATE - - - - -&quot; Zeile. |
| Stammzertifikat | Eine Zertifizierungsstelle stellt Zertifikate in Form einer Baumstruktur aus. Das Stammzertifikat ist das oberste Zertifikat der Baumstruktur. |
| SAN (alternativer Antragstellername) | Die alternativen Antragstellernamen sind zusätzliche Hostnamen (Websites, IP-Adressen, allgemeine Namen usw.), die als Teil eines einzelnen SSL-Zertifikats signiert werden sollten. |
| Selbstsigniertes Zertifikat | Ein Zertifikat, das nicht von einer vertrauenswürdigen Zertifizierungsstelle, sondern von der Person, die es erstellt, signiert wird. Selbstsignierte Zertifikate können denselben Verschlüsselungsgrad wie ein von einer Zertifizierungsstelle signiertes Zertifikat ermöglichen, haben jedoch zwei wesentliche Nachteile:<ul><li>Die Verbindung eines Besuchers könnte gekapert werden, sodass ein Angreifer alle gesendeten Daten sehen kann (und so den Zweck der Verschlüsselung der Verbindung vereitelt wird)</li><li> Das Zertifikat kann nicht wie ein vertrauenswürdiges Zertifikat widerrufen werden.</li></ul> |
| SSL (Secure Sockets Layer) | Die standardmäßige Sicherheitstechnologie zum Herstellen einer verschlüsselten Verbindung zwischen einem Webserver und einem Browser. |
| Platzhalterzertifikat | Ein Platzhalterzertifikat kann eine unbegrenzte Anzahl von Subdomains der ersten Ebene auf einem einzelnen Domain-Namen sichern, z. B. *.adobe.com. |

## Wichtigste Schritte

1. Fordern Sie eine CSR-Datei (Certificate Signing Request) an und geben Sie die erforderlichen Informationen (Land, Bundesland, Stadt, Organisationsname, Name der Organisationseinheit usw.) zum Adobe an.
1. Überprüfen Sie die vom Adobe generierte CSR-Datei und stellen Sie sicher, dass alle von Ihnen angegebenen Informationen korrekt sind.
1. Verwenden Sie die CSR-Details, um ein Zertifikat zu generieren, das von einer vertrauenswürdigen Zertifizierungsstelle signiert <!--taking care of asking for using the subjectAltName SSL extension (SAN) if it is for several domain names, and get/purchase the resulting certificate (ideally) in PEM format for Apache server-->.
1. Validieren Sie das SSL-Zertifikat und überprüfen Sie, ob es mit der CSR übereinstimmt.
1. Geben Sie das SSL-Zertifikat an Adobe, der es installieren wird.
1. Testen Sie, ob das SSL-Zertifikat für jede gesicherte Subdomain erfolgreich installiert wurde.
1. Überwachen des Gültigkeitszeitraums des SSL-Zertifikats.
1. Aktualisieren Sie alle spezifischen Konfigurationen in Adobe Campaign.

## Detaillierter Prozess

### Voraussetzungen

Sie müssen die Domain-Namen und die Funktionen (Tracking, Mirror-Seiten, WebApps usw.) identifizieren, um zu sichern.
>[!NOTE]
>
>Adobe kann bei der Definition der Domain-Namen und Funktionen helfen, die einbezogen werden sollen. Weitere Informationen erhalten Sie von Ihrem Adobe Account Team.

### Schritt 1: CSR-Datei abrufen

Gehen Sie wie folgt vor, um eine CSR-Datei (Certificate Signing Request) zu erhalten.

* Wenn Sie Zugriff auf das [Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de) haben, befolgen Sie die Anweisungen auf [dieser Seite](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/renewing-subdomain-certificate.html?lang=de#subdomains-and-certificates), um eine CSR-Datei vom Control Panel zu generieren und herunterzuladen.

* Erstellen Sie andernfalls ein Support-Ticket über https://adminconsole.adobe.com/ , um eine CSR-Datei von der Adobe-Kundenunterstützung für die erforderlichen Subdomains zu erhalten.

Im Folgenden finden Sie Best Practices:

* Eine Anfrage pro delegierter Subdomain auslösen.
* Es ist möglich, mehrere Subdomains in einer CSR-Anfrage zu kombinieren, jedoch nur innerhalb derselben Umgebung. In Campaign Classic sind der Marketing-Server, der [Mid-Sourcing-Server](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/install-campaign-on-prem/mid-sourcing-server.html?lang=de) und die [Ausführungsinstanz](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/configuring-instances.html?lang=de#execution-instance) beispielsweise drei separate Umgebungen.
* Sie müssen vor jeder Verlängerung eines SSL-Zertifikats eine neue CSR erhalten. Verwenden Sie keine alte CSR-Datei aus einem Jahr oder länger.

Sie müssen die folgenden Informationen angeben.

>[!CAUTION]
>
>Alle in den nachstehenden Tabellen angegebenen Felder müssen ausgefüllt werden. Andernfalls kann die CSR-Anfrage nicht verarbeitet werden.

**Informationen, die mithilfe des Adobe-Teams bereitzustellen sind:**

| Zu liefernde Informationen | Beispielwert | Hinweis |
|--- |--- |--- |
| Client-Name | Meine Firma Inc. | Name Ihres Unternehmens. Dieses Feld wird von Adobe für die Verfolgung Ihrer Anfrage verwendet (es ist nicht Teil des CSR/SSL-Zertifikats). |
| Adobe Campaign-Umgebungs-URL | https://client-mid-prod1.campaign.adobe.com | Adobe Campaign-Instanz-URL. |
| Allgemeiner Name [CN] | t.subdomain.customer.com | Dabei kann es sich um eine beliebige Domain handeln, normalerweise jedoch um die Tracking-Domain. |
| Alternativer Antragstellername [SAN] | t.subdomain.customer.com | Stellen Sie sicher, dass Sie die Tracking-Subdomain als SAN einbeziehen. |
| Alternativer Antragstellername [SAN] | m.subdomain.customer.com |
| Alternativer Antragstellername [SAN] | res.subdomain.customer.com |

**Informationen, die von Ihrem internen IT-/SSL-Team bereitzustellen sind:**

| Zu liefernde Informationen | Beispielwert | Hinweis |
|--- |--- |--- |
| Land [c] | USA | Dies muss ein Code mit zwei Buchstaben sein. Vollständige Liste der Länder [hier](https://www.ssl.com/csrs/country_codes/).</br>*Hinweis: Für das Vereinigte Königreich verwenden Sie GB (nicht UK).* |
| Bundesland (oder Provinzname) [ST] | Illinois | Falls zutreffend. Der Wert muss ein vollständiger Name sein, nicht abgekürzt. |
| Stadt-/Ortsname [L] | Chicago |
| Organisationsname [o] | KUPPEL |
| Name der Organisationseinheit [OU] | IT |

>[!NOTE]
>
>Ersetzen Sie „subdomain.customer.com“ durch Ihre delegierte Subdomain und die anderen Beispielwerte durch die entsprechenden Werte.

### Schritt 2: Validieren der CSR-Datei

Nachdem Sie Ihre Anfrage mit den entsprechenden Informationen gesendet haben, generiert Adobe eine CSR-Datei (Certificate Signing Request), die Sie über das Zertifikat erhalten.

Der Text in der resultierenden CSR-Datei muss mit &quot;**-----BEGIN CERTIFICATE REQUEST-----&quot;**.

Nachdem Sie die CSR-Datei vom Adobe erhalten haben, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den Text der CSR-Datei und fügen Sie ihn in einen Online-Decoder ein, z. B. https://www.sslshopper.com/csr-decoder.html, <!--https://www.certlogik.com/decoder/,--> oder https://www.entrust.net/ssl-technical/csr-viewer.cfm.
Alternativ können Sie den Befehl *OpenSSL* lokal auf einem Linux-Computer verwenden.
1. Überprüfen Sie, ob alle Prüfungen erfolgreich waren.
1. Überprüfen Sie, ob die richtigen Parameter und Domain-Namen enthalten sind.
1. Überprüfen Sie, ob alle anderen Daten mit den Details übereinstimmen, die Sie beim Senden Ihrer Anfrage angegeben haben.

### Schritt 3: Generieren des SSL-Zertifikats

Sobald die CSR-Datei bereitgestellt wurde, müssen Sie mithilfe der CSR-Datei ein SSL-Zertifikat für die entsprechenden Domains erwerben und generieren.

* Das SSL-Zertifikat:
   * muss im Apache PEM-Format vorliegen;
   * sollte nicht länger als 2048 Bit sein;
   * muss von einer gültigen Zertifizierungsstelle (Certification Authority) unterzeichnet sein;
   * muss alle SANs (Subject Alternative Names) enthalten, die in der CSR-Datei erwähnt werden.
* Wenn ein oder mehrere Zwischenzertifikate vorhanden sind, müssen Sie das Stammzertifikat und alle Zwischenzertifikate auf Adobe angeben.
* Sie können einen beliebigen Gültigkeitszeitraum für das Zertifikat festlegen, aber Adobe empfiehlt, ihn lange genug auszuwählen (z. B. zwei Jahre).

>[!NOTE]
>
>Wenn Sie Ihre eigenen internen Tools oder ein von einer Zertifizierungsstelle bereitgestelltes Portal verwenden, um das Zertifikat anzufordern, verwenden Sie dieselben Details wie in der CSR-Anfrage , um Verzögerungen oder Diskrepanzen beim Generierungsprozess des Zertifikats zu vermeiden.

### Schritt 4: Validieren des SSL-Zertifikats

Nachdem das SSL-Zertifikat generiert wurde, müssen Sie es vor dem Senden an Adobe validieren. Gehen Sie dazu wie folgt vor:

1. Stellen Sie sicher, dass das Zertifikat die Erweiterung .pem aufweist. Ist dies nicht der Fall, konvertieren Sie sie in das PEM-Format. Sie können die Konvertierung mit *OpenSSL* vornehmen.
1. Bestätigen Sie, dass das Zertifikat mit **-----BEGIN CERTIFICATE-----&quot;** beginnt.
1. Kopieren Sie den Zertifikatstext in einen Online-Decoder, z. B. https://www.sslshopper.com/certificate-decoder.html oder https://www.entrust.net/ssl-technical/csr-viewer.cfm.
Alternativ können Sie den Befehl *OpenSSL* lokal auf einem Linux-Computer verwenden. Weiterführende Informationen hierzu finden Sie auf [dieser externen Seite](https://www.shellhacks.com/decode-ssl-certificate/).
1. Stellen Sie sicher, dass das Zertifikat ordnungsgemäß aufgelöst wird, einschließlich des allgemeinen Namens, des SAN, des Ausstellers und des Gültigkeitszeitraums.
1. Wenn die Überprüfung des SSL-Zertifikats erfolgreich war, überprüfen Sie mithilfe [dieser Website](https://www.sslshopper.com/certificate-key-matcher.html), ob das Zertifikat mit der CSR übereinstimmt: Wählen Sie **Überprüfen, ob eine CSR und ein Zertifikat übereinstimmen** und geben Sie Ihr Zertifikat und Ihre CSR in die entsprechenden Felder ein. Sie sollten übereinstimmen.

### Schritt 5: SSL-Zertifikatinstallation anfordern

* Wenn Sie Zugriff auf das [Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de) haben, befolgen Sie die Anweisungen auf [dieser Seite](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/renewing-subdomain-certificate.html?lang=de#installing-ssl-certificate), um das Zertifikat in das Control Panel hochzuladen.

* Erstellen Sie andernfalls über https://adminconsole.adobe.com/ ein weiteres Support-Ticket, um Adobe zur Installation des Zertifikats auf den Adobe-Servern anzufordern.

Sie müssen Folgendes angeben:

* Die Zertifikatdatei, das Stammzertifikat und alle Zwischenzertifikate (die an das Ticket angehängt sind), vorzugsweise im Apache PEM-Format.
* Die Nummer des vorherigen Support-Tickets, das für die CSR ausgelöst wurde.
* dieselben Daten, die für das CSR-Ticket bereitgestellt wurden (einschließlich Gebrauchsname, Instanz-URL, Bundesland, Stadt/Ort, Organisationsname, Organisationseinheitenname usw.).

### Schritt 6: Installation des SSL-Zertifikats testen

Nachdem das SSL-Zertifikat installiert und von der Adobe-Kundenunterstützung bestätigt wurde, stellen Sie sicher, dass es für alle URLs erfolgreich installiert wurde.

Führen Sie die folgenden Tests durch, bevor Sie das SSL-Installationsticket schließen. Stellen Sie außerdem sicher, dass Sie jede spezifische Konfiguration aktualisieren, wie in [diesem Abschnitt) ](#update-configuration).

Navigieren Sie zu den folgenden URLs in Ihrem Browser (ersetzen Sie „subdomain.customer.com“ durch Ihre Subdomain):

* https://subdomain.customer.com/r/test (nur für [Web-Anwendungen](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/about-web-applications.html?lang=de) Subdomains - gilt nicht für E-Mail-Subdomains)
* https://t.subdomain.customer.com/r/test
* https://m.subdomain.customer.com/r/test
* https://res.subdomain.customer.com/r/test

Ein erfolgreiches Ergebnis gibt Umgebungsinformationen an, und die Adressleiste in der URL zeigt an, dass die Verbindung sicher ist. Sie können beispielsweise die folgende Meldung in Google Chrome sehen:

![](../../help/assets/ssl-google-successful-result.png)

Wenn das SSL-Zertifikat nicht ordnungsgemäß installiert ist, wird die folgende Warnung angezeigt:

![](../../help/assets/ssl-google-unsuccessful-result.png)

### Schritt 7: Gültigkeitszeitraum des Zertifikats überprüfen

Sie können die Gültigkeitsdauer des Zertifikats in Ihrem Browser überprüfen. Klicken Sie beispielsweise in Google Chrome auf **Sicher** > **Zertifikat**.

Es liegt in Ihrer Verantwortung, den Gültigkeitszeitraum zu überprüfen. Adobe empfiehlt die Implementierung eines Prozesses zur Überwachung des Zertifikatablaufs. Weitere Informationen dazu, was passiert, wenn Ihr SSL-Zertifikat abläuft, finden Sie in [diesem Artikel](https://www.thesslstore.com/blog/what-happens-when-your-ssl-certificate-expires/).

* Erstellen Sie ein Support-Ticket, um mindestens zwei Wochen vor Ablauf des Zertifikats ein aktualisiertes Zertifikat anzufordern. Sie müssen keine zusätzliche CSR anfordern, es sei denn, die CSR-Details wurden geändert.

* Wenn Sie Zugriff auf das [Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de) haben und Ihre Umgebung von Adobe in einer AWS-Umgebung gehostet wird, können Sie das Zertifikat über das Control Panel verlängern, bevor es abläuft. Weiterführende Informationen finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/monitoring-ssl-certificates.html?lang=de#monitoring-certificates).

### Schritt 8: Aktualisieren einer bestimmten Konfiguration {#update-configuration}

Sobald Sie sicher sind, dass die angeforderten SSL-Zertifikate ordnungsgemäß installiert sind, können Sie alle Verweise in Adobe Campaign von HTTP auf HTTPS aktualisieren.

>[!NOTE]
>
>Beim Campaign Classic befinden sich die zu aktualisierenden URLs hauptsächlich im [Bereitstellungsassistenten](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/initial-configuration/deploying-an-instance.html?lang=de#deployment-wizard) und in [Externe Konten](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html?lang=de) (Tracking, Mirrorseite und öffentliche Ressourcendomänen). Weitere Informationen zum Campaign Standard finden Sie unter [Branding-Konfiguration](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/application-settings/branding.html?lang=de#about-brand-identity).

Sobald die Konfigurationen aktualisiert wurden, werden neue E-Mails mit HTTPS-URLs und nicht mit HTTP gesendet. Um zu überprüfen, ob die URLs jetzt sicher sind, können Sie die folgenden Tests schnell durchführen:

* Laden Sie ein Bild aus Adobe Campaign hoch. Nach dem Hochladen des Bildes sollte die zurückgegebene URL HTTPS sein.
* Erstellen Sie einen E-Mail-Testversand mit einem Mirrorseiten-Link, einigen Bildern, Text und einem Abmelde-Link. Senden Sie die E-Mail an eine externe E-Mail-ID (z. B. Ihre Gmail-Adresse). Öffnen Sie nach dem Erhalt die E-Mail und stellen Sie sicher, dass alle Links in der E-Mail korrekt in ihrem HTTPS-Formular (nicht HTTP) ohne SSL-Zertifikatwarnungen oder -fehler geöffnet werden.

## Produktspezifische Ressourcen

**Campaign Classic**

* [Control Panel: Hinzufügen von SSL-Zertifikaten (Tutorial)](https://experienceleague.adobe.com/docs/campaign-classic-learn/control-panel/subdomains-and-certificates/adding-ssl-certificates.html?lang=de) - Erfahren Sie, wie Sie SSL-Zertifikate hinzufügen, um Ihre Subdomains zu schützen.

**Campaign Standard**

* [Control Panel: Hinzufügen von SSL-Zertifikaten (Tutorial)](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/subdomains-and-certificates/adding-ssl-certificates.html?lang=de) - Erfahren Sie, wie Sie SSL-Zertifikate hinzufügen, um Ihre Subdomains zu schützen.
