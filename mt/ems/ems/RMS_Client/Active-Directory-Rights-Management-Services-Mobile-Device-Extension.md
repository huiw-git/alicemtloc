---
title: Active Directory Rights Management Services-Mobilger&#228;teerweiterung
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.assetid: a69ead9d-7dd3-4b38-9830-4728e9757341
translation.priority.ht: 
  - cs-cz
  - es-es
  - fr-fr
  - hu-hu
  - it-it
  - ko-kr
  - nl-nl
  - pl-pl
  - pt-br
  - pt-pt
  - ru-ru
  - sv-se
  - tr-tr
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - de-de
  - ja-jp
---
# Active Directory Rights Management Services-Mobilger&#228;teerweiterung
Die Mobilgeräteerweiterung Active Directory Rights Management Services (AD RMS) läuft im Vordergrund einer vorhandenen AD RMS-Bereitstellung. Auf diese Weise können Benutzer von mobilen Geräten ihre vertrauliche Daten schützen, wenn ihr Gerät den neuesten RMS-Client unterstützt und RMS-fähige Apps verwendet. Benutzer dieser Geräte können z. B.:

-   mit der RMS-Freigabe-App geschützte Textdateien in verschiedenen Formaten verarbeiten (z. B. TXT, CSV und XML).

-   mit der RMS-Freigabe-App geschützte Bilddateien in verschiedenen Formaten verarbeiten (z. B. JPG, GIF und TIF).

-   mit der RMS-Freigabe-App jede Datei öffnen, die allgemein geschützt ist (Format PFILE).

-   mit der RMS-Freigabe-App Bilddateien auf ihrem Gerät schützen.

-   mit einem RMS-fähigen PDF-Viewer für mobile Geräte PDF-Dateien öffnen, die mit der RMS-Freigabeanwendung für Windows oder einer anderen RMS-fähigen Anwendung geschützt wurden.

-   andere Apps von Softwareherstellern verwenden, die RMS-fähige Apps anbieten, wenn diese Dateitypen für systemeigene RMS-Unterstützung unterstützen.

-   ihre eigenen RMS-fähigen Apps verwenden, die sie mit dem RMS SDK intern entwickelt haben.

> [!NOTE]
> Sie können die RMS-Freigabe-App von der Seite [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) Seite auf der Microsoft-Website herunterladen.
> 
> Weitere Informationen zu den verschiedenen Dateitypen, die RMS unterstützt, finden Sie im Abschnitt [Unterstützte Dateitypen und Dateinamenerweiterungen](http://technet.microsoft.com/library/dn339003.aspx) im Administratorhandbuch der Rights Management-Freigabeanwendung.

Sie müssen nicht die Mobilgeräteerweiterung verwenden, um vom Autor geschützte E-Mails öffnen zu können, wenn auf Ihrem Gerät eine Mail-Anwendung ausgeführt wird, die Exchange ActiveSync IRM unterstützt. Diese systemeigene Unterstützung für RMS und mobile Geräte wurde mit Exchange 2010 Service Pack 1 eingeführt.

Lesen Sie die folgenden Abschnitte, um die Mobilgeräteerweiterung Active Directory Rights Management Services (AD RMS) einzusetzen:

-   [Prerequisites for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_Preqs)

    -   [Configuring AD FS for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_ADFS)

    -   [Configuring AD FS for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_ADFS)

-   [Specifying the DNS SRV records for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_SRV)

-   [Deploying the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_Deploy)

## <a name="BKMK_Preqs"></a>Voraussetzungen für die AD RMS-Mobilgeräteerweiterung
Bevor Sie die AD RMS-Mobilgeräteerweiterung installieren, stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.

|Anforderungen|Weitere Informationen|
|-----------------|-------------------------|
|Eine vorhandene AD RMS-Bereitstellung auf Windows Server 2012 R2 oder Windows Server 2012. **Note:** AD RMS muss eine vollständige Microsoft SQL Server-Datenbank auf einem separaten Server und nicht die interne Windows-Datenbank verwenden, die häufig zum Testen auf dem gleichen Server verwendet wird.|Informationen zu Dokumentation über AD RMS finden Sie unter [Active Directory Rights Management Services](http://technet.microsoft.com/library/hh831364.aspx) in der Windows Server-Bibliothek.|
|AD FS, bereitgestellt unter Windows Server 2012 R2|Dokumentation zu AD FS finden Sie unter [Bereitstellungshandbuch für Windows Server 2012 R2 AD FS](http://technet.microsoft.com/library/dn486820.aspx) in der Windows Server-Bibliothek.<br /><br />AD FS muss für die Mobilgeräteerweiterung konfiguriert werden. Anweisungen finden Sie im Abschnitt [Configuring AD FS for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_ADFS) dieses Themas.|
|SRV-Einträge im DNS|Erstellen Sie einen oder mehrere SRV-Einträge in Ihrer/Ihren Unternehmensdomäne(n):<br /><br />-   einen Eintrag für jedes E-Mail-Domänensuffix, das die Benutzer verwenden<br />-   einen Eintrag für jeden FQDN, der von Ihren RMS-Clustern zum Schutz von Inhalten verwendet wird<br /><br />Wenn Benutzer ihre E-Mail-Adresse auf ihrem mobilen Gerät eingeben, wird das Domänensuffix verwendet, um festzustellen, ob sie eine RMS-Infrastruktur oder Azure RMS verwenden sollten. Wenn der SRV-Eintrag gefunden wird, werden Clients zu dem AD RMS-Server umgeleitet, der auf diese URL reagiert.<br /><br />Wenn Benutzer geschützte Inhalte auf einem mobilen Gerät öffnen, sucht die Clientanwendung im DNS nach einem Eintrag, der zum FQDN in der URL des Clusters passt, der die Inhalte schützt. Das Gerät wird dann zu dem im DNS-Eintrag angegebenen AD RMS-Cluster geleitet und erhält eine Lizenz zum Öffnen des Inhalts. In den meisten Fällen ist der RMS-Cluster mit dem RMS-Cluster identisch, der die Inhalte schützt.<br /><br />Informationen zum Festlegen von SRV-Einträgen finden Sie im Abschnitt  [Specifying the DNS SRV Records for the AD RMS mobile device extension](../../ems/RMS_Client/Active-Directory-Rights-Management-Services-Mobile-Device-Extension.md#BKMK_SRV) in diesem Thema.|
|Derzeit unterstützte Clients:<br /><br />-   Android-Geräte mit der neuesten Version der RMS-Freigabe-App für Android|Mindestversion von Android 4.0.3.<br /><br />Laden Sie die RMS-Freigabe-App für Android von der [Microsoft Connect-Website](https://connect.microsoft.com/site1170/Downloads) herunter, und laden Sie sie auf dem Gerät quer.|

### <a name="BKMK_ADFS"></a>Konfigurieren von AD FS für die AD RMS-Mobilgeräteerweiterung
Sie müssen zuerst AD FS konfigurieren und anschließend die RMS-Freigabe-App für Android autorisieren.

##### Schritt 1: So konfigurieren Sie AD FS

-   Sie können entweder ein Windows PowerShell-Skript ausführen, um AD FS automatisch für eine Unterstützung der AD RMS-Mobilgeräteerweiterung zu konfigurieren, oder Sie können die Konfigurationsoptionen und -werte manuell eingeben:

    -   Wenn Sie AD FS automatisch konfigurieren möchten, kopieren Sie Folgendes in eine Windows PowerShell-Skriptdatei, und führen Sie sie anschließend aus:

        ```
        # This Script Configures the Microsoft Rights Management Mobile Device Extension and Claims used in the ADFS Server

        # Check if Microsoft Rights Management Mobile Device Extension is configured on the Server 
        $CheckifConfigured = Get-AdfsRelyingPartyTrust -Identifier "api.rms.rest.com"
        if ($CheckifConfigured)
        {
        Write-Host "api.rms.rest.com Identifer used for Microsoft Rights Management Mobile Device Extension is already configured on this Server"
        Write-Host $CheckifConfigured 
        }
        else
        {
        Write-Host "Configuring  Microsoft Rights Management Mobile Device Extension "

        # TransformaRules used by Microsoft Rights Management Mobile Device Extension
        # Claims: E-mail, UPN and ProxyAddresses
        $TransformRules = @"
        @RuleTemplate = "LdapClaims"
        @RuleName = "Jwt Token"
        c:[Type ==
        "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname",
        Issuer == "AD AUTHORITY"]
         => issue(store = "Active Directory", types =
        ("http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress",
        "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn",
        "http://schemas.xmlsoap.org/claims/ProxyAddresses"), query =
        ";mail,userPrincipalName,proxyAddresses;{0}", param = c.Value);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through Proxy addresses"
        c:[Type == "http://schemas.xmlsoap.org/claims/ProxyAddresses"]
         => issue(claim = c);
        "@

        # AuthorizationRules used by Microsoft Rights Management Mobile Device Extension
        # Allow All users
        $AuthorizationRules = @"
        @RuleTemplate = "AllowAllAuthzRule"
         => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit",
        Value = "true");
        "@

        # Add a Relying Part Truest with Name -"Microsoft Rights Management Mobile Device Extension" Identifier "api.rms.rest.com"
        Add-ADFSRelyingPartyTrust -Name "Microsoft Rights Management Mobile Device Extension" -Identifier "api.rms.rest.com" -IssuanceTransformRules $TransformRules -IssuanceAuthorizationRules  $AuthorizationRules

        Write-Host "Microsoft Rights Management Mobile Device Extension Configured"
        }
        ```

    -   Verwenden Sie die folgenden Einstellungen, um AD FS manuell zu konfigurieren:

        |Konfiguration|Wert|
        |-----------------|--------|
        |**Vertrauensstellung der vertrauenden Seite**|api.rms.rest.com|
        |**Anspruchsregel**|**Attributspeicher**:  Active Directory<br /><br />**E-Mail-Adressen**:  E-Mail-Adresse<br /><br />**Benutzerprinzipalname**:  UPN<br /><br />**Proxyadresse**:  https://schemas.xmlsoap.org/claims/ProxyAddresses|

##### Schritt 2: Autorisieren der RMS-Freigabe-App für Android

-   Führen Sie den folgenden Windows PowerShell-Befehl aus, um Unterstützung für Android-Geräte hinzuzufügen:

    ```
    Add-AdfsClient -Name "RMSsharingAndroid" -ClientId "com.microsoft.ipviewer" -RedirectUri @("com.microsoft.ipviewer://authorize")
    ```

### <a name="BKMK_SRV"></a>Festlegen der DNS-SRV-Einträge für die AD RMS-Mobilgeräteerweiterung
Sie müssen DNS-SRV-Einträge für jede E-Mail-Domäne erstellen, die Ihre Benutzer verwenden. Wenn alle Ihre Benutzer untergeordnete Domänen aus einer einzigen übergeordneten Domäne verwenden und alle Benutzer aus diesem zusammenhängenden Namespace denselben RMS-Cluster verwenden, reicht ein SVR-Eintrag in der übergeordneten Domäne aus, damit RMS die entsprechenden DMS-Einträge findet.

Die SRV-Einträge haben folgendes Format: _rmsdisco._http._tcp. *&lt;E-Mail-Suffix&gt;**&lt;Portnummer&gt;**&lt;RMSClusterFQDN&gt;*

Beispiel: Wenn es in Ihrer Organisation Benutzer mit den folgenden E-Mail-Adressen gibt:

-   user@contoso.com

-   user@sales.contoso.com

-   user@fabrikam.com

und es gibt keine weiteren untergeordneten Domänen für "contoso.com", die einen anderen RMS-Cluster als **rmsserver.contoso.com** verwenden, erstellen Sie zwei DNS-SRV-Einträge, die die folgenden Werte aufweisen:

-   _rmsdisco._http._tcp.contoso.com 443 rmsserver.contoso.com

-   _rmsdisco._http._tcp.fabrikam.com 443 rmsserver.contoso.com

Zusätzlich zu diesen DNS-SRV-Einträgen für Ihre E-Mail-Domänen müssen Sie einen weiteren DNS-SRV-Eintrag in den Benutzerdomänen erstellen. Dieser Eintrag muss die URLs Ihres RMS-Clusters enthalten, der Inhalte schützt. Jede Datei, die von RMS geschützt wird, enthält eine URL für den Cluster, der diese Datei schützt. Mobile Geräte verwenden den DNS-SRV-Eintrag und den im Eintrag angegebenen URL-FQDN, um den entsprechenden RMS-Cluster zu finden, der mobile Geräte unterstützen kann.

Wenn Ihr RMS-Cluster beispielswiese **rmsserver.contoso.com** ist, erstellen Sie einen DNS-SRV-Datensatz mit den folgenden Werten: **_rmsdisco._http._tcp.rmsserver.contoso.com 443 rmsserver.contoso.com**

## <a name="BKMK_Deploy"></a>Bereitstellen der AD RMS-Mobilgeräteerweiterung
Bevor Sie die AD RMS-Mobilgeräteerweiterung installieren, stellen Sie sicher, dass die in den vorigen Abschnitten genannten Voraussetzungen erfüllt sind und dass Sie die URL Ihres AD FS-Servers kennen. Führen Sie dann folgende Schritte aus:

1.  Laden Sie die AD RMS-Mobilgeräteerweiterung von der [Microsoft Connect-Website](http://go.microsoft.com/fwlink/?LinkId=397245) herunter.

2.  Führen Sie Setup.exe aus, um den Setup-Assistenten für die Active Directory Rights Management Services-Mobilgeräteerweiterung zu starten.

3.  Wenn Sie dazu aufgefordert werden, geben Sie die URL des AD FS-Server an, den Sie zuvor konfiguriert haben.

4.  Beenden Sie den Assistenten.

Führen Sie den Assistenten auf allen Knoten in Ihrem RMS-Cluster aus.

