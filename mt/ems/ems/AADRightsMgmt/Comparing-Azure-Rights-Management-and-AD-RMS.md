---
title: Vergleich von Azure Rights Management und AD RMS
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8123bd62-1814-4d79-b306-e20c1a00e264
translation.priority.ht: 
  - bg-bg
  - el-gr
  - es-es
  - et-ee
  - fi-fi
  - fr-fr
  - hr-hr
  - it-it
  - kk-kz
  - ko-kr
  - lt-lt
  - lv-lv
  - pt-br
  - ro-ro
  - ru-ru
  - sk-sk
  - sl-si
  - sr-latn-cs
  - th-th
  - tr-tr
  - uk-ua
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
# Vergleich von Azure Rights Management und AD RMS
Wenn Sie wissen oder Active Directory Rights Management Services (AD RMS) bereits bereitgestellt haben, werden Sie vielleicht wie [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS) in Bezug auf die Funktionen und Anforderungen vergleicht. Verwenden Sie in der folgende Tabelle für einen Side-by-Side-Vergleich der Features und Vorteile von Azure RMS und AD RMS. Wenn Sie sicherheitsbezogene Vergleich Fragen haben, finden Sie unter den [Cryptographic controls for signing and encryption](../../ems/AADRightsMgmt/Comparing-Azure-Rights-Management-and-AD-RMS.md#BKMK_CryptographicControls) in diesem Thema.

> [!NOTE]
> Um den Vergleich zu erleichtern, wird hier einige Informationen aus wiederholt [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). Verwenden Sie dieses Thema Informationen spezifischere Support- und Versionsinformationen für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)].

|[!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS) <br /> <br />|Active Directory-Rechteverwaltungsdienste (AD RMS) <br /> <br />|
|---------------------------------------------------------------------------------------|------------------------------------------------------|
|Microsoft Online Services wie Exchange Online und SharePoint Online, als auch Office 365 unterstützt Informationen Rights Management (IRM) Funktionen. <br /> <br />Außerdem unterstützt lokale Microsoft-Serverprodukte, wie z. B. Exchange Server, SharePoint-Server und Dateiserver, Windows Server und Datei Classification-Infrastruktur (FCI). <br /> <br />|Unterstützt lokale Microsoft-Serverprodukte wie Exchange Server, SharePoint-Server und Dateiserver, Windows Server und Datei Classification-Infrastruktur (FCI). <br /> <br />|
|Ermöglicht die implizite Vertrauensstellungen zwischen Organisationen und Benutzer in jeder Organisation. Dies bedeutet, dass geschützter Inhalt zwischen Benutzern innerhalb einer Organisation oder zwischen Organisationen, wenn Benutzer freigegeben werden kann [!INCLUDE[o365_1](../../ems/AADRightsMgmt/includes/o365_1_md.md)], oder [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)], oder Benutzer registrieren für RMS für Einzelpersonen. <br /> <br />|Vertrauensstellungen müssen explizit definiert, die in einer direkten Punkt-Beziehung zwischen zwei Organisationen mit entweder Vertrauenswürdige Benutzerdomänen (vertrauenswürdiger Benutzerdomänen) oder federated darauf vertraut, dass Sie mithilfe von Active Directory Federation Services (AD FS) erstellen. <br /> <br />|
|Bietet zwei Standardrechte Richtlinienvorlagen, die Zugriff des Inhalts auf Ihre eigene Organisation beschränken. eine, die schreibgeschützte Anzeige geschützter Inhalte und eine andere Vorlage, enthält Schreib- oder Änderungsberechtigungen für geschützten Inhalt bereitstellt. <br /> <br />Sie können eigene benutzerdefinierten Vorlagen auch erstellen Abteilung Vorlagen enthält, die nur eine Teilmenge von Benutzern angezeigt werden. Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md). <br /> <br />Darüber hinaus können Benutzer ihre eigenen Berechtigungssatz definieren, wenn die Vorlagen nicht ausreichen. <br /> <br />|Es sind keine Vorlagen für Benutzerrechterichtlinien Standard. Sie erstellen und verteilen Sie diese. Weitere Informationen finden Sie unter [Aspekte der AD RMS-Richtlinie Vorlage](http://go.microsoft.com/fwlink/?LinkId=154765). <br /> <br />Darüber hinaus können Benutzer ihre eigenen Berechtigungssatz definieren, wenn die Vorlagen nicht ausreichen. <br /> <br />|
|Die unterstützte Mindestversion von Microsoft Office ist Office 2010 erfordert die [RMS-freigabeanwendung](http://technet.microsoft.com/library/dn339006.aspx).Microsoft Office für Mac:<ul><li>Microsoft Office für Mac 2016: unterstützt </li><li>Microsoft Office für Mac 2011: nicht unterstützt </li> </ul>|Die unterstützte Mindestversion von Microsoft Office ist Office 2007.Microsoft Office für Mac:<ul><li>Microsoft Office für Mac 2016: unterstützt </li><li>Microsoft Office für Mac 2011: unterstützt </li> </ul>|
|Unterstützt die [RMS-freigabeanwendung](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx) für Windows, Macintosh-Computern und mobilen Geräten.Darüber hinaus unterstützt die RMS-Freigabe:<ul><li>Gemeinsam mit Benutzern in einer anderen Organisation. </li><li>E-Mail-Benachrichtigung können Sie den Absender wissen, wenn jemand versucht, eine geschützte Anlage zu öffnen. </li><li>Ein Dokument, das Nachverfolgen der Website für Benutzer, die umfasst die Möglichkeit, ein Dokument zu widerrufen. </li> </ul>|Unterstützt die [RMS-freigabeanwendung](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx) für Windows, Macintosh-Computern und mobilen Geräten. Allerdings unterstützt Freigabe nicht gemeinsam mit Benutzern in einer anderen Organisation, e-Mail-Benachrichtigung oder das Dokument, das Nachverfolgen von Standort und die Möglichkeit für Benutzer, die Dokumente zu entziehen. <br /> <br />|
|Alle Dateitypen geschützt werden können, mit [native oder allgemeine Schutz bei der Verwendung der RMS-freigabeanwendung](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx). <br /> <br />Für andere Programme, überprüfen Sie die [Client Funktionen Tabelle](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities). <br /> <br />|Alle Dateitypen geschützt werden können, mit [native oder allgemeine Schutz bei der Verwendung der RMS-freigabeanwendung](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx). <br /> <br />Für andere Programme, überprüfen Sie die [Client Funktionen Tabelle](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities). <br /> <br />|
|Die unterstützte Mindestversion des Windows-Clients ist Windows 7. <br /> <br />|Die unterstützte Mindestversion des Windows-Clients ist Windows Vista Service Pack 2. <br /> <br />|
|Unterstützung mobiler Geräte umfasst Windows Phone, Android, iOS und Windows RT. <br /> <br />E-Mail-Unterstützung durch Verwendung von Exchange ActiveSync IRM wird ebenfalls auf allen Plattformen für mobile Geräte unterstützt, die dieses Protokoll unterstützen. <br /> <br />|Unterstützung mobiler Geräte umfasst Windows Phone, Android, iOS und Windows RT und erfordert die [Active Directory Rights Management Services Mobile Device Extension](http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341). <br /> <br />E-Mail-Unterstützung durch Verwendung von Exchange ActiveSync IRM wird auf allen Plattformen für mobile Geräte unterstützt, die dieses Protokoll unterstützen. <br /> <br />|
|Unterstützt Multi-Factor Authentication (MFA) von Computern und mobilen Geräten. <br /> <br />Weitere Informationen finden Sie im Abschnitt [Multi-factor authentication (MFA) and Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_MFA) des Themas [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). <br /> <br />|Smartcard-Authentifizierung unterstützt, wenn IIS so konfiguriert ist, um Zertifikate anzufordern. <br /> <br />|
|Unterstützt den Kryptografiemodus 2 ohne zusätzliche Konfiguration, die höhere Sicherheit für Schlüssellängen und Algorithmen für die Verschlüsselung bereitstellt. <br /> <br />Weitere Informationen finden Sie unter den [Cryptographic controls for signing and encryption](../../ems/AADRightsMgmt/Comparing-Azure-Rights-Management-and-AD-RMS.md#BKMK_CryptographicControls) in diesem Thema und [AD RMS-Kryptografiemodi](http://go.microsoft.com/fwlink/?LinkId=266659). <br /> <br />|Unterstützt den Kryptografiemodus 1 standardmäßig und erfordert zusätzliche Konfiguration zur Unterstützung des Kryptografiemodus 2 für erhöhte Sicherheit. <br /> <br />Weitere Informationen finden Sie unter den [Cryptographic controls for signing and encryption](../../ems/AADRightsMgmt/Comparing-Azure-Rights-Management-and-AD-RMS.md#BKMK_CryptographicControls) in diesem Thema und [AD RMS-Kryptografiemodi](http://go.microsoft.com/fwlink/?LinkId=266659). <br /> <br />|
|Unterstützt die Migration von AD RMS auf AD RMS erforderlich:<ul><li>[Migration von AD RMS zu Azure Rights Management](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md) </li><li>[Außerbetriebsetzen und Deaktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Decommissioning-and-Deactivating-Azure-Rights-Management.md) </li> </ul>|Unterstützt die Migration von Azure RMS und Azure RMS:<ul><li>[Außerbetriebsetzen und Deaktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Decommissioning-and-Deactivating-Azure-Rights-Management.md) </li><li>[Migration von AD RMS zu Azure Rights Management](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md) </li> </ul>|
|Erfordert eine RMS-Lizenz, um Inhalte zu schützen. Keine RMS-Lizenz ist erforderlich für die Nutzung der Inhalte, die von Azure RMS geschützt wurden (einschließlich der Benutzer aus einer anderen Organisation). <br /> <br />Weitere Informationen finden Sie unter der [Cloud subscriptions that support Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_SupportedSubscriptions) Abschnitt    [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). <br /> <br />|Erfordert eine RMS-Lizenz, um Inhalte zu schützen und Inhalte verwenden, die von AD RMS geschützt wurde. <br /> <br />Weitere Informationen über die Lizenzierung für AD RMS finden Sie unter [-Clientzugriffslizenzen und Management-Lizenzen](https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx) allgemeine Informationen, sondern wenden Sie sich an Ihrem Microsoft-Partner oder Microsoft-spezifische Informationen. <br /> <br />|

## <a name="BKMK_CryptographicControls"></a>Kryptografische Steuerelemente für Signierung und Verschlüsselung
[!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] verwendet immer RSA 2048 für alle Kryptografie mit öffentlichem Schlüssel und SHA-256 für Signaturvorgänge. Im Vergleich dazu unterstützt AD RMS RSA 1024 und RSA 2048 und SHA-1 oder SHA-256 für Signaturvorgänge.

Beide [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] und AD RMS verwenden AES 128 für symmetrische Verschlüsselung.

[!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)]mit FIPS 140-2 kompatibel ist, wenn Ihr mandantenschlüssel erstellt und verwaltet von Microsoft (Standard), oder wenn Sie Ihren eigenen mandantenschlüssel (bekannt als BYOK) verwalten. Weitere Informationen zum Verwalten Ihres mandantenschlüssels finden Sie unter [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

## Siehe auch
[Erste Schritte mit Azure Rights Management](../../ems/AADRightsMgmt/Getting-Started-with-Azure-Rights-Management.md)

