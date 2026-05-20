---
title: Echtzeit-Blackhole-Listen
description: Erfahren Sie mehr über Organisationen, die Listen mit IP-Adressen und Domains führen, die von Spammern verwendet werden könnten.
topics: Deliverability
doc-type: article
activity: understand
team: ACS
exl-id: 4155b89f-a636-404c-8951-563c1b4d0289
TQID: https://experienceleague.adobe.com/dsyoiAT3fYro3L8HkRT6OuXGfBqaVOJNy-IoFXQK37I
product_v2:
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5f60233-d5ea-4453-a799-0ad258b4d399
  - id: f71e690b-4480-4b67-9ef5-88f42f9cdfdb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 75df8537199680e5f1fc4b98cefdb05220fee7bf
workflow-type: tm+mt
source-wordcount: 423
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
