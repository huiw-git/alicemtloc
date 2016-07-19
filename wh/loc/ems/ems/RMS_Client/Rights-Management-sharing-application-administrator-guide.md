---
title: Rights Management freigabeanwendung – Administratorhandbuch
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
translation.priority.ht: 
  - es-es
  - fr-fr
  - it-it
  - ko-kr
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - da-dk
  - de-de
  - hu-hu
  - ja-jp
  - nb-no
  - nl-nl
  - pl-pl
  - pt-pt
  - sv-se
---
# Rights Management freigabeanwendung – Administratorhandbuch
Anhand der folgenden Informationen, wenn Sie für die gemeinsame Nutzung der Anwendung in einem Unternehmensnetzwerk Microsoft Rights Management verantwortlich sind oder ggf. Weitere technische Informationen als in den [Rights Management freigabeanwendung – Benutzerhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-user-guide.md) oder [häufig gestellte Fragen zur Microsoft Rights Management Freigabe-Anwendung für Windows](http://go.microsoft.com/fwlink/?LinkId=303971):

-   [Automatic deployment for the Microsoft Rights Management sharing application](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_ScriptedInstall)

    -   [Verifying installation success](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_verifyscripted)

    -   [Uninstall commands](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_uninstallscripted)

    -   [Suppressing automatic updates](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_SuppressAutomaticUpdates)

    -   [Azure RMS only: Configuring document tracking](#BKMK_DocumentTracking)

    -   [AD RMS only: Support for multiple email domains within your organization](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_FederatedDomains)

-   [Technical overview for the Microsoft Rights Management sharing application](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_AdminOverview)

    -   [Levels of protection – native and generic](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_LevelsofProtection)

    -   [Supported file types and file name extensions](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_SupportFileTypes)

    -   [Changing the default protection level of files](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_ChangeDefaultProtection)

> [!TIP]
> Wenn Sie Erfahrung mit der RMS-Freigabe-app oder benötigen Sie weitere Informationen sind, finden Sie unter [wie RMS schützt alle Dateitypen – mit der RMS-freigabeanwendung](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app).

Die RMS-Freigabe ist am besten für die Arbeit mit Azure RMS, weil diese Bereitstellungskonfiguration geschützte sendende von Anlagen für Benutzer in einer anderen Organisation und Optionen wie z. B. e-Mail-Benachrichtigungen und Nachverfolgen von Revocation Dokument unterstützt.  Allerdings funktioniert mit einigen Einschränkungen sie auch mit der lokalen Version AD RMS. Einen umfassenden Vergleich der Funktionen, die von Azure RMS und AD RMS unterstützt werden, finden Sie unter [Vergleich von Azure Rights Management und AD RMS](https://technet.microsoft.com/library/jj739831.aspx). Wenn Sie AD RMS und in Azure RMS migrieren möchten, finden Sie unter [Migration von AD RMS zu Azure Rights Management](https://technet.microsoft.com/library/dn858447.aspx).

## <a name="BKMK_ScriptedInstall"></a>Automatische Bereitstellung für die Microsoft Rights Management-freigabeanwendung
Die Windows-Version des RMS-freigabeanwendung unterstützt eine skriptbasierte Installation, die wodurch es für Unternehmen geeignet ist.

Die einzige Voraussetzung für Installationen sind, dass der Computer eine Mindestversion von Windows 7 Service Pack 1 ausführen und das Microsoft-Framework mindestens Version 4.0 installiert ist. Wenn Sie Microsoft .NET Framework 4.0 installieren müssen, können Sie [für die Installation über das Microsoft Download Center herunterladen](http://www.microsoft.com/download/details.aspx?id=17718).

#### Die RMS-Freigabe für die automatische Bereitstellung herunterladen

1.  Klicken Sie auf die [Microsoft Rights Management-freigabeanwendung für Windows](http://www.microsoft.com/download/details.aspx?id=40857) Seite im Microsoft Download Center, und klicken Sie auf **herunterladen**.

2.  Wählen Sie aus, und Laden Sie die Dateien, die Sie benötigen. Es gibt zwei Client-Installationspakete: eine für Windows 64-Bit (gemeinsame Nutzung von Microsoft Rights Management-Anwendung x64.zip) und die andere für 32-Bit-Windows (Microsoft Rights Management, die gemeinsame Nutzung der Anwendung x86.zip).

3.  Extrahieren Sie die Dateien aus der komprimierten Installationspakete, z. B. durch Doppelklicken. Kopieren Sie dann die extrahierten Dateien an einem Speicherort im Netzwerk, den Clientcomputer zugreifen können.

Der Setuppakete für die RMS-Freigabe unterstützt verschiedene Bereitstellungsszenarien und enthält Folgendes:

|Beschreibung|Bereitstellungsszenario|
|----------------|---------------------------|
|Microsoft Online-Anmeldeassistent|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2013 und Azure RMS, wenn Sie nicht installiert haben die [9 Juni 2015 für Office 2013 aktualisieren](https://support.microsoft.com/kb/3054853) (KB3054853)|
|Hotfix für Office (KB 2596501)|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2010 und AD RMS|
|Hotfix zum Aktivieren der AD RMS-Client 1.0 arbeiten mit Azure RMS (KB 2843630)|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2010 und AD RMS|
|AD RMS-Client und dem RMS-Freigabe|Für Folgendes erforderlich:<br /><br />-   Office 2016 oder Office 2013 und Azure RMS oder AD RMS<br />-   Office 2010 und Azure RMS<br />-   Office 2010 und AD RMS<br />-   RMS-Freigabe-Anwendung und Office-add-in nur|
|Office-add-Ins für die Multifunktionsleiste|Für Folgendes erforderlich:<br /><br />-   Office 2016 oder Office 2013 und Azure RMS oder AD RMS<br />-   Office 2010 und Azure RMS<br />-   Office 2010 und AD RMS<br />-   RMS-Freigabe-Anwendung und Office-add-in nur|
|Vorbereitungstool für Azure Active Directory Rights Management|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS|
Verwenden Sie die folgenden Verfahren, um die Befehle, die zum Bereitstellen der RMS-Freigabe für diesen Bereitstellungsszenarien erforderlich zu identifizieren:

-   **Office 2016 oder Office 2013 und Azure RMS oder AD RMS**

    Ihre Benutzer Office 2016 oder Office 2013 ausgeführt werden, Ihre Organisation Azure RMS oder Active Directory RMS verwendet und Benutzer-Zusammenarbeit mit anderen Unternehmen, die Azure RMS oder Active Directory RMS verwenden.

-   **Office 2010 und Azure RMS**

    Ihre Benutzer Office 2010 ausgeführt werden, Ihre Organisation verwendet Azure RMS und Benutzer-Zusammenarbeit mit anderen Unternehmen, die Azure RMS oder Active Directory RMS verwenden.

-   **Office 2010 und AD RMS**

    Ihre Benutzer Office 2010 ausgeführt werden, Ihre Organisation verwendet AD RMS und Benutzer-Zusammenarbeit mit anderen Unternehmen, die Azure RMS verwenden.

-   **RMS-Freigabe-Anwendung und Office-add-in nur**

    Ihre Benutzer 2016 Office, Office 2013 oder Office 2010 ausgeführt werden, Ihre Organisation verwendet AD RMS und Benutzer müssen sich nicht für die Zusammenarbeit mit anderen Unternehmen Azure RMS verwenden. Diese Installation können Sie die Installation nur die gemeinsame Nutzung Anwendung und Office-add-in.

> [!NOTE]
> In diesen Szenarien verwendet, wenn AD RMS in Ihrer Organisation ausgeführt wird, die Benutzer erhalten auf geschützten Inhalte von anderen Organisationen, die Azure RMS verwenden, aber die Benutzer nicht geschützten Senden von Inhalt an Benutzer in einer Organisation, die Azure RMS. Wenn Ihre Organisation Azure RMS ausgeführt wird, können Ihre Benutzer jedoch senden und empfangen geschützten Inhalte von anderen Organisationen.

Um die Installation für jede Prozedur abzuschließen, muss der Computer neu starten. Sie können einen automatischen Neustart initiieren, indem Sie mit einem Befehl wie Shutdown/i.

#### Die RMS-Freigabe für Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS bereitstellen

-   Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabe, Anwendung und der zugehörigen Komponenten installieren möchten den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s
    ```

Um erfolgreich zu überprüfen, finden Sie unter den [Verifying installation success](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_verifyscripted) in diesem Thema.

#### Die RMS-Freigabe für Office 2010 und Azure RMS bereitstellen

1.  Sie müssen der globale Administrator für Ihren Mandanten Office 365 oder Azure Active Directory sein, damit Sie durch Ausführen des Tool zum Vorbereiten der Azure Active Directory Rights Management Ihrer Organisation, Zertifizierung Dienst-URL abrufen können. Sie müssen dieses Tool auf einem einzelnen Computer nur einmal ausführen. Verwenden Sie die Zertifizierung URL bei der Installation der RMS-Freigabe auf jedem Computer:

    1.  Melden Sie sich an einem Computer mit einem lokalen Administratorkonto an.

    2.  Auf diesem Computer [herunterladen und Installieren der Microsoft Online Anmelde-Assistent](http://www.microsoft.com/download/details.aspx?id=28177).

    3.  Führen Sie zum finden Sie unter dem folgenden Befehl angezeigten auf dem Bildschirm Zertifizierung-Dienst-URL, die dann kopieren und für den nächsten Schritt speichern können:

        -   Für Windows 8.1 und Windows 8, 64-Bit:

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Für Windows 8.1 und Windows 8 32-Bit:

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Für Windows 7 64-Bit:

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > Mit diesem Befehl können Sie zur Eingabe Ihrer Anmeldeinformationen für Azure aufgefordert. Wenn der Computer nicht zu einer Domäne angehört, werden Sie aufgefordert werden. Wenn der Computer einer Domäne angehört, möglicherweise das Tool zwischengespeicherte Anmeldeinformationen verwenden.

2.  Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabe-Anwendung installieren möchten den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  Auf jedem Computer, auf dem Sie die RMS-Freigabe installieren, müssen Benutzer den folgenden Befehl ausführen (erhöhte Rechte nicht erforderlich). Es gibt verschiedene Möglichkeiten, um dies zu erreichen, einschließlich auffordern der Benutzer zum Ausführen des Befehls (z. B. einen Link in einer e-Mail-Nachricht oder einen Link auf das Helpdesk-Portal) oder Sie können ihre Anmeldeskript hinzufügen:

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

Um erfolgreich zu überprüfen, finden Sie unter den [Verifying installation success](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_verifyscripted) in diesem Thema.

#### Die RMS-Freigabe für Office 2010 und Active Directory RMS bereitstellen

1.  Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabe-Anwendung installieren möchten den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  Auf jedem Computer, auf dem Sie die RMS-Freigabe installieren, müssen Benutzer den folgenden Befehl ausführen (erhöhte Rechte nicht erforderlich). Es gibt verschiedene Möglichkeiten, um dies zu erreichen, einschließlich auffordern der Benutzer zum Ausführen des Befehls (z. B. einen Link in einer e-Mail-Nachricht oder einen Link auf das Helpdesk-Portal) oder Sie können ihre Anmeldeskript hinzufügen:

    -   Für Windows 10, Windows 8.1 und Windows 8, 64-Bit:

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   Für Windows 10, Windows 8.1 und Windows 8 32-Bit:

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   Für Windows 7 64-Bit:

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

Um erfolgreich zu überprüfen, finden Sie unter den [Verifying installation success](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_verifyscripted) in diesem Thema.

#### So installieren Sie die RMS-Freigabe, Anwendung und Office-add-in nur

1.  Installieren Sie die AD RMS-Client und dem RMS-Freigabe mithilfe des folgenden Befehls:

    -   Für 64-Bit-Windows:

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   Für 32-Bit-Windows:

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    Beispiel: `\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  Installieren Sie das Office-add-in mithilfe der folgenden Befehle aus:

    -   Für 64-Bit-Version von Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   Für 32-Bit-Version von Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    Beispiel: `\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

Um erfolgreich zu überprüfen, finden Sie unter den [Verifying installation success](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_verifyscripted) in diesem Thema.

### <a name="BKMK_verifyscripted"></a>Überprüfen der erfolgreichen installation
Die Installationsprotokolldateien können eine erfolgreiche Installation zu überprüfen.

##### Überprüfen der erfolgreichen Installation für den RMS-Freigabe für Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS

-   Erfolg des Befehls Setup.exe auf den einzelnen Computern überprüfen die Installationsprotokolldatei suchen **RMInstaller.log** in der *%temp%\RMS_installer_ &lt; Guid &gt;* Ordner, und identifizieren Sie den Exitcode.

    Eine erfolgreiche Installation hat einen Exitcode von 0 und jede andere Zahl gibt eine fehlerhafte Installation.

    Name der Protokolldatei Beispiel: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

##### Überprüfen der erfolgreichen Installation für den RMS-Freigabe für Office 2010 und Azure RMS

1.  Erfolg des Befehls Setup.exe auf den einzelnen Computern überprüfen die Installationsprotokolldatei suchen **RMInstaller.log** in der *%temp%\RMS_installer_ &lt; Guid &gt;* Ordner, und identifizieren Sie den Exitcode.

    Eine erfolgreiche Installation hat einen Exitcode von 0 und jede andere Zahl gibt eine fehlerhafte Installation.

    Name der Protokolldatei Beispiel: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Um Erfolg für den RMSSetup.exe-Befehl zu überprüfen, muss der Benutzer die folgenden Dateien im ihre *%localappdata%\microsoft\drm* Ordner:

    -   CERT-Computer-2048.drm

    -   CERT Machine.drm

    -   CLC &#42;.drm

    -   GIC &#42;.drm

    Beispiel einer CLC &#42;.drm-Datei:

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf k5b11; k4a10; kac15; k29b2b6980f4c} .drm**

##### Überprüfen der erfolgreichen Installation für den RMS-Freigabe für Office 2010 und Active Directory RMS

1.  Erfolg des Befehls Setup.exe auf den einzelnen Computern überprüfen suchen Sie nach der Protokolldatei in der *%temp%\RMS_installer_ &lt; Guid &gt;* Ordner, und den Exitcode zu identifizieren.

    Eine erfolgreiche Installation hat einen Exitcode von 0 und jede andere Zahl gibt eine fehlerhafte Installation.

    Name der Protokolldatei Beispiel: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Erfolg des Befehls aadrmprep.exe auf jedem Computer überprüfen suchen Sie nach den folgenden Text in der Protokolldatei für die Installation: **aadrmprep.exe wurde mit dem Status Erfolg beendet**

    > [!NOTE]
    > In manchen Fällen kann diese Installation zweimal ausgeführt werden. das erste Vorkommen schlägt fehl, und die zweite ist erfolgreich.

    Wenn Sie Änderungen an der Registrierung manuell zu überprüfen, die mit diesem Tool können möchten, sind sie wie folgt:

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="Urn: HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="Urn: HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @= "&lt; Zertifizierung Url &gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser = "&lt; Default_user &gt;"

##### Überprüfen der erfolgreichen Installation für die RMS-Freigabe, Anwendung und Office-add-in nur

1.  Zum Erfolg des Befehls Setup_ipviewer.exe zu überprüfen, suchen Sie nach den folgenden Text in der Protokolldatei: **Installationsstatus Erfolg oder Fehler: 0**

    Beispiel für Zeilen aus einer erfolgreichen Installation:

    **MSI (s) (F0:B8) [14:19:57:854]: Produkt: Active Directory Rights Management Services Client 2.1 – Installation wurde erfolgreich abgeschlossen.**

    **MSI (s) (F0:B8) [14:19:57:854]: Windows Installer installiert das Produkt. Produktname: Active Directory Rights Management Services Client 2.1. Produktversion: 1.0.1179.1. Produktsprache: 1033. Hersteller: Microsoft Corporation. Installationsstatus Erfolg oder Fehler: 0.**

2.  Erfolg des Office-add-Ins, auf jedem Computer überprüfen suchen Sie nach den folgenden Text in der Protokolldatei für die Installation: **Installationsstatus Erfolg oder Fehler: 0**

    Beispiel für Zeilen aus einer erfolgreichen Installation:

    **MSI (s) (9C: 88) [18:49:04:007]: Produkt: Microsoft RMS Office Add-Ins - Installation erfolgreich abgeschlossen wurde.**

    **MSI (s) (9C: 88) [18:49:04:007]: Windows Installer installiert das Produkt. Produktname: Microsoft RMS-Office-Add-Ins. Produktversion: 1.0.7. Produktsprache: 1033. Hersteller: Microsoft. Installationsstatus Erfolg oder Fehler: 0.**

### <a name="BKMK_uninstallscripted"></a>Deinstallieren von Befehlen
Nicht alle der Befehle für die Installation, die für diese Bereitstellung erforderlich sind unterstützen einen Deinstallation-Befehl. Können Sie die AD RMS-Client und die gemeinsame Nutzung von Anwendung deinstallieren, und Sie können das Office-add-in deinstallieren. Verwenden Sie die folgenden Befehle aus, um diese Elemente zu deinstallieren.

##### So deinstallieren Sie die AD RMS-Client und dem RMS-Freigabe

-   Verwenden Sie die folgenden Befehle ein:

    -   Für 64-Bit-Windows:

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   Für 32-Bit-Windows:

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

##### So deinstallieren Sie das Office-add-in

-   Verwenden Sie die folgenden Befehle ein:

    -   Für 64-Bit-Version von Office:

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   Für 32-Bit-Version von Office:

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

### <a name="BKMK_SuppressAutomaticUpdates"></a>Unterdrücken automatische updates
Standardmäßig werden Benutzer benachrichtigt, wenn es eine neuere Version des RMS-freigabeanwendung ist und aufgefordert, sie herunterzuladen. Sie können diese Benachrichtigung unterdrücken, indem Sie den folgenden Registrierungsschlüssel bearbeiten:

1.  Navigieren Sie zu **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** und sofern nicht bereits vorhanden ist, erstellen Sie einen neuen Schlüssel mit dem Namen **RmsSharingApp**.

2.  Wählen Sie **RmsSharingApp**, erstellen Sie einen neuen DWORD-Wert der **AllowUpdatePrompt**, und legen Sie den Wert **0**.

Da die gemeinsame Nutzung von RMS-Anwendung nicht von WSUS unterstützt wird, können Sie das folgende Verfahren, neuen Versionen des RMS-Freigabe-Anwendung vor der Bereitstellung für alle Benutzer zu testen:

1.  Führen Sie auf allen Benutzercomputern ein Skript aus, um automatische Updates zu unterdrücken. Führen Sie auf den Computern, die Administratoren verwenden, um neue Versionen zu testen dieses Skript nicht.

2.  Wenn eine neue Version verfügbar ist, werden Administratoren herunterladen und testen.

3.  Wenn Tests sind abgeschlossen, und alle Probleme gelöst, die neueste Version allen Benutzern bereitstellen, indem Sie mit der automatischen Bereitstellung in diesem Handbuch.

### <a name="BKMK_DocumentTracking"></a>Nur Azure RMS: Konfigurieren von Dokument-Überwachung
Wenn Sie haben ein [Abonnement, das Dokument Tracking unterstützt](https://technet.microsoft.com/en-us/dn858608), dem Nachverfolgen von Standort ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert.  Dokumenten verfolgt zeigt Informationen wie z. B. e-Mail-Adressen der Personen, die geschützte Dokumente zugreifen möchten, die von Benutzern gemeinsam verwendet, wenn diese Benutzer versuchen, und deren Standort zugreifen. Bei Anzeige dieser Informationen in Ihrer Organisation aufgrund von datenschutzanforderungen nicht zulässig ist, können Sie deaktivieren, dass Zugriff auf das Dokument, das Verfolgen der Website mithilfe der  [Deaktivieren AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032) Cmdlet. Zugriff auf die Site zu einem beliebigen Zeitpunkt können Sie erneut aktivieren, mit der [Aktivieren AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037), und Sie können überprüfen, ob Zugriff derzeit aktiviert oder deaktiviert werden, mit [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037).

 Um diese Cmdlets auszuführen, benötigen Sie mindestens Version **2.3.0.0 unterstützt** des Azure RMS-Moduls für Windows PowerShell.  Installationshinweise finden Sie unter [Installieren von Windows PowerShell für Azure Rights Management](https://technet.microsoft.com/library/jj585012.aspx).

> [!TIP]
> Wenn Sie zuvor heruntergeladen und das Modul installiert haben, überprüfen Sie die Versionsnummer durch ausführen: `(Get-Module aadrm –ListAvailable).Version`

die folgenden URLs werden zum Nachverfolgen von Dokument und muss zulässig sein (z. B. hinzufügen zu Ihren vertrauenswürdigen Sites wenn Sie Internet Explorer mit erhöhter Sicherheit verwenden):

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > dieser URL ist für Bing maps.

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

### <a name="BKMK_FederatedDomains"></a>Nur AD RMS: Unterstützung für mehrere e-Mail-Domänen innerhalb der Organisation
Wenn Sie AD RMS verwenden und Benutzer in Ihrer Organisation mehrere e-Mail-Domänen, müssen möglicherweise aufgrund einer Fusion oder Übernahme, den folgenden Registrierungsschlüssel bearbeiten:

1.  Navigieren Sie zu **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** und sofern nicht bereits vorhanden ist, erstellen Sie einen neuen Schlüssel mit dem Namen **RmsSharingApp**.

2.  Wählen Sie **RmsSharingApp**, erstellen Sie einen neuen mehrteiligen Zeichenfolgenwert namens **FederatedDomains**, und fügen Sie die Domänen und alle Unterdomänen, die Ihre Organisation verwendet. Platzhalter werden nicht unterstützt.

    Beispiel: das Unternehmen Coho Vineyard &amp; Winery verfügt über eine standard-e-Mail-Domäne des **cohovineyardandwinery.com**, aber durch Fusionen, verwenden sie auch die e-Mail-Domänen **cohowinery.com**, **eastcoast.cohowinery.com**, und **cohovineyard.com**. Für die **FederatedDomains** Wert der Administrator gibt: **cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

Wenn Sie nicht diese Änderung Registrierung vornehmen, Benutzer möglicherweise nicht für die Nutzung der Inhalte, die von anderen Benutzern in ihrer Organisation geschützt wurde. Diese Bearbeitung der Registrierung ist nicht erforderlich, wenn Sie Azure RMS verwenden.

## <a name="BKMK_AdminOverview"></a>Für die Microsoft Rights Management-freigabeanwendung – technische Übersicht
Die Microsoft Rights Management-freigabeanwendung ist eine optional herunterladbare Anwendung für Microsoft Windows und andere Plattformen, die Folgendes enthält:

-   Einer einzelnen Datei oder Bulk Schutz mehrerer Dateien sowie alle Dateien in einem ausgewählten Ordner.

-   Vollständige Unterstützung für den Schutz eines beliebigen Typs und einen integrierten Viewer für häufig verwendeten Text und Bild-Dateitypen.

-   Allgemeiner Schutz für Dateien, die RMS-Schutz nicht unterstützen.

-   Vollständige Interoperabilität mit Dateien, die mit Office Information Rights Management (IRM) geschützt.

-   Vollständige Interoperabilität mit PDF-Dateien, die mit SharePoint, FCI und unterstützten PDF-Erstellungstools geschützt.

Die Microsoft Rights Management-Freigabe-Anwendung verwendet die neue [AD RMS-Client 2.1 Runtime](http://www.microsoft.com/download/details.aspx?id=38396). Mithilfe von bietet die Funktionalität von AD RMS 2.1, die Microsoft Rights Management-freigabeanwendung Endbenutzer einfachen Schutz und den Verbrauch.

Mit der Version vom Oktober 2013 von RMS können systemintern Schützen von Dokumenten mithilfe von Office 2010 und anderen Personen in einem anderen Unternehmen, das dann diese nutzen kann, mithilfe von Azure RMS senden. Darüber hinaus mit dieser Version können bei Verwendung von AD RMS in Kryptografiemodus 2, mithilfe von RMS für Einzelpersonen und Nutzung von Inhalten von Personen in einem anderen Unternehmen, das Azure RMS verwendet. Weitere Informationen zu den Kryptografiemodus 2, finden Sie unter [AD RMS-Kryptografiemodi](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx).

### <a name="BKMK_LevelsofProtection"></a>Schutz – systemeigen und generisch
Microsoft Rights Management-freigabeanwendung unterstützt den Schutz auf zwei unterschiedlichen Ebenen, wie in der folgenden Tabelle beschrieben.

|Art des Schutzes|Native|Generisch|
|--------------------|----------|-------------|
|Beschreibung|Für Text, Bild, Microsoft Office (Word, Excel, PowerPoint) Dateien, PDF-Dateien und andere Anwendung Dateitypen, die AD RMS zu unterstützen, bietet einheitlicher Schutz einen hohen Grad an Sicherheit, die sowohl Verschlüsselung umfasst und Erzwingung von rechten (Berechtigungen).|Für alle anderen Programme und Dateitypen schützt generischen Schutz, der sowohl den Dateityp "pFile" und die Authentifizierung um zu überprüfen, ob ein Benutzer berechtigt ist, öffnen Sie die Datei mit Datei-Kapselung enthält.|
|Schutz|Dateien werden vollständig verschlüsselt und Schutz wird erzwungen, auf folgende Weise:<br /><br />-   Bevor geschützter Inhalt gerendert wird, muss eine erfolgreiche Authentifizierung für diejenigen, die auftreten, erhalten die Datei per e-Mail oder über Berechtigungen für Dateien oder Freigabe Zugriff darauf gewährt.<br />-   Benutzerrechte und Richtlinien, die vom Besitzer Inhalts festgelegt, wenn Dateien geschützt sind sind darüber hinaus in der vollständig erzwungen, wenn der Inhalt in IP-Viewer (für geschützte Text- und Image-Dateien) oder die zugeordnete Anwendung (für alle anderen unterstützten Dateitypen) gerendert wird.|Dateischutz wird auf folgende Weise erzwungen:<br /><br />-   Bevor geschützter Inhalt gerendert wird, muss eine erfolgreiche Authentifizierung erfolgen für diejenigen, die autorisiert sind, um die Datei zu öffnen und die Zugriffsrechte darauf. Wenn die Autorisierung fehlschlägt, wird die Datei nicht geöffnet werden.<br />-   Benutzerrechte und Richtlinien festlegen, indem Sie der Besitzer des Inhalts werden angezeigt, um autorisierte Benutzer der Richtlinie vorgesehene Verwendung zu informieren.<br />-   Tritt auf, Überwachungsprotokoll der autorisierten Benutzer öffnen und auf Dateien zugreifen, jedoch keine Nutzungsrechte erzwungen werden, nicht unterstützt Applications.|
|Standardwert für Dateitypen|Dies ist die Standardebene der Schutz für die folgenden Dateitypen:<br /><br />-   Text- und Image-Dateien<br />-   Microsoft Office (Word, Excel, PowerPoint)-Dateien<br />-   Portable Document Format (PDF)<br /><br />Weitere Informationen finden Sie im folgenden Abschnitt [Supported file types and file name extensions](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_SupportFileTypes).|Dies ist der Standardschutz für alle anderen Dateitypen (z. B. .vsdx, RTF und So weiter) über vollständigen Schutz nicht unterstützt.|
Sie können die Standard-Schutzebene ändern, die die gemeinsame Nutzung von RMS-Anwendung gilt. Sie können die Standardebene der systemeigenen generisch, vom generischen in systemeigenen Code ändern und sogar verhindern die RMS-Freigabe aus dem Schutz anwenden. Weitere Informationen finden Sie im Abschnitt [Changing the default protection level of files](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_ChangeDefaultProtection) dieses Themas.

### <a name="BKMK_SupportFileTypes"></a>Unterstützte Dateitypen und Dateinamenerweiterungen
Die folgende Tabelle enthält die Dateitypen, die standardmäßig von Microsoft Rights Management-freigabeanwendung unterstützt werden. Für diese Dateitypen wird die ursprünglichen Erweiterung geändert, wenn systemeigene geschützt angewendet wird, und diese Dateien schreibgeschützt sind.

Darüber hinaus bei die RMS-Freigabe systemintern eine Word, Excel oder PowerPoint-Datei, die den Benutzer schützt durch die gemeinsame Nutzung zu schützen, diese Aktion erstellt automatisch eine zweite Datei, die eine Kopie des Originals mit demselben Namen, jedoch mit einem **.ppdf** Dateinamenerweiterung ¹. Diese Version der Datei wird sichergestellt, dass der Empfänger, die die RMS-Freigabe installieren immer die Datei öffnen können, die systemeigenen Schutz angewendet wurde.

Für Dateien, die i. d. r. geschützt sind, wird die ursprünglichen Erweiterung immer in "pFile" geändert.

> [!WARNING]
> Wenn Sie keine Firewalls, Webproxys oder Sicherheitssoftware, die prüfen und nach Dateinamenerweiterungen Maßnahmen ergreifen, müssen Sie neu konfigurieren, um diese neue Dateinamenerweiterungen zu unterstützen.

|Ursprüngliche Erweiterung|RMS-geschützten Erweiterung|
|-----------------------------|-------------------------------|
|.txt|.ptxt|
|XML|.pxml|
|JPG|.pjpg|
|JPEG|.ppng|
|PDF|.ppdf|
|PNG|.ppng|
|TIFF|.ptiff|
|BMP|.pbmp|
|GIF|.pgif|
|.giff|.pgiff|
|jpe|.pjpe|
|.JFIF|.pjfif|
|.jif|.pjif|
|.JT|.PJT|
¹ PDF-Rendering Powered by Foxit. Copyright © 2003-2014 by Foxit Corporation.

In der folgende Tabelle werden die Dateitypen aufgeführt, die systemeigene Unterstützung für die gemeinsame Nutzung von Microsoft Rights Management-Anwendung in Microsoft Office 2016, Office 2013 und Office 2010. Für diese Dateien bleibt die Erweiterung nach von RMS geschützt ist.

|Von Office unterstützte Dateitypen|Von Office unterstützte Dateitypen|
|--------------------------------------|--------------------------------------|
|doc<br /><br />.docm<br /><br />.docx<br /><br />dot<br /><br />dotm<br /><br />dotx<br /><br />.potm<br /><br />.potx<br /><br />PPS<br /><br />.ppsm<br /><br />ZIP<br /><br />PPT<br /><br />pptm|PPTX<br /><br />thmx<br /><br />.xla<br /><br />xlam<br /><br />.xls<br /><br />.xlsb<br /><br />.xlt<br /><br />xlsm<br /><br />.xlsx<br /><br />.xltm<br /><br />xltx<br /><br />XPS|

### <a name="BKMK_ChangeDefaultProtection"></a>Die Standard-Schutzebene von Dateien
Sie können ändern, wie die RMS-Freigabe Dateien schützt, durch Bearbeiten der Registrierung. Beispielsweise können Sie Dateien erzwingen, die i. d. r. durch die gemeinsame Nutzung von RMS-Anwendung geschützt werden einheitlichen Schutz unterstützen.

Gründen, warum Sie dies tun möchten:

-   Sicherstellen, dass alle Benutzer die Datei auf ihren mobilen Geräten öffnen können.

-   Um sicherzustellen, dass alle Benutzer die Datei öffnen können, wenn sie nicht über eine Anwendung verfügen, die systemeigenen Schutz unterstützt.

-   Um die Sicherheitssysteme aufzunehmen, die Maßnahmen auf Dateien durch ihre Erweiterung und neu konfiguriert werden kann, um die Erweiterung "pFile" aufzunehmen, aber kann nicht neu konfiguriert werden, um mehrere Dateinamenerweiterungen für den einheitlichen Schutz zu ermöglichen.

Auf ähnliche Weise können Sie erzwingen, die RMS-Freigabe Anwendung einheitlichen Schutz auf Dateien, die in der Standardeinstellung generischen Schutz angewendet hätten angewendet wird. Dies ist möglicherweise geeignet, wenn eine Anwendung, die RMS-APIs – z. B. unterstützt, eine Line-of-Business-Anwendung, die durch Ihre internen Entwickler geschrieben oder eine Anwendung, die von einem unabhängigen Softwareanbieter (ISV) erworben haben.

Sie können auch erzwingen, die RMS-Freigabe, den Schutz der Dateien zu blockieren (nicht systemeigenen oder generischen Schutz anwenden). Dies kann z. B. erforderlich, wenn man eine automatische Anwendung oder ein Dienst, der eine bestimmte Datei, um seinen Inhalt verarbeiten öffnen kann. Wenn Sie den Schutz für einen Dateityp blockieren, können Benutzer keine RMS-Freigabe, um eine Datei zu schützen, die diesen Dateityp wurde. Wenn sie versuchen, eine Meldung, dass der Administrator durch Schutz verhindert wurde und müssen sie ihre Aktion zum Schutz der Datei Abbrechen angezeigt.

Um die RMS-Freigabe anzuwendende generischen Schutz für alle Dateien, die in der Standardeinstellung einheitlichen Schutzes hätte zu konfigurieren, bearbeiten Sie die folgenden Registrierung:

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: Erstellen Sie einen neuen Schlüssel mit dem Namen **&#42;**.

    Diese Einstellung gibt Dateien mit jeder beliebigen Erweiterung.

2.  In der neu hinzugefügten Schlüssel des **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\ &#42;**, erstellen Sie einen neuen Zeichenfolgenwert (REG_SZ) mit dem Namen **Verschlüsselung** die den Wert des hat **Pfile**.

    Diese Einstellung führt die RMS-Freigabe generischen Schutz der Anwendung anwenden.

Diese beiden Einstellungen dazu führen, dass die RMS-Freigabe Anwendung anwenden generischen Schutz für alle Dateien mit der Erweiterung. Wenn dies Ihr Ziel ist, ist keine weitere Konfiguration erforderlich. Sie können jedoch Ausnahmen für bestimmte Dateitypen definieren, so, dass sie weiterhin systemintern geschützt sind. Zu diesem Zweck müssen Sie drei zusätzliche Registrierungsinformationen Bearbeitungsvorgänge für jeden Dateityp:

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: Fügen Sie einen neuen Schlüssel mit dem Namen von der Erweiterung (ohne vorherigen Punkt).

    Z. B. für Dateien mit einer DOCX-Erweiterung, erstellen Sie einen Schlüssel namens **DOCX**.

2.  In der neu hinzugefügten Datei Typ-Schlüssel (z. B. **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**), erstellen Sie einen neuen DWORD-Wert namens **AllowPFILEEncryption** hat, die den Wert **0**.

3.  In der neu hinzugefügten Datei Typ-Schlüssel (z. B. **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**), erstellen Sie einen neuen Zeichenfolgenwert mit dem Namen **Verschlüsselung** hat, die den Wert **systemeigene**.

Durch diese Einstellungen sind alle Dateien generisch mit Ausnahme der Dateien mit der Erweiterung einer DOCX geschützt, die systemintern durch die gemeinsame Nutzung von RMS-Anwendung geschützt werden.

Wiederholen Sie diese drei Schritte für andere Dateitypen, die als Ausnahmen definiert werden, da einheitlichen Schutz unterstützen und Sie nicht möchten, werden i. d. r. durch die gemeinsame Nutzung von RMS-Anwendung geschützt werden soll.

Sie können bearbeiten ähnlich wie die Registrierung für andere Szenarien durch Ändern des Werts der **Verschlüsselung** Zeichenfolge, die die folgenden Werte unterstützt:

-   **Pfile**: Allgemeiner Schutz

-   **Systemeigene**: systemeigener Schutz

-   **Aus**: Schutz blockieren

## Siehe auch
[Rights Management freigabeanwendung – Benutzerhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-user-guide.md)
[Curah!: wie RMS schützt das alle Dateitypen – mit der RMS-Freigabe-app](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app)

