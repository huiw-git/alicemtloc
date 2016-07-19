---
title: Konfigurieren benutzerdefinierter Vorlagen f&#252;r Azure Rights Management
ms.custom: na
ms.date: 12/25/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1775d8d0-9a59-42c8-914f-ce285b71ac1c
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
# Konfigurieren benutzerdefinierter Vorlagen f&#252;r Azure Rights Management
Nachdem Sie Azure Rights Management (Azure RMS) aktiviert haben, können Benutzer automatisch zwei Standardvorlagen zu verwenden, die für diese Richtlinien auf vertrauliche Dateien anwenden, die Zugriff auf autorisierte Benutzer in Ihrer Organisation zu erleichtern. Diese zwei Vorlagen enthalten die folgenden rechterichtlinieneinschränkungen:

-   Schreibgeschützte Anzeige geschützter Inhalte

    -   Anzeigename: **&lt; Name der Organisation &gt; – nur vertrauliche Ansicht**

    -   Spezielle Berechtigung: Inhalt anzeigen

-   Lesen oder Ändern von Berechtigungen für den geschützten Inhalt

    -   Anzeigename: **&lt; Name der Organisation &gt; - vertrauliche**

    -   Bestimmte Berechtigungen: Inhalt anzeigen, speichern, Inhalt bearbeiten, zugewiesenen Rechte anzeigen, können Makros, weiterleiten, Antworten, allen Antworten

Darüber hinaus die [RMS-freigabeanwendung](http://technet.microsoft.com/library/dn339006.aspx) können Benutzer ihre eigenen Berechtigungssatz definieren. Und für den Outlook-Client und der Outlook Web Access können Benutzer auswählen den **nicht weiterleiten** Option für e-Mail-Nachrichten.

Für viele Organisationen möglicherweise die Standardvorlagen ausreichen. Aber wenn Sie Vorlagen für eigene benutzerdefinierten Benutzerrechterichtlinien erstellen möchten, Sie können dies tun. Gründe für das Erstellen einer benutzerdefinierten Vorlage umfassen Folgendes:

-   Eine Vorlage für eine Teilmenge von Benutzern in der Organisation statt allen Benutzern zuweisen möchten.

-   Sie soll nur eine Teilmenge der Benutzer anzeigen und Auswählen einer Vorlage (Abteilung) Applications, anstatt alle Benutzer in der Organisation finden Sie unter, und wählen Sie die Vorlage.

-   Definieren ein benutzerdefiniertes Recht für eine Vorlage, z. B. das Anzeigen und bearbeiten, aber nicht kopiert und gedruckt werden soll.

-   Möchten Sie zusätzliche Optionen konfigurieren, in einer Vorlage, die ein Ablaufdatum und gibt an, ob der Inhalt ohne Verbindung zum Internet zugegriffen werden kann.

Für Benutzer in der Lage, eine benutzerdefinierte Vorlage auszuwählen, die solche Einstellungen enthält, müssen Sie zuerst eine benutzerdefinierte Vorlage erstellen, konfigurieren und veröffentlichen Sie sie.

Verwenden Sie zum Konfigurieren und Verwenden von benutzerdefinierten Vorlagen in den folgenden Abschnitten:

-   [How to create, configure, and publish a custom template](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_HowToConfigureCustomTemplates)

-   [How to copy a template](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_HowToCopyTemplates)

-   [How to remove (archive) templates](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_HowToArchiveTemplates)

-   [Refreshing templates for users](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_RefreshingTemplates)

-   [Windows PowerShell reference](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_PowerShellTemplates)

## <a name="BKMK_HowToConfigureCustomTemplates"></a>Erstellen, konfigurieren und Veröffentlichen einer benutzerdefinierten Vorlage
Sie erstellen und verwalten Sie benutzerdefinierte Vorlagen im Azure-Verwaltungsportal. Hierzu können Sie direkt aus dem Azure-Verwaltungsportal, oder melden Sie sich bei Office 365 Administrationscenter, und wählen Sie die **Erweiterte Features** für Rights Management, das dann leitet Sie an das Azure-Verwaltungsportal.

Verwenden Sie die folgenden Verfahren zum Erstellen, konfigurieren und Veröffentlichen von benutzerdefinierten Vorlagen für Rights Management.

#### Beim Erstellen einer benutzerdefinierten Vorlage

1.  Je nachdem, ob Sie das Office 365 Administrationscenter oder Azure-Verwaltungsportal anmelden führen Sie eine der folgenden:

    -   Aus der [Office 365 Administrationscenter](https://portal.office.com/):

        1.  Klicken Sie im linken Bereich auf **diensteinstellungen**.

        2.  Aus der **diensteinstellungen** auf **rights Management**.

        3.  In der **Schützen Sie Ihre Informationen** auf **verwalten**.

        4.  In der **rights Management** auf **Erweiterte Features**.

            > [!NOTE]
            > Wenn Sie Rights Management noch nicht aktiviert haben, klicken Sie zunächst auf **aktivieren** und bestätigen Sie Ihre Aktion. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md).
            > 
            > Wenn Sie nicht aktiviert haben, **Erweiterte Features** nach Rights Management aktiviert ist, befolgen Sie die auf dem Bildschirm Anweisungen, um ein kostenloses Azure-Abonnement erhalten, die erforderlich ist, um das Azure-Verwaltungsportal zugreifen.

    -   Aus der [Azure-Verwaltungsportal](http://go.microsoft.com/fwlink/p/?LinkID=275081):

        1.  Klicken Sie im linken Bereich auf **ACTIVE DIRECTORY**.

        2.  Aus der **active Directory** auf **RIGHTS MANAGEMENT**.

        3.  Wählen Sie das Verzeichnis für Rights Management zu verwalten.

        4.  Wenn Sie Rights Management noch nicht aktiviert haben, klicken Sie auf **aktivieren** und bestätigen Sie Ihre Aktion.

            > [!NOTE]
            > Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md).

2.  Erstellen Sie eine neue Vorlage:

    -   Aus der **Erste Schritte mit Rights Management** schnell Seite zu beginnen, klicken Sie auf **erstellen eine neuen Vorlage für Benutzerrechterichtlinien**.

3.  Auf der **Fügen Sie eine neue Vorlage für Benutzerrechterichtlinien** Seite, wählen Sie eine Sprache, geben Sie den Vorlagennamen und die Beschreibung, die Benutzern angezeigt werden soll (Sie können weitere Sprachen später hinzufügen). Dann geben Sie einen eindeutigen Namen und eine Beschreibung ein, und klicken Sie auf die Schaltfläche Fertig.

Aus der **Erste Schritte mit Rights Management** schnell Seite zu beginnen, klicken Sie auf **verwalten Ihre Vorlagen für Benutzerrechterichtlinien**. Sie sehen Ihre neu erstellte Vorlage hinzugefügt, um die Liste der Vorlagen mit dem Status **archiviert**. In dieser Phase die Vorlage wird erstellt, aber nicht konfiguriert, und ist für Benutzer nicht sichtbar.

#### Konfigurieren und Veröffentlichen einer benutzerdefinierten Vorlage

1.  Wählen Sie die neu erstellte Vorlage aus der **Vorlagen** Seite in Azure-Verwaltungsportal.

2.  Aus der **die Vorlage hinzugefügt wurde** schnell Seite zu beginnen, klicken Sie auf **Einstieg** aus Schritt 1, **Konfigurieren von Berechtigungen für Benutzer und Gruppen,** klicken Sie dann auf **STEIGEN Sie jetzt** oder **Hinzufügen**, und wählen Sie dann die Benutzer und Gruppen mit rechten für den Inhalt zu verwenden, die durch die neue Vorlage geschützt ist.

    > [!NOTE]
    > Die Benutzer oder Gruppen, die Sie auswählen, müssen eine e-Mail-Adresse haben. In einer produktionsumgebung wird dies praktisch immer der Fall sein, aber in einer einfachen testumgebung müssen Sie möglicherweise Benutzerkonten oder Gruppen e-Mail-Adressen hinzufügen.

    Verwenden Sie als bewährte Methode Gruppen statt Benutzer dies vereinfacht die Verwaltung der Vorlagen aus. Wenn Sie lokale Active Directory und Azure AD synchronisiert werden, können Sie e-Mail-aktivierte Gruppen, die von Sicherheitsgruppen oder Verteilergruppen sind. Jedoch wenn Sie allen Benutzern in der Organisation Rechte erteilen möchten, werden effizienter, kopieren Sie die Standardvorlagen, anstatt mehrere Gruppen anzugeben. Weitere Informationen finden Sie im Abschnitt [How to copy a template](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_HowToCopyTemplates) dieses Themas.

    > [!TIP]
    > Vorlagen funktionieren am besten, wenn Gruppen als Empfänger von Rechte angegeben werden. Gruppen in anderen Unternehmen kann nicht derzeit angegeben werden, aber wenn Sie externe Benutzer in einer Vorlage angeben möchten, Sie können dazu mit den folgenden Einschränkungen:
    > 
    > -   Aktivieren Sie die externe Benutzer müssen hier Sie zuerst Kontakte Konten für diese im Verzeichnis erstellen. Wie bereits erwähnt, angeben nicht externe Gruppen.
    > -   Nachdem Sie die Vorlage erstellt haben, können Sie das Windows PowerShell-Cmdlet [Set AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) RightsDefinitions &lt; Liste &lt; TemplateRightsDefinition &gt;&gt;-Parameter die externen Benutzer e-Mail-Adressen hinzu.

3.  Klicken Sie auf die Schaltfläche "Weiter", und weisen Sie eine der aufgeführten Rechte zu Ihren ausgewählten Benutzern und Gruppen.

    Verwenden Sie die angezeigte Beschreibung, Weitere Informationen zu einzelnen Rechte (und für benutzerdefinierte Berechtigungen). Ausführlichere Informationen finden Sie auch in [Konfigurieren von Nutzungsrechte für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Usage-Rights-for-Azure-Rights-Management.md). Allerdings können Clientanwendungen, die RMS unterstützen variieren, Implementierung von diese Rechte. Wenden Sie sich an ihre Dokumentation und eigene Tests für die Programme, die Benutzer verwenden, um das Verhalten zu überprüfen, bevor Sie die Vorlage für Benutzer bereitstellen. Um diese Vorlage für diese Tests nur Administratoren sichtbar zu machen, stellen Sie diese Vorlage eine Abteilung Vorlage (Schritt 6).

4.  Bei Auswahl von **benutzerdefinierte**, klicken Sie auf die Schaltfläche "Weiter", und wählen Sie dann diese benutzerdefinierten Rechte.

    Obwohl Sie eine beliebige Kombination der einzelnen Rechte verfügbar, in einigen Programmen verwenden können, könnten einige Rechte anderen einzelnen rechten abhängig sein. Wenn dies der Fall ist, werden die abhängigen Rechte automatisch für Sie ausgewählt.

    > [!TIP]
    > Erwägen der **Kopieren und extrahieren Sie Content** nach rechts, und gewähren Sie dies für ausgewählte Administratoren oder Mitarbeiter in anderen Rollen, die Verantwortung für die Wiederherstellung von Informationen. Dieses Recht erteilen, können sie das Entfernen des Schutzes bei Bedarf von Dateien und e-Mails, die mit dieser Vorlage geschützt werden. Diese Fähigkeit beim Entfernen des Schutzes auf der Vorlagenebene bietet eine präzisere Kontrolle als die Verwendung der Administratorfunktion.

5.  Klicken Sie auf die Schaltfläche Fertig.

6.  Wenn die Vorlage, die auf nur eine Teilmenge von Benutzern angezeigt werden, wenn sie eine Liste der Vorlagen in der Anwendung angezeigt werden sollen: Klicken Sie auf **Bereich** dies als Abteilung Vorlage konfigurieren, und klicken Sie auf **STEIGEN Sie jetzt**. Andernfalls fahren Sie mit Schritt 9 fort.

    Weitere Informationen zu Vorlagen Abteilungsebene: standardmäßig für alle Benutzer in Ihrem Azure-Verzeichnis alle veröffentlichten Vorlagen angezeigt und sie können wählen Sie sie aus Clientanwendungen beim Inhalt geschützt werden sollen. Gegebenenfalls bestimmte Benutzer nur auf einige der veröffentlichten Vorlagen müssen Sie die Vorlagen für diese Benutzer beschränken. Dann werden nur diese Benutzer diese Vorlagen auswählen können. Andere Benutzer, die Sie nicht angeben werden die Vorlagen nicht angezeigt und daher können nicht ausgewählt werden. Diese Technik kann stellen die richtige Vorlage für Benutzer leichter auswählen, insbesondere, wenn Sie Vorlagen erstellen, die von bestimmten Gruppen oder Abteilungen verwendet werden sollen. Benutzer sehen dann nur die Vorlagen, die dafür entwickelt wurden.

    Beispielsweise haben Sie eine Vorlage für die Personalabteilung erstellt, die die Leseberechtigung für Mitglieder der Finanzabteilung gilt. So, dass bei Verwendung von Rights Management-freigabeanwendung diese Vorlage angewendet werden können wird nur von Mitgliedern der Personalabteilung, benannte Bereich die Vorlage, die die e-Mail-aktivierte Gruppe HumanResources. Nur Mitglieder dieser Gruppe finden Sie unter und kann dann wenden Sie diese Vorlage.

7.  Auf der **Vorlage Sichtbarkeit** Seite, wählen Sie die Benutzer und Gruppen, die anzeigen, und wählen Sie die Vorlage aus der RMS-fähige Anwendung. Als benötigen zuvor als bewährte Methode, verwenden Sie Gruppen statt Benutzer und Gruppen oder Benutzer, die Sie auswählen, eine e-Mail-Adresse.

8.  Klicken Sie auf die Schaltfläche "Weiter", und entscheiden Sie, ob die Anwendungskompatibilität für Ihre Abteilung Vorlage konfigurieren. Wenn Sie klicken, **APPLICATION COMPATIBILITY**, aktivieren Sie das Kontrollkästchen, und klicken Sie auf **Complete**.

    Warum müssen Sie möglicherweise die Anwendungskompatibilität zu konfigurieren? Nicht alle Programme können Abteilung Vorlagen unterstützen. Dazu muss die Anwendung zunächst mit dem RMS-Dienst authentifizieren, vor dem Herunterladen der Vorlagen. Wenn der Authentifizierungsprozess wird standardmäßig nicht auftreten werden keine der Abteilung Vorlagen heruntergeladen. Sie können dieses Verhalten überschreiben, angeben, dass alle Abteilung Vorlagen herunterladen soll, durch Konfigurieren der Anwendungskompatibilität und Auswählen der **Diese Vorlage für alle Benutzer anzeigen, wenn die Anwendung keine Benutzeridentität unterstützen** Kontrollkästchen.

    Z. B., wenn Sie nicht in unserem Beispiel Human Resources-Anwendungskompatibilität für die Abteilung Vorlage konfigurieren, finden Sie unter nur Benutzer in der Personalabteilung die Abteilung Vorlage bei der Verwendung der RMS-freigabeanwendung, aber keine Benutzer finden Sie unter der Abteilung Vorlage aus, wenn sie Outlook Web Access (OWA) von Exchange Server 2013 verwenden, weil Exchange OWA und Exchange ActiveSync zurzeit keine Abteilung Vorlagen unterstützen. Wenn Sie dieses Standardverhalten überschreiben, indem Sie die Anwendungskompatibilität zu konfigurieren, unter nur Benutzer in der Personalabteilung der Abteilung eine Vorlage aus, bei der Verwendung der RMS-Freigabe, aber alle Benutzer finden Sie in der Abteilung Vorlage bei Verwendung von Outlook Web Access (OWA). Wenn Benutzer über OWA oder Exchange ActiveSync von Exchange Online verwenden, alle Benutzer sehen die Abteilung Vorlagen oder keine Benutzer sehen die Department-Vorlagen, basierend auf der Vorlage Status (Archivierung oder veröffentlichten) in Exchange Online.

    > [!NOTE]
    > Wenn Sie Programme, die noch systemintern Abteilung Vorlagen nicht unterstützen verfügen, können Sie eine [benutzerdefinierte RMS-Vorlage-Download-Skript](http://go.microsoft.com/fwlink/?LinkId=524506) oder andere Tools zur Bereitstellung dieser Vorlagen im lokalen Ordner der RMS-Client. Dann werden diese Programme ordnungsgemäß anzeigen die Abteilung Vorlagen nur die Benutzer und Gruppen, die Sie für den Bereich der Vorlage ausgewählt:
    > 
    > -   Für Office 2010 ist der Ordner "Client" **%localappdata%\Microsoft\DRM\Templates**.
    > -   Von einem Client-Computer, der alle Vorlagen heruntergeladen wurde, können Sie kopieren und fügen Sie dann die Vorlagendateien auf anderen Computern.
    > 
    > Systemeigene Unterstützung für Office 2016 Abteilung Vorlagen und wird somit Office 2013 mit den neuesten Office-Updates ([KB 3054853](https://support.microsoft.com/kb/3054853)).

9. Klicken Sie auf **konfigurieren** und Hinzufügen von zusätzlichen Sprachen, die Benutzer, sowie Name und Beschreibung dieser Vorlage in dieser Sprache verwenden. Wenn Sie mehrsprachige Benutzer haben, ist es wichtig, fügen jede Sprache, die sie verwenden, und geben Sie einen Namen und eine Beschreibung in der jeweiligen Sprache. Benutzer dann sehen den Namen und die Beschreibung der Vorlage in derselben Sprache wie ihre Client-Betriebssystem die stellt sicher, dass sie die Richtlinie für ein Dokument oder eine e-Mail-Nachricht verstehen. Liegt keine Übereinstimmung mit ihrem Clientbetriebssystem, fragt Name und Beschreibung, die sie sehen die Sprache und die Beschreibung, die beim Erstellen der Vorlage definiert.

    Überprüfen Sie, ob Sie den folgenden Einstellungen ändern möchten:

    |Einstellung|Weitere Informationen|
    |---------------|-------------------------|
    |**Ablauf von Inhalten**|Definieren Sie ein Datum oder eine Anzahl von Tagen für diese Vorlage, wenn die Vorlage geschützte Dateien nicht geöffnet werden soll. Sie können ein Datum oder eine Anzahl von Tagen ab dem Zeitpunkt, die der Schutz der Datei angewendet wird.<br /><br />Wenn Sie ein Datum angeben, ist es effektiver Mitternacht in der aktuellen Zeitzone.|
    |**Offline-Zugriff**|Verwenden Sie diese Einstellung, um sicherheitsanforderungen zu, dass Sie für die Anforderung, die Benutzern geöffnet werden müssen, Dateien geschützte, wenn sie nicht über einen Internetanschluss verfügen.<br /><br />Wenn Sie angeben, dass Inhalt ohne Internetzugang verfügbar ist, dass der Inhalt ist nur verfügbar für eine angegebene Anzahl von Tagen, wenn dieser Schwellenwert erreicht ist, können Benutzer müssen erneut authentifiziert und Zugriffe werden protokolliert. In diesem Fall ist ihre Anmeldeinformationen nicht zwischengespeichert sind, werden Benutzer aufgefordert, sich anzumelden, bevor die Datei geöffnet werden kann.<br /><br />Zusätzlich zur erneuten Authentifizierung wird der Richtlinie und die Gruppenmitgliedschaft des Benutzers erneut ausgewertet. Dies bedeutet, dass Benutzer Zugriff auf unterschiedliche Ergebnisse für dieselbe Datei entstünde, wenn Änderungen in die Mitgliedschaft in Gruppen oder Richtlinien aus, wann sie zuletzt auf die Datei zugegriffen.|

10. Wenn Sie sicher sind, dass die Vorlage für Ihre Benutzer ordnungsgemäß konfiguriert ist, klicken Sie auf **Veröffentlichen** die Vorlage für Benutzer sichtbar machen, und klicken Sie auf **Speichern**.

11. Klicken Sie auf die Schaltfläche "zurück" im Verwaltungsportal wieder den **Vorlagen** Seite, in dem Ihre Vorlage nun aktualisierten Status hat **veröffentlicht**.

Ändern Sie die Vorlage, wählen Sie diese und verwenden Sie die schnellstartschritte erneut. Oder wählen Sie eine der folgenden Optionen:

-   Mehrere Benutzer und Gruppen hinzufügen und die Berechtigungen für diese Benutzer und Gruppen definieren: Klicken Sie auf **Rechte**, klicken Sie dann auf **Hinzufügen**.

-   So entfernen Sie Benutzer oder Gruppen, die Sie zuvor ausgewählt haben: Klicken Sie auf **Rechte**, wählen Sie aus der Liste der Benutzer oder die Gruppe, und klicken Sie dann auf **Löschen**.

-   So ändern Sie die Benutzer sehen können, die Vorlagen für diese Anwendung auswählen: Klicken Sie auf **Bereich**, klicken Sie dann auf **Hinzufügen** oder **Löschen**, oder **APPLICATION COMPATIBILITY**.

-   Um die Vorlage für alle Benutzer nicht mehr sichtbar zu machen: Klicken Sie auf **konfigurieren**, klicken Sie auf **Archiv**, und klicken Sie dann auf **Speichern**.

-   Andere Konfiguration ändern: Klicken Sie auf **konfigurieren**, nehmen die Änderungen vor, und klicken Sie dann auf **Speichern**.

> [!WARNING]
> Wenn Sie eine Vorlage, die zuvor gespeichert wurde ändern, werden Clients erst sichtbar, diese Änderungen an der Vorlage Vorlagen auf deren Computern aktualisiert werden. Weitere Informationen finden Sie im Abschnitt [Refreshing templates for users](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_RefreshingTemplates) dieses Themas.

## <a name="BKMK_HowToCopyTemplates"></a>Gewusst wie: Kopieren einer Vorlage
Wenn Sie eine neue Vorlage erstellen, die sehr ähnliche Einstellungen für eine vorhandene Vorlage hat möchten, wählen Sie die ursprüngliche Vorlage auf die **Vorlagen** auf **Kopie**, geben Sie einen eindeutigen Namen und nehmen Sie die Änderungen, die Sie benötigen.

> [!IMPORTANT]
> Wenn Sie eine Vorlage kopieren der **veröffentlicht** oder **archiviert** Status wird ebenfalls kopiert. Also, wenn Sie eine veröffentlichte Vorlage kopieren, dessen Status sofortige veröffentlicht, wenn Sie ihn nicht ändern.

Sie können benutzerdefinierte Vorlagen und die Standardvorlagen kopieren. Es wird empfohlen kopieren Sie die Standardvorlagen, anstatt eine neue benutzerdefinierte Vorlage erstellen, wenn Sie die Vorlage für alle Benutzer in Ihrer Organisation zuweisen möchten. Diese Methode bedeutet, dass Sie nicht erstellen oder mehrere Gruppen an alle Benutzer auswählen. In diesem Szenario jedoch müssen Sie einen neuen Namen und eine Beschreibung für die kopierte Vorlage für weitere Sprachen angeben.

## <a name="BKMK_HowToArchiveTemplates"></a>Vorgehensweise beim Entfernen von Vorlagen (Archiv)
Die Standardvorlagen können nicht gelöscht werden, aber sie archiviert werden, sodass Benutzer nicht angezeigt werden.

Auf ähnliche Weise Wenn Sie eine benutzerdefinierte Vorlage veröffentlicht haben und nicht mehr Benutzer in der Lage zu sein, Sie können die Vorlage bearbeiten, und wählen Sie **Archiv** und **Speichern** aus der **konfigurieren** Seite. Oder wählen Sie ihn aus der **Vorlagen** Seite, und wählen Sie **Archiv**.

Da Sie die Standardvorlagen zum Archivieren dieser Vorlagen bearbeiten können müssen, verwenden die **Archiv** option die **Vorlagen** Seite. Outlook kann nicht archiviert werden **nicht weiterleiten** Option.

#### So entfernen Sie eine Standardvorlage

-   Aus der **Vorlagen** Seite, wählen Sie die Standardvorlage, und klicken Sie auf **Archiv**.

Der Status wechselt von **veröffentlicht** auf **archiviert**. Wenn Sie Ihre Meinung ändern, wählen Sie die Vorlage, und klicken Sie auf **Veröffentlichen**.

## <a name="BKMK_RefreshingTemplates"></a>Aktualisieren von Vorlagen für Benutzer
Wenn Sie Azure RMS verwenden, werden Vorlagen automatisch auf Clientcomputer heruntergeladen, damit Benutzer sie ihre Anwendung auswählen können. Sie müssen jedoch möglicherweise zusätzliche Schritte durchführen, wenn Sie die Vorlagen ändern:

|Anwendung oder Dienst|Wie Vorlagen nach der Änderung aktualisiert werden.|
|-------------------------|-------------------------------------------------------|
|Exchange Online|Manuelle Konfiguration erforderlich, um Vorlagen zu aktualisieren.<br /><br />Erweitern Sie die Konfigurationsschritte im folgenden Abschnitt [Exchange Online only: How to configure Exchange to download changed custom templates](../../ems/AADRightsMgmt/Configuring-Custom-Templates-for-Azure-Rights-Management.md#BKMK_ExchangeOnlineTemplatesUpdate).|
|Office 365|Automatische Aktualisierung, es sind keine weiteren Schritte erforderlich.|
|Office 2016 und Office 2013<br /><br />RMS-freigabeanwendung für Windows|Automatische Aktualisierung nach einem Zeitplan:<br /><br />-   Für diese neueren Versionen von Office: Das Standardaktualisierungsintervall ist 7 Tage.<br />-   Für die RMS-freigabeanwendung für Windows: ab Version 1.0.1784.0 ist das Standardaktualisierungsintervall jeden Tag. Frühere Versionen haben eine standardmäßige Aktualisierungsintervall von 7 Tagen.<br /><br />Dieser Zeitplan schneller, eine Aktualisierung zu erzwingen, erweitern den folgenden Abschnitt, [Office 2016,  Office 2013, and RMS sharing application for Windows: How to force a refresh for a changed custom template](#BKMK_Office2013ForceUpdate).|
|Office 2010|Aktualisiert, wenn sich Benutzer anmelden.<br /><br />Um eine Aktualisierung zu erzwingen, bitten, oder erzwingen, dass Benutzer ab- und wieder anmelden. Oder finden Sie im folgenden Abschnitt [Office 2010 only: How to force a refresh for a changed custom template](#BKMK_Office2010ForceUpdate).|
Für mobile Geräte, mit denen die RMS-Freigabe Vorlagen automatisch heruntergeladen (und erforderlichenfalls) ohne zusätzliche Konfiguration erforderlich.

### <a name="BKMK_ExchangeOnlineTemplatesUpdate"></a>Exchange Online nur: Konfigurieren von Exchange für das Herunterladen geänderter, benutzerdefinierter Vorlagen
Wenn Sie Information Rights Management (IRM) für Exchange Online bereits konfiguriert haben, werden benutzerdefinierte Vorlagen für Benutzer, bis Sie die folgenden Änderungen vornehmen, mit Windows PowerShell in Exchange Online nicht heruntergeladen.

> [!NOTE]
> Weitere Informationen zur Verwendung von Windows PowerShell in Exchange Online finden Sie unter [mithilfe von PowerShell mit Exchange Online](https://technet.microsoft.com/library/jj200677%28v=exchg.160%29.aspx).

Sie müssen dieses Verfahren jedes Mal ausführen, wenn Sie eine Vorlage ändern.

##### Aktualisieren von Vorlagen für Exchange Online

1.  Verbinden Sie mithilfe von Windows PowerShell in Exchange Online mit dem Dienst:

    1.  Geben Sie Ihre Office 365-Benutzername und Kennwort:

        ```
        $Cred = Get-Credential
        ```

    2.  Herstellen einer Verbindung mit Exchange Online-Dienst, indem Sie die folgenden beiden Befehle ausführen:

        ```
        $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
        ```

        ```
        Import-PSSession $Session
        ```

2.  Verwenden der [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200724%28v=exchg.160%29.aspx) Cmdlet, um Ihre vertrauenswürdige Veröffentlichungsdomäne (TPD) von Azure RMS erneut zu importieren:

    ```
    Import-RMSTrustedPublishingDomain -Name "<TPD name>" -RefreshTemplates -RMSOnline
    ```
    Wenn der Name Ihrer TPD beispielsweise **RMS Online - 1** (ein typsicher Name für zahlreiche Organisationen) eingeben: **Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates -RMSOnline**

    > [!NOTE]
    > Um den Namen Ihres TPD zu überprüfen, können Sie die [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200707%28v=exchg.160%29.aspx) Cmdlet.

3.  Um zu bestätigen, dass die Vorlagen erfolgreich importiert haben, warten Sie einige Minuten, und führen Sie dann die [Get-RMSTemplate](http://technet.microsoft.com/library/dd297960%28v=exchg.160%29.aspx) Cmdlet und den Typ für alle. Beispiel:

    ```
    Get-RMSTemplate -TrustedPublishingDomain "RMS Online - 1" -Type All
    ```
    > [!TIP]
    > Es empfiehlt sich, eine Kopie der Ausgabe speichern, sodass Sie problemlos die Vorlage oder -GUIDs kopieren können, wenn Sie später eine Vorlage archivieren.

4.  Für jede importierte Vorlage, die in Outlook Web App verfügbar sein soll, verwenden Sie die [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) Cmdlet und legen Sie den Typ auf verteilt:

    ```
    Set-RMSTemplate -Identity "<name  or GUID of the template>" -Type Distributed
    ```
    Da Outlook Web Access die Benutzeroberfläche für 24 Stunden zwischenspeichert, können die neue Vorlage für bis zu einem Tag von Benutzern nicht angezeigt.

Darüber hinaus, wenn Sie eine Vorlage archivieren (benutzerdefinierte oder Standard) und Exchange Online mit Office 365, Benutzer weiterhin die archivierten Vorlagen finden bei Verwendung der Outlook Web App oder mobile Geräte, die Exchange ActiveSync-Protokoll verwenden.

Verbinden mit dem Dienst mithilfe von Windows PowerShell in Exchange Online, damit Benutzer nicht mehr für diese Vorlagen angezeigt, und verwenden Sie dann die [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) Cmdlet durch den folgenden Befehl ausführen:

```
Set-RMSTemplate -Identity "<name or GUID of the template>" -Type Archived
```

### <a name="BKMK_Office2013ForceUpdate"></a>2016 Office, Office 2013 und RMS-freigabeanwendung für Windows: Erzwingen der Aktualisierung einer geänderten benutzerdefinierten Vorlage
Durch Bearbeiten der Registrierungs auf den Computern 2016 Office, Office 2013 oder die Freigabe-Anwendung für Windows Rights Management (RMS), können Sie den automatischen Zeitplan ändern, sodass geänderte Vorlagen auf Computern häufiger als ihren Standardwert aktualisiert werden. Sie können auch eine sofortige Aktualisierung erzwingen, indem die vorhandenen Daten in einem Registrierungswert löschen.

> [!WARNING]
> Durch eine unsachgemäße Verwendung des Registrierungs-Editors können schwerwiegende Fehler auftreten, die möglicherweise eine Neuinstallation des Betriebssystems erforderlich machen. Microsoft kann nicht garantieren, dass Probleme, die aufgrund einer unsachgemäßen Verwendung des Registrierungs-Editors entstehen, behoben werden können. Die Verwendung des Registrierungs-Editors erfolgt auf eigene Gefahr.

##### So ändern Sie den automatischen Zeitplan

1.  Erstellen Sie mithilfe eines Registrierungs-Editors und legen Sie die folgenden Registrierungswerte:

    -   Ein Aktualisierungsintervall in Tagen (mindestens 1 Tag) festgelegt: Erstellen Sie einen neuen Registrierungswert namens **TemplateUpdateFrequency** und definieren Sie einen ganzzahligen Wert für Daten, die die Häufigkeit in Tagen zum Herunterladen von Änderungen an einer heruntergeladenen Vorlage angibt. Verwenden Sie in der folgende Tabelle finden Sie den Registrierungspfad, um diese neuen Registrierungswert erstellen.

        |Registrierungspfad|Typ|Wert|
        |----------------------|-------|--------|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD-WERT|TemplateUpdateFrequency|

    -   Ein Aktualisierungsintervall in Sekunden (mindestens 1 Sekunde) festgelegt: Erstellen Sie einen neuen Registrierungswert namens **TemplateUpdateFrequencyInSeconds** und definieren Sie einen ganzzahligen Wert für Daten, die die Häufigkeit in Sekunden zum Herunterladen von Änderungen an einer heruntergeladenen Vorlage angibt. Verwenden Sie in der folgende Tabelle finden Sie den Registrierungspfad, um diese neuen Registrierungswert erstellen.

        |Registrierungspfad|Typ|Wert|
        |----------------------|-------|--------|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD-WERT|TemplateUpdateFrequencyInSeconds|

    Stellen Sie sicher, dass Sie erstellen, und legen Sie die Registrierungswerte, nicht beides. Wenn beide vorhanden sind, **TemplateUpdateFrequency** wird ignoriert.

2.  Wenn Sie eine sofortige Aktualisierung der Vorlagen erzwingen möchten, fahren Sie mit der nächsten Prozedur. Andernfalls jetzt neu starten der Office-Anwendung und die Instanzen von Datei-Explorer.

##### Um eine sofortige Aktualisierung erzwingen

1.  Mit einem Registrierungs-Editor, löschen Sie die Daten für die **LastUpdatedTime** Wert. Die Daten möglicherweise angezeigt, z. B. **2015-04-20T15:52**; 2015 löschen-04-20T15:52, damit keine Daten angezeigt werden. Verwenden Sie in der folgende Tabelle finden Sie den Registrierungspfad zum Löschen dieser Daten des Registrierungswerts.

    |Registrierungspfad|Typ|Wert|
    |----------------------|-------|--------|
    |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\ &lt; MicrosoftRMS_FQDN &gt; \Template|REG_SZ|LastUpdatedTime|
    > [!TIP]
    > In den Registrierungspfad *&lt; MicrosoftRMS_FQDN &gt;* bezieht sich auf Ihre Microsoft RMS-Dienst-FQDN. Wenn Sie diesen Wert überprüfen möchten:
    > 
    > 1.  Führen Sie die [Get-AadrmConfiguration](https://msdn.microsoft.com/library/windowsazure/dn629410.aspx) Cmdlet für Azure RMS. Wenn Sie Windows PowerShell-Modul für Azure RMS bereits installiert haben, finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).
    > 2.  Identifizieren Sie anhand der Ausgabe der **LicensingIntranetDistributionPointUrl** Wert.
    > 
    >     Beispiel: **LicensingIntranetDistributionPointUrl: https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing**
    > 3.  Entfernen Sie den Wert **https://** und **/_wmcs/licensing** aus der Zeichenfolge. Der verbleibende Wert ist Ihre Microsoft RMS-Dienst-FQDN. In unserem Beispiel wäre der Microsoft RMS-Dienst-FQDN den folgenden Wert:
    > 
    >     **5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com**

2.  Löschen Sie den folgenden Ordner und alle darin enthaltenen Dateien: **%localappdata%\Microsoft\MSIPC\Templates**

3.  Starten Sie die Office-Anwendung und die Instanzen von Datei-Explorer.

### <a name="BKMK_Office2010ForceUpdate"></a>Nur Office 2010: Erzwingen der Aktualisierung einer geänderten benutzerdefinierten Vorlage
Durch Bearbeiten der Registrierung auf den Computern mit Office 2010 können Sie einen Wert festlegen, sodass geänderte Vorlagen auf Computern ohne warten auf Benutzer abmelden und wieder aktualisiert werden. Sie können auch eine sofortige Aktualisierung erzwingen, indem die vorhandenen Daten in einem Registrierungswert löschen.

> [!WARNING]
> Durch eine unsachgemäße Verwendung des Registrierungs-Editors können schwerwiegende Fehler auftreten, die möglicherweise eine Neuinstallation des Betriebssystems erforderlich machen. Microsoft kann nicht garantieren, dass Probleme, die aufgrund einer unsachgemäßen Verwendung des Registrierungs-Editors entstehen, behoben werden können. Die Verwendung des Registrierungs-Editors erfolgt auf eigene Gefahr.

##### So ändern Sie das Aktualisierungsintervall

1.  Mit einem Registrierungs-Editor, erstellen Sie einen neuen Registrierungswert namens **UpdateFrequency** und definieren Sie einen ganzzahligen Wert für Daten, die die Häufigkeit in Tagen zum Herunterladen von Änderungen an einer heruntergeladenen Vorlage angibt. Verwenden Sie in der folgende Tabelle finden Sie den Registrierungspfad, um diese neuen Registrierungswert erstellen.

    |Registrierungspfad|Typ|Wert|
    |----------------------|-------|--------|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_DWORD-WERT|UpdateFrequency|

2.  Wenn Sie eine sofortige Aktualisierung der Vorlagen erzwingen möchten, fahren Sie mit der nächsten Prozedur. Andernfalls jetzt neu starten einer Office-Anwendung.

##### Um eine sofortige Aktualisierung erzwingen

1.  Mit einem Registrierungs-Editor, löschen Sie die Daten für die **LastUpdatedTime** Wert. Die Daten möglicherweise angezeigt, z. B. **2015-04-20T15:52**; 2015 löschen-04-20T15:52, damit keine Daten angezeigt werden. Verwenden Sie in der folgende Tabelle finden Sie den Registrierungspfad zum Löschen dieser Daten des Registrierungswerts.

    |Registrierungspfad|Typ|Wert|
    |----------------------|-------|--------|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_SZ|lastUpdatedTime|

2.  Löschen Sie den folgenden Ordner und alle darin enthaltenen Dateien: **%localappdata%\Microsoft\MSIPC\Templates**

3.  Starten einer Office-Anwendung neu.

## <a name="BKMK_PowerShellTemplates"></a>Windows PowerShell-Referenz
Alle Elemente, die Sie in der Azure-Verwaltungsportal zu Vorlagen erstellen und verwalten Sie dazu über die Befehlszeile mithilfe von Windows PowerShell. Darüber hinaus können Sie exportieren und Importieren von Vorlagen, damit Sie Vorlagen zwischen Mandanten kopieren oder massenbearbeitungen komplexer Eigenschaften in Vorlagen, z. B. von mehrsprachigen Namen und Beschreibungen ausführen können.

> [!IMPORTANT]
> Um Windows PowerShell zum Erstellen und Verwalten von Vorlagen für Benutzerrechterichtlinien Azure RMS verwenden, benötigen Sie mindestens Version 2.0.0.0 der [Windows PowerShell-Modul für Azure RMS](http://go.microsoft.com/fwlink/?LinkId=257721).
> 
> Wenn Sie dieses Windows PowerShell-Modul bereits installiert haben, führen Sie den folgenden Befehl in einem PowerShell-Fenster die Versionsnummer zu überprüfen: `(Get-Module aadrm -ListAvailable).Version`

Installationshinweise finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md).

Die Cmdlets, die Unterstützung von Vorlagen erstellen und verwalten:

-   [Hinzufügen AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)

-   [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx)

-   [Get-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727079.aspx)

-   [Get-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727081.aspx)

-   [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx)

-   [Neue AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx)

-   [Remove-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727082.aspx)

-   [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)

## Nächste Schritte
Nachdem Sie benutzerdefinierte Vorlagen für Azure Rights Management konfiguriert haben, verwenden Sie die [Roadmap für die Bereitstellung von Azure Rights Management](../../ems/AADRightsMgmt/Azure-Rights-Management-Deployment-Roadmap.md) überprüfen, ob weitere Konfigurationsschritte ausführen, die Sie möchten möglicherweise vor dem Rollout [!INCLUDE[aad_rightsmanagement_1](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_1_md.md)] für Benutzer und Administratoren. Es sind keine Konfigurationsschritte ausgeführt werden, die angezeigt wird müssen, [Mithilfe von Azure Rights Management](../../ems/AADRightsMgmt/Using-Azure-Rights-Management.md) für Betriebsanleitung, um eine erfolgreiche Bereitstellung für Ihre Organisation zu unterstützen.

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

