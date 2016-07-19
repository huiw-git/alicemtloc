---
title: Migration von AD RMS zu Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 828cf1f7-d0e7-4edf-8525-91896dbe3172
translation.priority.ht: 
  - es-es
  - fr-fr
  - it-it
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - de-de
  - ja-jp
---
# Migration von AD RMS zu Azure Rights Management
Verwenden Sie die folgende Gruppe von Anweisungen, um die Active Directory-Rechteverwaltungsdienste (AD RMS)-Bereitstellung zu Azure Rights Management (Azure RMS) zu migrieren. Benutzer haben weiterhin Zugriff auf Dokumente und e-Mail-Nachrichten, die Ihre Organisation mithilfe von AD RMS geschützt und neu geschützte Inhalte Azure RMS verwenden, nach der Migration.

Nicht sicher, ob diese AD RMS-Migration für Ihre Organisation geeignet ist?

- Eine Einführung in Azure RMS, die geschäftlichen Probleme, die sie lösen kann, Administratoren und Benutzern Eindruck und wie es funktioniert, finden Sie unter [Was ist Azure Rights Management?](../../ems/AADRightsMgmt/What-is-Azure-Rights-Management-.md)

- Einen Vergleich von Azure RMS mit AD RMS finden Sie unter [Vergleich von Azure Rights Management und AD RMS](../../ems/AADRightsMgmt/Comparing-Azure-Rights-Management-and-AD-RMS.md).

Vor Beginn der Migration zu Azure RMS, stellen Sie sicher, dass die folgenden erforderlichen Komponenten vorhanden sind und Sie Einschränkungen verstehen.

|Anforderung <br /> <br />|Weitere Informationen <br /> <br />|
|---------------|-------------------------|
|Unterstützte RMS-Bereitstellung <br /> <br />|Alle AD RMS-Versionen von Windows Server 2008 und Windows Server 2012 R2 unterstützen eine Migration zu Azure RMS:<ul><li>WindowsServer 2008 (X 86 oder X 64) </li><li>Windows Server 2008 R2 (x 64) </li><li>WindowsServer 2012 (x 64) </li><li>Windows Server 2012 R2 (x 64) </li> </ul>________ **Note:** Wenn Sie Windows RMS unter Windows Server 2003 ausführen, werden diese Version des Betriebssystems nicht mehr unterstützt, während 2015. Sie können diese Version von RMS in Azure RMS migrieren, aber dieser Vorgang wird nur unterstützt, wenn das Betriebssystem weiterhin unterstützt wird. Sie könnten dieses Problem zu umgehen importieren die vertrauenswürdige Veröffentlichungsdomäne (TPD) auf eine Version von AD RMS, die unterstützt wird und importieren Sie dann erneut die vertrauenswürdige Veröffentlichungsdomäne, ohne die RMS-1.0-Kompatibilitätsoption. Weitere Informationen über Vertrauenswürdige Veröffentlichungsdomänen finden Sie unter [vertrauenswürdige Veröffentlichungsdomäne](http://technet.microsoft.com/library/dd996639%28v=ws.10%29.aspx)Alle gültige AD RMS-Topologien werden unterstützt:<ul><li>Einzelne Gesamtstruktur, single-RMS-cluster </li><li>Gesamtstruktur, mehrere reine Lizenzierungscluster RMS-Cluster </li><li>Mehrere Gesamtstrukturen, mehrere RMS-Cluster </li> </ul>________ **Note:** Migrieren standardmäßig mehrere RMS-Cluster zu einem einzigen Azure RMS-Mandanten. Wenn Sie möchten, dass die verschiedene RMS-Mandanten, müssen Sie sie als andere Migrationen behandeln. Ein Schlüssel von einem RMS-Cluster kann mehr als eine Azure RMS-Mandanten importiert werden.|
|Alle Anforderungen zum Ausführen von Azure RMS, einschließlich einen Azure RMS-Mandanten (nicht aktiviert) <br /> <br />|Siehe [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). <br /> <br />Obwohl Sie Azure RMS-Mandanten verfügen müssen, bevor Sie von AD RMS migrieren können, empfehlen wir, dass Sie vor der Migration den Rights Management-Dienst nicht aktivieren. Der Migrationsvorgang umfasst dieser Schritt nach Schlüsseln und Vorlagen von AD RMS exportiert und importiert sie in Azure RMS. Jedoch wenn Azure RMS bereits aktiviert wurde, können Sie dennoch von AD RMS migrieren. <br /> <br />|
|Vorbereitung für Azure RMS:<ul><li>Directory-Synchronisierung zwischen Ihrem lokalen Verzeichnis und Azure Active Directory </li><li>E-Mail-aktivierte Gruppen in Azure Active Directory </li> </ul>|Siehe [Vorbereiten für Azure Rights Management](../../ems/AADRightsMgmt/Preparing-for-Azure-Rights-Management.md). <br /> <br />|
|Wenn Sie die Verwaltung von Informationsrechten (IRM) Funktionalität von Exchange Server (z. B. Transportregeln und Outlook Web Access) oder SharePoint Server mit AD RMS verwendet haben:<ul><li>Planen Sie ein kurzer Zeit beim IRM nicht auf diesen Servern zur Verfügung steht </li> </ul>|Sie können weiterhin IRM nach der Migration auf diesen Servern mit Azure RMS zu verwenden. Eine der Migrationsschritte ist jedoch auf den IRM-Dienst vorübergehend zu deaktivieren, installieren und Konfigurieren eines Connectors, konfigurieren Sie den Server neu, und reaktivieren Sie IRM. <br /> <br />Dies ist die einzige Unterbrechung des Diensts während der Migration. <br /> <br />|
Nachteile:

- Obwohl während der Migration unterstützt das Migrieren Ihrer Servers-Lizenzierung Zertifikatschlüssel (SLC) zu einem Hardwaresicherheitsmodul (HSM) für Azure RMS, unterstützt Exchange Online derzeit diese Konfiguration nicht. Sie gegebenenfalls alle IRM-Funktionen mit Exchange Online nach der Migration zu Azure RMS muss Ihren Azure RMS-mandantenschlüssel [von Microsoft verwalteten](http://technet.microsoft.com/library/dn440580.aspx). Alternativ können Sie IRM mit eingeschränkter Funktionalität in Exchange Online ausführen, wenn Azure RMS-Mandanten von Ihnen (BYOK) verwaltet wird. Weitere Informationen zur Verwendung von Exchange Online mit Azure RMS finden Sie unter [Step 6. Configure IRM integration for Exchange Online](#BKMK_Step6Migration) beschrieben.

- Wenn Sie Software und Clients, die nicht mit Azure RMS unterstützt werden, werden sie nicht in der Lage zum Schützen und Nutzung von Inhalten, die von Azure RMS geschützt ist. Die unterstützte Anwendung überprüfen und Clients im Abschnitt der [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md) Thema.

- Wenn Sie Ihren lokalen Schlüssel in Azure RMS als importieren archiviert (nicht festlegen die vertrauenswürdigen Veröffentlichungsdomäne während des Importvorgangs zu den aktiven) und Migrieren von Benutzern in Batches, die für eine Migration in Phasen, Inhalte, die von den migrierten Benutzern neu geschützt ist nicht für Benutzer, die auf AD RMS bleiben zugegriffen werden. Können Sie in diesem Szenario möglichst kurze Zeit beibehalten und Migrieren von Benutzern in logische Gruppen, wenn sie mit anderen zusammenarbeiten, diese zusammen migriert, sind.

   Diese Einschränkung gilt nicht für Sie die vertrauenswürdigen Veröffentlichungsdomäne aktiv während des Importvorgangs festlegen, da alle Benutzer Inhalte mit dem gleichen Schlüssel geschützt werden. Diese Konfiguration wird empfohlen, da sie alle Benutzer unabhängig voneinander und in Ihrem eigenen Tempo migrieren können.

- Wenn Sie mit externen Partnern (z. B. mithilfe von vertrauenswürdigen Benutzerdomänen oder Verbund) arbeiten, müssen sie auch in Azure RMS entweder zur gleichen Zeit wie die Migration oder so bald wie möglich danach migriert werden. Um den Vorgang fortzusetzen, den Zugriff auf Inhalte, die Ihrer Organisation, die zuvor mithilfe von AD RMS geschützt, sie Client Configuration Änderungen vornehmen müssen, die denen ähneln, die Sie vornehmen, und in diesem Dokument enthalten.

   Aufgrund der möglichen Konfigurationsvarianten, die möglicherweise Ihren Partnern, sind genaue Anweisungen für diese Neukonfiguration über den Rahmen dieses Dokuments. Hilfe benötigen wenden Sie sich an Microsoft Customer Support Services (CSS).

|Schritt der Migration <br /> <br />|Weitere Informationen <br /> <br />|
|-------------------------|-------------------------|
|**1. Die Azure RMS-Management-Verwaltungsprogramme herunterladen** <br /> <br />|Anleitungen hierzu finden Sie unter [Step 1: Download the Azure Rights Management Administration Tool](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step1Migration) <br /> <br />|
|**2. Exportieren Sie Konfigurationsdaten aus AD RMS und importieren Sie sie in Azure RMS** <br /> <br />|Sie die Konfigurationsdaten (Schlüssel, Vorlagen, URLs) von AD RMS in einer XML-Datei exportieren und dann diese Datei in Azure RMS mithilfe des Import AadrmTpd Windows PowerShell-Cmdlets hochladen. Je nach Ihrer auf wichtige AD RMS-Konfiguration möglicherweise zusätzliche Schritte erforderlich sein:<ul><li>Software geschützt-Taste, um die Migration von Software geschützt: zentral verwalteten kennwortbasierte Schlüssel in AD RMS verwaltet von Microsoft Azure RMS-Mandanten Schlüssel. Dies ist der einfachste Weg für die Migration, und es sind keine weiteren Schritte erforderlich. </li><li>HSM-geschützte-Taste, um die Migration von HSM-geschützte: Schlüssel, die von einem HSM für AD RMS zu Azure RMS-mandantenschlüssel vom Kunden verwaltet gespeichert sind (der "bring your own Key" oder BYOK-Szenario). Dies erfordert zusätzliche Schritte zum Übertragen des Schlüssels aus Ihrem lokalen Thales HSM an das Azure RMS HSM. </li><li>Migration von HSM-geschützten Schlüssel Software geschützt: zentral verwalteten kennwortbasierte Schlüssel in AD RMS zu Azure RMS-mandantenschlüssel vom Kunden verwaltet (die "bring your own Key" oder BYOK-Szenario). Dies erfordert die meisten Konfiguration, da müssen Sie zuerst Ihren Softwareschlüssel zu extrahieren und in einer lokalen HSM importieren und Sie dann die zusätzlichen Schritte zum Übertragen des Schlüssels aus Ihrem lokalen Thales HSM an das Azure RMS-HSM führen. </li> </ul>Anleitungen hierzu finden Sie unter [Step 2. Export configuration data from AD RMS and import it to Azure RMS](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step2Migration)|
|**3. Aktivieren Sie den RMS-Mandanten** <br /> <br />|Falls möglich, führen Sie diesen Schritt aus, nachdem der Importvorgang und nicht vorher. <br /> <br />Weitere Informationen und eine Anleitung hierzu finden Sie unter [Step 3. Activate your RMS tenant](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step3Migration). <br /> <br />|
|**4. Konfigurieren Sie importierte Vorlagen** <br /> <br />|Wenn Sie die Vorlagen für Benutzerrechterichtlinien importieren, wird deren Status archiviert. Wenn Benutzer sehen und verwenden soll, müssen Sie den Status der Vorlage zur Veröffentlichung in Azure-Verwaltungsportal ändern. <br /> <br />Anleitungen hierzu finden Sie unter [Step 4. Configure imported templates](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step4Migration) <br /> <br />|
|**5. Konfigurieren von Clients für die Verwendung von Azure RMS** <br /> <br />|Vorhandene Windows-Computer müssen neu konfiguriert werden, um den Azure RMS-Dienst anstelle von AD RMS verwenden. Dieser Schritt gilt für Computer in Ihrem Unternehmen sowie für Computer in Partnerorganisationen, wenn eine Verbindung mit ihnen Virtualisierungssoftware, während Sie AD RMS ausgeführt wurden. <br /> <br />Darüber hinaus, wenn Sie bereitgestellt haben die [mobiler Geräte Extensions](http://technet.microsoft.com/library/dn673574.aspx) für die Unterstützung mobiler Geräte wie iOS-Telefone und iPads, Android-Telefone und Tablets, Windows Phone und Macintosh-Computern müssen Sie die SRV-Einträge im DNS, die diese Clients zum Verwenden von AD RMS umgeleitet entfernen. <br /> <br />Anleitungen hierzu finden Sie unter [Step 5. Reconfigure clients to use Azure RMS](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step5Migration) <br /> <br />|
|**6. Konfigurieren von IRM-Integration mit Exchange Online** <br /> <br />|Dieser Schritt ist erforderlich, wenn Sie Exchange Online mit Azure RMS verwenden möchten. <br /> <br />Anleitungen hierzu finden Sie unter [Step 6. Configure IRM integration for Exchange Online](#BKMK_Step6Migration) <br /> <br />|
|**7. Der RMS-Verbindungsdienst bereitstellen** <br /> <br />|Dieser Schritt ist erforderlich, wenn Sie einen der folgenden lokalen Dienste mit Azure RMS verwenden möchten:<ul><li>Exchange-Server (z. B. Transportregeln und Outlook Web Access) </li><li>SharePoint Server </li><li>Windows-Server, der die Dateiklassifizierungsinfrastruktur ausgeführt wird. </li> </ul>Anleitungen hierzu finden Sie unter [Step 7. Deploy the RMS connector](#BKMK_Step7Migration)|
|**8. Außerbetriebnahme von AD RMS** <br /> <br />|Wenn sichergestellt ist, die alle Clients Azure RMS verwenden und nicht mehr auf die AD RMS-Server, Sie können außer Betrieb setzen die AD RMS-Bereitstellung. <br /> <br />Anleitungen hierzu finden Sie unter [Step 8. Decommission AD RMS](#BKMK_Step8Migration) <br /> <br />|
|**9. Erneut Ihren Azure RMS-mandantenschlüssel** <br /> <br />|Dieser Schritt ist erforderlich, wenn Sie nicht in Kryptografiemodus 2 vor der Migration und optional ausgeführt wurden, aber empfohlen für alle Migrationen zum Schutz die Sicherheit Ihrer Azure RMS-mandantenschlüssel. <br /> <br />Anleitungen hierzu finden Sie unter [Step 9. Re-key your Azure RMS tenant key](#BKMK_Step9Migration) <br /> <br />|

### <a name="BKMK_Step1Migration"></a>Schritt 1: Herunterladen von Azure Rights Management-Administrationstool
Rufen Sie im Microsoft Download Center und laden die [Azure Rights Management-Administrationstool](http://go.microsoft.com/fwlink/?LinkId=257721), das das Azure RMS-Verwaltung-Modul für Windows PowerShell enthält.

### <a name="BKMK_Step2Migration"></a>Schritt 2. Exportieren Sie Konfigurationsdaten aus AD RMS und importieren Sie sie in Azure RMS
Dieser Schritt ist ein zweistufiger Prozess:

1. AD RMS die vertrauenswürdigen Veröffentlichungsdomänen (Vertrauenswürdige Veröffentlichungsdomänen) in eine XML-Datei exportieren, um die Konfigurationsdaten zu exportieren. Dieser Prozess ist für alle Migrationen identisch.

2. Importieren Sie die Konfigurationsdaten in Azure RMS. Es gibt verschiedene Prozesse für diesen Schritt, abhängig von Ihrer aktuellen Konfiguration des AD RMS-Bereitstellung und Ihre bevorzugten Topologie für Ihren Azure RMS-mandantenschlüssel.

Führen Sie das folgende Verfahren auf alle AD RMS-Cluster für alle Vertrauenswürdige Veröffentlichungsdomänen, die geschützte Inhalte für Ihre Organisation. Sie müssen nicht auf reine Lizenzierungscluster ausführen.

> [!NOTE]
> Wenn Sie Windows Server 2003 Rights Management, anstatt diese Anweisungen verwenden, gehen Sie [Exportieren SLC, TUD, TPD und RMS privaten Schlüssel](http://technet.microsoft.com/library/jj835767%28v=ws.10%29.aspx) aus der [Migration von Windows RMS auf AD RMS in einer anderen Infrastruktur](http://technet.microsoft.com/library/jj835767%28v=ws.10%29.aspx) Thema.

1. Melden Sie sich auf dem AD RMS-Cluster mit AD RMS-Administratorberechtigungen.

2. Der AD RMS-Verwaltungskonsole (**Active Directory-Rechteverwaltungsdienste**), erweitern Sie den Namen des AD RMS-Clusters und **Vertrauensrichtlinien**, und klicken Sie dann auf **Vertrauenswürdige Veröffentlichungsdomänen**.

3. Klicken Sie im Ergebnisbereich die vertrauenswürdige Veröffentlichungsdomäne auswählen, und klicken Sie im Aktionsbereich auf **vertrauenswürdige Veröffentlichungsdomäne exportieren**.

4. In der **vertrauenswürdige Veröffentlichungsdomäne exportieren** (Dialogfeld):

   - Klicken Sie auf **Speichern unter** und Pfad und einen Dateinamen Ihrer Wahl speichern. Geben Sie **.xml** als der Erweiterung (Dies ist nicht angefügt automatisch).

   - Geben Sie an, und ein sicheres Kennwort. Merken Sie dieses Kennwort, da Sie es später beim Importieren von Konfigurationsdaten in Azure RMS benötigen.

   - Aktivieren Sie nicht das Kontrollkästchen zum Speichern der vertrauenswürdigen Domäne-Datei in RMS, Version 1.0.

Wenn Sie die vertrauenswürdigen Veröffentlichungsdomänen exportiert haben, können Sie das Verfahren zum Importieren von Daten in Azure RMS zu starten.

Die genaue Vorgehensweise bei diesem Schritt ist abhängig von Ihrer aktuellen Konfiguration des AD RMS-Bereitstellung und Ihre bevorzugten Topologie für Ihren Azure RMS-mandantenschlüssel.

Die aktuelle AD RMS-Bereitstellung wird eine der folgenden Konfigurationen für den Server Licensor Certificate (SLC)-Schlüssel verwenden:

- Der Kennwortschutz in der AD RMS-Datenbank. Dies ist die Standardkonfiguration.

- HSM-Schutz mit einem Thales Hardwaresicherheitsmodul (HSM).

- Mit einem Hardwaresicherheitsmodul (HSM) von einem anderen Hersteller als Thales HSM-Schutz.

- Kennwort mit einem externen Kryptografieanbieter geschützt.

> [!NOTE]
> Weitere Informationen zu AD RMS mit Hardwaresicherheitsmodulen finden Sie unter [mit AD RMS mit Hardwaresicherheitsmodulen](http://technet.microsoft.com/library/jj651024.aspx).

Die beiden Azure RMS-Mandanten wichtige Topologie-Optionen sind: Ihr mandantenschlüssel von Microsoft verwaltet (**Microsoft verwalteten**) oder Sie Ihren mandantenschlüssel verwalten (**Kunden verwaltet**). Wenn Sie Ihren eigenen Azure RMS-mandantenschlüssel verwalten, es wird manchmal als "bring your own Key" (BYOK) und erfordert ein Hardwaresicherheitsmodul (HSM) von Thales. Weitere Informationen finden Sie im Abschnitt [Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ChooseTenantKey) des Themas [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

> [!IMPORTANT]
> Exchange Online kann derzeit nicht mit Azure RMS BRING.  Wenn Sie BYOK verwenden, nach der Migration und Exchange Online verwenden möchten, stellen Sie sicher, dass Sie verstehen, wie diese Konfiguration IRM-Funktionen für Exchange Online reduziert. Überprüfen Sie die Informationen in der [BYOK pricing and restrictions](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_Pricing) im Abschnitt der  [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md) Thema zur Auswahl der besten Azure RMS Mandanten wichtige Topologie für die Migration.

Verwenden Sie in der folgende Tabelle, um die Prozedur für die Migration verwenden zu identifizieren. Kombinationen aus, die nicht aufgeführt sind, werden nicht unterstützt.

|Aktuelle AD RMS-Bereitstellung <br /> <br />|Ausgewählte Azure RMS-mandantenschlüsseltopologie <br /> <br />|Anweisungen zur Migration <br /> <br />|
|----------------------------------|-----------------------------------------------------|-----------------------------|
|Der Kennwortschutz in der AD RMS-Datenbank <br /> <br />|Microsoft verwaltet <br /> <br />|Finden Sie unter der **Software geschützt-Taste, um die Migration von Software geschützt** Verfahren nach dieser Tabelle. <br /> <br />Dies ist der einfachste Weg, und erfordert lediglich, dass die Konfigurationsdaten in Azure RMS zu übertragen. <br /> <br />|
|HSM-Schutz mit einem Thales nShield-Hardwaresicherheitsmodul (HSM) <br /> <br />|Vom Kunden verwaltet (BYOK) <br /> <br />|Finden Sie unter der **HSM-geschützte-Taste, um die Migration von HSM-geschützten** Verfahren nach dieser Tabelle. <br /> <br />Dies erfordert das BYOK-Toolset und zwei Reihe von Schritten, den Schlüssel aus Ihrem lokalen HSM an Azure RMS-HSMs übertragen, und anschließend die Konfigurationsdaten in Azure RMS übertragen. <br /> <br />|
|Der Kennwortschutz in der AD RMS-Datenbank <br /> <br />|Vom Kunden verwaltet (BYOK) <br /> <br />|Finden Sie unter der **Software geschützt-Taste, um die Migration von HSM-geschützten** Verfahren nach dieser Tabelle. <br /> <br />Dies erfordert, dass das BYOK-Toolset und drei Sätze von Schritten, die erste extrahieren, Ihre Software-Schlüssel und importieren sie ein HSM lokalen übertragen Sie den Schlüssel aus Ihrem lokalen HSM, um Azure RMS-HSMs und schließlich die Konfigurationsdaten in Azure RMS übertragen. <br /> <br />|
|Mit einem Hardwaresicherheitsmodul (HSM) von einem anderen Hersteller als Thales HSM-Schutz <br /> <br />|Vom Kunden verwaltet (BYOK) <br /> <br />|Wenden Sie sich an dem Lieferanten für Sie HSM Anweisungen zur Übertragung von Ihren Schlüssels aus dieser HSM zu einem Thales nShield Hardwaresicherheitsmodul (HSM). Gehen Sie für die **HSM-geschützte-Taste, um die Migration von HSM-geschützten** Verfahren nach dieser Tabelle. <br /> <br />|
|Durch Verwenden einer externen Kryptografieanbieter kennwortgeschützt <br /> <br />|Vom Kunden verwaltet (BYOK) <br /> <br />|Wenden Sie sich an dem Lieferanten für Sie Kryptografieanbieter Anweisungen zur Übertragung von Ihren Schlüssels zu einem Thales nShield-Hardwaresicherheitsmodul (HSM). Gehen Sie für die **HSM-geschützte-Taste, um die Migration von HSM-geschützten** Verfahren nach dieser Tabelle. <br /> <br />|
Bevor Sie diese Vorgänge ausführen, stellen Sie sicher, dass Sie die XML-Dateien, die Sie zuvor erstellt haben zugreifen können, wenn Sie vertrauenswürdigen Veröffentlichungsdomänen exportiert. Diese können z. B. auf ein USB-Stick gespeichert werden, die Sie an der Arbeitsstation mit Internetanschluss aus der AD RMS-Server verschieben.

> [!NOTE]
> Aber speichern Sie diese Dateien mit bewährten Sicherheitsmethoden, sie zu schützen, da diese Daten auf Ihren privaten Schlüssel enthält.

Verwenden Sie dieses Verfahren zum Importieren der AD RMS-Konfiguration in Azure RMS, um Ihren Azure RMS-mandantenschlüssel führen, die von Microsoft verwaltet wird.

1. Eine Arbeitsstation mit Internet herunter und installieren Sie Windows PowerShell-Modul für Azure RMS (Mindestversion 2.1.0.0), enthält die [Import AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx) Cmdlet.

   > [!TIP]
   >    Wenn Sie zuvor heruntergeladen und das Modul installiert haben, überprüfen Sie die Versionsnummer durch ausführen: **(Get-Module aadrm -ListAvailable).Version**

   Installationshinweise finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).

2. Starten Sie Windows PowerShell mit der **als Administrator ausführen** aus, und verwenden Sie die [Connect-AadrmService](http://msdn.microsoft.com/library/azure/dn629415.aspx) Cmdlet mit dem Azure RMS-Dienst herstellen:

   ```
   Connect-AadrmService
   ```
   Wenn Sie dazu aufgefordert werden, geben Sie Ihre [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] mandantenadministrator-Anmeldeinformationen (in der Regel verwenden Sie ein Konto, ein globaler Administrator für Azure Active Directory oder Office 365 ist).

3. Verwenden der [Import AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx) -Cmdlet zum Hochladen der erste exportierte Datei vertrauenswürdigen Veröffentlichungsdomäne (.xml). Wenn Sie mehr als eine XML-Datei verfügen, da Sie mehrere Vertrauenswürdige Veröffentlichungsdomänen hatten, wählen Sie die Datei, die die exportierte vertrauenswürdige Veröffentlichungsdomäne, die Sie in Azure RMS verwenden enthält, um nach der Migration Inhalte schützen möchten. Verwenden Sie den folgenden Befehl ein:

   ```
   Import-AadrmTpd -TpdFile <PathToTpdPackageFile> -ProtectionPassword -Active $True -Verbose
   ```
   Beispiel: **Import-AadrmTpd -TpdFile E:\contosokey1.xml -ProtectionPassword -Active $true -Verbose**

   Wenn Sie aufgefordert werden, geben Sie das Kennwort, das Sie zuvor angegeben, und vergewissern Sie sich, dass Sie diese Aktion ausführen möchten.

4. Wenn der Befehl abgeschlossen ist, wiederholen Sie Schritt 3 für jede verbleibende XML-Datei, die Sie erstellt haben, exportieren Sie Ihre vertrauenswürdigen Veröffentlichungsdomänen. Aber für diese Dateien **-Activefalse** beim Ausführen des Import-Befehls. Beispiel: **Import-AadrmTpd -TpdFile E:\contosokey2.xml -ProtectionPassword -Active $false -Verbose**

5. Verwenden der [Disconnect-AadrmService](http://msdn.microsoft.com/library/azure/dn629416.aspx) -Cmdlet zum Trennen von Azure RMS-Dienst:

   ```
   Disconnect-AadrmService
   ```

Sie sind jetzt bereit, fahren Sie mit [Step 3. Activate your RMS tenant](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step3Migration).

Es ist ein zwei Schritte zum Importieren der HSM-Schlüssel und die AD RMS-Konfiguration in Azure RMS, um Ihren Azure RMS-mandantenschlüssel führen, die von Ihnen (BYOK) verwaltet wird.

Daher ist es in Azure RMS übertragen und dann mit den Konfigurationsdaten importieren möchten, müssen Sie zunächst den HSM-Key verpacken.

1. Führen Sie die Schritte in der [Implementing bring your own key (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ImplementBYOK) Teil der [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md), mit dem Verfahren **generieren und übertragen Ihres Mandanten Schlüssel – über das Internet** mit den folgenden Ausnahmen:

   - Führen Sie die Schritte für nicht **generieren Ihres mandantenschlüssels**, da Sie bereits über die Entsprechung von AD RMS-Bereitstellung verfügen. Sie identifizieren den Schlüssel von AD RMS-Server aus der Thales-Installation verwendet und verwenden Sie diesen Schlüssel während der Migration. Verschlüsselte Schlüsseldateien sind in der Regel mit dem Namen Thales **key_(keyAppName)_(keyIdentifier)** lokal auf dem Server.

   - Führen Sie die Schritte für nicht **übertragen Ihres mandantenschlüssels an Azure RMS**, den Befehl Add-AadrmKey verwendet.  Stattdessen übertragen Sie Ihre vorbereiteten HSM-Schlüssel beim Hochladen der exportierten vertrauenswürdigen Veröffentlichungsdomäne, mit dem Import-AadrmTpd-Befehl.

2. Schließen Sie auf der Arbeitsstation Internetzugang in Windows PowerShell-Sitzung mit dem Azure RMS-Dienst.

Nun, da Sie Ihren HSM-Schlüssel für Azure RMS vorbereitet haben, können Sie die Schlüsseldatei HSM und AD RMS-Konfigurationsdaten importiert.

1. Immer noch auf der Arbeitsstation Internet verbinden und in der Windows PowerShell-Sitzung Hochladen der ersten exportierte Datei vertrauenswürdigen Veröffentlichungsdomäne (.xml). Wenn Sie mehr als eine XML-Datei verfügen, da Sie mehrere Vertrauenswürdige Veröffentlichungsdomänen hatten, wählen Sie die Datei, die exportierte vertrauenswürdige Veröffentlichungsdomäne enthält, die den HSM-Schlüssel, die Sie in Azure RMS verwenden entspricht, um nach der Migration Inhalte schützen möchten. Verwenden Sie den folgenden Befehl ein:

   ```
   Import-AadrmTpd -TpdFile <PathToTpdPackageFile> -ProtectionPassword -HsmKeyFile <PathToBYOKPackage> -Active $True -Verbose
   ```
   Beispiel: **Import -TpdFile E:\no_key_tpd_contosokey1.xml  -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $true -Verbose**

   Wenn Sie aufgefordert werden, geben Sie das Kennwort, das Sie zuvor angegeben, und vergewissern Sie sich, dass Sie diese Aktion ausführen möchten.

2. Wenn der Befehl abgeschlossen ist, wiederholen Sie Schritt 1 für jeden verbleibenden XML-Datei, die Sie exportieren die vertrauenswürdigen Veröffentlichungsdomänen erstellt. Aber für diese Dateien **-Activefalse** beim Ausführen des Import-Befehls.  Beispiel: **Import -TpdFile E:\contosokey2.xml -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $false -Verbose**

3. Verwenden der [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) -Cmdlet zum Trennen von Azure RMS-Dienst:

   ```
   Disconnect-AadrmService
   ```

Sie sind jetzt bereit, fahren Sie mit [Step 3. Activate your RMS tenant](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step3Migration).

Es ist eine dreiteilige Verfahren zum Importieren der AD RMS-Konfiguration in Azure RMS, um Ihren Azure RMS-mandantenschlüssel führen, die von Ihnen (BYOK) verwaltet wird.

Sie müssen zuerst den Server Licensor Certificate (SLC)-Schlüssel aus den Konfigurationsdaten zu extrahieren und übertragen den Schlüssel in einer lokalen Thales HSM dann Paket übertragen Ihrer HSM-Schlüssel in Azure RMS und importieren Sie die Konfigurationsdaten.

1. Die folgenden Schritte aus, in der [Implementing bring your own key (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ImplementBYOK) Teil der [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md) Thema:

   - **Generieren und übertragen Ihres Mandanten Schlüssel – über das Internet**: **Vorbereiten Ihrer Arbeitsstation Internetzugang**

   - **Generieren und übertragen Ihres Mandanten Schlüssel – über das Internet**: **Vorbereiten Ihrer nicht verbundenen Arbeitsstation**

   Führen Sie die Schritte zum Generieren Ihres mandantenschlüssels nicht, da Sie bereits die Entsprechung in der exportierten Konfiguration-Datendatei (.xml) verfügen. Stattdessen führen Sie einen Befehl aus, um diesen Schlüssel aus der Datei zu extrahieren, und importieren sie in Ihrer lokalen HSM.

2. Führen Sie auf der nicht verbundenen Arbeitsstation den folgenden Befehl ein:

   ```
   KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath <TPD> -ProtectionPassword -KeyIdentifier <KeyID> -ExchangeKeyPackage <BYOK-KEK-pka-Region> -NewSecurityWorldPackage <BYOK-SecurityWorld-pkg-Region>
   ```
   Beispielsweise für Nordamerika: **KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath E:\contosokey1.xml -ProtectionPassword -KeyIdentifier contosorms1key –- -ExchangeKeyPackage &lt;BYOK-KEK-pka-NA-1&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-NA-1&gt;**

   Weitere Informationen:

   - Der ImportRmsCentrallyManagedKey-Parameter gibt an, dass der Vorgang der SLC-Schlüssel importiert.

   - Wenn Sie das Kennwort im Befehl angeben, werden Sie aufgefordert, anzugeben.

   - Der KeyIdentifier-Parameter ist für einen Schlüssel Anzeigenamen, der den Namen der Schlüsseldatei erstellt. Sie müssen nur Kleinbuchstabe ASCII-Zeichen verwenden.

   - Der ExchangeKeyPackage-Parameter gibt einen Schlüsselaustausch regionsspezifische Schlüssel (KEK)-Paket, eine Name beginnt mit BYOK-KEK - Pkg-.

   - Der NewSecurityWorldPackage-Parameter gibt ein regionsspezifische Security World-Paket, das ist eine Name beginnt mit BYOK-SecurityWorld - Pkg-.

   Mit diesem Befehl ergibt sich Folgendes:

   - Ein HSM-Schlüsseldatei: %NFAST_KMDATA%\local\key_mscapi_ &lt; KeyID &gt;

   - RMS-Konfiguration-Datendatei mit der SLC entfernt: %NFAST_KMDATA%\local\no_key_tpd_ &lt; KeyID &gt; .xml

3. Wenn Sie mehrere Datendateien der RMS-Konfiguration verfügen, wiederholen Sie Schritt 2 für den Rest dieser Dateien.

Jetzt Ihre SLC extrahiert wurde, damit es ein HSM-basierten Schlüssel ist, können Sie zum Packen und in Azure RMS zu übertragen.

1. Verwenden Sie die folgenden Schritte aus der [Implementing bring your own key (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ImplementBYOK) Teil der [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md):

   - **Generieren und übertragen Ihres Mandanten Schlüssel – über das Internet**: **Vorbereiten Ihres mandantenschlüssels für die Übertragung**

   - **Generieren und übertragen Ihres Mandanten Schlüssel – über das Internet**: **übertragen Ihres mandantenschlüssels an Azure RMS**

Nun, da Sie Ihren HSM-Schlüssel in Azure RMS übertragen haben, können Sie nur einen Zeiger auf den mandantenschlüssel neu übertragenen enthält die AD RMS-Konfigurationsdaten importieren.

1. Immer noch auf der Arbeitsstation Internetzugang und in der Windows PowerShell-Sitzung über die RMS-Konfigurationsdateien mit der SLC entfernt (aus der nicht verbundenen Arbeitsstation %NFAST_KMDATA%\local\no_key_tpd_ &lt; KeyID &gt; .xml) kopieren

2. Hochladen Sie die erste Datei. Wenn Sie mehr als eine XML-Datei verfügen, da Sie mehrere Vertrauenswürdige Veröffentlichungsdomänen hatten, wählen Sie die Datei, die exportierte vertrauenswürdige Veröffentlichungsdomäne enthält, die den HSM-Schlüssel, die Sie in Azure RMS verwenden entspricht, um nach der Migration Inhalte schützen möchten. Verwenden Sie den folgenden Befehl ein:

   ```
   Import-AadrmTpd -TpdFile <PathToNoKeyTpdPackageFile> -ProtectionPassword -HsmKeyFile <PathToKeyTransferPackage> -Active $true -Verbose
   ```
   Beispiel: **Import -TpdFile E:\no_key_tpd_contosorms1key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $true -Verbose**

   Wenn Sie aufgefordert werden, geben Sie das Kennwort, das Sie zuvor angegeben, und vergewissern Sie sich, dass Sie diese Aktion ausführen möchten.

3. Wenn der Befehl abgeschlossen ist, wiederholen Sie Schritt 2 für jeden verbleibenden XML-Datei, die Sie exportieren die vertrauenswürdigen Veröffentlichungsdomänen erstellt. Aber für diese Dateien **-Activefalse** beim Ausführen des Import-Befehls. Beispiel: **Import -TpdFile E:\no_key_tpd_contosorms2key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $false -Verbose**

4. Verwenden der [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) -Cmdlet zum Trennen von Azure RMS-Dienst:

   ```
   Disconnect-AadrmService
   ```

Sie sind jetzt bereit, fahren Sie mit [Step 3. Activate your RMS tenant](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md#BKMK_Step3Migration).

### <a name="BKMK_Step3Migration"></a>Schritt 3. Aktivieren Sie den RMS-Mandanten
Eine Anleitung für diesen Schritt sind in vollem Umfang die [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md) Thema.

> [!TIP]
> Wenn Sie ein Office 365-Abonnement verfügen, können Sie Azure RMS über das Office 365 Administrationscenter oder Azure-Verwaltungsportal aktivieren. Es wird empfohlen, Azure-Verwaltungsportal verwenden, da Sie diese Verwaltungsportal verwendet, die den nächsten Schritt durchführen.

**Was geschieht, wenn Ihre Azure RMS-Mandanten bereits aktiviert wurde?** Wenn der Azure RMS-Dienst für Ihre Organisation bereits aktiviert ist, Benutzer möglicherweise bereits Azure RMS verwendet zum Schützen von Inhalt mit einer automatisch generierten mandantenschlüssels (und die Standardvorlagen) und nicht die vorhandenen Schlüssel (und Vorlagen) von AD RMS. Dies ist wahrscheinlich nicht auf Computern im Intranet, gut verwaltete daran sie automatisch für die AD RMS-Infrastruktur konfiguriert werden. Aber es kann passieren, auf dem Arbeitsgruppencomputer oder Computer, die selten mit dem Intranet verbunden. Leider ist es auch schwierig, diese Computer identifizieren deshalb empfohlen, dass Sie den Dienst vor dem import der Konfigurationsdaten aus AD RMS nicht aktivieren.

Wird Ihre Azure RMS-Mandanten bereits aktiviert ist, und Sie können diese Computer identifizieren, stellen Sie sicher, dass Sie das Skript CleanUpRMS_RUN_Elevated.cmd auf diesen Computern ausführen wie in Schritt 5 beschrieben. Dieses Skript ausführen, erzwingen sie die Benutzer-Umgebung neu zu initialisieren, damit sie die aktualisierte mandantenschlüssel und die importierten Vorlagen herunterladen.

### <a name="BKMK_Step4Migration"></a>Schritt 4. Konfigurieren Sie importierte Vorlagen
Da die Vorlagen, die Sie importiert den Standardzustand der haben **archiviert**, müssen Sie diesen Zustand zu ändern **veröffentlicht** sollen Benutzer diese Vorlagen mit Azure RMS verwenden können.

Vorlagen, die Sie von AD RMS importieren Aussehen und Verhalten sich ebenso wie benutzerdefinierte Vorlagen, die Sie in der Azure-Verwaltungsportal erstellen können. Ändern der importierte Vorlagen veröffentlicht werden, damit Benutzer Sie anzeigen und Applikationen auswählen können, oder auf andere Vorlagen ändern, finden Sie [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md).

> [!NOTE]
> Nehmen Sie für eine konsistente Umgebung für Benutzer während der Migration keine Änderungen auf die importierten Vorlagen veröffentlichen, und veröffentlichen Sie die beiden Standardvorlagen, die im Lieferumfang von Azure RMS oder Erstellen neuer Vorlagen zu diesem Zeitpunkt nicht. Stattdessen, warten Sie, bis der Migrationsprozess abgeschlossen ist und die AD RMS-Server außer Betrieb gesetzt werden müssen.

### <a name="BKMK_Step5Migration"></a>Schritt 5. Konfigurieren von Clients für die Verwendung von Azure RMS
Für Windows-Clients:

1. [Herunterladen der Migrationsskripts](http://go.microsoft.com/fwlink/?LinkId=524619):

   - CleanUpRMS_RUN_Elevated.cmd

   - Redirect_OnPrem.cmd

   Diese Skripts zurücksetzen die Konfiguration auf Computern unter Windows, sodass diese anstelle von AD RMS die Azure RMS-Dienst verwenden.

2. Gehen Sie in das Skript Umleitung (Redirect_OnPrem.cmd), ändern Sie das Skript auf den neuen Azure RMS-Mandanten.

3. Führen Sie diese Skripts auf Windows-Computern mit erweiterten Berechtigungen im Kontext des Benutzers.

Für Clients für mobile Geräte und Macintosh-Computer:

- Entfernen Sie die DNS-SRV-Einträge, die Sie erstellt haben, bei der Bereitstellung der [AD RMS-Erweiterung für mobile Geräte](http://technet.microsoft.com/library/dn673574.aspx).

Dieser Abschnitt beschreibt die Änderungen, die Migrationsskripts vornehmen. Sie können diese Informationen nur zu Informationszwecken und zur Fehlerbehebung verwenden, oder möchten Sie diese erstellen, ändert sich.

CleanUpRMS_RUN_Elevated.cmd:

- Löschen Sie den Inhalt der Ordner %userprofile%\AppData\Local\Microsoft\DRM und %userprofile%\AppData\Local\Microsoft\MSIPC, einschließlich Unterordner und Dateien mit langen Dateinamen.

- Löschen Sie den Inhalt der folgenden Registrierungsschlüssel:

   - HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM

   - HKEY_CURRENT_USER\Software\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM

   - HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM

   - HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM

   - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation

   - HKEY_LOCAL_MACHINE\SOFTWARE\WoW6432Node\Microsoft\MSIPC\ServiceLocation

   - HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation

- Löschen Sie die folgenden Registrierungswerte:

   - HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServerURL

   - HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServer

Redirect_OnPrem.cmd:

- Erstellen Sie die folgenden Registrierungswerte für jede URL, die als Parameter unter jedem der folgenden Speicherorte:

   - HKEY_CURRENT_USER\Software\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM\LicenseServerRedirection

   - HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM\LicenseServerRedirection

   - HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM\LicenseServerRedirection

   - HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\ (11.0|12.0|14.0) \Common\DRM\LicenseServerRedirection

   - HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\LicensingRedirection

   Jeder Eintrag hat einen REG_SZ-Wert der **https://OldRMSserverURL/_wmcs/licensing** mit den Daten im folgenden Format: **https://&lt;YourTenantURL&gt;/_wmcs/licensing**.

   > [!NOTE]
   >    *&lt; YourTenantURL &gt;* weist das folgende Format: **{GUID} .rms. [Region].aadrm.com**.
   > 
   >    Beispiel: 5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com
   > 
   >    Finden Sie diesen Wert durch Identifizieren der **RightsManagementServiceId** Wert beim Ausführen der [Get-AadrmConfiguration](http://msdn.microsoft.com/library/windowsazure/dn629410.aspx) Cmdlet für Azure RMS.

### <a name="BKMK_Step6Migration"></a>Schritt 6. Konfigurieren von IRM-Integration für Exchange Online
Wenn Sie Ihre TDP von AD RMS mit Exchange Online bereits importiert haben, müssen Sie diese TDP zur Vermeidung von in Konflikt stehenden Vorlagen und Richtlinien, wenn Sie in Azure RMS migriert haben entfernen. Verwenden Sie hierzu die [Remove-RMSTrustedPublishingDomain](https://technet.microsoft.com/en-us/library/jj200720%28v=exchg.150%29.aspx) Cmdlet von Exchange Online.

Bei Verwendung einer Azure RMS wichtige Topologie eines Mandanten **verwaltet Microsoft**:

- Informationen hierzu finden Sie im Abschnitt [Exchange Online: IRM Configuration](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md#BKMK_ExchangeOnline) des Themas [Konfigurieren von Clientanwendungen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md). Dieser Abschnitt enthält die normalen Befehle ausführen, die eine Verbindung mit Exchange Online-Dienst, importiert den mandantenschlüssel von Azure RMS und IRM-Funktionen für Exchange Online ermöglicht. Nachdem Sie diese Schritte abgeschlossen haben, müssen Sie die volle Funktionalität von RMS mit Exchange Online.

Bei Verwendung einer Azure RMS wichtige Topologie eines Mandanten **Kunden verwaltet (BYOK)**:

- Sie werden reduziert haben RMS-Funktionalität mit Exchange Online, wie beschrieben in der [BYOK pricing and restrictions](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_Pricing) im Abschnitt der [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md) Thema.

### <a name="BKMK_Step7Migration"></a>Schritt 7 fort. Der RMS-Verbindungsdienst bereitstellen
Wenn Sie die Verwaltung von Informationsrechten (IRM) Funktionalität von Exchange Server oder SharePoint Server mit AD RMS verwendet haben, müssen Sie IRM auf diesen Servern deaktivieren und Entfernen von AD RMS-Konfiguration. Den Rights Management (RMS)-Connector, fungiert als Kommunikationsschnittstelle (Relay) zwischen dem lokalen Server und Azure RMS dann bereitgestellt.

Schließlich für diesen Schritt, müssen wenn Sie mehrere Vertrauenswürdige Veröffentlichungsdomänen importiert haben, in Azure RMS, die verwendet wurden, zum Schutz von e-Mail-Nachrichten, Sie manuell die Registrierung auf dem Exchange Server-Computer alle Vertrauenswürdige Veröffentlichungsdomänen URLs an den RMS-Verbindungsdienst umleiten bearbeiten.

> [!NOTE]
> Bevor Sie beginnen, überprüfen Sie die unterstützten Versionen von lokalen Servern, auf denen der RMS-Verbindungsdienst unterstützt in "lokalen Servern, die Azure RMS unterstützen" in der [Applications that support Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_SupportedApplications) Teil der [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md) Thema.

1. Auf jedem Server, suchen Sie den folgenden Ordner, und löschen Sie alle Einträge in diesem Ordner: \ProgramData\Microsoft\DRM\Server\S-1-5-18

2. Verwenden Sie von einem Exchange-Server, das Exchange [Set_IRMConfiguration](http://technet.microsoft.com/library/dd979792.aspx) -Cmdlet zum Deaktivieren Sie zuerst die IRM-Funktionen für Nachrichten, die für interne Empfänger gesendet werden:

   ```
   Set-IRMConfiguration -InternalLicensingEnabled $false
   ```

3. Dann verwenden Sie das gleiche Cmdlet Deaktivieren von IRM-Funktionen für Nachrichten, die an externe Empfänger gesendet werden:

   ```
   Set-IRMConfiguration -ExternalLicensingEnabled $false
   ```

4. Als Nächstes verwenden Sie das gleiche Cmdlet IRM in Microsoft Office Outlook Web App und Microsoft Exchange ActiveSync zu deaktivieren:

   ```
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

5. Schließlich verwenden Sie demselben Cmdlet, um zwischengespeicherte Zertifikate zu löschen:

   ```
   Set-IRMConfiguration -RefreshServerCertificates
   ```

6. Auf jedem Exchange-Server jetzt setzen Sie IIS zurück, z. B. indem Sie ein Eingabeaufforderungsfenster als Administrator ausführen und eingeben **iisreset**.

1. Stellen Sie sicher, dass keine Dokumente von RMS-geschützten Bibliotheken ausgecheckt sind. Wenn Sie vorhanden sind, werden sie am Ende dieses Verfahrens nicht mehr zugegriffen werden.

2. Für die SharePoint Central Administration Web site, in der **Schnellstart** auf **Security**.

3. Auf der **Security** Seite der **Informationsrichtlinie** auf **Verwaltung von Informationsrechten konfigurieren**.

4. Auf der **Information Rights Management** Seite der **Information Rights Management** Abschnitt **Verwenden Sie IRM nicht auf diesem Server**, klicken Sie dann auf **OK**.

5. Löschen Sie auf der SharePoint-Server-Computer, den Inhalt der Ordner \ProgramData\Microsoft\MSIPC\Server\*&lt; SID des Kontos mit SharePoint Server &gt;*.

- Verwenden Sie die Anweisungen in der [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md) Thema.

- Auf jedem Exchange-Server müssen fügen Sie die folgenden Registrierungsschlüssel manuell für jede zusätzliche vertrauenswürdige Veröffentlichungsdomäne, die Sie importiert, um die URLs der vertrauenswürdigen Veröffentlichungsdomäne in RMS-Verbindungsdienst umzuleiten hinzu. Diese Registrierungseinträge sind spezifisch für Migration und nicht vom Server-Konfigurationstool für Microsoft RMS-Verbindungsdienst hinzugefügt werden.

   Wenn Sie die Registrierung bearbeitet haben, gehen Sie folgendermaßen vor:

   - Ersetzen Sie *ConnectorFQDN* mit dem Namen, den Sie in DNS für den Connector definiert. Beispielsweise **rmsconnector.contoso.com**.

   - Verwenden Sie das HTTP- oder HTTPS-Präfix für den Connector-URL, je nachdem, ob Sie den Connector für HTTP oder HTTPS verwenden für die Kommunikation mit Ihren lokalen Servern konfiguriert haben.

   **Für Exchange 2013:**

|Registrierungspfad <br /> <br />|Typ <br /> <br />|Wert <br /> <br />|Daten <br /> <br />|
|----------------------|-------|--------|---------|
|HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection <br /> <br />|Reg_SZ <br /> <br />|https://&lt;AD Lizenzierung RMS Intranet-URL &gt;/_wmcs/licensing <br /> <br />|Einer der folgenden Werte, abhängig davon, ob Sie HTTP oder HTTPS von Ihrem Exchange-Server zum RMS-Connector:<ul><li>http://&lt;connectorFQDN&gt;/_wmcs/Licensing </li><li>https://&lt;connectorName&gt;/_wmcs/Licensing </li> </ul>|
|HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection <br /> <br />|Reg_SZ <br /> <br />|https://&lt;AD Lizenzierung RMS Extranet-URL &gt;/_wmcs/licensing <br /> <br />|Einer der folgenden Werte, abhängig davon, ob Sie HTTP oder HTTPS von Ihrem Exchange-Server zum RMS-Connector:<ul><li>http://&lt;connectorFQDN&gt;/_wmcs/Licensing </li><li>https://&lt;connectorFQDN&gt;/_wmcs/Licensing </li> </ul>|
   **Für Exchange Server 2010:**

|Registrierungspfad <br /> <br />|Typ <br /> <br />|Wert <br /> <br />|Daten <br /> <br />|
|----------------------|-------|--------|---------|
|HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection <br /> <br />|Reg_SZ <br /> <br />|https://&lt;AD Lizenzierung RMS Intranet-URL &gt;/_wmcs/licensing <br /> <br />|Einer der folgenden Werte, abhängig davon, ob Sie HTTP oder HTTPS von Ihrem Exchange-Server zum RMS-Connector:<ul><li>http://&lt;connectorName&gt;/_wmcs/Licensing </li><li>https://&lt;connectorName&gt;/_wmcs/Licensing </li> </ul>|
|HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection <br /> <br />|Reg_SZ <br /> <br />|https://&lt;AD Lizenzierung RMS Extranet-URL &gt;/_wmcs/licensing <br /> <br />|Einer der folgenden Werte, abhängig davon, ob Sie HTTP oder HTTPS von Ihrem Exchange-Server zum RMS-Connector:<ul><li>http://&lt;connectorName&gt;/_wmcs/Licensing </li><li>https://&lt;connectorName&gt;/_wmcs/Licensing </li> </ul>|

Nachdem Sie diese Verfahren abgeschlossen haben, müssen Sie unbedingt Lesen der **Nächste Schritte** im Abschnitt der [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md) Thema.

### <a name="BKMK_Step8Migration"></a>Schritt 8. Außerbetriebnahme von AD RMS
Optional: Entfernen Sie (Service Connection Point, SCP) von Active Directory zu verhindern, dass Computer ermitteln Ihre lokalen Rights Management-Infrastruktur. Dies ist aufgrund der Umleitung, die Sie in der Registrierung konfiguriert (z. B. durch Ausführen des Migrations-Skripts) optional. Um den Service Connection Point zu entfernen, verwenden Sie das AD-SCP-Register-Tool von der [Rights Management Services Administration Toolkit](http://www.microsoft.com/download/details.aspx?id=1479).

Der AD RMS-Server für die Aktivität, z. B. überwachen, indem Sie überprüfen die [Anforderungen in der Systemintegritätsbericht](https://technet.microsoft.com/library/ee221012%28v=ws.10%29.aspx), der [Service-Anforderung Tabelle](http://technet.microsoft.com/library/dd772686%28v=ws.10%29.aspx) oder [Überwachung des Benutzerzugriffs auf geschützte Inhalte](http://social.technet.microsoft.com/wiki/contents/articles/3440.ad-rms-frequently-asked-questions-faq.aspx). Wenn Sie sichergestellt haben, dass RMS-Clients kommunizieren nicht mehr mit diesen Servern und Clients erfolgreich Azure RMS verwenden, können Sie die AD RMS-Serverrolle aus diesen Server entfernen. Wenn Sie dedizierte Server verwenden, möchten Sie vielleicht den Warnhinweis Schritt des ersten Herunterfahren der Server für eine bestimmte Zeitdauer, um sicherzustellen, dass keine gemeldeten Probleme auftreten, das möglicherweise Neustarten von diesen Servern um Kontinuität des Dienstes sicherzustellen, während Sie untersuchen, warum Azure RMS Clients nicht verwendet werden.

Nach außer Betrieb Ihrer AD RMS-Server, sollten Sie die Gelegenheit nutzen, überprüfen die Vorlagen im Azure-Verwaltungsportal und Konsolidierung, damit Benutzer weniger zwischen, auswählen oder neu konfigurieren oder sogar neue Vorlagen hinzugefügt. Außerdem wäre dies ein guter Zeitpunkt, um die Standardvorlagen zu veröffentlichen. Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md).

### <a name="BKMK_Step9Migration"></a>Schritt 9. Erneut Ihren Azure RMS-mandantenschlüssel
Dieser Schritt ist erforderlich, wenn die Migration ist abgeschlossen, wenn die AD RMS-Bereitstellung RMS kryptografische Modus 1 verwendet wurde, da Neuvergabe einen neuen mandantenschlüssel erstellt, der RMS-Kryptografiemodus 2 verwendet. Verwenden von Azure RMS mit den Kryptografiemodus 1 wird nur während der Migration unterstützt.

Dieser Schritt ist optional, jedoch empfohlen, wenn die Migration abgeschlossen ist, auch wenn Sie im RMS-Kryptografiemodus 2, ausgeführt wurden, da es schützt Ihren Azure RMS-mandantenschlüssel von potenziellen Sicherheitslücken auf Ihren AD RMS-Schlüssel. Wenn Sie Ihren Azure RMS-mandantenschlüssel (auch bekannt als "Ihres Schlüssels Gleitender") neu vergeben, ein neuer Schlüssel erstellt wird, und der ursprüngliche Schlüssel archiviert. Da die Umstellung von einem Schlüssel zu einem anderen geschieht nicht unmittelbar, aber in einigen Wochen nicht warten bis Sie vermuten eine Verletzung auf Ihren ursprünglichen Schlüssel jedoch Ihre RMS-mandantenschlüssel neu vergeben, sobald die Migration abgeschlossen ist.

Um Ihre Azure RMS-mandantenschlüssel neu vergeben:

- Wenn Ihr RMS-mandantenschlüssel von Microsoft verwaltet wird: Rufen Sie Microsoft Customer Support Services (CSS) und nachweisen, dass Sie den RMS-Tenant-Administrator sind.

- Wenn Ihr RMS-mandantenschlüssel von Ihnen (BYOK) verwaltet wird: Wiederholen Sie den Vorgang BYOK generieren und einen neuen Schlüssel zu erstellen, über das Internet oder persönlich.

Weitere Informationen zum Verwalten der RMS-mandantenschlüssel finden Sie unter [Vorgänge für Ihren Azure Rights Management-Mandantenschlüssel](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

