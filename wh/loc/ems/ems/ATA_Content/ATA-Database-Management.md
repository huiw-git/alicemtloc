---
title: ATA-Verwaltung
ms.custom: na
ms.date: 12/22/2015
ms.prod: identity-ata
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1d27dba8-fb30-4cce-a68a-f0b1df02b977
---
# ATA-Verwaltung
Verschieben, sichern oder Wiederherstellen der Datenbank ATA werden sollen, verwenden Sie diese Verfahren für die Arbeit mit MongoDB.


## Sichern der ATA-Datenbank

Finden Sie in der [relevanten MongoDB-Dokumentation](http://docs.mongodb.org/manual/administration/backup/).


## Wiederherstellen der ATA-Datenbank

Finden Sie in der [relevanten MongoDB-Dokumentation](http://docs.mongodb.org/manual/administration/backup/).


## Die ATA-Datenbank verschieben auf ein anderes Laufwerk

1. Beenden Sie die **Microsoft Advanced Threat Analytics Center** Service.

2. Beenden Sie die **MongoDB** Service.

3. Öffnen Sie die standardmäßig unter Mongo Konfigurationsdatei: C:\Program Files\Microsoft erweiterte Threat Analytics\Center\MongoDB\bin\mongod.cfg.

    Suchen Sie den Parameter **Speicher: DbPath**

4. Verschieben Sie den Ordner aufgeführt, die der **DbPath** Parameter an die neue Position.

5. Ändern der **DbPath** Parameter innerhalb der Konfiguration für die Mongo-Datei in den neuen Ordnerpfad und speichern und schließen Sie die Datei.

    ![](/Image/ATA+mongoDB+moveDB.png)

6. Starten Sie die **MongoDB** Service.

7. Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie die Mongo-Shell durch Ausführen von **mongo.exe ATA** .

    In der Standardeinstellung die mongo.exe befinden sich in: C:\Program Files\Microsoft erweiterte Bedrohung Analytics\Center\MongoDB\bin

8. Führen Sie den folgenden Befehl: **Db. SystemProfiles.update ({_t: "CenterSystemProfile"}, {$set:{"Configuration.CenterDatabaseClientConfiguration.DataPath": "& Lt; Neuer DB-Speicherort & Gt ;"}})**
    **Instead of & Lt; Neuer DB-Speicherort & Gt;** Wo & Lt; Neue DB-Speicherort & Gt; ist der neue Pfad an.

9. Starten Sie die **Microsoft Advanced Threat Analytics Center** Service.


## Siehe auch

[ATA-Architektur](/Topic/ATA+Architecture.md)
[ATA-Planung und Anforderungen](/Topic/ATA+Planning+and+Requirements.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





