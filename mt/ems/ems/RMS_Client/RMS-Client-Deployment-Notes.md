---
title: Notes-RMS-Client-Bereitstellung
ms.custom: na
ms.date: 03/02/2016
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f
robots: noindex,nofollow
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
# Notes-RMS-Client-Bereitstellung
Die Rights Management\-Dienst\-Client (RMS\-Client) Version 2 ist auch bekannt als MSIPC\-Client. Er ist Software für Windows\-Computer, die Kommunikation mit Microsoft Rights Management Services\-lokal oder in der Cloud, den Zugriff auf und Verwendung von Informationen schützen, während es über Clientanwendungen und Geräten fließen, innerhalb der Grenzen des Unternehmens oder nicht den verwalteten Grenzen. Zusätzlich zu den im Lieferumfang der [Rights Management-freigabeanwendung für Windows](https://technet.microsoft.com/library/dn919648.aspx), steht der RMS\-Client [als ein optionaler Download](http://www.microsoft.com/download/details.aspx?id=38396) können mit Bestätigung und seine Zustimmung Lizenz frei verteilt werden mit Software von Drittanbietern, um Clients zu schützen und Nutzung von Inhalten, die von Rights Management Services geschützt wurde.

Dieses Dokument beinhaltet die folgenden Abschnitte:

-   [Redistributing the RMS Client](#BKMK_RedistributeInstaller)

-   [Installing the RMS Client](#BKMK_InstallClient)

-   [Questions and Answers about the RMS Client](#BKMK_QA)

-   [RMS Client Settings](#BKMK_Settings)

-   [AD RMS Only: Limiting the RMS Client to Use Trusted AD RMS Servers](#BKMK_UsingTrustedServers)

-   [RMS Service Discovery](#BKMK_ServiceDiscovery)

## <a name="BKMK_RedistributeInstaller"></a>Neuverteilen von RMS\-Client
Der RMS\-Client kann frei verteilt und mit anderen Systemen und IT\-Lösungen gebündelt. Wenn Sie ein Anwendungsentwickler oder Lösungsanbieter und den RMS\-Client neu verteilen möchten, haben Sie zwei Optionen:

-   Empfohlen: Das RMS\-Client\-Installationsprogramm in die Installation Ihrer Anwendung einbetten und es im unbeaufsichtigten Modus ausgeführt werden (die **\/quiet** Switch, die im nächsten Abschnitt beschrieben).

-   Stellen Sie dem RMS\-Client eine Voraussetzung für die Anwendung. Mit dieser Option müssen Sie möglicherweise bereitstellen für Benutzer mit zusätzlichen Anleitungen zu erhalten, installieren und ihre Computer mit dem Client aktualisieren, damit Ihre Anwendung verwendet werden kann.

## <a name="BKMK_InstallClient"></a>Installieren des RMS\-Clients
Der RMS\-Client befindet sich in einer ausführbaren Installer\-Datei mit dem Namen **setup\_msipc\_***&lt; Arch &gt;***.exe**, wobei *&lt; Arch &gt;* ist entweder **x86** (für 32\-Bit\-Client\-Computer) oder **x64** (für 64\-Bit\-Client\-Computern). Das Installationspaket für 64\-Bit (x 64) wird sowohl eine 32\-Bit\-Laufzeit ausführbare Datei für die Kompatibilität mit 32\-Bit\-Anwendung, die auf einer 64\-Bit\-Betriebssystem\-Installation ausführen, als auch eine ausführbare Datei für die Unterstützung von systemeigenen 64\-Bit\-Anwendung 64\-Bit\-Laufzeit installiert. Das Installationsprogramm für die 32\-Bit (x 86) wird auf einer 64\-Bit\-Windows\-Installation nicht ausgeführt werden.

> [!NOTE]
> Sie benötigen die erhöhte Berechtigungen für den RMS\-Client, wie z. B. ein Mitglied der Gruppe "Administratoren" auf dem lokalen Computer zu installieren.

Sie können den RMS\-Client installieren, mithilfe einer der folgenden Installationsmethoden:

-   **Unbeaufsichtigten Modus.** Mithilfe der **\/quiet** Wechseln im Rahmen der Befehlszeilenoptionen können Sie automatisch den RMS\-Client auf Computern installieren. Das folgende Beispiel zeigt eine automatische Installation für den RMS\-Client auf einem 64\-Bit\-Clientcomputer:

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **Im interaktiven Modus.** Alternativ können Sie den RMS\-Client installieren, mit dem GUI\-basiertes Setup\-Programm, das vom Installations\-Assistenten von RMS\-Client bereitgestellt wird. Doppelklicken Sie dazu das RMS Client Installer\-Paket (**setup\_msipc\_***&lt; Arch &gt;***.exe**) in den Ordner, zu dem es kopiert oder auf dem lokalen Computer heruntergeladen wurde.

## <a name="BKMK_QA"></a>Fragen und Antworten zu den RMS\-Client
Der folgende Abschnitt enthält häufig gestellte Fragen zu den RMS\-Client und die Antworten auf diese.

### Welche Betriebssysteme unterstützt den RMS\-Client?
Der RMS\-Client wird mit den folgenden Betriebssystemen unterstützt:

|Windows Server\-Betriebssystem|Windows\-Clientbetriebssystem|
|----------------------------------|---------------------------------|
|Windows Server 2012 R2|Windows 8.1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7 mit SP1|
|WindowsServer 2008 (nur AD RMS)|Windows Vista mit mindestens SP2 (nur AD RMS)|

### Welche Prozessoren oder Plattformen den RMS\-Client unterstützt?
Der RMS\-Client wird auf X 86\- und X 64\-computing\-Plattformen unterstützt.

### Wo ist der RMS\-Client installiert?
In der Standardeinstellung der RMS\-Client installiert ist, in %ProgramFiles%\\Active Directory Rights Management Services Client 2. &lt; niedrigere Versionsnummer &gt;.

### Welche Dateien der RMS\-Clientsoftware zugeordnet sind?
Die folgenden Dateien werden als Teil der RMS\-Clientsoftware installiert werden:

-   Datei

-   Ipcsecproc.dll

-   Ipcsecproc\_ssp.dll

-   MSIPCEvents.man

Zusätzlich zu diesen Dateien wird der RMS\-Client auch Unterstützungsdateien für multilingual User Interface (MUI) in 44 Sprachen installiert. Um unterstützten Sprachen zu überprüfen, führen Sie die Installation der RMS\-Client, und wenn die Installation abgeschlossen ist, überprüfen Sie den Inhalt der Ordner unter dem Standardpfad mehrsprachige Unterstützung.

### Ist der RMS\-Client standardmäßig enthalten, bei der Installation von eines unterstützten Betriebssystems?
Nein. Diese Version des RMS\-Clients enthalten ist, als ein optionaler Download installiert werden kann, die separat auf Computern, unterstützte Versionen von Microsoft Windows\-Betriebssystem ausführen.

### Wird der RMS\-Client von Microsoft Update automatisch aktualisiert?
Wenn Sie diesen RMS\-Client installiert, mit der Option für die unbeaufsichtigte Installation, erbt der RMS\-Client die aktuellen Einstellungen für Microsoft Update. Wenn Sie den RMS\-Client mithilfe des GUI\-basierten Setup\-Programms installiert haben, werden Sie von RMS Clientinstallations\-Assistenten aufgefordert, Microsoft Update aktivieren.

## <a name="BKMK_Settings"></a>RMS\-Clienteinstellungen
Der folgende Abschnitt enthält Informationen über den RMS\-Client. Diese Informationen sind möglicherweise hilfreich, wenn Probleme mit Programme oder Dienste, die den RMS\-Client verwenden.

> [!NOTE]
> Einige Einstellungen, hängt davon ab, ob die RMS\-fähige Anwendung als Modus\-Clientanwendung (z. B. Microsoft Word und Outlook oder die RMS\-Freigabe) oder Server\-Modus\-Anwendung (z. B. SharePoint und Exchange) ausgeführt wird.  In den folgenden Tabellen werden diese Einstellungen als identifiziert **Clientmodus** und **Servermodus**, bzw..

### Die RMS\-Client\-Speicher, in dem auf den Clientcomputern Lizenzen
Der RMS\-Client Lizenzen auf dem lokalen Datenträger gespeichert und werden auch einige Informationen in der Windows\-Registrierung zwischengespeichert.

|Beschreibung|Client\-Modus\-Pfade|Serverpfad\-Modus|
|----------------|------------------------|---------------------|
|Lizenz\-Speicherort|%LocalAppData%\\Microsoft\\MSIPC|%ALLUSERSPROFILE%\\Microsoft\\MSIPC\\Server\\*&amp;lt; SID &amp;gt;*\\|
|Speicherort der Vorlage|%LocalAppData%\\Microsoft\\MSIPC\\Templates|%ALLUSERSPROFILE%\\Microsoft\\MSIPC\\Server\\Templates\\*&amp;lt; SID &amp;gt;*\\|
|Registrierungsschlüssel|HKEY\_CURRENT\_USER<br /> \\Software<br /> \\Classes<br /> \\Local Einstellungen<br /> \\Software<br /> \\Microsoft<br /> \\MSIPC|HKEY\_CURRENT\_USER<br /> \\Software<br /> \\Microsoft<br /> \\MSIPC<br /> \\Server<br /> \\*&amp;lt; SID &amp;gt;*|

> [!NOTE]
> *&lt; SID &gt;* ist die sichere\-ID (SID) für das Konto, unter dem die Server\-Anwendung ausgeführt wird. Wenn die Anwendung unter dem integrierten Netzwerkdienstkonto ausgeführt wird, z. B. ersetzen *&lt; SID &gt;* mit dem Wert, der die bekannte SID für dieses Konto (S\-1\-5\-20).

### Windows\-Registrierungseinträge für den RMS\-Client
Sie können Windows\-Registrierungsschlüssel festlegen oder Ändern von einigen Clientkonfigurationen RMS verwenden. Beispielsweise sollten Sie als Administrator für die RMS\-fähige Anwendung, die mit AD RMS\-Server kommunizieren Updatedienst der Enterprise (Überschreiben der AD RMS\-Server, die derzeit für die Veröffentlichung ausgewählt ist) abhängig vom aktuellen Speicherort des Clientcomputers, innerhalb Ihrer Active Directory\-Topologie. Oder möglicherweise möchten RMS\-Protokollierung auf dem Client\-Computer zur Problembehandlung bei einem Problem mit einer RMS\-fähige Anwendung zu aktivieren. Verwenden Sie in der folgende Tabelle, um die Registrierungseinträge zu identifizieren, die Sie für den RMS\-Client ändern können.

|Aufgabe|Einstellung|
|-----------|---------------|
|Nur AD RMS: Aktualisieren Sie den Speicherort des Unternehmens für einen Clientcomputer|Aktualisieren Sie die folgenden Registrierungsschlüssel:<br /><br />-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC\\ServiceLocation\\EnterpriseCertification<br />    REG\_SZ: Standard<br />    **Wert:**&amp;lt; http oder Https &amp;gt; :\/\/ *RMS\_Cluster\_Name*\/\_wmcs\/Zertifizierung<br />-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC\\ServiceLocation\\EnterprisePublishing<br />    REG\_SZ: Standard<br />    **Wert:** &amp;lt; http oder Https &amp;gt; :\/\/ *RMS\_Cluster\_Name*\/\_wmcs\/Licensing|
|Aktivieren und Deaktivieren der Protokollierung|Aktualisieren Sie den folgenden Registrierungsschlüssel:<br /><br />-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC<br />    REG\_DWORD: Trace<br />    **Wert:** 1 Aktivierung tracing, 0, so deaktivieren Sie die Protokollierung (Standard)|
|So ändern Sie die Häufigkeit in Tagen zum Aktualisieren von Vorlagen|Die folgenden Werte angeben, wie häufig Vorlagen werden auf dem Computer des Benutzers aktualisiert werden, wenn der Wert der TemplateUpdateFrequencyInSeconds nicht festgelegt ist.  Wenn keiner dieser Werte festgelegt werden, ist das Standardaktualisierungsintervall für Applikationen mit der RMS\-Client (Version 1.0.1784.0) zum Herunterladen von Vorlagen 1 Tag. Versionen vor dies über einen Standardwert von 7 Tagen verfügen.<br /><br />**Clientmodus:**<br /><br />-   HKEY\_CURRENT\_USER\\Software\\Classes\\Local Settings\\Software\\Microsoft\\MSIPC<br />    REG\_DWORD: TemplateUpdateFrequency<br />    **Wert:** ein Ganzzahlwert, der die Anzahl der Tage (mindestens 1) zwischen Downloads angibt.<br /><br />**Server\-Modus:**<br /><br />-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC\\Server\\*&amp;lt; SID &amp;gt;*<br />    REG\_DWORD: TemplateUpdateFrequency<br />    **Wert:** ein Ganzzahlwert, der die Anzahl der Tage (mindestens 1) zwischen Downloads angibt.|
|So ändern Sie die Häufigkeit in Sekunden zum Aktualisieren von Vorlagen **Important:** Wenn dies angegeben ist, wird der Wert zum Aktualisieren von Vorlagen in Tagen ignoriert. Geben Sie einen oder anderen, nicht beides.|Die folgenden Werte angeben, wie häufig Vorlagen auf dem Computer des Benutzers aktualisiert werden. Wenn dieser Wert oder den Wert so ändern Sie die Häufigkeit in Tagen (TemplateUpdateFrequency) nicht festgelegt ist, ist das Standardaktualisierungsintervall für Applikationen mit der RMS\-Client (Version 1.0.1784.0) zum Herunterladen von Vorlagen 1 Tag. Versionen vor dies über einen Standardwert von 7 Tagen verfügen.<br /><br />**Clientmodus:**<br /><br />-   HKEY\_CURRENT\_USER\\Software\\Classes\\Local Settings\\Software\\Microsoft\\MSIPC<br />    REG\_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Wert:** ein Ganzzahlwert, der die Anzahl der Sekunden (mindestens 1) zwischen Downloads angibt.<br /><br />**Server\-Modus:**<br /><br />-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC\\Server\\*&amp;lt; SID &amp;gt;*<br />    REG\_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Wert:** ein Ganzzahlwert, der die Anzahl der Sekunden (mindestens 1) zwischen Downloads angibt.|
|Nur AD RMS: Herunterladen der Vorlagen sofort bei der nächsten Veröffentlichung Anforderung|Test\-und Produkttests sollten Sie den RMS\-Client Herunterladen der Vorlagen so bald wie möglich. Zu diesem Zweck den folgenden Registrierungsschlüssel entfernen und der RMS\-Client wird Vorlagen sofort bei der nächsten Veröffentlichung Anforderung statt der Einstellung TemplateUpdateFrequency in der Registrierung angegebene Zeit warten:<br /><br />-   HKEY\_CURRENT\_USER\\Software\\Classes\\Local Settings\\Software\\Microsoft\\MSIPC\\ &amp;lt; Servername &amp;gt; \\Template **Note:** &amp;lt; Servername &amp;gt; konnte extern (corprights.contoso.com) und interne (Corprights) URLs sowohl daher zwei verschiedene Einträge vorhanden sein.|
|Nur AD RMS: Aktivieren der Unterstützung für Verbundauthentifizierung|Wenn der RMS\-Client\-Computer mit einem AD RMS\-Cluster mit einer Vertrauensstellung verbunden ist, müssen Sie den Startbereich Föderation konfigurieren.<br /><br />-   HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSIPC\\Federation<br />    REG\_SZ: FederationHomeRealm<br />    **Wert:** der Wert dieses Registrierungseintrags ist den uniform Resource Identifier (URI) für den Verbunddienst (z. B. "https:\/\/fs\-01.contoso.com").|
|Nur AD RMS: zur Unterstützung von Verbundservern Partner, die formularbasierte Authentifizierung für Benutzereingaben erfordern|Standardmäßig der RMS\-Client im unbeaufsichtigten Modus arbeitet, und eine Benutzereingabe ist nicht erforderlich. Partner\-Verbundserver, können jedoch für die erforderlich ist, z. B. wie über die formularbasierte Authentifizierung Benutzereingabe konfiguriert werden. In diesem Fall müssen Sie den RMS\-Client konfigurieren, damit die Verbundauthentifizierung wird in einem Browserfenster angezeigt, und der Benutzer wird zur Authentifizierung heraufgestuft unbeaufsichtigten Modus zu ignorieren.<br /><br />-   HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSIPC\\Federation<br />    REG\_DWORD: EnableBrowser **Note:** Wenn der Verbundserver für die formularbasierte Authentifizierung konfiguriert ist, ist dieser Schlüssel erforderlich. Wenn der Verbundserver Verwendung der integrierten Windows\-Authentifizierung konfiguriert ist, ist dieser Schlüssel nicht erforderlich.|
|Nur AD RMS: ILS\-Dienst Verbrauch blockieren|Standardmäßig der RMS\-Client ermöglicht es, verarbeitende Inhalt durch den ILS\-Dienst geschützt, aber Sie können den Client für diesen Dienst blockieren, indem Sie den folgenden Registrierungsschlüssel konfigurieren. Wenn dieser Registrierungsschlüssel festgelegt ist, blockiert den ILS\-Dienst, werden jeder Versuch, öffnen und die Nutzung von Inhalten durch den ILS\-Dienst geschützt folgende Fehlermeldung zurück:<br />HRESULT\_FROM\_WIN32(ERROR\_ACCESS\_DISABLED\_BY\_POLICY)<br /><br />-   HKEY\_CURRENT\_USER\\Software\\Classes\\Local Settings\\Software\\Microsoft\\MSIPC<br />    REG\_DWORD: **DisablePassportCertification**<br />    **Wert:** 1 ILS\-Verbrauch, 0 ILS\-Verbrauch (Standard) zu blockieren.|

### Verwalten der Verteilung von Vorlagen für den RMS\-Client
Vorlagen erleichtern Benutzern und Administratoren das Rights Management\-Schutz schnell anwenden und der RMS\-Client automatisch heruntergeladen Vorlagen aus der RMS\-Server oder Dienst, wenn Sie die Vorlagen im folgenden Ordner abgelegt, der RMS\-Client nicht Vorlagen von seinem Standardspeicherort und Laden Sie stattdessen die Vorlagen, die Sie in diesem Ordner gespeichert haben. Der RMS\-Client möglicherweise weiterhin Vorlagen von anderen verfügbaren RMS\-Server herunterladen.

**\-Modus:** %localappdata%\\Microsoft\\MSIPC\\UnmanagedTemplates

**Servermodus:** %allusersprofile%\\Microsoft\\MSIPC\\Server\\UnmanagedTemplates\\*&lt; SID &gt;*

Wenn Sie diesen Ordner verwenden, gibt es keine spezielle Namenskonvention, die erforderlich sind, außer dass die Vorlagen von dem RMS\-Server ausgestellt werden sollten, oder \-Dienst, und sie die XML\-Erweiterung müssen ist. Beispielsweise sind Contoso\-Confidential.xml "oder" Contoso\-ReadOnly.xml gültige Namen.

## <a name="BKMK_UsingTrustedServers"></a>Nur AD RMS: Beschränken der RMS\-Client zu verwendenden vertrauenswürdige AD RMS\-Server
Der RMS\-Client kann mit nur bestimmte vertrauenswürdige AD RMS\-Server durch die folgenden Änderungen an der Windows\-Registrierung auf dem lokalen Computer beschränkt werden.

**Zum Aktivieren der RMS eingeschränkt vertrauenswürdigen Client für die ausschließliche Verwendung AD RMS\-Server**

-   HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSIPC\\TrustedServers\\
    REG\_DWORD: AllowTrustedServersOnly

    **Wert:** ein Wert ungleich NULL angegeben wird, werden die RMS\-Clients vertrauen nur die angegebenen Server, die in der Liste der TrustedServers und dem Azure Rights Management\-Dienst konfiguriert sind.

**Beim Hinzufügen von Mitgliedern zur Liste der vertrauenswürdigen AD RMS\-Server**

-   HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSIPC\\TrustedServers\\
    REG\_SZ: *&lt; URL\_or\_HostName &gt;*

    **Wert:** die Zeichenfolgenwerte aufgeführt, die in diesem Registrierungsschlüssel hinzugefügt kann entweder Format des DNS\-Domänennamens (z. B. **adrms.contoso.com**) oder vollständige URLs zu vertrauenswürdigen AD RMS\-Servern (z. B. **https:\/\/adrms.contoso.com**). Wenn mit die angegebene URL beginnt **https:\/\/**,  der RMS\-Client verwenden SSL oder TLS zum angegebenen AD RMS\-Server herstellen.

## <a name="BKMK_ServiceDiscovery"></a>RMS\-Dienstermittlung
RMS\-Dienstermittlung kann den RMS\-Client die RMS\-Server oder die Kommunikation zwischen vor dem Schützen von Inhalten zu überprüfen. Dienstermittlung kann auch auftreten, wenn der RMS\-Client geschützten Inhalte nutzt, aber dies weniger wahrscheinlich, dass Sie eintreten ist, da die Richtlinie angefügt, um den Inhalt, der bevorzugte RMS\-Server oder Dienst enthält und nur, wenn dies nicht erfolgreich ist der Client Dienstermittlung führen wird.

Dienstermittlung sucht zuerst nach einer lokalen Version der Verwaltung von Informationsrechten (AD RMS). Wenn dies nicht erfolgreich ist, sucht die Dienstermittlung automatisch für die cloudversion der Verwaltung von Informationsrechten (Azure RMS).

Um die Dienstermittlung für eine lokale Bereitstellung durchzuführen, prüft der RMS\-Client Folgendes:

1.  Der Windows\-Registrierung auf dem lokalen Computer: Wenn Service Discovery Settings in der Registrierung konfiguriert sind, werden diese Einstellungen zuerst getestet.  Standardmäßig werden diese Einstellungen nicht in der Registrierung konfiguriert werden.

2.  Active Directory\-Domänendiensten: Ein Domäne beigetretenen Computer fragt Active Directory ein Dienstverbindungspunkt (SCP). Wenn ein Dienstverbindungspunkt registriert ist, wird an den RMS\-Client verwendet die URL des RMS\-Servers zurückgegeben.

### Nur AD RMS: Aktivieren von serverseitigen Dienstermittlung mithilfe von Active Directory
Wenn Ihr Konto über ausreichende Berechtigungen (Organisations\-Admins und lokaler Administrator für den AD RMS\-Server) verfügt, können Sie automatisch registrieren einer ein Dienstverbindungspunkt (SCP), bei der Installation des AD RMS\-Stammserver Cluster. Wenn bereits ein Dienstverbindungspunkt in der Gesamtstruktur vorhanden ist, müssen Sie zunächst den vorhandenen Dienstverbindungspunkt löschen, bevor Sie eine neue registrieren können.

Registrieren, und löschen Sie nach der Installation von AD RMS mithilfe des folgenden Verfahrens SCP. Bevor Sie beginnen, stellen Sie sicher, dass Ihr Konto die erforderlichen Berechtigungen (Organisations\-Admins und lokaler Administrator für den AD RMS\-Server).

##### So aktivieren Sie die AD RMS\-Dienstermittlung SCP in Active Directory registrieren

1.  Öffnen Sie die Active Directory Management Services\-Konsole auf dem AD RMS\-Server:

    -   Wenn Sie Windows Server 2008 R2 oder Windows Server 2008 verwenden, klicken Sie auf **Starten**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory\-Rechteverwaltungsdienste**.

    -   Wenn Sie Windows Server 2012 R2 oder Windows Server 2012 im Server\-Manager verwenden, klicken Sie auf **Tools**, und klicken Sie dann auf **Active Directory\-Rechteverwaltungsdienste**.

2.  In der AD RMS\-Konsole mit der rechten Maustaste in des AD RMS\-Clusters, und klicken Sie dann auf **Eigenschaften**.

3.  Klicken Sie auf die **SCP** Registerkarte.

4.  Wählen Sie die **Änderung SCP** Kontrollkästchen.

5.  Wählen Sie die **SCP auf aktuellen Zertifizierungscluster festlegen** aus, und klicken Sie dann auf **OK**.

### Aktivieren der clientseitigen Dienstermittlung mithilfe der Windows\-Registrierungs
Als Alternative zur Verwendung SCP oder wo SCP nicht vorhanden ist können Sie die Registrierung auf dem Clientcomputer konfigurieren, damit der RMS\-Client auf den AD RMS\-Server finden kann.

##### So aktivieren Sie die clientseitige AD RMS\-Dienstermittlung mithilfe der Windows\-Registrierungs

1.  Öffnen Sie den Windows\-Registrierungseditor Regedit.exe:

    -   Geben Sie auf dem Clientcomputer im Fenster ausführen **regedit**, und drücken Sie dann die EINGABETASTE, um den Registrierungs\-Editor zu öffnen.

2.  Navigieren Sie im Registrierungseditor zu **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSIPC**.

    > [!IMPORTANT]
    > Wenn Sie eine 32\-Bit\-Anwendung auf einem 64\-Bit\-Computer ausführen, der Pfad werden wie folgt: 
    > **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\MSIPC**

3.  Zum Erstellen des Unterschlüssels ServiceLocation Maustaste **MSIPC**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann **ServiceLocation**.

4.  Zum Erstellen des Unterschlüssels EnterpriseCertification Maustaste **ServiceLocation**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann **EnterpriseCertification**.

5.  Um die Enterprise\-Zertifizierung URL festzulegen, doppelklicken Sie auf die **(Standard)** Wert unter der **EnterpriseCertification** Unterschlüssel, und wann die **Zeichenfolge bearbeiten** Dialogfeld angezeigt wird, für **Wert**, Typ &lt;http or https&gt;:\/\/*AD RMS\_cluster\_name*\/\_wmcs\/Certification, und klicken Sie dann auf **OK**.

6.  Zum Erstellen des Unterschlüssels EnterprisePublishing Maustaste **ServiceLocation**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann EnterprisePublishing.

7.  Um Unternehmen veröffentlichen URL festzulegen, doppelklicken Sie auf **(Standard)** , unter der **EnterprisePublishing** Unterschlüssel, und wann die **Zeichenfolge bearbeiten** Dialogfeld angezeigt wird, geben Sie **Wert** folgenden &lt;http or https&gt;:\/\/*AD RMS\_cluster\_name*\/\_wmcs\/Licensing, und klicken Sie dann auf **OK**.

8.  Schließen Sie den Registrierungs\-Editor.

Ermittlung Dienstaufrufe für AD RMS schlägt fehl, wenn der RMS\-Client ein SCP durch Abfragen von Active Directory kann nicht gefunden werden, wird Sie nicht in der Registrierung angegeben.

### Umleiten von Serverdatenverkehr\-Lizenzierung
In einigen Fällen müssen Sie Datenverkehr während der Dienstermittlung, z. B. umleiten, wenn zwei Unternehmen zusammengeführt werden und der alte Lizenzserver in einer Organisation veraltet ist und Clients müssen auf einen neuen Lizenzdaten Server umgeleitet werden. Oder der Migration von AD RMS in Azure RMS. Gehen Sie zum Aktivieren der Lizenzierung Umleitung.

##### Der RMS\-Lizenzierung Umleitung mithilfe der Windows\-Registrierungs aktivieren

1.  Öffnen Sie den Windows\-Registrierungseditor Regedit.exe:

    -   Geben Sie auf dem Clientcomputer im Fenster ausführen **regedit**, und drücken Sie dann die EINGABETASTE, um den Registrierungs\-Editor zu öffnen.

2.  Navigieren Sie im Registrierungseditor, zu einem der folgenden:

    -   Für 64\-Bit\-Version von Office auf X 64 Plattform: HKLM\\SOFTWARE\\Microsoft\\MSIPC\\Servicelocation

    -   Für 32\-Bit\-Version von Office auf X 64 Plattform: HKLM\\SOFTWARE\\Wow6432Node\\Microsoft\\MSIPC\\Servicelocation

3.  Erstellen Sie mit der rechten Maustaste einen Unterschlüssel LicensingRedirection **Servicelocation**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann **LicensingRedirection**.

4.  Zum Festlegen der Lizenzierung Umleitung Maustaste der **LicensingRedirection** Unterschlüssel select **Neu**, und wählen Sie dann **Zeichenfolgenwert**.  Für **Name**, geben Sie den vorherigen Server URL\-Lizenzierung und für **Wert** Geben Sie den neuen Server URL\-Lizenzierung.

    Z. B. zum Umleiten von einem Server in der Contoso.com\-Lizenzierung auf jeweils Fabrikam.com Sie können die folgenden Werte eingeben:

    **Name:** `https://contoso.com/_wmcs/licensing`

    **Wert:** `https://fabrikam.com/_wmcs/licensing`

    > [!NOTE]
    > Wenn der alte Lizenzserver verfügt Intranet\- und extranet\-URLs angegeben einen neuen Namen und wertezuordnung muss für beide dieser URLs unter dem Schlüssel LicensingRedirection festgelegt werden.

5.  Wiederholen Sie den vorherigen Schritt für alle Server, die umgeleitet werden müssen.

6.  Schließen Sie den Registrierungs\-Editor.

