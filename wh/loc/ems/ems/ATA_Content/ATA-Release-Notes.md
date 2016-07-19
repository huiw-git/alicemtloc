---
title: ATA-Versionsinformationen
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
ms.assetid: 606ab8db-3c42-4d99-90dc-c54a76f52d13
---
# ATA-Versionsinformationen
Diese Versionshinweise enthalten Informationen über bekannte Probleme in dieser Version von Advanced Threat-Analyse.


## Was ist neu in dieser Version?

- Unterstützung für Windows Event weiterleiten (im WEF) Ereignisse direkt von Domänencontrollern an das ATA-Gateway zu senden.

- Erkennung von Pass-The-Hash-Erweiterungen auf Unternehmensressourcen durch die Kombination der DPI-Wert (Deep Packet Inspection) und Windows-Ereignisprotokolle.

- Geräte und nicht-Windows-Geräte für Erkennung und Sichtbarkeit, Erweiterungen für die Unterstützung von keiner Domäne gehören.

- Leistungssteigerungen mehr Datenverkehr pro ATA-Gateway zu unterstützen.

- Leistungssteigerungen Weitere ATA-Gateways pro ATA-Center zu unterstützen.

- Eine neue automatische Namensauflösungsprozess wurde hinzugefügt, die Computernamen und IP-Adressen entspricht – diese einzigartige Funktion sparen Sie kostbare Zeit bei der Untersuchung und starke Beweise für Sicherheitsanalysten

- Verbesserte Fähigkeit auf Benutzereingaben automatisch den Erkennungsprozess Feinabstimmung sammeln.

- Automatische Erkennung für NAT-Geräte.

- Automatisches Failover, wenn der Domänencontroller nicht erreichbar sind.

- Überwachung der Integrität und Benachrichtigungen bieten jetzt Gesamtstatus der Bereitstellung als auch bestimmte Probleme im Zusammenhang mit der Konfiguration und Konnektivität.

- Einblick in Websites und Speicherorte, in denen Entitäten ausgeführt werden.

- Unterstützung für mit mehreren Domänen.

- Unterstützung für Domänen mit einfacher Bezeichnung (SLD).

- Unterstützung für die IP-Adresse und das Zertifikat des ATA-Gateways und ATA Center ändern.

- Telemetrie zur Verbesserung der Kundenzufriedenheit.


## Bekannte Probleme

Die folgenden bekannten Probleme in dieser Version vorhanden.


### Capture-Netzwerksoftware

Auf das ATA-Gateway, das einzige unterstützte Netzwerksammlung ist Software, die Sie installieren können [Microsoft Network Monitor 3.4](http://www.microsoft.com/en-us/download/details.aspx?id=4865). Installieren Sie Microsoft Message Analyzer oder einem anderen Netzwerk erfassen die Software nicht. Die Installation anderer Software führt dazu, dass das ATA-Gateway nicht mehr ordnungsgemäß funktionieren.


### Installation von Zip-Datei

Stellen Sie beim Installieren des ATA-Gateways, extrahieren Sie die Dateien aus der Zipdatei in ein lokales Verzeichnis, und installieren Sie es von dort aus. ATA-Gateway direkt innerhalb der Zip-Datei nicht installieren oder die Installation schlägt fehl.


### Deinstallieren früherer Versionen von ATA

Wenn Sie eine frühere Version von ATA, Public Preview oder Private Preview-Versionen installiert haben, müssen Sie vor der Installation dieser Version des ATA ATA Zentrierung und ATA-Gateways deinstallieren.

Sie müssen auch löschen Sie die Datenbankdateien und Protokolldateien. Die Datenbanken aus früheren Versionen von ATA sind nicht kompatibel mit der GA-Version des ATA.

Beim Versuch, die ATA- oder ATA-Gateway zu deinstallieren, wenn die ATA-Installation anstelle der Deinstallation wird geöffnet, müssen Sie den folgenden Registrierungsschlüssel hinzufügen, und deinstallieren Sie ATA erneut.

**ATA-Center**


- HKLM\SOFTWARE\Microsoft\Microsoft erweiterte Bedrohung Analytics\Center

- Fügen Sie einen neuen Zeichenfolgenwert mit dem Namen **Installationspfad** mit einem Wert von **C:\Program Files\Microsoft erweiterte Threat Analytics\Center** . Dies ist der Standard-Installationsordner. Wenn Sie geändert haben der Installationsordner Geben Sie den Pfad dem ATA installiert ist.

    ![](/Image/ATA+uninstall+center+bug.jpg)

**ATA-Gateway**


- HKLM\SOFTWARE\Microsoft\Microsoft erweiterte Bedrohung Analytics\Gateway

- Fügen Sie einen neuen Zeichenfolgenwert mit dem Namen **Installationspfad** mit einem Wert von **C:\Program Files\Microsoft erweiterte Threat Analytics\Gateway**. Dies ist der Standard-Installationsordner. Wenn Sie geändert haben der Installationsordner Geben Sie den Pfad dem ATA installiert ist.

    ![](/Image/ATA+GW+uninstall+bug.jpg)

Löschen Sie nach der Deinstallation den Installationsordner auf der ATA-Center und das ATA-Gateway. Wenn Sie die Datenbank in einem separaten Ordner installiert haben, löschen Sie den Datenbankordner im ATA-Center.


### Integrität Warnung - getrennten ATA-Gateway

Wenn Sie mehr als ein ATA-Gateway haben und Auflösen von Warnungen, automatische getrennt ATA-Gateway funktioniert nur in einer von ihnen, und die übrigen in den Status "Offen". Sie müssen manuell bestätigen, dass die ATA-Gateway ist und der Dienst ausgeführt wird, und lösen Sie die Warnung manuell.


### KB auf Virtualisierungshost

KB-3047154 darf nicht auf einem Virtualisierungshost installiert werden. Dadurch kann Port Spiegelung nicht mehr ordnungsgemäß funktioniert.


## Siehe auch

[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





