---
title: Wie Applikationen Azure Rights Management unterst&#252;tzen
ms.custom: na
ms.date: 03/02/2016
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
translation.priority.ht: 
  - bg-bg
  - da-dk
  - de-de
  - el-gr
  - es-es
  - et-ee
  - fi-fi
  - fr-fr
  - hr-hr
  - it-it
  - ja-jp
  - kk-kz
  - ko-kr
  - lt-lt
  - lv-lv
  - nb-no
  - nl-nl
  - pt-br
  - ro-ro
  - ru-ru
  - sk-sk
  - sl-si
  - sr-latn-cs
  - sv-se
  - th-th
  - tr-tr
  - uk-ua
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - hu-hu
  - pl-pl
  - pt-pt
---
# Wie Applikationen Azure Rights Management unterst&#252;tzen
Die folgenden Informationen sollen Ihnen dabei helfen zu verstehen, wie die Anwendungen Ihrer Endbenutzer (wie Office-Anwendungen, Word, Excel, PowerPoint und Outlook) und die Dienste (wie Exchange und SharePoint) Microsoft [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] verwenden können, um die Daten Ihrer Organisation besser zu schützen:

- [RMS sharing application for Windows and mobile platforms](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_SharingAppIntro)

- [Office applications: Word, Excel, PowerPoint, Outlook](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_OfficeAppsIntro)

   - [Exchange Online and Exchange Server](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_ExchangeIntro)

   - [SharePoint Online and SharePoint Server](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_SharePointIntro)

- [File servers that run Windows Server and use file classification infrastructure (FCI)](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_FCIIntro)

- [Other applications that support the RMS APIs](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md#BKMK_APIAppsIntro)

> [!NOTE]
> Informationen zur Überprüfung der Anwendungen und Versionen, die von [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS) unterstützt werden, finden Sie unter [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md).

In manchen Fällen wird Informationsschutz automatisch gemäß den von Ihnen konfigurierten Richtlinien angewendet. Dies ist beispielsweise bei SharePoint-Bibliotheken, klassifizierten Dateien und Exchange-Transportregeln der Fall. In anderen Fällen müssen Benutzer Informationsschutz selbst aus ihren Anwendungen heraus anwenden, entweder durch Auswählen einer Vorlage oder durch Auswahl bestimmter Optionen. Dies ist beispielsweise der Fall, wenn Benutzer eine Datei per E-Mail teilen oder eine Datei direkt schützen, indem sie den Zugriff oder die Verwendung auf ausgewählte Benutzer bzw. auf Benutzer außerhalb der Organisation einschränken.

Vorlagen erleichtern den Benutzern (und den Administratoren, die Richtlinien konfigurieren) das Anwenden der richtigen Schutzstufe und das Einschränken des Zugriffs auf Personen innerhalb Ihrer Organisation. Obwohl [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] zwei Standardvorlagen enthält, möchten Sie vermutlich benutzerdefinierte Vorlagen erstellen, damit Benutzer weniger Zeit darauf verwenden, einzelne Optionen angeben zu müssen. Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md).

In den Fällen, in denen Benutzer Informationsschutz selber anwenden müssen, stellen Sie sicher, dass Sie ihnen Anweisungen und Anleitungen geben, wie und wann dies zu erfolgen hat. Die Anweisungen sollten spezifisch für die Anwendung und Version sein, die verwendet wird, sowie für deren Verwendungsart. Außerdem sollte die Anleitung dafür, wann und wie Informationschutz angewendet werden sollte, für Ihr Geschäft geeignet sein. Weitere Informationen finden Sie unter [Unterstützung von Benutzern beim Schützen von Dateien mithilfe von Azure Rights Management](../../ems/AADRightsMgmt/Helping-Users-to-Protect-Files-by-Using-Azure-Rights-Management.md).

Informationen dazu, wie diese Anwendungen für Azure RMS konfiguriert werden, finden Sie unter [Konfigurieren von Clientanwendungen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md).

> [!TIP]
> Beispiele und Bildschirmfotos von Anwendungen, die Azure RMS verwenden, finden Sie im Thema [Was ist Azure Rights Management?](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md) im Abschnitt [Azure RMS in action: What administrators and users see](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md#BKMK_RMSpictures).

## <a name="BKMK_SharingAppIntro"></a>RMS-Freigabeanwendung für Windows und mobile Plattformen
Die RMS-Freigabeanwendung ist eine kostenlose, herunterladbare Anwendung, die für die Unterstützung von Office 2010 erforderlich ist, aber auch für Windows-Computer, Mac-Computer und mobile Geräte empfohlen wird. Einer ihrer Vorteile besteht darin, dass sie generischen Schutz für Anwendungen und Dateien anwenden kann, die keine systemeigene Unterstützung für [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] bieten, was bedeutet, dass alle Dateien geschützt werden können. Weitere Informationen zu den verschiedenen Schutzstufen finden Sie im Abschnitt [Schutzstufen – systemeigen und generisch](http://technet.microsoft.com/library/dn339003.aspx#BKMK_LevelsofProtection) im [Administratorhandbuch der Rights Management-Freigabeanwendung](http://technet.microsoft.com/library/dn339003.aspx).

Wenn Benutzer ihre Dateien mit der RMS-Freigabeanwendung schützen, können sie auch von ihnen geschützte Dokumente nachverfolgen und bei Bedarf den Zugriff hierauf widerrufen. Hierfür wird die [Website zum Nachverfolgen von Dokumenten](http://go.microsoft.com/fwlink/?LinkId=529562) verwendet.

Bei Windows-Computern integriert sich die RMS-Freigabeanwendung unauffällig in die bereits von Benutzern verwendeten Anwendungen und erweitert deren Funktionsumfang:

- Ein Office-Add-In für Word, Excel, PowerPoint und Outlook wird installiert. Dieses bietet Benutzern im Menüband eine Schaltfläche **Geschützt freigeben**, die ein bequem zu verwendendes Dialogfeld mit Einstellungen aufruft, die am häufigsten zum Schützen von Dateien, die per E-Mail gesendet werden, verwendet werden. Diese Schaltfläche bietet zudem eine schnelle Möglichkeit für den Zugriff auf die Website zum Nachverfolgen von Dokumenten.

- Eine neue Kontextmenüoption für Datei-Explorer. Diese bietet Benutzern eine Option **Direkt schützen**, die ein bequem zu verwendendes Dialogfeld mit Einstellungen aufruft, die am häufigsten zum Schützen von Dateien verwendet werden, die auf einem Datenträger gespeichert sind.

- Eine Anzeige zum Öffnen von Dateien, die durch [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] geschützt sind. Diese Anzeige wird automatisch aufgerufen, wenn keine andere Anwendung installiert ist, mit der die geschützte Datei geöffnet werden kann.

- Back-End-Konfiguration für Office 2010, die Word, Excel, PowerPoint und Outlook aus dieser Suite die nahtlose Zusammenarbeit mit [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] gestattet.

Obwohl die RMS-Freigabeanwendung für Windows über die [Microsoft Rights Management-Seite](http://go.microsoft.com/fwlink/?LinkId=303970) auf einzelnen Computer heruntergeladen und installiert werden kann, wird auch eine Unternehmensbereitstellung mit automatischer Installation und benutzerdefinierter Konfiguration unterstützt. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Rights Management-Freigabeanwendung – Administratorhandbuch](http://technet.microsoft.com/library/dn339003.aspx)

- [Rights Management-Freigabeanwendung – Benutzerhandbuch](http://technet.microsoft.com/library/dn339006.aspx)

Die RMS-Freigabeanwendung für mobile Geräte unterstützt die gängigsten verwendeten mobilen Geräte wie iPad und iPhone, Android, Windows Phone und Windows RT. Benutzer können diese App aus dem relevanten Store herunterladen, zu denen es Links auf der Seite [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) gibt.

## <a name="BKMK_OfficeAppsIntro"></a>Office-Anwendungen: Word, Excel, PowerPoint, Outlook
Diese Anwendungen bieten systemeigene Unterstützung für Rights Management durch Verwendung von IRM (Information Rights Management, Verwaltung von Informationsrechten) und ermöglichen Benutzern das Schützen eines gespeicherten Dokuments oder einer zu sendenden E-Mail. Benutzer können Vorlagen anwenden oder stark angepasste Einstellungen für Zugriff, Rechte und Nutzungseinschränkungen verwenden. Beispielsweise können Benutzer eine Datei so konfigurieren, dass nur Personen in Ihrer Organisation darauf zugreifen können, oder kontrollieren, ob die Datei bearbeitet werden kann, oder die Datei auf schreibgeschützt einschränken oder das Drucken der Datei verhindern. Für Dateien mit zeitlicher Relevanz kann eine Ablaufzeit konfiguriert werden (direkt von Benutzern oder durch Anwenden einer Vorlage), nach deren Erreichen kein Zugriff auf die Datei mehr möglich ist. Für Outlook können Benutzer außerdem die Option **Nicht weiterleiten** auswählen, um Datenlecks zu verhindern.

### <a name="BKMK_ExchangeIntro"></a>Exchange Online und Exchange Server
Wenn Sie Exchange Online oder Exchange Server verwenden, können Sie IRM-Integration (Verwaltung von Informationsrechten) verwenden, die zusätzliche Informationsschutzlösungen bereitstellt:

- **Exchange ActiveSync IRM**, sodass mobile Geräte E-Mails schützen und geschützte E-Mails nutzen können.

- RMS-Unterstützung für die **Outlook Web App**, ähnlich implementiert wie der Outlook-Client, sodass Benutzer E-Mails per Vorlagen oder durch Angabe einzelner Optionen schützen und Benutzer geschützte E-Mails, die an sie gesendet werden, lesen und verwenden können.

- **Schutzregeln** für Outlook-Clients, die ein Administrator so konfiguriert, dass sie automatisch RMS-Vorlagen auf E-Mails für angegebene Empfänger anwenden. Wenn beispielsweise interne E-Mails an Ihre Rechtsabteilung gesendet werden, können sie nur von Mitgliedern der Rechtsabteilung gelesen und nicht weitergeleitet werden. Benutzer sehen den auf die E-Mail angewendeten Schutz vor dem Senden und können diesen standardmäßig entfernen, falls sie ihn für unnötig halten. E-Mails werden vor dem Senden verschlüsselt. Weitere Informationen finden Sie unter [Outlook-Schutzregeln](http://technet.microsoft.com/library/dd638178%28v=exchg.150%29.aspx) und [Erstellen einer Outlook-Schutzregel](http://technet.microsoft.com/library/dd638196%28v=exchg.150%29.aspx) in der Exchange-Bibliothek.

- **Transportregeln**, die ein Administrator so konfiguriert, dass automatisch auf Grundlage von Eigenschaften wie Absender, Empfänger, Nachrichtenbetreff und Inhalt RMS-Vorlagen auf E-Mails angewendet werden. Diese Regeln ähneln dem Konzept nach Schutzregeln, doch können Benutzer den Schutz nicht entfernen, sie können auf Outlook Web Access und auf von mobilen Geräten gesendete E-Mails angewendet werden, und die E-Mails werden vor dem Senden vom Client nicht verschlüsselt. Weitere Informationen finden Sie unter [Erstellen einer Transportschutzregel](http://technet.microsoft.com/library/dd302432.aspx) in der Exchange-Bibliothek.

- **DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust)**, die Bedingungssätze enthalten, um E-Mails zu filtern und Maßnahmen zur Verhinderung von Datenverlusten bei vertraulichen oder sensiblen Inhalten zu ergreifen (z. B. personenbezogene Daten oder Kreditkarteninformationen). Richtlinientipps können verwendet werden, wenn sensible Daten erkannt werden, um Benutzer darauf aufmerksam zu machen, dass sie eventuell Informationsschutz anwenden sollten, basierend auf den in der E-Mail enthaltenen Informationen. Weitere Informationen finden Sie unter [Data Loss Prevention](http://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx) (Verhinderung von Datenverlust) in der Exchange-Bibliothek.

- **Office 365-Nachrichtenverschlüsselung**, die Transportregeln verwendet, um verschlüsselte E-Mails an Personen außerhalb Ihres Unternehmens zu senden, wobei die E-Mail in einem Browser gelesen wird, dessen Oberfläche Outlook Web App ähnelt. Sie können den Haftungsausschluss- und Kopfzeilentext in den verschlüsselten E-Mails Ihres Unternehmens anpassen und sogar Ihr Firmenlogo hinzufügen. Weitere Informationen finden Sie unter [Office 365-Nachrichtenverschlüsselung](http://office.microsoft.com/o365-message-encryption-FX104179182.aspx) auf der Office-Website.

Wenn Sie Exchange Server verwenden, können Sie die Informationsschutzfeatures mit [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] verwenden, indem Sie den RMS-Verbindungsdienst bereitstellen, der als Relay zwischen lokalen Servern und dem RMS-Cloud-Dienst fungiert. Weitere Informationen finden Sie unter [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md).

### <a name="BKMK_SharePointIntro"></a>SharePoint Online und SharePoint Server
Wenn Sie SharePoint Online oder SharePoint Server verwenden, können Sie IRM-Integration verwenden, wodurch Administratoren Listen und Bibliotheken schützen können, damit eine Datei, die von einem Benutzer ausgecheckt wird, geschützt ist, sodass nur autorisierte Personen sie entsprechend der von Ihnen angegebenen Informationsschutzregeln anzeigen und verwenden können. So kann die Datei beispielsweise schreibgeschützt sein, das Kopieren von Text deaktivieren, das Speichern einer lokalen Kopie oder das Drucken der Datei verhindern.

Bei Listen und Bibliotheken wird der Informationsschutz immer von einem Administrator und nie von einem Endbenutzer angewendet. Außerdem wird er auf Listen- oder Bibliotheksebene für alle Dokumente in dem betreffenden Container angewendet statt auf einzelne Dateien.  Wenn Sie SharePoint Online verwenden, können die Benutzer IRM auch auf ihre OneDrive for Business-Bibliothek anwenden.

Zuerst muss der IRM-Dienst für SharePoint aktiviert werden. Dann geben Sie die Verwaltung von Informationsrechten für eine Bibliothek an. Im Falle von SharePoint Online und OneDrive for Business können die Benutzer IRM auch für ihre OneDrive for Business-Bibliothek festlegen. SharePoint verwendet keine Richtlinienvorlagen für Rechte. Allerdings stehen SharePoint-Konfigurationseinstellungen zur Wahl, die größtenteils den Einstellungen entsprechen, die Sie in Vorlagen angeben können.

Wenn Sie SharePoint Server verwenden, können Sie die Informationsschutzfeatures mit [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] verwenden, indem Sie den RMS-Verbindungsdienst bereitstellen, der als Relay zwischen lokalen Servern und dem RMS-Cloud-Dienst fungiert. Weitere Informationen finden Sie unter [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md).

> [!NOTE]
> Gegenwärtig gibt es einige Beschränkungen bei der Verwendung von IRM mit SharePoint:
> 
> - Sie können weder die standardmäßigen noch die benutzerdefinierten Vorlagen verwenden, die Sie im Azure-Portal verwalten.
> - Dateien mit der Dateinamenerweiterung PPDF für geschützte PDF-Dateien werden nicht unterstützt. Dateien mit der Dateinamenerweiterung PDF, die systemintern von RMS geschützt wurden, werden unterstützt, wenn Sie einen PDF-Reader verwenden, der eine systemeigene Unterstützung von RMS bietet.
> - Da Office auf mobilen Geräten RMS noch nicht unterstützt, muss auf diesen Geräten ein Browser zum Anzeigen von mit RMS geschützten Dateien verwendet werden, und die Dateien sind schreibgeschützt.

Weitere Informationen zu Azure RMS in Verbindung mit SharePoint finden Sie im folgenden Beitrag im Office-Blog: [Neuerungen bei Information Rights Management in SharePoint und SharePoint Online](http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/)

## <a name="BKMK_FCIIntro"></a>Dateiserver, die unter Windows Server ausgeführt werden und die Dateiklassifizierungsinfrastruktur verwenden
Wenn Sie Windows Server für die Verwendung der Dateiklassifizierungsinfrastruktur konfigurieren, kann dieses „Ressourcen-Manager für Dateiserver“-Feature lokale Dateien untersuchen und bestimmen, ob sie sensible Daten enthalten. Dateien, die dieses Kriterien erfüllen, werden mit Klassifizierungseigenschaften gekennzeichnet, die ein Administrator definiert. Die Dateiklassifizierungsinfrastruktur kann dann automatisch entsprechend der Klassifizierung Aktionen vornehmen. Eine dieser Aktionen umfasst die Anwendung von Informationsschutz mithilfe von [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] sowie die Bereitstellung des Rights Management-Connectors (auch als RMS-Verbindungsdienst bezeichnet). Office-Dateien werden von Azure RMS dann automatisch geschützt.

Zum Schützen aller Dateitypen verwenden Sie nicht den RMS-Verbindungsdienst, sondern führen stattdessen ein Windows PowerShell-Skript aus, das Cmdlets aus dem [RMS Protection-Tool](https://www.microsoft.com/en-us/download/details.aspx?id=47256) verwendet.

Die Klassifizierungsrichtlinien sind vollständig konfigurierbar und in hohem Maße erweiterbar, sodass Sie potenzielle Datenlecks durch nicht autorisierte und autorisierte Benutzer verhindern können. Sie können damit sogar das Risiko potenzieller Datenlecks durch Netzwerkadministratoren verringern, weil Sie Richtlinien konfigurieren können, die nicht erfordern, dass diese Administratoren Zugriff auf die Dateien haben.

Anweisungen zum Bereitstellen und Konfigurieren des RMS-Connectors für Office-Dateien finden Sie unter [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md).

Anweisungen zum Verwenden des Windows PowerShell-Skripts für alle Dateitypen finden Sie unter [RMS-Schutz mit Windows Server-Dateiklassifizierungsinfrastruktur &#40;FCI&#41;](../../ems/RMS_Client/RMS-Protection-with-Windows-Server-File-Classification-Infrastructure--FCI-.md).

## <a name="BKMK_APIAppsIntro"></a>Sonstige Anwendungen, die die RMS-APIs unterstützen
Durch die Verwendung des RMS SDKs können Ihre internen Entwickler Branchenanwendungen schreiben, die systemeigene Unterstützung für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] enthalten. Wie Informationsschutz in diese Anwendungen integriert wird, hängt davon ab, wie sie geschrieben sind. Beispielsweise kann die Integration automatisch, mit nur einem Minimum an erforderlicher Benutzerinteraktion angewendet werden, oder Benutzer können zur Erzeugung einer stärker angepassten Erfahrung aufgefordert werden, Einstellungen für die Anwendung von Informationsschutz auf Dateien zu konfigurieren. Weitere Informationen zum SDK finden Sie unter [Microsoft Rights Management SDK](http://msdn.microsoft.com/library/hh552972%28v=vs.85%29.aspx).

Ähnlich bieten zahlreiche Softwarehersteller Anwendungen für die Bereitstellung von Informationsschutzlösungen an, auch bekannt als ERM-Produkte (Enterprise Rights Management). Ein beliebtes Beispiel ist ein PDF-Reader, der [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] für bestimmte Plattformen unterstützt. Mithilfe der Tabelle im Abschnitt [Client device capabilities](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_ClientCapabilities) des Themas [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md) finden Sie Anwendungen, die RMS unterstützen (für RMS aktivierte Anwendungen). Führen Sie dann eine Websuche durch, um die Anwendung zu kaufen oder herunterzuladen.

> [!TIP]
> Neu freigegebene Anwendungen finden Sie in den RMS-Communitykanälen, die unter [Informationen und Support für Azure Rights Management](../../ems/AADRightsMgmt/Information-and-Support-for-Azure-Rights-Management.md) aufgelistet sind.

## Siehe auch
[Erste Schritte mit Azure Rights Management](../../ems/AADRightsMgmt/Getting-Started-with-Azure-Rights-Management.md)

