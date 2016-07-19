---
title: Arbeiten mit der ATA-Konsole
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
ms.assetid: 1bf264d9-9697-44b5-9533-e1c498da4f07
---
# Arbeiten mit der ATA-Konsole
Dieser Abschnitt beschreibt die ATA-Konsole.


## Aktivieren des Zugriffs auf die ATA-Konsole

Jeder Benutzer, der Mitglied der lokalen Administratorgruppe auf dem Server ATA-Center ist berechtigt, melden Sie sich an die Konsole ATA und ATA-Einstellungen verwalten.
Damit wird einen Benutzer in der ATA-Konsole anmelden, ohne sie als lokalen Administrator, Hinzufügen der lokalen Gruppe: **Microsoft Advanced Bedrohung Analytics Administratoren**.


## Anmeldung an der Konsole ATA

- Klicken Sie im Server-ATA-Center auf der **ATA-MMC** Symbol auf dem Desktop oder öffnen Sie einen Browser und öffnen Sie die ATA-Konsole.

    Sie können alternativ öffnen Sie einen Browser aus der Mitte ATA oder ATA-Gateways und Durchsuchen, um die IP-Adresse, die Sie bei der Installation ATA-Center für die ATA-Konsole konfiguriert.

- Geben Sie Ihren Benutzernamen und Ihr Kennwort ein, und klicken Sie auf **Anmelden**.

    In diesem Fall müssen Sie eine Anmeldung mit einem Benutzer, der Mitglied der lokalen Administratorgruppe oder der Microsoft Advanced Bedrohung Analytics Administratorengruppe ist.

    ![](/Image/ATA+log+in+screen.jpg)


## ATA-Konsolenelemente

- **Zeitachse Angriff**

    Dies ist die Standardseite, die bei der Anmeldung auf der ATA-Konsole angezeigt werden. Standardmäßig werden alle offene verdächtige Aktivitäten auf der Zeitachse Angriff angezeigt. Sie können der zeitliche Angriff, um anzuzeigen, Filtern Dismissed oder aufgelöst verdächtige Aktivitäten zu öffnen. Die neuesten Einträge in der Liste zuerst angezeigt werden chronologisch verdächtige Aktivitäten aufgelistet.

- **Verdächtige Aktivitäten**

    Wenn ATA eine verdächtige Aktivität entdeckt wird ein Eintrag in der Angriff Zeitachse erstellt. Weitere Informationen finden Sie unter [Arbeiten mit verdächtigen Aktivitäten](/Topic/Working+with+Suspicious+Activities.md).

- **Benachrichtigungsleiste**

    Wenn ein neuer verdächtiger Aktivitäten erkannt wird, wird die Benachrichtigungsleiste auf der rechten Seite automatisch geöffnet. Wenn seit der letzten Anmeldung in der Benachrichtigungsleiste geöffnet wird, nachdem Sie sich erfolgreich angemeldet haben, neue verdächtige Aktivitäten werden. Um darauf zuzugreifen, können Sie jederzeit den Pfeil nach rechts klicken.

- **Filtern**

    Sie können filtern, welche verdächtigen Aktivitäten in der Zeitachse Angriff angezeigt oder in Entity verdächtige Aktivitäten Registerkarte Profil basierend auf Status und den Schweregrad angezeigt werden.

- **Suchleiste**

    Oben auf dem Bildschirm finden Sie eine Suchleiste. Sie können für einen bestimmten Benutzer, Computer oder Gruppen in ATA suchen. Um auszuprobieren, starten Sie Sie eingeben.

    ![](/Image/ATA+console+search.png)

- **Integrität Center**

    Die Integrität Center erhalten Sie Warnungen, wenn etwas in Ihrem Netzwerk ATA nicht ordnungsgemäß funktioniert.

    Jederzeit Ihr System ein Problem erkennt z. B. einen Verbindungsfehler oder einen getrennten ATA-Gateway können das Symbol Integrität Center kennen, indem ein roter Punkt angezeigt Sie. ![](/Image/ATA+Health+Center+Alert+red+dot.png)

    Wie verdächtige Aktivitäten Integrität Center Warnungen können ignoriert werden aufgelöst und kategorisierte hoch, Mittel oder niedrig sind, je nach deren Schweregrad. Wenn Sie eine Warnung, die der ATA-Dienst weiterhin als aktiv erkannt wird beheben, wird es automatisch in der geöffneten Liste der Warnungen verschoben werden. Wenn das System erkennt, dass die Ursache für eine Warnung (die Situation wurde korrigiert) nicht mehr vorhanden ist, wird es automatisch in die Liste der aufgelösten verschoben werden.

- **Konfiguration**

    Ändern und Anzeigen der ATA-Konfiguration erfolgt durch Klicken auf das Symbol "Settings" (drei Punkte) auf der Menüleiste, gefolgt von der Konfiguration.

    ![](/Image/ATA+config+icon.JPG)

- **Profile für Benutzer und computer**

    ATA erstellt ein Profil für jeden Benutzer und Computer in der Domäne. Im Benutzerprofil ATA zeigt allgemeine Informationen über den Benutzer und bietet zusätzliche Informationen zu den folgenden Seiten: Zusammenfassung, Aktivitäten und verdächtige Aktivitäten.

    > [! HINWEIS:]
    > Ein Profil, das ATA wurde nicht vollständig auflösen wird mit halber kreisförmiges Symbol neben dem identifiziert werden. ![](/Image/ATA+Unresolved+Profile.jpg)

- **Mini-Profil**

    An einer beliebigen Stelle in der Konsole vorhanden ist eine einzelne Entität dargestellt sein können, wie z. B. einen Benutzer oder Computer, wenn Sie Sie zeigen Sie die Maus auf die Entität, die ein Mini-Profil wird automatisch geöffnet, die folgende Informationen anzeigen, sofern verfügbar:

    ![](/Image/ATA+mini+profile.jpg)
    
    - Name

    - Bild

    - E-Mail

    - Telefon

    - Anzahl der verdächtigen Aktivitäten nach Schweregrad


## Siehe auch

[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





