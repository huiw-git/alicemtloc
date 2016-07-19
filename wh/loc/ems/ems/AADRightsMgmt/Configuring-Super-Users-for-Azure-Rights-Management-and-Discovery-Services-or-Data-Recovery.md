---
title: Konfigurieren von Administratoren f&#252;r Azure Rights Management und Discovery Services oder Wiederherstellen von Daten
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: acb4c00b-d3a9-4d74-94fe-91eeb481f7e3
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
# Konfigurieren von Administratoren f&#252;r Azure Rights Management und Discovery Services oder Wiederherstellen von Daten
Mit der Administratorfunktion von Microsoft [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS) wird sichergestellt, dass nur entsprechend berechtigte Personen und Dienste immer auf die Daten zugreifen und diese überprüfen können, die Azure RMS für Ihre Organisation schützt. Falls notwendig, können diese Personen/Dienste auch den zuvor angewendeten Schutz aufheben oder ändern. Ein Administrator verfügt immer über die vollständigen Besitzerrechte für alle Nutzungslizenzen, die vom RMS-Mandanten der Organisation gewährt wurden. Diese Fähigkeit wird gelegentlich als "Schlussfolgern über Daten" (reasoning over data) bezeichnet und ist ein ausschlaggebendes Element dabei, die Kontrolle über die Daten Ihrer Organisation zu behalten. So verwenden Sie diese Funktion beispielsweise für alle der folgenden Szenarien:

-   Ein Mitarbeiter verlässt die Organisation, und Sie müssen alle Dateien lesen können, die von dieser Person geschützt wurden.

-   Ein IT-Administrator muss die aktuelle Schutzrichtlinie entfernen, die für Dateien konfiguriert wurde, und eine neue Schutzrichtlinie anwenden.

-   Exchange Server muss Postfächer für Suchvorgänge indizieren.

-   Sie verfügen über IT-Dienste für DLP-Lösungen (Data Loss Prevention, Verhinderung von Datenverlust), über Inhaltsverschlüsselungsgateways (Content Encryption Gateways, CEGs) und Antischadsoftware, die Dateien überprüfen müssen, die bereits geschützt sind.

-   Sie müssen große Mengen von Dateien in einem Zug zu Überwachungszwecken oder aus rechtlichen oder anderen Compliance-Gründen entschlüsseln.

Standardmäßig ist die Administratorfunktion nicht aktiviert, und dieser Rolle sind keine Benutzer zugeordnet. Sie wird jedoch automatisch aktiviert, wenn Sie den Rights Management-Connector für Exchange konfigurieren; für Standarddienste, die unter Exchange Online, SharePoint Online oder SharePoint Server ausgeführt werden, ist sie nicht erforderlich.

Wenn Sie die Administratorfunktion manuell aktivieren müssen, verwenden Sie das Windows PowerShell-Cmdlet [Enable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629400.aspx), und ordnen Sie dann mithilfe des Cmdlets [Add-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629411.aspx) Benutzer (oder Dienstkonten) zu. Sie können einen oder mehrere Administratoren für Ihre Organisation haben, jedoch müssen Sie einzelne Benutzer hinzufügen; Gruppen werden nicht unterstützt.

> [!NOTE]
> Wenn Sie das Windows PowerShell-Modul für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] noch nicht installiert haben, finden Sie Informationen hierzu unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).

Bewährte Sicherheitsmethoden für die Administratorfunktion:

-   Beschränken und überwachen Sie die Administratoren, die als globale Administratoren für Ihren Office 365- oder Azure RMS-Mandanten fungieren oder denen mithilfe des Cmdlets [Add-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629417.aspx) die Rolle „GlobalAdministrator“ zugeordnet wurde. Diese Benutzer können die Administratorfunktion aktivieren und Benutzer (einschließlich der eigenen Person) als Administratoren festlegen und damit potenziell alle Dateien entschlüsseln, die von Ihrer Organisation geschützt werden.

-   Wenn Sie anzeigen möchten, welche Benutzer- und Dienstkonten Administratorrechte haben, verwenden Sie das Cmdlet [Get-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629408.aspx).  Wie alle administrativen Vorgänge werden auch das Aktivieren oder Deaktivieren der Administratorfunktion sowie das Hinzufügen oder Entfernen von Administratoren protokolliert und können mithilfe des Befehls [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) überwacht werden. Wenn Administratoren Dateien entschlüsseln, wird dieser Vorgang ebenfalls protokolliert und kann mit der [Verwendungsprotokollierung](https://technet.microsoft.com/library/dn529121.aspx) überwacht werden.

-   Wenn Sie die Administratorfunktion für die alltäglichen Dienste nicht benötigen, sollten Sie diese Funktion nur im Bedarfsfall aktivieren und mit dem Cmdlet [Disable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629428.aspx) wieder deaktivieren.

Der folgende Protokollauszug zeigt einige Beispieleinträge, die mit dem Cmdlet „Get-AadrmAdminLog“ erstellt wurden. In diesem Beispiel bestätigt der Administrator von Contoso Ltd., dass die Administratorfunktion deaktiviert ist, fügt Richard Simone als Administrator hinzu, überprüft, dass Richard der einzige für Azure RMS konfigurierte Administrator ist, und aktiviert dann die Administratorfunktion, damit Richard nun einige Dateien entschlüsseln kann, die zuvor von einem Mitarbeiter geschützt wurden, der das Unternehmen mittlerweile verlassen hat.

`2015-08-01T18:58:20	admin@contoso.com	GetSuperUserFeatureState	Passed	Disabled`
`2015-08-01T18:59:44	admin@contoso.com	AddSuperUser -id rsimone@contoso.com	Passed	True`
`2015-08-01T19:00:51	admin@contoso.com	GetSuperUser	Passed	rsimone@contoso.com`
`2015-08-01T19:01:45	admin@contoso.com	SetSuperUserFeatureState -state Enabled	Passed	True`

## <a name="BKMK_RMSProtectionModule"></a>Skriptoptionen für Administratoren
Eine Person, die als Administrator für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] fungiert, muss häufig den Schutz von mehreren Dateien an mehreren Speicherorten aufheben. Dies kann zwar manuell erfolgen, es ist jedoch effizienter (und häufig auch zuverlässiger), wenn ein Skript verwendet wird. Laden Sie hierfür das [RMS Protection Tool](http://www.microsoft.com/en-us/download/details.aspx?id=47256) herunter. Verwenden Sie dann die Cmdlets [Unprotect-RMSFile](https://msdn.microsoft.com/library/azure/mt433200.aspx) und [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx) den Anforderungen entsprechend.

> [!IMPORTANT]
> Obwohl das RMS Protection Tool für Administratoren entwickelt wurde, die den Schutz von großen Dateimengen zu Wiederherstellungszwecken aufheben müssen, unterstützt die aktuelle Version des Tools nicht die Benutzerauthentifizierung für Azure RMS. Bis die Einschränkung aufgehoben wurden, müssen Sie ein Dienstprinzipalkonto für die Authentifizierung bei Azure RMS verwenden, bevor Sie den Schutz von Dateien aufheben können.  Weitere Informationen und Anleitungen finden Sie unter [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/azure/mt433202.aspx).

Weitere Informationen zu diesen Cmdlets finden Sie unter [RMS Protection Cmdlets](https://msdn.microsoft.com/library/azure/mt433195.aspx).

> [!NOTE]
> Das Windows-PowerShell-Modul RMSProtection im Lieferumfang des RMS Protection Tools unterscheidet sich vom [Windows PowerShell-Hauptmodul für Azure Rights Management](https://technet.microsoft.com/library/jj585027.aspx) und soll als Ergänzung dienen. Es unterstützt sowohl Azure RMS als auch AD RMS.

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

