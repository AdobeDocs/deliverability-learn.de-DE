---
title: Echtzeit-Blackhole-Listen
description: Erfahren Sie mehr über Organisationen, die Listen mit IP-Adressen und Domains führen, die von Spammern verwendet werden könnten.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 4155b89f-a636-404c-8951-563c1b4d0289
source-git-commit: b859229410ca0199f9e9d57025a9fe022834a217
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 38%

---

# Echtzeit-Blackhole-Listen

Mehrere Unternehmen unterhalten Datenbanken mit IP-Adressen und Domains, die von Spammern verwendet werden sollen. Der Besuch dieser Websites kann nützlich sein, um zu verstehen, warum bestimmte Nachrichten als Spam abgelehnt wurden. Es ist im Allgemeinen möglich, die Entfernung einer Adresse zu beantragen, die irrtümlich zu diesen Listen hinzugefügt wurde.

Diese Datenbanken werden als RBLs (Real-time Blackhole Lists) bezeichnet und über einen DNS-Mechanismus abgerufen. Es gibt drei Arten von RBLs:

* Nach IP-Adresse: Auflistung von IP-Adressen, die Spam senden oder ihn wahrscheinlich weiterleiten.
* Nach Absender-Domain: Auflistung von Absender-Domains (vollständige Domain der Bounce-Message-Adresse), die Spam senden oder eine falsche Konfiguration aufweisen.
* Nach Webdomain: Listet die Domains (Domänen auf hoher Ebene, wie bei den Registrierungsstellen registriert) auf, die in den URLs der Links und Bilder im Spam-Inhalt gefunden wurden. In Adobe-Lösungen ist die zu berücksichtigende Domain im Allgemeinen die für das Tracking verwendete Adresse.

Im Folgenden finden Sie eine Liste der am häufigsten verwendeten RBLs. Eine umfassendere Liste finden Sie unter [https://www.dnsstuff.com/](https://tools.dnsstuff.com/).

* **Spamhaus**

  Weiterführende Informationen finden Sie unter [https://www.spamhaus.org/](https://www.spamhaus.org/),

  Die Datenbank ist wichtiger. In diese Liste aufgenommen zu werden, ist im Allgemeinen eine ernste Situation. In diesem Fall müssen Sie SOFORT handeln und kommerzielle Dienste, Zustellbarkeitsdienste und die [Adobe Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html) warnen.

* **SpamCop**

  Weiterführende Informationen finden Sie unter [https://www.spamcop.net/](https://www.spamcop.net/),

  Es ist eine der renommiertesten Datenbanken. Wenn eine Ihrer IP-Adressen auf dieser Liste aufgeführt ist, bedeutet dies im Allgemeinen, dass die SpamCop-Benutzer Ihre Nachrichten als Spam deklariert haben oder dass Sie Nachrichten an einen SpamCop-Honeypot gesendet haben.

* **URIBL**

  Weiterführende Informationen finden Sie unter [https://www.uribl.com/](https://www.uribl.com/),

  Diese Liste identifiziert die Domains, die regelmäßig in als Spam deklarierten Nachrichten angezeigt werden. Wenn Ihre Domain auf dieser Liste erscheint, kann sie sich erheblich auf Ihre Zustellbarkeit auswirken. Sie sollten die Zustellbarkeitsdienste und die [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html) sofort informieren.

* **SURBL**

  Siehe [https://surbl.org/](https://surbl.org/)

  SURBL identifiziert die Websites, die regelmäßig in Spam erscheinen. Wenn Ihre Domain auf dieser Liste erscheint, kann sie sich erheblich auf Ihre Zustellbarkeit auswirken. Sie sollten die Zustellbarkeitsdienste und die [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html) sofort informieren.

* **iX Manitu**

  Dies ist eine Liste von IPs, die in Deutschland weit verbreitet ist. Siehe [https://www.heise.de/ix/nixspam/](https://www.heise.de/ix/nixspam/)

<!--
* SORBS

  [https://www.nl.sorbs.net](https://www.nl.sorbs.net) compiles a list of IP addresses that are reputed to be dynamic IP address (i.e. attributed temporarily to ISP subscribers) or "open relay" addresses. Certain domains check whether the IP address of a sender is not listed on this site before accepting email. Checking the IP addresses on this site can prove useful.
-->
