---
title: ATA-Installation
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
ms.assetid: 3715b69e-e631-449b-9aed-144d0f9bcee7
translation.priority.mt: 
  - de-de
  - ja-jp
---
# ATA-Installation
Es folgen die erforderlichen Schritte zum Abrufen der ATA bereitgestellt, konfiguriert und ausgeführt.

Gehen Sie folgendermaßen vor, um ATA zu konfigurieren:

-   [Preinstallation steps](#Preinstallsteps)

-   [Step 1. Download and Install the ATA Center](#InstallATACtr)

-   [Step 3. Configure ATA Gateway Domain Connectivity Settings](#ConfigConSettings)

-   [Step 4. Download the ATA Gateway Setup Package](#DownloadATA)

-   [Step 5. ATA Gateway installation](#InstallATAGW)

-   [Step 6. Configure the ATA Gateway settings](#ConfigATAGW)

-   [Step 7. Configure VPN Subnets and Honeytoken user](#ATAvpnHoneytokensetting)

## <a name="Preinstallsteps"></a>Schritte vor der installation

1.  Wenn Sie die ATA-public Preview-Version installiert haben, finden Sie unter [ATA-Versionsinformationen](../../ems/ATA_Content/ATA-Release-Notes.md) Hilfestellung bei der Deinstallation der ATA-Preview-Version.

2.  KB2934520 auf dem Server ATA-Center und auf der ATA-Gatewayservern vor der Installation von Anfang andernfalls die ATA-Installation installieren Sie dieses Update ist einen Neustart in der Mitte der ATA-Installation erforderlich.

## <a name="InstallATACtr"></a>Schritt 1. Herunterladen und Installieren der ATA-Center
Nachdem Sie überprüft haben, dass der Server die Mindestanforderungen erfüllt, können Sie mit der Installation des Mittelpunkts ATA fortfahren.

Führen Sie die folgenden Schritte auf dem Server ATA-Center.

1.  Herunterladen von ATA aus der [TechNet Evaluation Center](http://www.microsoft.com/en-us/evalcenter/).

2.  Melden Sie sich ein Benutzer, der Mitglied der lokalen Administratorgruppe ist.

3.  Führen Sie Setup.EXE von Microsoft ATA-Center ein Eingabeaufforderungsfenster mit erhöhten Rechten und führen Sie den Setup-Assistenten.

4.  Auf der **Willkommen** Seite, wählen Sie Ihre Sprache aus, und klicken Sie auf **Weiter**.

5.  Lesen Sie den Endbenutzer-Lizenzvertrag, und wenn Sie zustimmen, klicken Sie auf **Weiter**.

6.  Auf der **Center Configuration** Seite, geben Sie die folgende Informationen basierend auf Ihrer Umgebung:

    |Feld|Beschreibung|Kommentare|
    |--------|----------------|--------------|
    |Installationspfad|Dies ist der Speicherort, auf den ATA-Center installiert werden. Standardmäßig ist dies %programfiles%\Microsoft erweiterte Bedrohung Analytics\Center|Übernehmen Sie den Standardwert|
    |Datenbank-Datenpfad|Dies ist der Speicherort, in dem die MongoDB-Datenbankdateien gespeichert werden sollen. Standardmäßig ist dies %programfiles%\Microsoft erweiterte Bedrohung Analytics\Center\MongoDB\bin\data|Ändern Sie die Position, an einem Ort, in dem Sie Platz für Wachstum haben, auf der Grundlage Ihrer Größe. **Note:** <ul><li>In produktionsumgebungen sollten Sie ein Laufwerk verwenden, die basierend auf der Kapazität zu planen, um Speicherplatz verfügt.</li><li>Bei großen Bereitstellungen sollte die Datenbank auf einem separaten physischen Datenträger sein.</li></ul>Finden Sie unter [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md) zum Anpassen von Informationen.|
    |Datenbankpfad für die Erfassung|Dies ist der Speicherort, in dem die Journal-Datenbankdateien gespeichert werden sollen. Standardmäßig ist dies %programfiles%\Microsoft erweiterte Bedrohung Analytics\Center\MongoDB\bin\data\journal|Für große Bereitstellungen sollte die Erfassung der Datenbank auf einem separaten physischen Datenträger aus der Datenbank und das Systemlaufwerk. Ändern Sie den Speicherort an einen Ort, in dem Sie Raum für die Erfassung Ihrer Datenbank haben.|
    |ATA-Center-Dienst-IP-Adresse: Port|Dies ist die IP-Adresse, die der ATA-Center-Dienst für die Kommunikation zwischen den Gateways ATA abgehört wird.<br /><br />**Der Standardport:** 443|Klicken Sie auf den Pfeil nach unten, markieren Sie die IP-Adresse von der ATA-Center-Dienst verwendet werden.<br /><br />Die IP-Adresse und den Port des ATA-Center-Diensts nicht identisch mit der IP-Adresse und Port der ATA-Konsole. Stellen Sie sicher, dass den Port der ATA-Konsole.|
    |SSL-Dienstzertifikat ATA-Center|Dies ist das Zertifikat, das von den ATA-Center-Dienst verwendet wird.|Klicken Sie auf das Schlüsselsymbol wählen Sie ein Zertifikat installiert oder selbst signiertes Zertifikat überprüfen, wenn Sie in einer Lab-Umgebung bereitstellen.|
    |ATA-Konsole IP-Adresse|Dies ist die IP-Adresse, die von IIS für die ATA-Konsole verwendet werden.|Klicken Sie auf den Pfeil nach unten, um die IP-Adresse verwendet, die für die ATA-Konsole auswählen. **Note:** Notieren Sie sich diese IP-Adresse des Gateways ATA ATA-Konsole zugreifen zu vereinfachen.|
    |ATA-Konsole SSL-Zertifikat|Dies ist das Zertifikat von IIS verwendet werden.|Klicken Sie auf das Schlüsselsymbol wählen Sie ein Zertifikat installiert oder selbst signiertes Zertifikat überprüfen, wenn Sie in einer Lab-Umgebung bereitstellen.|
    ![](../Image/ATA%20Center%20Configuration.JPG)

7.  Klicken Sie auf **Installation** ATA und seine Komponenten zu installieren und die Verbindung zwischen dem ATA-Mittelpunkt und die ATA-Konsole erstellen.

8.  Wenn die Installation abgeschlossen ist, klicken Sie auf **Starten**  zum Herstellen der ATA-Konsole.

### Überprüfen der installation

1.  Stellen Sie sicher, dass der Dienst Microsoft Advanced Threat Analytics Center ausgeführt wird.

2.  Klicken Sie auf dem Desktop auf die Verknüpfung Microsoft Advanced Threat-Analyse für die Verbindung an die ATA-Konsole. Melden Sie sich die gleichen Benutzeranmeldeinformationen, die Sie zum Installieren der ATA-Center. Der erstmaligen Anmeldung an der ATA-Konsole werden Sie automatisch zur begründet werden die **Domäne Konnektivitätseinstellungen** Seite, um die Konfiguration und die Bereitstellung der ATA-Gateways fortgesetzt werden.

3.  Überprüfen Sie die Datei in der **"Microsoft.Tri.Center-c:\tests"** Datei am folgenden Standardspeicherort gefunden werden kann: %programfiles%\Microsoft Bedrohung Analytics\Center\Logs erweitert.

## <a name="ConfigConSettings"></a>Schritt 2. ATA-Gateway Domäne Konnektivität konfigurieren
Die Einstellungen im Abschnitt zur Domäne Konnektivität-Einstellungen gelten für alle ATA-Gateways, die von der ATA-Center verwaltet werden.

Um die Domäne konfigurieren, führen Sie die folgenden auf dem Server ATA-Center Konnektivitätseinstellungen.

1.  Öffnen Sie die ATA-Konsole, und melden Sie sich. Anweisungen finden Sie unter [Arbeiten mit der ATA-Konsole](../../ems/ATA_Content/Working-with-the-ATA-Console.md).

2.  Beim ersten bei der ATA-Konsole, anmelden nachdem die ATA-Center installiert wurde, werden Sie automatisch zur Konfigurationsseite ATA-Gateways weitergeleitet. Wenn Sie die Einstellungen später ändern möchten, klicken Sie auf das Symbol, und wählen **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

3.  Auf der **Gateways** Seite, klicken Sie auf **Domäne Konnektivitätseinstellungen**, geben Sie Folgendes ein, und klicken Sie auf **Speichern**.

    |Feld|Kommentare|
    |--------|--------------|
    |**Benutzername** (erforderlich)|Geben Sie nur-Lese-Benutzernamen ein, z. B.: **user1**.|
    |**Kennwort** (erforderlich)|Geben Sie das Kennwort für den Benutzer schreibgeschützt, z. B.: **Pencil1**. **Note:** Stellen Sie sicher, dass das Kennwort richtig ist. Wenn Sie das falsche Kennwort speichern, wird der ATA-Dienst beendet, die auf die ATA-Gatewayserver ausgeführt.|
    |**Domäne** (erforderlich)|Geben Sie die Domäne für den Benutzer schreibgeschützt, z. B. **contoso.com**. **Note:** Es ist wichtig, dass Sie den vollständigen FQDN der Domäne eingeben, wo sich der Benutzer befindet. Wenn das Konto des Benutzers in der Domäne "corp.contoso.com" ist, müssen Sie eingeben `corp.contoso.com` nicht "contoso.com"|
    ![](../Image/ATA%20Domain%20Connectivity%20User.JPG)

## <a name="DownloadATA"></a>Schritt 3. ATA-Gateway-Setup-Paket herunterladen
Nach dem Konfigurieren der Domäne Konnektivitätseinstellungen können Sie das ATA-Gateway-Setup-Paket herunterladen.

Das Gateway ATA-Paket herunterladen:

1.  Öffnen Sie einen Browser, und geben Sie die IP-Adresse, die Sie in der Mitte des ATA für die ATA-Konsole konfiguriert, auf dem Computer ATA-Gateway. ATA-Konsole wird geöffnet, klicken Sie auf das Symbol, und wählen Sie **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

2.  In der **ATA-Gateways** auf **herunterladen ATA-Gateway-Setup**.

3.  Das Paket lokal zu speichern.

Die Zip-Datei enthält Folgendes:

-   ATA-Gateway-installer

-   Einstellung der Konfigurationsdatei mit den erforderlichen Informationen zum Herstellen der ATA-Center

## <a name="InstallATAGW"></a>Schritt 4. Installieren Sie das ATA-Gateway
Überprüfen Sie vor der Installation des ATA-Gateways, Port-mirroring ordnungsgemäß konfiguriert ist, und ob das ATA-Gateway Datenverkehr zu und von den Domänencontrollern sehen können. Weitere Informationen finden Sie unter [Überprüfen Sie die Port-Spiegelung](../../ems/ATA_Content/Validate-Port-Mirroring.md).

> [!IMPORTANT]
> Stellen Sie sicher, dass [KB2919355](http://support.microsoft.com/kb/2919355/) installiert wurde.  Führen Sie das folgende PowerShell-Cmdlet zu überprüfen, ob das Update installiert ist:
> 
> `Get-HotFix -Id kb2919355`

Führen Sie die folgenden Schritte auf dem ATA-Gatewayserver.

1.  Extrahieren Sie die Dateien aus der Zipdatei.

2.  Führen Sie Setup.exe von Microsoft ATA-Gateway ein Eingabeaufforderungsfenster mit erhöhten Rechten und führen Sie den Setup-Assistenten.

3.  Auf der **Willkommen** Seite, wählen Sie Ihre Sprache aus, und klicken Sie auf **Weiter**.

4.  Klicken Sie unter  **ATA-Gateway-Konfiguration**, geben Sie die folgende Informationen basierend auf Ihrer Umgebung:

    ![](../Image/ATA%20Gateway%20Configuration.JPG)

    |Feld|Beschreibung|Kommentare|
    |--------|----------------|--------------|
    |Installationspfad|Dies ist der Speicherort, auf das ATA-Gateway installiert werden. Standardmäßig ist dies %programfiles%\Microsoft erweiterte Bedrohung Analytics\Gateway|Übernehmen Sie den Standardwert|
    |ATA-Gateway-Dienst SSL-Zertifikat|Dies ist das Zertifikat, das von der ATA-Gateway verwendet wird.|Verwenden Sie ein selbstsigniertes Zertifikat für nur Lab-Umgebungen.|
    |ATA-Gateway-Registrierung|Geben Sie den Benutzernamen und das Kennwort des Administrators ATA.|Geben Sie für das ATA-Gateway mit der ATA-Center zu registrieren den Benutzernamen und das Kennwort des Benutzers, der die ATA-Center installiert. Dieser Benutzer muss Mitglied einer der folgenden lokalen Gruppen der ATA-Center sein.<br /><br />-   Administratoren<br />-   Microsoft Threat-Analyse-Administratoren erweitert **Note:** Diese Anmeldeinformationen werden nur für die Registrierung verwendet und nicht in ATA gespeichert werden.|

5.  Nachdem die Installation abgeschlossen ist, klicken Sie auf **Starten**  öffnen Sie Ihren Browser und melden Sie sich bei der ATA-Konsole.

### <a name="ConfigATAGW"></a>Schritt 5. Konfigurieren Sie die ATA-Gateway
Nachdem das ATA-Gateway installiert wurde, führen Sie die folgenden Schritte aus, um die Einstellungen für die ATA-Gateway konfigurieren.

1.  Klicken Sie auf der Maschine ATA-Gateway in der ATA-Konsole auf den **Konfiguration** und wählen Sie die **ATA-Gateways** Seite.

2.  Geben Sie die folgende Informationen ein.

    |Feld|Beschreibung|Kommentare|
    |--------|----------------|--------------|
    |Beschreibung|Geben Sie eine Beschreibung des ATA-Gateways (optional).||
    |**Domänencontroller** (erforderlich)<br /><br />Weitere Informationen zu der Liste von Domänencontrollern finden Sie weiter unten.|Geben Sie den vollständigen FQDN des Domänencontrollers, und klicken Sie auf das Pluszeichen, um ihn der Liste hinzuzufügen. Zum Beispiel  **dc01.contoso.com**<br /><br />![](../Image/ATAGWDomainController.png)|Die Objekte in den ersten Domänencontroller in der Liste werden über LDAP-Abfragen synchronisiert. Je nach Größe der Domäne kann dies einige Zeit dauern. **Note:** <ul><li>Stellen Sie sicher, dass der erste Domänencontroller ist **nicht** schreibgeschützt.    Lesen Sie nur die Domäne, die Domänencontroller erst nach Abschluss der ersten Synchronisierung hinzugefügt werden soll.</li></ul>|
    |**Capture Netzwerkadapter** (erforderlich)|Wählen Sie die Netzwerkadapter, die mit dem Switch verbunden sind, die als Ziel Mirror-Port zum Empfangen von Datenverkehr auf dem Domänencontroller konfiguriert sind.|Wählen Sie den Netzwerkadapter für die Erfassung.|
    ![](../Image/ATA%20Config%20GW%20Settings.jpg)

3.  Klicken Sie auf **Speichern**.

    > [!NOTE]
    > Es dauert einige Minuten, bis der ATA-Gateway-Dienst zum ersten Mal starten, da er den Cache des Netzwerks Capture-Parser verwendet, die für die ATA-Gateway erstellt.

Die folgenden Informationen gelten für die Server aus, Sie in geben, der **Domänencontroller** Liste.

-   Der erste Domänencontroller in der Liste wird vom ATA-Gateway für die Synchronisierung der Objekte in der Domäne über LDAP-Abfragen verwendet werden. Je nach Größe der Domäne kann dies einige Zeit dauern.

-   Müssen alle Domänencontroller, für deren Datenverkehr über Port Spiegelung vom Gateway ATA überwacht wird, aufgeführt werden die **Domänencontroller** Liste. Wenn ein Domänencontroller nicht, in aufgeführt ist der **Domänencontroller** Liste Erkennung von verdächtigen Aktivitäten möglicherweise nicht wie erwartet funktionieren.

-   Stellen Sie sicher, dass der erste Domänencontroller ist **nicht** einem schreibgeschützten Domänencontroller (RODC).

    Lesen Sie nur die Domäne, die Domänencontroller erst nach Abschluss der ersten Synchronisierung hinzugefügt werden soll.

-   Mindestens ein Domänencontroller in der Liste wird ein globaler Katalogserver sein. Dadurch werden die ATA auf Computer- und Objekte in anderen Domänen in der Gesamtstruktur zu beheben.

Die geänderte Konfiguration werden auf das ATA-Gateway auf die nächste geplante Synchronisierung zwischen dem ATA-Gateway und dem ATA-Center angewendet werden.

### Überprüfen der Installation:
Um zu überprüfen, dass die ATA-Gateway erfolgreich bereitgestellt wurde, überprüfen Sie die folgenden Schritte aus:

1.  Überprüfen Sie, dass der Microsoft Advanced Bedrohung Analytics-Dienst ausgeführt wird. Nachdem Sie die ATA-Gateway-Einstellungen gespeichert haben, kann es einige Minuten, bis der Dienst gestartet dauern.

2.  Wenn der Dienst nicht gestartet wird, überprüfen Sie die Datei "Microsoft.Tri.Gateway"-c:\tests "" im folgenden Standardordner "%programfiles%\Microsoft erweitert Bedrohung Analytics\Gateway\Logs", suchen Sie nach Einträgen mit "Transfer" oder "Start-service".

3.  Überprüfen Sie die folgenden Leistungsindikatoren für den Microsoft-ATA-Gateway:

    -   **NetworkListener erfasst Nachrichten / Sek.**: Dieser Leistungsindikator verfolgt, wie viele Nachrichten durch die ATA pro Sekunde aufgezeichnet werden. Der Wert sollte mid Hunderte oder Tausende abhängig von der Anzahl der überwachten Domänencontroller und Auslastung jeder Domänencontroller ist. Mit dem Port Spiegelungskonfiguration können einfache oder doppelte Ziffer Werte auf ein Problem hinweisen.

    -   **EntityTransfer Aktivität/s**: Dieser Wert muss im Bereich von ein paar Hundert alle paar Sekunden.

4.  Ist dies das erste ATA-Gateway installiert, melden Sie sich nach wenigen Minuten in die ATA-Konsole, und öffnen Sie im Bereich der Benachrichtigung, durch ein Lesegerät der rechten Seite des Bildschirms geöffnet. Daraufhin sollte eine Liste der **Entitäten vor kurzem gelernt** in der Benachrichtigungsleiste auf der rechten Seite der Konsole.

5.  So überprüfen Sie, dass die Installation erfolgreich abgeschlossen wurde:

    Suchen Sie in der Konsole für etwas in der Suchleiste, z. B. ein Benutzer oder eine Gruppe in Ihrer Domäne.

    Öffnen Sie den Systemmonitor. Klicken Sie in der Struktur der Leistung auf **Systemmonitor** und klicken Sie dann auf das Plussymbol, **einen Zähler hinzufügen**. Erweitern Sie **Microsoft ATA-Gateway** und führen Sie einen Bildlauf nach unten zum **Network Listener erfasst Nachrichten pro Sekunde** und fügen Sie es hinzu. Stellen Sie dann sicher, dass Sie die Aktivitäten im Diagramm angezeigt.

    ![](../Image/ATA%20performance%20monitoring%20add%20counters.png)

### <a name="ATAvpnHoneytokensetting"></a>Schritt 6. Konfigurieren Sie die kurzfristigen Lease Subnetze und Honeytoken Benutzer
Kurzfristige Lease Subnetze sind Subnetze, in dem die IP-Adresszuweisung sehr schnell ändert - innerhalb von Sekunden oder Minuten. Beispielsweise verwendet IP-Adressen für Ihre VPNs und Wi-Fi-IP-Adressen. Um die Liste der kurzfristigen Lease Subnetze in Ihrem Unternehmen verwendeten einzugeben, gehen Sie folgendermaßen vor:

1.  Der ATA-Konsole auf dem ATA-Gatewaycomputer, klicken Sie auf das Symbol, und wählen **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

2.  Klicken Sie unter **Erkennung**, geben Sie Folgendes für kurzfristige Lease Subnetze. Geben Sie die kurzfristigen Lease Subnetze Schrägstrich Notation Format, z. B. mit:  `192.168.0.0/24` und klicken Sie auf das Pluszeichen (+).

3.  Geben Sie für das Honeytoken-Konto-SIDs die SID für das Benutzerkonto an, die keine Netzwerkaktivität, und klicken Sie auf das Pluszeichen (+). Beispiel: `S-1-5-21-72081277-1610778489-2625714895-10511`.

    > [!NOTE]
    > Um die SID für einen Benutzer zu finden, führen Sie das folgende Windows PowerShell-Cmdlet `Get-ADUser UserName`.

4.  Konfigurieren von Ausschlüssen: Sie können konfigurieren, dass IP-Adressen von bestimmten verdächtige Aktivitäten ausgeschlossen werden sollen. Weitere Informationen finden Sie unter [Arbeiten mit Einstellungen für ATA-Erkennung](../../ems/ATA_Content/Working-with-ATA-Detection-Settings.md).

5.  Klicken Sie auf **Speichern**.

![](../Image/ATA%20VPN%20Subnets.JPG)

Herzlichen Glückwunsch, Sie Microsoft Advanced Threat-Analyse erfolgreich bereitgestellt haben!

Überprüfen der Angriff Zeitachse anzeigen verdächtige Aktivitäten und suchen Sie nach Benutzern oder Computern erkannt und ihre Profile anzeigen.

Denken Sie daran, dass es dauert mindestens drei Wochen für ATA Verhaltensunterschiede Profile erstellen, damit während der ersten drei Wochen verdächtigen Aktivitäten, die nicht angezeigt werden.

## Siehe auch
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)
 [Konfigurieren der Ereignissammlung](../../ems/ATA_Content/Configure-Event-Collection.md)
 [ATA-Planung und Anforderungen](../../ems/ATA_Content/ATA-Planning-and-Requirements.md)

