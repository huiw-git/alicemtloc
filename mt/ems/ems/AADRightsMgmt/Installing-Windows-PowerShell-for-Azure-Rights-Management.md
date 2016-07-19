---
title: Installieren WindowsPowerShell f&#252;r Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0d665ed6-b1de-4d63-854a-bc57c1c49844
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
# Installieren WindowsPowerShell f&#252;r Azure Rights Management
Verwenden Sie die folgende Informationen können Sie die Installation von Windows PowerShell für Microsoft [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS).

Können Sie dieses Windows PowerShell-Modul verwaltet [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] von der Befehlszeile aus mithilfe von jedem Computer, der über einen Internetanschluss verfügt und die erforderlichen Komponenten erfüllt, die im nächsten Abschnitt aufgeführt. Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] unterstützt Skripts für die Automatisierung oder kann für erweiterte Szenarien erforderlich sein. Weitere Informationen zu den Verwaltungsaufgaben und Konfigurationen, die das Modul unterstützt, finden Sie unter [Verwalten von Azure Rights Management mithilfe von WindowsPowerShell](../../ems/AADRightsMgmt/Administering-Azure-Rights-Management-by-Using-Windows-PowerShell.md).

## Voraussetzungen
Diese Tabelle listet die erforderlichen Komponenten zum Installieren und Verwenden von Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)].

|Anforderung|Weitere Informationen|
|---------------|-------------------------|
|Eine Version von Windows, unterstützt die [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] Verwaltungsmodul|Überprüfen Sie die Liste der unterstützten Betriebssysteme in der **System Requirements** Teil der [-Downloadseite für Azure Rights Management-Administrationstool](http://go.microsoft.com/fwlink/?LinkId=257721).|
|Mindestversion von Windows PowerShell: 2.0|Unterstützung für die [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] Verwaltungsmodul wird in Windows PowerShell 2.0 eingeführt.<br /><br />Die meisten Windows-Betriebssystemen installiert standardmäßig mit mindestens Version 2.0 von Windows PowerShell. Wenn Sie Windows PowerShell 2.0 installieren müssen, finden Sie unter [Installieren von Windows PowerShell 2.0](http://msdn.microsoft.com/library/ff637750.aspx). **Tip:** Sie können bestätigen, dass die Version von Windows PowerShell, die Sie durch Eingabe ausführen **$PSVersionTable** in einer Windows PowerShell-Sitzung.|
|Mindestversion von Microsoft .NET Framework: 4.5 **Tip:** Diese Version von Microsoft .NET Framework ist in den späteren Betriebssystemen enthalten, benötigen Sie nur sollte es manuell zu installieren, wenn Ihr Clientbetriebssystem kleiner als Windows 8.0 ist oder das Betriebssystem kleiner als Windows Server 2012 ist.|Wenn dies nicht bereits installiert ist, können Sie Herunterladen der [Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653).<br /><br />Diese Version von Microsoft .NET Framework ist für einige der Klassen erforderlich, die [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] -Administrationsmodul verwendet.|
|Microsoft Online Services-In-Assistent 7.0|Der Microsoft Online Services-Anmeldeassistent ist erforderlich für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] Authentifizierung.<br /><br />Weitere Informationen finden Sie unter [Download Center: Microsoft Online Services-Assistent für IT-Experten RTW](http://www.microsoft.com/en-us/download/details.aspx?id=41950).|

## Gewusst wie: Installieren der Rights Management-Moduls "Verwaltung"

1.  Wechseln Sie zum Microsoft Download Center und [Herunterladen von Azure Rights Management-Administrationstool](https://go.microsoft.com/fwlink/?LinkId=257721), enthält die [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] Verwaltungsmodul für Windows PowerShell.

2.  Aus dem lokalen Ordner, in dem Sie heruntergeladen haben, und speichern, die [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] Installer-Datei, doppelklicken Sie auf die ausführbare Datei, die Sie für Ihre Plattform (WindowsAzureADRightsManagementAdministration_x64 oder WindowsAzureADRightsManagementAdministration_x86.exe) heruntergeladen haben, um den Azure AD Rights Management Administration Setup-Assistenten zu starten.

3.  Schließen Sie den Assistenten ab.

Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] ist jetzt installiert.

## Nächste Schritte
Um zu sehen, welche Cmdlets verfügbar sind, starten Sie Windows PowerShell mit dem **als Administrator ausführen** aus, und geben Sie Folgendes ein:

```
Get-Command -Module aadrm
```
Verwendung `the Get-Help <cmdlet_name>` Befehl aus, um die Hilfe für ein bestimmtes Cmdlet anzuzeigen.

Weitere Informationen:

-   Vollständige Liste der verfügbaren Cmdlets: [Azure Rights Management-Cmdlets](https://msdn.microsoft.com/library/windowsazure/dn629398.aspx)

-   Die Liste der hauptkonfigurationsszenarios, die Windows PowerShell unterstützen: [Verwalten von Azure Rights Management mithilfe von WindowsPowerShell](../../ems/AADRightsMgmt/Administering-Azure-Rights-Management-by-Using-Windows-PowerShell.md)

Bevor Sie Befehle ausführen können, die Konfigurieren der [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] -Dienst müssen Sie mit dem Dienst verbinden, mit der [Connect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629415.aspx) Cmdlet. Wenn Sie die Konfigurationsbefehlen ausgeführt haben, trennen Sie den Dienst mithilfe der [Disconnect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629416.aspx) Cmdlet.

> [!NOTE]
> Wenn Sie noch nicht aktiviert haben [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)], Sie können dies tun, nachdem Sie mit dem Dienst verbunden haben, mit der [Enable-Aadrm](https://msdn.microsoft.com/library/windowsazure/dn629412.aspx) Cmdlet.

## Siehe auch
[Verwalten von Azure Rights Management mithilfe von WindowsPowerShell](../../ems/AADRightsMgmt/Administering-Azure-Rights-Management-by-Using-Windows-PowerShell.md)

