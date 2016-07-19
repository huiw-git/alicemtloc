---
title: Au&#223;erbetriebsetzen und Deaktivieren von Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0b1c2064-0d01-45ae-a541-cebd7fd762ad
translation.priority.ht: 
  - bg-bg
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
  - hu-hu
  - nb-no
  - nl-nl
  - pl-pl
  - pt-pt
  - sv-se
---
# Au&#223;erbetriebsetzen und Deaktivieren von Azure Rights Management
Sie können jederzeit steuern, ob Ihre Organisation Inhalte mithilfe von [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] (Azure RMS) schützt, und wenn Sie entscheiden, dass diese Lösung zum Schützen von Daten nicht mehr verwendet werden soll, können Sie sich sicher sein, dass Ihnen die Inhalte, die zuvor geschützt waren, weiterhin uneingeschränkt zur Verfügung stehen. Wenn Sie keinen weiteren Zugriff auf zuvor geschützte Inhalte mehr benötigen, deaktivieren Sie einfach den Dienst, und lassen Sie Ihr Abonnement für Azure Rights Management ablaufen. Dies ist zum Beispiel angebracht, nachdem Sie das Testen von [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] abgeschlossen haben, und bevor Sie es in der Produktionsumgebung bereitstellen.

Wenn Sie [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] jedoch in der Produktionsumgebung bereitgestellt haben, müssen Sie sicherstellen, dass Sie über eine Kopie Ihres Azure Rights Management-Mandantenschlüssels verfügen, bevor Sie den Dienst deaktivieren. Tun Sie dies vor Ablauf des Abonnements, weil dadurch sichergestellt ist, dass Sie nach dem Deaktivieren des Diensts weiterhin Zugriff auf Inhalte haben, die von Azure Rights Management geschützt wurden. Wenn Sie die BYOK-Lösung (Bring Your Own Key) verwendet haben, bei der Sie Ihren eigenen Schlüssel in einem HSM erzeugen und verwalten, verfügen Sie bereits über Ihren Azure Rights Management-Mandantenschlüssel. Wenn der Schlüssel jedoch von Microsoft verwaltet wurde (Standardlösung), lesen Sie die Anweisungen zum Exportieren Ihres Mandantenschlüssels im Thema [Vorgänge für Ihren Azure Rights Management-Mandantenschlüssel](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md).

> [!TIP]
> Selbst nachdem Ihr Abonnement abgelaufen ist, steht Ihnen Ihr Azure Rights Management-Mandant zur Nutzung der Inhalte für einen erweiterten Zeitraum zur Verfügung. Sie können den Mandantenschlüssel dann jedoch nicht mehr exportieren.

Wenn Sie über einen Azure RMS-Mandantenschlüssel verfügen, können Sie Rights Management lokal bereitstellen (AD RMS) und Ihren Mandantenschlüssel als eine vertrauenswürdige Veröffentlichungsdomäne (Trusted Publishing Domain, TPD) importieren. Ihnen stehen dann die folgenden Optionen für die Außerbetriebsetzung Ihrer Azure Rights Management -Bereitstellung zur Verfügung:

|Wenn dies auf Sie zutrifft, ...|… gehen Sie wie folgt vor:|
|-----------------------------------|------------------------------|
|Sie möchten, dass alle Benutzer weiterhin Rights Management verwenden, wobei Sie jedoch eine lokale Lösung statt Azure RMS verwenden möchten.    →|Verwenden Sie das Cmdlet [Set-AadrmMigrationUrl](https://msdn.microsoft.com/library/azure/dn629429.aspx), um vorhandene Benutzer zu Ihrer lokalen Bereitstellung zu leiten, wenn diese Benutzer Inhalte verwenden möchten, die nach dieser Änderung geschützt wurden. Benutzer verwenden automatisch die AD RMS-Installation, um die geschützten Inhalt zu nutzen.<br /><br />Damit Benutzer Inhalte verwenden können, die vor dieser Änderung geschützt wurden, leiten Sie die Clients auf die lokale Bereitstellung um, indem Sie den **LicensingRedirection**-Registrierungsschlüssel für Office 2016 oder Office 2013 verwenden, wie im [Abschnitt zur Diensterkennung](https://technet.microsoft.com/library/jj159267%28v=ws.10%29.aspx#BKMK_ServiceDiscovery) in den Bereitstellungsanmerkungen für den RMS-Client beschrieben, sowie den **LicenseServerRedirection**-Registrierungsschlüssel für Office 2010 verwenden, wie unter [Office Registry Settings](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx) beschrieben.|
|Sie möchten die Rights Management-Technologie überhaupt nicht mehr verwenden    →|Gewähren Sie einem vorgesehenen Administrator [Administratorberechtigungen](https://technet.microsoft.com/library/mt147272.aspx), und stellen Sie dieser Person das [RMS Protection Tool](http://www.microsoft.com/en-us/download/details.aspx?id=47256) zur Verfügung.<br /><br />Dieser Administrator kann dann mit dem Tool eine Massenentschlüsselung der Dateien in Ordnern durchführen, die durch Azure RMS geschützt wurden, sodass die Dateien wieder ungeschützt sind und daher ohne eine Rights Management-Technologie wie Azure RMS oder AD RMS gelesen werden können. Dieses Tool kann sowohl mit Azure RMS als auch mit AD RMS verwendet werden. Sie können daher wählen, ob die Dateien vor oder nach dem Deaktivieren von Azure RMS oder in einer Kombination entschlüsselt werden sollen.|
|Sie können nicht alle Dateien ermitteln, die durch Azure RMS geschützt wurden, oder Sie möchten, dass alle Benutzer automatisch jede geschützte Datei lesen können, die verpasst wurde    →|Stellen Sie eine Registrierungseinstellung auf allen Clientcomputern bereit, indem Sie den **LicensingRedirection**-Registrierungsschlüssel für Office 2016 und Office 2013 verwenden, wie im [Abschnitt zur Diensterkennung](https://technet.microsoft.com/library/jj159267%28v=ws.10%29.aspx#BKMK_ServiceDiscovery) in den Bereitstellungsanmerkungen für den RMS-Client beschrieben, sowie den **LicenseServerRedirection**-Registrierungsschlüssel für Office 2010 verwenden, wie unter [Office Registry Settings](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx) beschrieben.<br /><br />Stellen Sie außerdem eine weitere Registrierungseinstellung bereit, um zu verhindern, dass Benutzer neue Dateien schützen. Legen Sie dazu **DisableCreation** auf **1** fest, wie unter [Office Registry Settings](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx) beschrieben.|
|Sie möchten einen kontrollierten, manuellen Wiederherstellungsdienst für Dateien verwenden, die übergangen wurden    →|Gewähren Sie designierten Benutzern in einer Datenwiederherstellungsgruppe [Administratorberechtigungen](https://technet.microsoft.com/library/mt147272.aspx), und stellen Sie diesen Benutzern das [RMS Protection Tool](http://www.microsoft.com/en-us/download/details.aspx?id=47256) zur Verfügung, sodass sie den Schutz von Dateien aufheben können, wenn sie von Standardbenutzern dazu aufgefordert werden.<br /><br />Stellen Sie auf allen Computern die Registrierungseinstellung bereit, mit der verhindert wird, dass Benutzer neue Dateien schützen können. Legen Sie dazu **DisableCreation** auf **1** fest, wie unter [Office Registry Settings](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx) beschrieben.|
Weitere Informationen zu den Vorgehensweisen in dieser Tabelle finden Sie in den folgenden Ressourcen:

-   Informationen zu AD RMS und Bereitstellungsreferenzen finden Sie unter [Active Directory-Rechteverwaltungsdienste (Übersicht)](https://technet.microsoft.com/library/hh831364.aspx).

-   Anweisungen, wie Sie Ihren Azure RMS-Mandantenschlüssel als TPD-Datei importieren, finden Sie unter [Hinzufügen einer vertrauenswürdigen Veröffentlichungsdomäne](https://technet.microsoft.com/library/cc771460.aspx).

-   Informationen zum Installieren des Windows PowerShell-Moduls für Azure RMS, um die Migrations-URL festzulegen, finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).

Wenn Sie soweit sind, dass Sie den Azure RMS-Dienst für Ihre Organisation deaktivieren können, gehen Sie gemäß den folgenden Anweisungen vor.

## Deaktivieren von Rights Management
Verwenden Sie eine der folgenden Methoden, um [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] zu deaktivieren.

> [!TIP]
> Sie können auch das Windows PowerShell-Cmdlet [Disable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629422.aspx) verwenden, um [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] zu deaktivieren.

#### So deaktivieren Sie Rights Management über das Office 365 Admin Center

1.  [Melden Sie sich bei Office 365 mit Ihrem Geschäfts- oder Schulkonto an](https://portal.office.com/), das für Ihre Office 365-Bereitstellung ein Administratorkonto ist.

2.  Wenn das Office 365 Admin Center nicht automatisch angezeigt wird, wählen Sie in der linken oberen Ecke das Symbol für das App-Startprogramm aus, und wählen Sie dann **Administrator** aus. Die Kachel **Administrator** wird nur für Office 365-Administratoren angezeigt.

    > [!TIP]
    > Hilfe zum Admin Center finden Sie unter [Informationen zum Office 365 Admin Center - Administratorhilfe](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547).

3.  Klicken Sie im linken Bereich auf **DIENSTEINSTELLUNGEN**.

4.  Klicken Sie auf **Rights Management**.

5.  Klicken Sie auf der Seite **RIGHTS MANAGEMENT** auf **Verwalten**.

6.  Klicken Sie auf der Seite **Rechteverwaltung** auf **Deaktivieren**.

7.  Klicken Sie, wenn Sie gefragt werden **Möchten Sie die Rechteverwaltung deaktivieren?**, auf **Deaktivieren**.

Es sollten jetzt **Rights Management ist nicht aktiviert** und die Option zum Aktivieren angezeigt werden.

#### So deaktivieren Sie Rights Management über das Azure-Portal

1.  Melden Sie sich beim [Azure-Portal](http://go.microsoft.com/fwlink/p/?LinkID=275081) an.

2.  Klicken Sie im linken Bereich auf **ACTIVE DIRECTORY**.

3.  Klicken Sie auf der Seite **Active Directory** auf **RIGHTS MANAGEMENT**.

4.  Wählen Sie das Verzeichnis aus, für das Sie [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] verwalten möchten, klicken Sie auf **DEAKTIVIEREN**, und bestätigen Sie Ihre Aktion.

Der **RECHTEVERWALTUNGSSTATUS** sollte jetzt als **Inaktiv** angezeigt werden und die Option **DEAKTIVIEREN** durch **AKTIVIEREN** ersetzt sein.

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

