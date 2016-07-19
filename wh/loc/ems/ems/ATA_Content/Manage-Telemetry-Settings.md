---
title: Verwalten der f&#252;r Telemetrieeinstellungen
ms.custom: na
ms.date: 12/22/2015
ms.prod: identity-ata
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8c1c7a1b-a3de-4105-9fd0-08a061952172
---
# Verwalten der f&#252;r Telemetrieeinstellungen
Erweiterte Threat-Analyse (ATA) anonymen Telemetriedaten über ATA sammelt und überträgt die Daten über eine HTTPS-Verbindung mit Servern von Microsoft. Diese Daten werden von Microsoft zur Verbesserung von zukünftigen Versionen ATA-verwendet.


## Gesammelte Daten

Gesammelte Daten umfassen Folgendes:


- Leistungsindikatoren aus dem ATA-Center und das ATA-Gateway

- Produkt-ID nach ATA lizenziert wurde

- Bereitstellungsdatum des ATA-Center

- Anzahl der bereitgestellten ATA-Gateways

- Die folgenden Active Directory-Informationen:
    
    - Domänen-ID für die Domäne, deren Name die erste Domäne, wenn Sie alphabetisch sortiert werden

    - Anzahl der Domänencontroller

    - Anzahl der Domänencontroller durch ATA überwacht wird, über Port Spiegelung

    - Anzahl der Standorte

    - Anzahl der Computer

    - Anzahl von Gruppen

    - Anzahl der Benutzer

- Verdächtige Aktivitäten – die folgenden Daten werden für jede verdächtige Aktivitäten erfasst:

    (Computernamen, Benutzernamen und IP-Adressen sind **nicht** gesammelt)
    
    - Verdächtige Aktivitäten-Typ

    - Verdächtige Aktivitäts-ID

    - Status

    - Start- und Endzeit

    - Benutzereingabe


### Deaktivieren der Datensammlung

Zum Beenden der sammeln und Senden von Telemetriedaten gehen Daten an Microsoft.


1. Melden Sie sich bei der ATA-Konsole auf die drei Punkten in der Symbolleiste, und wählen Sie **über**.

2. Deaktivieren Sie das Kontrollkästchen für **Senden Sie uns Informationen zur Verwendung in der Zukunft verbessern die Kundenzufriedenheit**.


## Siehe auch

[ATA-Versionsinformationen](/Topic/ATA+Release+Notes.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





