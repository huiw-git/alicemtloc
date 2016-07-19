---
title: Arbeiten mit Einstellungen f&#252;r ATA-Erkennung
ms.custom: 
  - ATA
ms.date: 12/22/2015
ms.prod: identity-ata
ms.reviewer: na
ms.suite: na
ms.technology: 
  - security
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f4f2ae30-4849-4a4f-8f6d-bfe99a32c746
---
# Arbeiten mit Einstellungen f&#252;r ATA-Erkennung
Die **Erkennung** Seite "Konfiguration" ermöglicht das Festlegen eine Liste von IP-Adressen und Subnetzen, die Sonderfälle und etwas anders als andere Entitäten in Ihrem Netzwerk behandelt werden sollen.


## Einrichten von Erkennung

Auf der **Erkennung** Seite können Sie Folgendes definieren:


- **Kurzfristigen Lease Subnetze** – Wenn Ihre Organisation Subnetze verfügt, auf dem die IP-Adressen sind sehr kurzfristige, z. B. VPN-IP-adresssubnetze oder Wi-Fi-Subnetze, es ist wichtig für die Eingabe von diesen IP-Adressen und Subnetze in ATA, sodass diese ATA zum Speichern der Zuordnung zwischen einem Computer und eine IP kann-Adresse, die aus diesen Bereichen für einen kürzeren Zeitraum als, für andere IP-Adressen würde.

- **Honeytoken Konto-SIDs** – Dies ist ein Benutzerkonto, das keine Netzwerkaktivitäten aufweisen sollte. Dieses Konto wird als ATA-Honeytoken Benutzer konfiguriert werden. Wenn jemand versucht, verwenden Sie diesen Benutzer Konto ATA eine verdächtige Aktivität erstellt und ist ein Hinweis auf schädliche Aktivitäten. Zum Konfigurieren des Honeytoken Benutzers benötigen Sie die SID des Benutzerkontos ein, nicht den Benutzernamen ein.

Sie können IP-Adressen aus den folgenden Erkennungen ausschließen. Bei der Eingabe einer IP-Adresse in diesen Listen wird ATA dieser IP-Adresse diese Art von Aktivität erkannte ausgeschlossen werden soll.


- DNS-Erkundung IP-Adressausschlüsse

- Pass-the-Ticket IP-Adressausschlüsse


## Siehe auch

[Arbeiten mit verdächtigen Aktivitäten](/Topic/Working+with+Suspicious+Activities.md)
[ATA-Konfiguration ändern](/Topic/Modifying+ATA+Configuration.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





