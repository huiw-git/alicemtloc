---
title: RMS-Schutz mit Windows Server-Dateiklassifizierungsinfrastruktur (FCI)
ms.custom: na
ms.date: 03/02/2016
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9aa693db-9727-4284-9f64-867681e114c9
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
---
# RMS-Schutz mit Windows Server-Dateiklassifizierungsinfrastruktur (FCI)
Verwenden Sie diesen Anweisungsartikel und ein Skript, um den RMS\-Client (Rights Management) mit dem RMS\-Schutztool zum Konfigurieren des Ressourcen\-Managers für Dateiserver und der Dateiklassifizierungsinfrastruktur (FCI) zu verwenden.

Mit diesen Lösungen können Sie automatisch alle Dateien in einem Ordner auf einem Dateiserver unter Windows Server oder automatisch Dateien schützen, die bestimmten Kriterien entsprechen. Das sind z. B. Dateien, die vertrauliche Informationen enthalten und entsprechend klassifiziert wurden. Diese Lösung verwendet [Azure Rights Management](../../ems/AADRightsMgmt/Azure-Rights-Management.md) (Azure RMS), um die Dateien zu schützen, daher müssen Sie diese Technologie in Ihrer Organisation bereitgestellt haben.

> [!NOTE]
> Obwohl Azure RMS einen [Connector](https://technet.microsoft.com/library/dn375964.aspx) enthält, der die Dateiklassifizierungsinfrastruktur unterstützt, unterstützt diese Lösung nur systemeigenen Schutz, z. B. Office\-Dateien.
> 
> Um alle Dateitypen mit der Dateiklassifizierungsinfrastruktur zu unterstützen, müssen Sie das Windows PowerShell\-**RMS\-Schutzmodul** verwenden, wie in diesem Artikel beschrieben wird. Die RMS\-Schutz\-Cmdlets, wie z. B. die RMS\-Freigabeanwendung, unterstützen generischen Schutz und systemeigenen Schutz, was bedeutet, dass alle Dateien geschützt werden können. Weitere Informationen zu diesen verschiedenen Schutzebenen finden Sie im [Levels of protection – native and generic](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_LevelsofProtection)\-Abschnitt im [Rights Management freigabeanwendung – Administratorhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md).

Die folgenden Anleitungen gelten für Windows Server 2012 R2 oder Windows Server 2012. Wenn Sie andere unterstützte Versionen von Windows ausführen, müssen Sie möglicherweise einige Schritte aufgrund der Unterschiede zwischen der Version Ihres Betriebssystems und der in diesem Artikel beschriebenen Version anpassen.

## Voraussetzungen für Azure RMS\-Schutz mit Windows Server FCI
Voraussetzungen für diese Anweisungen:

-   Auf jedem Dateiserver, auf dem Sie den Dateiressourcen\-Manager mit Dateiklassifizierungsinfrastruktur ausführen:

    -   Sie haben den Dateiressourcen\-Manager als einen der Rollendienste für die Dateidiensterolle installiert .

    -   Sie haben einen lokalen Ordner identifiziert, der Dateien enthält, die mit Rights Management geschützt werden sollen. Beispielsweise „C:\\FileShare“.

    -   Sie haben das RMS\-Schutztool einschließlich der Voraussetzungen für das Tool (z. B. der RMS\-Client) und für Azure RMS (z. B. das Dienstprinzipalkonto) installiert. Weitere Informationen finden Sie im Thema zu [RMS-Schutz-Cmdlets](https://msdn.microsoft.com/library/azure/mt433195.aspx).

    -   Wenn Sie die Standardstufe des RMS\-Schutzes (systemeigen oder generisch) für bestimmte Dateinamenserweiterungen ändern möchten, haben Sie die Registrierung bearbeitet, wie auf der Seite [Datei-API-Konfiguration](https://msdn.microsoft.com/library/dn197834(v=vs.85).aspx) beschrieben wird.

    -   Sie haben eine Internetverbindung mit konfigurierten Computereinstellungen, falls für einen Proxyserver erforderlich. Beispiel: `netsh winhttp import proxy source=ie`

-   Sie haben die zusätzlichen Voraussetzungen für die Azure Rights Management\-Bereitstellung konfiguriert, wie unter [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx) beschrieben wird. Insbesondere verwenden Sie die folgenden Werte zum Herstellen einer Verbindung mit Azure RMS mithilfe eines Dienstprinzipals:

    -   BposTenantId

    -   AppPrincipalId

    -   Symmetrischer Schlüssel

-   Sie haben Ihre lokalen Active Directory\-Benutzerkonten, einschließlich ihrer E\-Mail\-Adressen, mit Azure Active Directory oder Office 365 synchronisiert. Dies ist für alle Benutzer erforderlich, die möglicherweise auf Dateien zugreifen müssen, nachdem diese mit FCI und Azure RMS geschützt wurden. Wenn Sie diesen Schritt nicht ausführen (z. B. in einer Testumgebung), kann der Benutzerzugriff auf diese Dateien möglicherweise blockiert werden. Weitere Informationen zu dieser Kontokonfiguration finden Sie unter [Vorbereiten für Azure Rights Management](../../ems/AADRightsMgmt/Preparing-for-Azure-Rights-Management.md).

-   Sie haben die zu verwendende Rights Management\-Vorlage identifiziert, die die Dateien schützen wird. Stellen Sie mithilfe des [Get-RMSTemplate](https://msdn.microsoft.com/library/azure/mt433197.aspx)\-Cmdlets sicher, dass Sie die ID für diese Vorlage kennen.

## Anweisungen zum Konfigurieren der Ressourcen\-Manager für Dateiserver\-FCI für den Azure RMS\-Schutz
Folgen Sie diesen Anweisungen, um mithilfe eines Windows PowerShell\-Skripts als benutzerdefinierte Aufgabe alle Dateien in einem Ordner zu schützen. Führen Sie diese Verfahren in folgender Reihenfolge aus:

1.  Speichern des Windows PowerShell\-Skripts

2.  Erstellen einer Klassifizierungseigenschaft für Rights Management (RMS)

3.  Erstellen einer Klassifizierungsregel (Klassifizierung für RMS)

4.  Konfigurieren des Klassifizierungszeitplans

5.  Erstellen einer benutzerdefinierten Dateiverwaltungsaufgabe (Schützen von Dateien mit RMS)

6.  Testen der Konfiguration durch manuelles Ausführen der Regel und der Aufgabe

Am Ende dieser Anweisungen sind alle Dateien im ausgewählten Ordner mit der benutzerdefinierten Eigenschaft von RMS klassifiziert, und diese Dateien werden dann durch Rights Management geschützt. Dann können Sie für eine komplexere Konfiguration, die nur bestimmte Dateien selektiv schützt, eine andere Klassifizierungseigenschaft und \-regel mit einer Dateiverwaltungsaufgabe, die nur diese Dateien schützt, erstellen oder verwenden.

#### Speichern des Windows PowerShell\-Skripts

1.  Erweitern Sie den Abschnitt [Windows PowerShell Script](#BKMK_RMSProtection_Script) in diesem Artikel, und kopieren Sie den Inhalt. Fügen Sie den Inhalt des Skripts ein, und benennen Sie die Datei auf Ihrem Computer **RMS\-Protect\-FCI.ps1**.

2.  Überprüfen Sie das Skript, und nehmen Sie folgende Änderungen vor:

    -   Suchen Sie nach der folgenden Zeichenfolge, und ersetzen Sie sie durch Ihre eigene AppPrincipalId, die Sie mit dem [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)\-Cmdlet für die Verbindung zu Azure RMS verwenden:

        ```
        <enter your AppPrincipalId here>
        ```

        Das Skript könnte beispielsweise folgendermaßen aussehen:

        `[Parameter(Mandatory = $false)]`

        `[Parameter(Mandatory = $false)] [string]$AppPrincipalId = "b5e3f76a-b5c2-4c96-a594-a0807f65bba4",`

    -   Suchen Sie nach der folgenden Zeichenfolge, und ersetzen Sie sie durch Ihren eigenen symmetrischen Schlüssel, den Sie mit dem [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)\-Cmdlet für die Verbindung zu Azure RMS verwenden:

        ```
        <enter your key here>
        ```

        Das Skript könnte beispielsweise folgendermaßen aussehen:

        `[Parameter(Mandatory = $false)]`

        `[string]$SymmetricKey = "zIeMu8zNJ6U377CLtppkhkbl4gjodmYSXUVwAO5ycgA="`

    -   Suchen Sie nach der folgenden Zeichenfolge, und ersetzen Sie sie durch Ihre eigene BposTenantId (Mandanten\-ID), die Sie mit dem [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)\-Cmdlet für die Verbindung zu Azure RMS verwenden:

        ```
        <enter your BposTenantId here>
        ```

        Das Skript könnte beispielsweise folgendermaßen aussehen:

        `[Parameter(Mandatory = $false)]`

        `[string]$BposTenantId = "23976bc6-dcd4-4173-9d96-dad1f48efd42",`

    -   Wenn auf Ihrem Server Windows Server 2012 ausgeführt wird, müssen Sie das RMSProtection\-Modul möglicherweise am Anfang des Skripts manuell laden. Fügen Sie den folgenden Befehl (oder einen entsprechenden, wenn sich der Ordner „Program Files“ auf einem anderen Laufwerk als C: befindet) hinzu:

        ```
        Import-Module "C:\Program Files\WindowsPowerShell\Modules\RMSProtection\RMSProtection.dll"
        ```

3.  Signieren Sie das Skript. Sollten Sie das Skript nicht signieren (sicherer), müssen Sie Windows PowerShell auf den Servern konfigurieren, auf denen es ausgeführt wird. Starten Sie beispielsweise eine Windows PowerShell\-Sitzung mit der Option **Als Administrator ausführen**, und geben Sie Folgendes ein: **Set\-ExecutionPolicy Unrestricted**. Diese Konfiguration ermöglicht allerdings die Ausführung aller unsignierten Skripts (weniger sicher).

    Weitere Informationen zum Signieren von Windows PowerShell\-Skripts finden Sie unter [about_Signing](https://technet.microsoft.com/library/hh847874.aspx) in der PowerShell\-Dokumentationsbibliothek.

4.  Speichern Sie die Datei lokal auf jedem Dateiserver, auf dem Sie den Dateiressourcen\-Manager mit Dateiklassifizierungsinfrastruktur ausführen: Speichern Sie die Datei beispielsweise unter **C:\\RMS\-Protection**. Sichern Sie diese Datei mithilfe von NTFS\-Berechtigungen, damit sie nur von autorisierten Benutzern geändert werden kann.

Sie können jetzt mit der Konfiguration des Ressourcen\-Managers für Dateiserver beginnen.

#### Erstellen einer Klassifizierungseigenschaft für Rights Management (RMS)

-   Erstellen Sie im Ressourcen\-Manager für Dateiserver in der Klassifizierungsverwaltung eine neue lokale Eigenschaft:

    -   **Name**: Geben Sie **RMS** ein.

    -   **Beschreibung**:   Geben Sie **Rights Management\-Schutz** ein.

    -   **Eigenschaftstyp**: Wählen Sie **Ja\/Nein** aus.

    -   **Wert**: Wählen Sie **Ja** aus.

Wir können nun eine Klassifizierungsregel erstellen, die diese Eigenschaft verwendet.

#### Erstellen einer Klassifizierungsregel (Klassifizierung für RMS)

-   Erstellen Sie eine neue Klassifizierungsregel:

    -   Auf der Registerkarte **Allgemein**:

        -   **Name**: Geben Sie **Für RMS klassifizieren** ein.

        -   **Enabled**: Behalten Sie die Standardeinstellung bei (das Kontrollkästchen ist aktiviert).

        -   **Beschreibung**: Geben Sie **Alle Dateien im Ordner &lt;Ordnername&gt; für Rights Management klassifizieren**.

            Ersetzen Sie *&lt;Ordnername&gt;* durch Ihren ausgewählten Ordnernamen. Beispiel: **Alle Dateien im Ordner C:\\FileShare für Rights Management klassifizieren**

        -   **Umfang**: Fügen Sie den ausgewählten Ordner hinzu. Beispiel: **C:\\FileShare**.

            Aktivieren Sie keine Kontrollkästchen.

    -   Auf der Registerkarte **Klassifizierung**:

    -   **Klassifizierungsmethode**: Wählen Sie **Ordnerklassifizierung** aus.

    -   Name der **Eigenschaft**: Wählen Sie **RMS** aus.

    -   **Wert** der Eigenschaft: Wählen Sie **Ja** aus.

Obwohl Sie die Klassifizierungsregeln manuell für den laufenden Betrieb ausführen können, sollten Sie diese Regel nach einem Zeitplan ausführen, damit neue Dateien mit der RMS\-Eigenschaft klassifiziert werden.

#### Konfigurieren des Klassifizierungszeitplans

-   Auf der Registerkarte **Automatische Klassifizierung**:

    -   **Festen Zeitplan aktivieren**: Aktivieren Sie dieses Kontrollkästchen.

    -   Konfigurieren Sie den Zeitplan für alle auszuführenden Klassifizierungsregeln, einschließlich unsere neue Regel, um Dateien mit der RMS\-Eigenschaft zu klassifizieren.

    -   **Fortlaufende Klassifizierung für neue Dateien zulassen**: Aktivieren Sie dieses Kontrollkästchen, damit neue Dateien klassifiziert werden.

    -   Optional: Nehmen Sie ggf. andere Änderungen vor, z. B. das Konfigurieren von Optionen für Berichte und Benachrichtigungen.

Nachdem Sie die Klassifizierungskonfiguration abgeschlossen haben, können Sie eine Verwaltungsaufgabe zum Anwenden des RMS\-Schutzes auf die Dateien konfigurieren.

#### Erstellen einer benutzerdefinierten Dateiverwaltungsaufgabe (Schützen von Dateien mit RMS)

-   Erstellen Sie unter **Dateiverwaltungsaufgaben** eine neue Dateiverwaltungsaufgabe:

    -   Auf der Registerkarte **Allgemein**:

        -   **Aufgabenname**: Geben Sie **Schützen von Dateien mit RMS** ein.

        -   Vergewissern Sie sich, dass das Kontrollkästchen **Aktivieren** aktiviert ist.

        -   **Beschreibung**: Geben Sie **Schützen von Dateien in &lt;Ordnername&gt; mit Rights Management und einer Vorlage mit einem Windows PowerShell\-Skript** ein.

            Ersetzen Sie *&lt;Ordnername&gt;* durch Ihren ausgewählten Ordnernamen. Beispiel: **Schützen von Dateien in C:\\FileShare mit Rights Management und einer Vorlage mit einem Windows PowerShell\-Skript**

        -   **Umfang**: Wählen Sie Ihren Ordner aus. Beispiel: **C:\\FileShare**.

            Aktivieren Sie keine Kontrollkästchen.

    -   Auf der Registerkarte **Aktion**:

        -   **Typ**: Wählen Sie **Benutzerdefiniert** aus.

        -   **Ausführbare Datei**: Geben Sie Folgendes an:

            ```
            C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
            ```

            Wenn sich Windows nicht auf Laufwerk C: befindet, ändern Sie diesen Pfad, oder navigieren Sie zu dieser Datei.

        -   **Argument**: Geben Sie Folgendes an, und stellen Sie dabei Ihre eigenen Werte für &lt;Pfad&gt; und &lt;Vorlagen\-ID&gt; bereit:

            ```
            -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID <template GUID> -OwnerMail [Source File Owner Email]"
            ```

            Wenn Sie das Skript nach „C:\\RMS\-Protection“ kopiert haben und die aus den Voraussetzungen identifizierte Vorlagen\-ID „e6ee2481\-26b9\-45e5\-b34a\-f744eacd53b0“ lautet, geben Sie beispielsweise Folgendes an:

            `-Noprofile -Command "C:\RMS-Protection\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID e6ee2481-26b9-45e5-b34a-f744eacd53b0 -OwnerMail [Source File Owner Email]"`

            In diesem Befehl sind **\[Quelldateipfad]** und **\[Quelldateibesitzer\-E\-Mail]** FCI\-spezifische Variablen. Geben Sie diese also genau wie im obigen Befehl ein. Die erste wird von FCI verwendet, um automatisch die identifizierte Datei im Ordner anzugeben, und die zweite wird verwendet, damit FCI automatisch die E\-Mail\-Adresse des benannten Besitzers der identifizierten Datei abrufen kann. Dieser Befehl wird für jede Datei im Ordner wiederholt, in unserem Beispiel für jede Datei im Ordner „C:\\FileShare“, die außerdem noch RMS als Dateiklassifizierungseigenschaft aufweist.

            > [!NOTE]
            > Durch den  **\-OwnerMail \[Source File Owner Email]**\-Parameter und seinen Wert wird sichergestellt, dass dem ursprünglichen Besitzer der Datei nach dem Schutz der Datei die Berechtigung "Rights Management\-Besitzer" gewährt wird. Dadurch wird sichergestellt, dass der ursprüngliche Dateibesitzer über alle Rights Management\-Rechte für seine eigenen Dateien verfügt. Wenn Dateien von einem Domänenbenutzer erstellt werden, wird die E\-Mail\-Adresse automatisch aus Active Directory abgerufen, wobei der Benutzerkontoname aus der Eigenschaft "Besitzer" der Datei verwendet wird. Hierzu muss sich der Dateiserver in derselben Domäne bzw. vertrauenswürdigen Domäne wie der Benutzer befinden.
            > 
            > Weisen Sie, sofern möglich, den ursprünglichen Besitzer geschützten Dokumenten zu, um sicherzustellen, dass diese Benutzer weiterhin die volle Kontrolle über die von ihnen erstellten Dateien haben. Wenn Sie aber die Variable \[Quelldateibesitzer\-E\-Mail] wie oben beschrieben verwenden und für eine Datei kein Domänenbenutzer als Besitzer definiert wurde (wenn z. B. ein lokales Konto zum Erstellen der Datei verwendet wurde, sodass der Besitzer als "SYSTEM" angezeigt wird), verursacht das Skript einen Fehler.
            > 
            > Für Dateien, die keinen Domänenbenutzer als Besitzer aufweisen, können Sie diese Dateien selbst als Domänenbenutzer kopieren und speichern, sodass Sie zum Besitzer nur dieser Dateien werden. Alternativ können Sie, wenn Sie über Berechtigungen verfügen, manuell den Besitzer ändern.  Oder alternativ können Sie eine bestimmte E\-Mail\-Adresse (z. B. Ihre eigene oder eine Gruppenadresse für die IT\-Abteilung) anstelle der \[Quelldateibesitzer\-E\-Mail]\-Variablen angeben, was bedeutet, dass alle Dateien, die Sie mit diesem Skript schützen, diese E\-Mail\-Adresse zum Definieren des neuen Besitzers verwenden.

    -   **Führen Sie den Befehl wie folgt aus**: Wählen Sie **Lokales System** aus.

    -   Auf der Registerkarte **Bedingung**:

        -   **Eigenschaft**: Wählen Sie **RMS** aus.

        -   **Operator**: Wählen Sie **Gleich** aus.

        -   **Wert**: Wählen Sie **Ja** aus.

    -   Auf der Registerkarte **Zeitplan**:

        -   **Ausführen um**: Konfigurieren Sie Ihren bevorzugten Zeitplan.

            Ermöglichen Sie ausreichend Zeit für den Abschluss des Skripts. Obwohl diese Lösung alle Dateien im Ordner schützt, wird das Skript jedes Mal genau ein Mal für jede Datei ausgeführt. Obwohl dies länger dauert als das gleichzeitige Schützen aller Dateien, was das RMS\-Schutztool unterstützt, ist diese dateibasierte Konfiguration für FCI leistungsfähiger. Die geschützten Dateien können z. B. verschiedene Besitzern haben (Beibehalten des ursprünglichen Besitzers), wenn Sie die \[Quelldateibesitzer\-E\-Mail]\-Variable verwenden, und diese dateibasierte Aktion wird erforderlich sein, wenn Sie später die Konfiguration zum selektiven Schutz von Dateien anstatt zum Schutz aller Dateien in einem Ordner ändern.

        -   **Für neue Dateien fortlaufend ausführen**: Aktivieren Sie dieses Kontrollkästchen.

#### Testen der Konfiguration durch manuelles Ausführen der Regel und der Aufgabe

1.  Führen Sie die Klassifizierungsregel aus:

    1.  Klicken Sie auf **Klassifizierungsregeln** &gt; **Klassifizierung mit allen Regeln jetzt ausführen**.

    2.  Klicken Sie auf **Warten, bis die Klassifizierung abgeschlossen ist**, und klicken Sie dann auf **OK**.

2.  Warten Sie, bis das Dialogfeld **Klassifizierung wird ausgeführt** geschlossen wurde, und sehen Sie sich dann die Ergebnisse im automatisch angezeigten Bericht an. Es sollte **1** für das Feld **Eigenschaften** und die Anzahl der Dateien im Ordner angezeigt werden. Überprüfen Sie mithilfe des Datei\-Explorers die Eigenschaften der Dateien im ausgewählten Ordner. Auf der Registerkarte **Klassifizierung** sollte **RMS** als Eigenschaftsname und **Ja** für den **Wert** angezeigt werden.

3.  Führen Sie die Dateiverwaltungsaufgabe aus:

    1.  Klicken Sie auf **Dateiverwaltungsaufgaben** &gt; **Dateien mit RMS schützen** &gt; **Dateiverwaltungsaufgabe jetzt ausführen**.

    2.  Klicken Sie auf **Warten, bis die Aufgabe abgeschlossen ist**, und klicken Sie dann auf **OK**.

4.  Warten Sie, bis das Dialogfeld **Dateiverwaltungsaufgabe wird ausgeführt** geschlossen wurde, und sehen Sie sich dann die Ergebnisse im automatisch angezeigten Bericht an. Daraufhin sollte die Anzahl der Dateien im ausgewählten Ordner im Feld **Dateien** angezeigt werden. Vergewissern Sie sich, dass die Dateien im ausgewählten Ordner jetzt durch RMS geschützt sind. Wenn z. B. der ausgewählte Ordner „C:\\FileShare“ ist, geben Sie Folgendes in einer Windows PowerShell\-Sitzung ein und stellen sicher, dass keine Dateien den Status **Ungeschützt** haben:

    ```
    foreach ($file in (Get-ChildItem -Path C:\FileShare -Force | where {!$_.PSIsContainer})) {Get-RMSFileStatus -f $file.PSPath}
    ```

    > [!TIP]
    > Einige Tipps zur Problembehandlung:
    > 
    > -   Wenn Sie im Bericht **0** anstatt der Anzahl der Dateien in Ihrem Ordner sehen, weist dies darauf hin, dass das Skript nicht ausgeführt wurde. Überprüfen Sie zunächst das Skript durch Laden in Windows PowerShell ISE, um die Inhalte des Skripts zu überprüfen, und führen sie es aus, um zu ermitteln, ob Fehler angezeigt werden. Wenn keine Argumente angegeben werden, versucht das Skript, eine Verbindung herzustellen und sich bei Azure RMS zu authentifizieren.
    > 
    >     -   Wenn das Skript meldet, dass es keine Verbindung mit Azure RMS herstellen konnte, überprüfen Sie die Werte, die für das Dienstprinzipalkonto, das Sie im Skript angegeben haben, angezeigt werden.  Weitere Informationen zum Erstellen dieses Dienstprinzipalkontos finden Sie in der zweiten Voraussetzung unter [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx).
    >     -   Wenn das Skript meldet, dass es die Verbindung mit Azure RMS herstellen konnte, und wenn Ihre Azure\-Region außerhalb von Nordamerika liegt, überprüfen Sie, dass Sie die Registrierung für diese Konfiguration ordnungsgemäß bearbeitet haben. Ein guter Test dafür ist das Ausführen von „Get\-RMSTemplate“ direkt aus Windows PowerShell auf dem Server. Weitere Informationen zur Bearbeitung der Registrierung finden Sie in der dritten Voraussetzung unter [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx).
    > -   Wenn das Skript selbst in Windows PowerShell ISE ohne Fehler ausgeführt wird, führen Sie es wie folgt in einer PowerShell\-Sitzung aus. Geben Sie dabei den Namen einer zu schützenden Datei ohne den „OwnerEmail“\-Parameter an:
    > 
    >     ```
    >     powershell.exe -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File <full path and name of a file>' -TemplateID <template GUID>"
    >     ```
    > 
    >     -   Wenn das Skript in dieser Windows PowerShell\-Sitzung erfolgreich ausgeführt wurde, überprüfen Sie Ihre Einträge für **Executive** und **Argument** in der Dateiverwaltungsaufgaben\-Aktion.  Wenn Sie **\-OwnerEmail \[Quelldateibesitzer\-E\-Mail]** angegeben haben, entfernen Sie diesen Parameter.
    > 
    >         Wenn die Dateiverwaltungsaufgabe erfolgreich ohne **\-OwnerEmail \[Quelldateibesitzer\-E\-Mail]** funktioniert, überprüfen Sie, ob für die nicht geschützten Dateien anstelle von **SYSTEM** ein Domänenbenutzer als Dateibesitzer aufgeführt wird.  Verwenden Sie hierzu die Registerkarte **Sicherheit** für die Eigenschaften der Datei, und klicken Sie dann auf **Erweitert**. Der **Besitzer**\-Wert wird sofort hinter dem **Name**n der Datei angezeigt. Überprüfen Sie außerdem, ob sich der Dateiserver in derselben Domäne bzw. einer vertrauenswürdigen Domäne befindet, um die E\-Mail\-Adresse des Benutzers in den Active Directory\-Domänendiensten nachzuschlagen.
    > -   Wenn Sie die richtige Anzahl von Dateien im Bericht sehen, die Dateien aber nicht geschützt sind, versuchen Sie, die Dateien manuell mithilfe des [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx)\-Cmdlets zu schützen, um festzustellen, ob Fehler angezeigt werden.

Wenn Sie sichergestellt haben, dass diese Aufgaben erfolgreich ausgeführt werden, können Sie den Dateiressourcen\-Manager schließen. Neue Dateien werden automatisch geschützt, und alle Dateien werden erneut geschützt, wenn die Zeitpläne ausgeführt werden. Das erneute Schützen der Dateien stellt sicher, dass alle Änderungen an der Vorlage auf die Dateien angewendet werden.

### <a name="BKMK_RMSProtection_Script"></a>Windows PowerShell\-Skript für Azure RMS\-Schutz mithilfe der Ressourcen\-Manager für Dateiserver\-FCI
Dieser Abschnitt enthält das zu kopierende und zu bearbeitende Beispielskript, wie im vorherigen Abschnitt beschrieben.

*&#42;&#42;Haftungsausschluss&#42;&#42;: Dieses Beispielskript wird unter keinem Microsoft\-Standardsupportprogramm oder \-dienst unterstützt. Dieses Beispielskript wird OHNE jede Gewährleistung bereitgestellt.*

```
<# .SYNOPSIS Helper script to protect all file types with Azure RMS and FCI. .DESCRIPTION Protect files with Azure RMS and Windows Server FCI, using an RMS template ID. #> param( [Parameter(Mandatory = $false)] [ValidateScript({ If($_ -eq "") {$true} else { if (Test-Path -Path $_ -PathType Leaf) {$true} else {throw "Can't find file specified"} } })] [string]$File, [Parameter(Mandatory = $false)] [string]$TemplateID, [Parameter(Mandatory = $false)] [string]$OwnerMail, [Parameter(Mandatory = $false)] [string]$AppPrincipalId = "<enter your AppPrincipalId here>", [Parameter(Mandatory = $false)] [string]$SymmetricKey = "<enter your key here>", [Parameter(Mandatory = $false)] [string]$BposTenantId = "<enter your BposTenantId here>" ) # script information [String] $Script:Version = 'version 1.0' [String] $Script:Name = "RMS-Protect-FCI.ps1" #global working variables [switch] $Script:isScriptProcess = $False # Controls the script process. If false, the script gracefully stops running. #**Functions (general helper)*************************************** function Get-ScriptName(){ return $MyInvocation.ScriptName.Substring($MyInvocation.ScriptName.LastIndexOf('\') + 1, $MyInvocation.ScriptName.LastIndexOf('.') - $MyInvocation.ScriptName.LastIndexOf('\') - 1) } #**Functions (script specific)************************************** function Check-Module{ param ([String]$Module = $(Throw "Module name not specified")) [bool]$isResult = $False #try to load the module if (get-module -list -name $Module) { import-module $Module if (get-module -name $Module ) { $isResult = $True } else { $isResult = $False } } else { $isResult = $False } return $isResult } function Protect-File ($ffile, $ftemplateId, $fownermail) { [bool] $returnValue = $false try { If ($OwnerMail -eq $null -or $OwnerMail -eq "") { $protectReturn = Protect-RMSFile -File $ffile -TemplateID $ftemplateId $returnValue = $true Write-Host ( "Information: " + "Protected File: $ffile with Template: $ftemplateId") } else { $protectReturn = Protect-RMSFile -File $ffile -TemplateID $ftemplateId -OwnerEmail $fownermail $returnValue = $true Write-Host ( "Information: " + "Protected File: $ffile with Template: $ftemplateId, set Owner: $fownermail") } } catch { Write-Host ( "ERROR" + "During protection of file: $ffile with Template: $ftemplateId") } return $returnValue } function Set-RMSConnection ($fappId, $fkey, $fbposId) { [bool] $returnValue = $false try { Set-RMSServerAuthentication -AppPrincipalId $fappId -Key $fkey -BposTenantId $fbposId Write-Host ("Information: " + "Connected to Azure RMS Service with BposTenantId: $fbposId using AppPrincipalId: $fappId") $returnValue = $true } catch { Write-Host ("ERROR" + "During connection to Azure RMS Service with BposTenantId: $fbposId using AppPrincipalId: $fappId") } return $returnValue } #**Main Script (Script)********************************************* Write-Host ("-== " + $Script:Name + " " + $Version + " ==-") $Script:isScriptProcess = $True # Validate Azure RMS connection by checking the module and then connection if ($Script:isScriptProcess) { if (Check-Module -Module RMSProtection){ $Script:isScriptProcess = $True } else { Write-Host ("The RMSProtection module is not loaded") -foregroundcolor "yellow" -backgroundcolor "black" $Script:isScriptProcess = $False } } if ($Script:isScriptProcess) { #Write-Host ("Try to connect to Azure RMS with AppId: $AppPrincipalId and BPOSID: $BposTenantId" ) if (Set-RMSConnection $AppPrincipalId $SymmetricKey $BposTenantId) { Write-Host ("Connected to Azure RMS") } else { Write-Host ("Couldn't connect to Azure RMS") -foregroundcolor "yellow" -backgroundcolor "black" $Script:isScriptProcess = $False } } #  Start working loop if ($Script:isScriptProcess) { if ( !(($File -eq $null) -or ($File -eq "")) ) { if (!(Protect-File -ffile $File -ftemplateId $TemplateID -fownermail $OwnerMail)) { $Script:isScriptProcess = $False } } } # Closing if (!$Script:isScriptProcess) { Write-Host "ERROR occurred during script process" -foregroundcolor "red" -backgroundcolor "black"} write-host ("-== " + $Script:Name + " " + $Version + "  ==-") if (!$Script:isScriptProcess) { exit(-1) } else {exit(0)}
```

## Ändern der Anweisungen zum selektiven Schutz von Dateien
Wenn Sie die zuvor beschriebenen Anweisungen abgeschlossen haben, ist es sehr einfach, sie für eine komplexere Konfiguration zu ändern. Schützen Sie Dateien beispielsweise mithilfe des gleichen Skripts, jedoch nur für Dateien mit personenbezogenen Informationen, und wählen Sie vielleicht eine Vorlage aus, die über restriktivere Berechtigungen verfügt.

Verwenden Sie hierzu eine der integrierten Klassifizierungseigenschaften (z. B. **Daten mit persönlich identifizierbaren Informationen**), oder erstellen Sie eine eigene neue Eigenschaft. Erstellen Sie dann eine neue Regel, die diese Eigenschaft verwendet. Sie können z. B. die **Inhaltsklassifizierung** und die **Daten mit persönlich identifizierbaren Informationen**\-Eigenschaft mit dem Wert **Hoch** auswählen und die Zeichenfolge oder das Ausdrucksmuster konfigurieren, die bzw. das die Datei identifiziert, die für diese Eigenschaft konfiguriert werden soll (z. B. die Zeichenfolge „**Geburtsdatum**“).

Jetzt müssen Sie nur eine neue Dateiverwaltungsaufgabe erstellen, die das gleiche Skript verwendet, aber möglicherweise mit einer anderen Vorlage, und die Bedingung für die Klassifizierungseigenschaft, die Sie gerade konfiguriert haben, konfigurieren. Wählen Sie beispielsweise anstatt der Bedingung, die wir zuvor konfiguriert haben (**RMS**\-Eigenschaft, **Gleich**, **Ja**), die **Daten mit persönlich identifizierbaren Informationen**\-Eigenschaft mit dem **Operator**\-Wert **Gleich** und dem **WertHoch** aus.

