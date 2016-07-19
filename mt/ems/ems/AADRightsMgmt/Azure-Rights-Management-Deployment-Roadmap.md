---
title: Roadmap f&#252;r die Bereitstellung von Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
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
# Roadmap f&#252;r die Bereitstellung von Azure Rights Management
Führen Sie die folgenden Schritte aus, um Azure Rights Management (Azure RMS) für Ihre Organisation vorzubereiten, zu implementieren und zu verwalten.

Wenn Sie Azure RMS jedoch schnell einmal selbst ausprobieren möchten, statt es in eine Produktionsumgebung einzuführen, siehe [Schnellstart-Lernprogramm für Azure Rights Management](../../ems/AADRightsMgmt/Quick-Start-Tutorial-for-Azure-Rights-Management.md).

> [!IMPORTANT]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md) gelesen haben.

Es gibt mehrere Abonnementtypen, die [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] einschließen. Weitere Informationen finden Sie im Abschnitt [Cloud subscriptions that support Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_SupportedSubscriptions) im Thema [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md). Stellen Sie außerdem sicher, dass Ihr Abonnement die Funktionen umfasst, die Sie in Ihrer Organisation verwenden möchten, indem Sie die Tabelle unter [Vergleich der Rights Management Services (RMS)-Angebote](https://technet.microsoft.com/dn858608) heranziehen.

Bevor Sie mit der Verwendung von [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] beginnen, führen Sie folgende Vorbereitungsschritte aus:

1. Stellen Sie sicher, dass Ihr Azure- oder Office 365-Mandant die Benutzerkonten und -gruppen enthält, die zum Authentifizieren von Benutzern in Ihrer Organisation durch Azure RMS verwendet werden. Falls erforderlich, erstellen Sie diese Konten und Gruppen, oder synchronisieren Sie diese über Ihr lokales Verzeichnis. Weitere Informationen finden Sie unter [Vorbereiten für Azure Rights Management](../../ems/AADRightsMgmt/Preparing-for-Azure-Rights-Management.md).

2. Entscheiden Sie, ob Sie möchten, dass Microsoft Ihren Mandantenschlüssel verwaltet (Standard), oder ob Sie Ihren Mandantenschlüssel selber generieren und verwalten möchten (bekannt als BYOK, Bring Your Own Key). Beachten Sie, dass Sie derzeit BYOK nicht verwenden können, wenn Sie Exchange Online nutzen. Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

3. Installieren Sie das Windows PowerShell-Modul für [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] auf mindestens einem Computer, der Zugang zum Internet hat. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).

4. Wenn Sie derzeit lokale Rights Management Services verwenden: Führen Sie eine Migration aus, um die Schlüssel, Vorlagen und URLs in die Cloud zu verschieben. Weitere Informationen finden Sie unter [Migration von AD RMS zu Azure Rights Management](../../ems/AADRightsMgmt/Migrating-from-AD-RMS-to-Azure-Rights-Management.md).

5. Aktivieren Sie Rights Management, damit Sie mit der Verwendung des Diensts beginnen können. Wenn eine Bereitstellung in Phasen erforderlich ist, konfigurieren Sie benutzerbezogene Steuerungsrichtlinien für die Einbindung (Onboarding), um die Nutzung auf bestimmte Benutzer zu beschränken. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md).

Erwägen Sie optional die Konfigurierung folgender Funktionen:

- Benutzerdefinierte Vorlagen, wenn die Standardvorlagen für Rechterichtlinien für Ihre Organisation nicht ausreichend sind. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md).

- Nutzungsprotokollierung, sodass Sie überwachen können, wie Ihre Organisation Rights Management verwendet. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Protokollieren und Analysieren von Azure Rights Management-Nutzung](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md).

Die Konfiguration Ihrer Anwendungen kann das Installieren der Rights Management-Freigabeanwendung umfassen sowie die Aktivierung von Unterstützung für IRM-Features in SharePoint Online oder Exchange Online. Weitere Informationen finden Sie unter [Konfigurieren von Clientanwendungen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md).

Wenn Sie über vorhandene IT-Dienste verfügen, die von Azure RMS zu schützende Dateien überprüfen müssen (z. B. DLP-Lösungen, Gateways zur Inhaltsverschlüsselung und Antischadsoftware), konfigurieren Sie die Dienstkonten mit Administratorberechtigungen für Azure RMS. Weitere Informationen finden Sie unter [Konfigurieren von Administratoren für Azure Rights Management und Discovery Services oder Wiederherstellen von Daten](../../ems/AADRightsMgmt/Configuring-Super-Users-for-Azure-Rights-Management-and-Discovery-Services-or-Data-Recovery.md).

Wenn Sie über lokale Dienste verfügen, die Sie mit Azure Rights Management verwenden möchten, installieren und konfigurieren Sie den Rights Management-Verbindungsdienst. Weitere Informationen finden Sie unter [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md).

Sie können jetzt geschützte Inhalte veröffentlichen und nutzen sowie die Nutzung von Rights Management durch Ihre Organisation protokollieren. Weitere Informationen finden Sie unter [Mithilfe von Azure Rights Management](../../ems/AADRightsMgmt/Using-Azure-Rights-Management.md).

Wenn Sie mit der Verwendung von [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] beginnen, kann das [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)]-Modul für Windows PowerShell nützlich sein, um administrative Änderungen skriptgestützt oder automatisiert durchzuführen. Weitere Informationen finden Sie unter [Verwalten von Azure Rights Management mithilfe von WindowsPowerShell](../../ems/AADRightsMgmt/Administering-Azure-Rights-Management-by-Using-Windows-PowerShell.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

