---
title: H&#228;ufig gestellte Fragen zur Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
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
# H&#228;ufig gestellte Fragen zur Azure Rights Management
Einige häufig gestellte Fragen zu Microsoft [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)], das auch als Azure RMS bezeichnet wird:

Prüfen Sie zunächst [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). Darin sind Informationen über Cloud-Abonnementoptionen enthalten, und es wird gezeigt, wie Sie Ihre lokalen Server mit Azure RMS verwenden können, welche Bereitstellungsszenarien zurzeit nicht unterstützt werden sowie welche Geräte und Anwendungen Azure RMS unterstützen. Zudem enthält das Thema einen Link, wenn Sie eine Liste von IP-Adressen und Domänennamen für Firewalls oder Proxyserver benötigen. Es kann ferner sinnvoll sein, die anderen Themen im Abschnitt [Erste Schritte mit Azure Rights Management](../../ems/AADRightsMgmt/Getting-Started-with-Azure-Rights-Management.md) anzusehen, um ein grundlegendes Verständnis dafür zu entwickeln, wie [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] den Schutz der Daten Ihrer Organisation unterstützen kann, wie es sich im Vergleich zur lokalen Version der Active Directory-Rechteverwaltungsdienste verhält und welche Begriffe und Abkürzungen für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] spezifisch sind.

Wenn Sie dann bereit sind, Azure RMS selbst auszuprobieren oder es für Ihre Organisation bereitzustellen, verwenden Sie die [Roadmap für die Bereitstellung von Azure Rights Management](../../ems/AADRightsMgmt/Azure-Rights-Management-Deployment-Roadmap.md), die eine Liste mit Schritten und Links zu weiteren Informationen sowie Anweisungen zur Umsetzung enthält.

Weitere Informationen, Ressourcen und Supportoptionen finden Sie unter [Informationen und Support für Azure Rights Management](../../ems/AADRightsMgmt/Information-and-Support-for-Azure-Rights-Management.md).

Ja. Azure RMS kann in Ihre lokalen Server, etwa Exchange Server, SharePoint und Windows-Dateiserver, integriert werden. Dazu verwenden Sie den [Rights Management-Connector](https://technet.microsoft.com/library/dn375964.aspx). Sie können Ihre Active Directory-Domänencontroller auch mit Azure AD synchronisieren und zusammenführen, um eine übergangslosere Authentifizierungshandhabung für Benutzer zu erreichen. Dazu können Sie beispielsweise [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) verwenden.

Azure RMS generiert und verwaltet XrML-Zertifikate automatisch nach Bedarf, sodass es keine lokale PKI verwendet. Weitere Informationen dazu, wie Azure RMS Zertifikate verwendet, finden Sie im Abschnitt [Walkthrough of how Azure RMS works: First use, content protection, content consumption](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md#BKMK_Walthrough) im Thema [Was ist Azure Rights Management?](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md).

Ja, und das Gute ist, dass Benutzer über zwei Exchange-Bereitstellungen hinweg E-Mails und Anlagen nahtlos schützen sowie geschützte E-Mails und Anlagen nutzen können. Führen Sie für diese Konfiguration folgende Schritte aus: [Aktivieren von Azure RMS](https://technet.microsoft.com/library/jj658941.aspx), [Aktivieren von IRM für Exchange Online](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx) und [Bereitstellen und Konfigurieren des RMS-Connectors](https://technet.microsoft.com/library/dn375964.aspx) für Exchange Server.

Nein, Sie behalten immer die Kontrolle über Ihre Daten und können weiterhin darauf zugreifen, selbst wenn Sie sich entscheiden, Azure RMS nicht mehr zu verwenden. Weitere Informationen finden Sie unter [Außerbetriebsetzen und Deaktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Decommissioning-and-Deactivating-Azure-Rights-Management.md).

Bevor Sie Ihre Azure RMS-Bereitstellung außer Betrieb setzen, würden wir jedoch gerne erfahren bzw. verstehen, warum Sie diese Entscheidung getroffen haben. Wenn Azure RMS Ihren geschäftlichen Anforderungen nicht gerecht wird, können Sie Kontakt mit uns aufnehmen, um zu erfahren, ob in naher Zukunft neue Funktionen geplant oder ob Alternativen verfügbar sind. Senden Sie eine E-Mail-Nachricht an [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS). Wir freuen uns darauf, Ihre technischen und geschäftlichen Anforderungen mit Ihnen zu besprechen.

Ja, hat Azure RMS hat hierfür Steuerelemente zum Einbinden (Onboarding) von Benutzern. Weitere Informationen finden Sie im Thema [Configuring onboarding controls for a phased deployment](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md#BKMK_OnboardingControls) im Abschnitt [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md).

Einer der größten Vorteile von Azure RMS besteht darin, dass es B2B-Zusammenarbeit unterstützt, ohne dass Sie explizite Vertrauensstellungen für jede Partnerorganisation konfigurieren müssen, denn Azure AD übernimmt die Authentifizierung für Sie.

Es gibt keine Verwaltungsoption, mit der verhindert werden kann, dass Benutzer Dokumente geschützt für bestimmte Organisationen freigeben. Angenommen, Sie möchten eine Organisation blockieren, der Sie nicht vertrauen oder die ein konkurrierendes Unternehmen hat. Azure RMS daran zu hindern, geschützte Dokumente an Benutzer in dieser Organisationen zu senden, wäre nicht sinnvoll, da Benutzer ihre Dokumente dann ungeschützt freigeben würden, und dies ist wahrscheinlich genau das, was in diesem Szenario nicht geschehen soll! Beispielsweise könnten Sie nicht erkennen, wer vertrauliche Unternehmensdokumente für welche Benutzer in dieser Organisation freigibt, wogegen Sie dies erkennen können, wenn das Dokument (oder die E-Mail) durch Azure RMS geschützt wird.

Azure RMS verwendet immer ein Azure Active Directory-Konto und eine zugeordnete E-Mail-Adresse für die Benutzerauthentifizierung, wodurch sich eine nahtlose Business-to-Business-Zusammenarbeit für Administratoren ergibt. Wenn die andere Organisation Azure-Dienste verwendet, haben Benutzer bereits Konten in Azure Active Directory, selbst wenn diese Konten lokal erstellt und verwaltet und dann mit Azure synchronisiert werden.  Wird in der Organisation Office 365 verwendet, verwendet dieser Dienst (im Hintergrund) ebenfalls Azure Active Directory für die Benutzerkonten.  Wenn die Organisation des Benutzers keine verwalteten Konten in Azure hat, können sich Benutzer für [RMS for Individuals](https://technet.microsoft.com/library/dn592127.aspx) registrieren. Dadurch werden ein nicht verwalteter Azure-Mandant und ein Verzeichnis für die Organisation mit einem Konto für den Benutzer erstellt, sodass dieser Benutzer dann für Azure RMS authentifiziert werden kann.

Die Authentifizierungsmethode für diese Konten kann unterschiedlich sein, je nachdem, wie der Administrator in der anderen Organisation die Azure Active Directory-Konten konfiguriert hat. Beispielsweise können Kennwörter, die für diese Konten erstellt wurden, Multi-Factor Authentication (MFA, mehrstufige Authentifizierung), Verbund oder Kennwörter verwendet werden, die in Active Directory-Domänendienste erstellt und dann mit Azure Active Directory synchronisiert wurden.

Ja.  Ein Erstellen von benutzerdefinierten Vorlagen, die Endbenutzer (und Administratoren) in Anwendungen auswählen können, ermöglicht es Benutzern, schnell und problemlos Informationsschutz anzuwenden, indem sie vordefinierte Richtlinien verwenden, die Sie definiert haben. Eine der Einstellungen in der Vorlage bestimmt, wer auf den Inhalt zugreifen kann, und Sie können Benutzer und Gruppen aus Ihrer Organisation sowie Benutzer angeben, die nicht zu Ihrer Organisation gehören.

Wie Sie die Benutzer angeben, die nicht zu Ihrer Organisation gehören, hängt davon ab, ob Sie die Vorlagen aus dem Azure-Portal oder mithilfe von Windows PowerShell konfigurieren. Dabei stehen folgende Optionen zur Auswahl:

- **Aus dem Azure-Portal**:  Erstellen Sie im Azure-Verzeichnis Kontaktkonten für diese Benutzer, und konfigurieren Sie diese Konten mit den externen E-Mail-Adressen der Benutzer. Dann können Sie, wenn Sie die Vorlagen konfigurieren, diese Benutzer auf dieselbe Weise auswählen wie Benutzer aus Ihrer eigenen Organisation.

- **Windows PowerShell**:    Geben Sie die externen E-Mail-Adressen in einem Rechtedefinitionsobjekt an, das Sie dann beim Erstellen oder Aktualisieren einer Vorlage verwenden. Sie geben das Rechtedefinitionsobjekt an, indem Sie den -RightsDefinition-Parameter im [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)-Cmdlet (für eine neue Vorlage) oder im [Set AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)-Cmdlet (wenn Sie eine vorhandene Vorlage ändern) verwenden.

Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md).

Eine Liste der unterstützten Geräte finden Sie im Abschnitt [Client devices that support Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_SupportedDevices) im Thema [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). Da derzeit nicht alle unterstützten Geräte alle RMS-Funktionen unterstützen, sehen Sie sich auch die [Client device capabilities](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_ClientCapabilities)-Tabelle im gleichen Thema an.

Azure RMS kann alle Dateitypen unterstützen. Für Text-, Bild-, Microsoft Office-Dateien (Word, Excel, PowerPoint), PDF-Dateien und einige andere Anwendungsdateitypen stellt Azure RMS systemeigenen Schutz bereit, der Verschlüsselung und die Durchsetzung von Rechten (Berechtigungen) umfasst. Für alle anderen Anwendungen und Dateitypen bietet generischer Schutz Dateiverkapselung und Authentifizierung, damit überprüft wird, ob ein Benutzer zum Öffnen der Datei autorisiert ist.

Eine Liste der Dateinamenerweiterungen, die systemeigen von Azure RMS unterstützt werden, finden Sie im Abschnitt [Unterstützte Dateitypen und Dateinamenerweiterungen](http://technet.microsoft.com/library/dn339003.aspx) im [Rights Management-Freigabeanwendung – Administratorhandbuch](http://technet.microsoft.com/library/dn339003.aspx). Nicht aufgeführte Dateinamenerweiterungen werden mithilfe der RMS-Freigabeanwendung unterstützt, die automatisch generischen Schutz auf diese Dateien anwendet.

Zunächst hat Azure RMS Migration von einer lokalen Bereitstellung von Rights Management, z. B. AD RMS, nicht unterstützt. Eine solche Migration wird aber jetzt unterstützt.

Weitere Informationen finden Sie unter [Migration von AD RMS zu Azure Rights Management](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md).

Lassen Sie sich durch diese aktuelle Einschränkung nicht von der Azure RMS-Bereitstellung abbringen. Wenn Sie Exchange Online verwenden und BYOK (Bring Your Own Key) nutzen möchten, empfehlen wir, dass Sie Azure RMS im Standard-Schlüsselverwaltungsmodus bereitstellen, in dem Microsoft Ihren Schlüssel generiert und verwaltet. Auf diese Weise erhalten Sie jetzt alle Vorteile bezüglich des Schutzes wichtiger Dateien und E-Mails mit der Option, zu einem späteren Zeitpunkt zu BYOK zu wechseln (z. B. wenn Exchange Online BYOK unterstützt).

Wenn Ihre Unternehmensrichtlinien jedoch erfordern, dass Sie ein Hardwaresicherheitsmodul (HSM) verwenden, und dies würde Ihre Azure RMS-Bereitstellung blockieren, können Sie alternativ jetzt Azure RMS mit BYOK bereitstellen, mit verminderter RMS-Funktionalität für Exchange. Weitere Informationen finden Sie im Thema [BYOK pricing and restrictions](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_Pricing) im Abschnitt [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

Derzeit unterstützt SharePoint RMS-geschützte Dokumente durch Verwenden von IRM-geschützten Bibliotheken, die weder benutzerdefinierte Vorlagen, noch Dokumentnachverfolgung noch einige andere Funktionen unterstützen.  Weitere Informationen finden Sie, wenn Sie den Abschnitt [SharePoint Online and OneDrive for Business: IRM Configuration](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md#BKMK_SharePointOnline) im Thema [Wie Applikationen Azure Rights Management unterstützen](../../ems/AADRightsMgmt/How-Applications-Support-Azure-Rights-Management.md) erweitern.

Wenn Sie an einer bestimmten Funktion interessiert sind, die noch nicht unterstützt wird, sollten Sie die Ankündigungen im [RMS Team Blog](http://blogs.technet.com/b/rms/) verfolgen.

Als Office 365-Administrator konfigurieren Sie dies nicht. Eine solche Konfiguration erfolgt durch Benutzer.

So, wie ein SharePoint-Websiteadministrator IRM für eine SharePoint-Bibliothek, deren Besitzer er ist,aktiviert und konfiguriert, müssen Benutzer IRM für ihre eigenen OneDrive for Business-Bibliotheken aktivieren und konfigurieren.  Allerdings müssen Sie, bevor Websiteadministratoren oder Benutzer diese IRM-Konfiguration vornehmen können, zuerst IRM für Office 365 aktivieren. Anweisungen zu den drei Konfigurationen erhalten Sie, wenn Sie den Abschnitt [SharePoint Online and OneDrive for Business: IRM Configuration](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md#BKMK_SharePointOnline) im Thema [Konfigurieren von Clientanwendungen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md) erweitern.

Nachdem wir viele Bereitstellungen begleitet und uns mit Kunden, Partnern, Beratern und Supportmitarbeitern unterhalten haben – ist das einer der größten Tipps, die wir aus unserer Erfahrung weitergeben können: **Entwerfen Sie einfache Rechterichtlinien, und stellen Sie sie entsprechend bereit**.

Da Azure RMS sichere Freigaben mit praktisch jedermann unterstützt, können Sie bei der Reichweite Ihres Informationsschutzes Ehrgeiz entwickeln. Seien Sie aber konservativ bei Ihren Rechterichtlinien. Für die meisten Organisationen hat die Vermeidung von Datenlecks durch Anwenden der standardmäßigen Rechterichtlinienvorlage, die den Zugriff auf Personen in der eigenen Organisation einschränkt, die größte geschäftliche Bedeutung. Natürlich können Sie Rechte, wenn nötig, viel kleinteiliger festlegen – etwa indem Sie Personen am Drucken, Bearbeiten usw. hindern. Behandeln Sie die kleinteiligeren Einschränkungen jedoch als Ausnahme für Dokumente, die wirklich hohe Sicherheitsstufen benötigen, und implementieren Sie diese restriktiveren Richtlinien nicht am ersten Tag, sondern gehen Sie eher stufenweise vor.

Bei kostenpflichtigen Abonnements, die Azure RMS unterstützen (Office 365, Azure RMS Standalone und Enterprise Mobility Suite), gibt es hinsichtlich der unterstützten RMS-Features einige Unterschiede. Eine Liste der Features finden Sie unter [Vergleich der Angebote zu den Rights Management Services (RMS)](http://technet.microsoft.com/dn858608).

Das kostenlose Abonnement, das Azure RMS unterstützt (RMS für Einzelpersonen), unterstützt das Nutzen von Inhalten, die durch die Azure RMS geschützt sind. Weitere Informationen finden Sie unter [RMS für Einzelpersonen und Azure Rights Management](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md).

Die Antworten auf diese Fragen finden Sie im Thema [RMS für Einzelpersonen und Azure Rights Management](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md).

Verwenden Sie die Administratorfunktion von Azure RMS, über die autorisierte Benutzer volle Besitzerrechte für alle Nutzungslizenzen erhalten, die vom RMS-Mandanten Ihrer Organisation gewährt wurden. Dieselbe Funktion ermöglicht darüber hinaus autorisierten Diensten ggf. die Indizierung und Inspektion von Dateien.

Weitere Informationen finden Sie unter [Konfigurieren von Administratoren für Azure Rights Management und Discovery Services oder Wiederherstellen von Daten](../../ems/AADRightsMgmt/Configuring-Super-Users-for-Azure-Rights-Management-and-Discovery-Services-or-Data-Recovery.md).

Azure RMS unterstützt weitere Dienste und verwendet zusätzliche Dienste. Wenn Sie Informationen zur Azure RMS suchen, jedoch nicht zur Verwendung des Azure RMS-Diensts, sehen Sie sich folgende Ressourcen an:

**Rechtliche Hinweise und Datenschutz:**

- Informationen zur Microsoft Azure-Vereinbarung: [Microsoft Azure-Vereinbarung](http://azure.microsoft.com/support/legal/subscription-agreement/)

- Informationen zum Microsoft Azure-Datenschutz: [Datenschutzerklärung zu Microsoft Azure](http://azure.microsoft.com/support/legal/privacy-statement/)

**Sicherheit, Compliance und Überwachung:**

Siehe den Abschnitt [Security, compliance, and regulatory requirements](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md#BKMK_RMScompliance) im Thema [Was ist Azure Rights Management?](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md). Zusätzlich:

- Informationen zu externen Zertifizierungen für Azure RMS: [Microsoft Azure Trust Center](http://azure.microsoft.com/support/trust-center/)

- FIPS 140-Informationen: [FIPS 140-Überprüfung](https://technet.microsoft.com/library/security/cc750357.aspx)

**Vereinbarungen zum Servicelevel:**

- Vereinbarung zum Servicelevel für Azure RMS, ausgewählt nach Land: [Vereinbarung zum Servicelevel](http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)

- Vereinbarung zum Servicelevel für Azure Active Directory: [Vereinbarungen zum Servicelevel](http://azure.microsoft.com/support/legal/sla/)

**Dokumentation:**

- Azure Active Directory-Dokumentationswebsite: [Azure Active Directory](http://azure.microsoft.com/documentation/services/active-directory/)

- Azure Active Directory-Bibliothek: [Azure Active Directory](http://msdn.microsoft.com/library/azure/jj673460.aspx)

- Office 365-Bibliothek: [Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

Verwenden Sie die Links und Ressourcen, die unter [Informationen und Support für Azure Rights Management](../../ems/AADRightsMgmt/Information-and-Support-for-Azure-Rights-Management.md) aufgeführt werden.

Darüber hinaus gibt es häufig gestellte Fragen (FAQs) für Endbenutzer:

- [Häufig gestellte Fragen zur Rights Management-Freigabeanwendung für Windows](https://technet.microsoft.com/dn467883)

- [Häufig gestellte Fragen (FAQ) zur Rights Management-Freigabeanwendung für mobile und für Mac-Plattformen](https://technet.microsoft.com/dn451248)

- [Häufig gestellte Fragen zur Dokumentenverfolgung](http://go.microsoft.com/fwlink/?LinkId=523977)

Diese FAQ-Seite wird regelmäßig aktualisiert. Dabei werden die neuen Beiträge in den Ankündigungen zu den monatlichen Dokumentationsaktualisierungen im Blog des [RMS-Teams (Microsoft Rights Management)](http://blogs.technet.com/b/rms/) aufgelistet.

> [!TIP]
> Sie können das [Tag "docs"](http://blogs.technet.com/b/rms/archive/tags/docs/) für den Blog verwenden, um diese Dokumentationsankündigungen leichter zu finden.

## Siehe auch
[Erste Schritte mit Azure Rights Management](../../ems/AADRightsMgmt/Getting-Started-with-Azure-Rights-Management.md)

