---
title: Optionen des Dialogfelds f&#252;r die Rights Management-freigabeanwendung
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7b91ab30-6363-4929-bcbd-4dfbd05f644a
translation.priority.ht: 
  - es-es
  - fr-fr
  - it-it
  - ko-kr
  - pt-br
  - ru-ru
  - tr-tr
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
# Optionen des Dialogfelds f&#252;r die Rights Management-freigabeanwendung
Anhand dieser Informationen können Sie die Optionen in der RMS-Freigabe angeben **Schutz hinzufügen** das Dialogfeld oder die **geschütztes freigeben** (Dialogfeld). Dieses Dialogfeld wird angezeigt Feld, wenn Sie [schützen eine freigegebene Datei](http://technet.microsoft.com/library/dn574735.aspx) oder [schützen eine Datei](http://technet.microsoft.com/library/dn574733.aspx) und wählen Sie benutzerdefinierte Berechtigungen.

> [!IMPORTANT]
> Wenn die angezeigten Optionen abweichen hier dokumentiert sind, haben nicht Sie wahrscheinlich die neueste Version der freigegebenen Anwendung installiert. Sie können die neueste Version Herunterladen der [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) Seite.
> 
> Woher wissen Sie, wenn Sie die neueste Version haben? Suchen Sie nach **Microsoft Rights Management-freigabeanwendung** in Programme und Funktionen aufgeführt, und überprüfen Sie die entsprechende Versionsnummer. Um anzuzeigen, und verwenden Sie die Optionen in der Tabelle, die Version sollte mindestens **1.0.1770.0**. Sie können die letzte Versionsnummer von der Downloadseite überprüfen.

Zusätzlich zu den Optionen, die Sie auswählen können, können Sie auch Fragen:

-   [What’s the .ppdf file that’s automatically created?](../../ems/RMS_Client/Dialog-box-options-for-the-Rights-Management-sharing-application.md#BKMK_PPDF)

-   [What’s the difference between generic protection and built-in (native) protection?](../../ems/RMS_Client/Dialog-box-options-for-the-Rights-Management-sharing-application.md#BKMK_GenericNative)

|Option|Beschreibung|
|----------|----------------|
|**BENUTZER**|Wenn Sie bereits eine e-Mail-Adresse aus Outlook angegeben haben, geben Sie die e-Mail-Adressen der Personen, die die Datei geöffnet werden soll.<br /><br />Wenn die lokale Version der Verwaltung von Informationsrechten (AD RMS) in Ihrer Organisation verwendet wird, sind die e-Mail-Adressen, die Sie angeben können, auf Personen innerhalb Ihrer Organisation beschränkt. Wenn dies zutrifft und Sie versuchen, externe e-Mail-Adressen angeben, sehen Sie eine Meldung, die besagt, dass die Unternehmenskonfiguration ermöglicht die gleichzeitige Verwendung von geschütztem Inhalt nur innerhalb des Unternehmens. Wenn Ihre Organisation Azure RMS verwendet, kann diese e-Mail-Adressen für Personen innerhalb Ihrer Organisation oder für Personen in einer anderen Organisation jedoch.<br /><br />Beispiel: Janetm@contoso.com; p.dover@Fabrikam.com|
|**Allgemeiner Schutz**|Wenn diese Option ausgewählt ist, bedeutet dies, dass die ausgewählte Datei nicht systemintern geschützt werden kann. Weitere Informationen finden Sie unter. [What’s the difference between generic protection and built-in (native) protection?](../../ems/RMS_Client/Dialog-box-options-for-the-Rights-Management-sharing-application.md#BKMK_GenericNative) in diesem Thema.|
|**Ereignisanzeige – nur Ansicht**<br /><br />**Prüfer – anzeigen und bearbeiten**<br /><br />**Co-Autor – anzeigen, bearbeiten, kopieren und Drucken**<br /><br />**Co-Besitzer – alle Berechtigungen** **Note:** Alle diese Optionen haben ein rundes Symbol vor dem Namen, die einen Weltglobus darzustellen. Dieses Symbol wird verwendet, da in der Regel Sie eine der folgenden Optionen wählen, wenn Sie die Anlage an jemanden in einer anderen Organisation senden.|Wählen Sie eine der folgenden Optionen, wenn Sie die Berechtigungen für das geschützte Dokument definieren möchten. Klicken Sie auf jede Option aus, um eine Beschreibung anzuzeigen.<br /><br />Wenn Sie eine dieser Optionen auswählen, nur die Personen Angabe **Benutzer** berechtigt Sie angeben, um das Dokument zu öffnen. Wenn sie einem anderen Benutzer weiterleiten, würde z. B. das Dokument nicht geöffnet.|
|Vorlagen, die von Ihrem Administrator konfiguriert.<br /><br />Namen Ihres Unternehmens beispielsweise Contoso, Ltd: **Contoso, Ltd – nur vertrauliche Ansicht** **Note:** Alle diese Optionen haben ein quadratisches Symbol vor dem Namen ein Bürogebäude darstellen. Dieses Symbol wird verwendet, da in der Regel Sie eine der folgenden Optionen wählen, wenn Sie die Anlage an jemanden in Ihrer Organisation senden.|Bei der Freigabe eines Dokuments mit Personen, die Arbeiten für Ihre Organisation sehen Sie die verfügbaren Vorlagen, die von Ihrem Administrator konfiguriert. Wählen Sie einen der folgenden, wenn das Dokument nicht außerhalb Ihrer Organisation freigegeben werden sollen.<br /><br />Wenn Sie eine dieser Optionen auswählen, definiert der Administrator die Rechte für das Dokument und die, die sie öffnen können.|
|**Diese Dokumente gültig bis**|Wählen Sie diese Option nur für zeitempfindliche-Dateien, die die Benutzer die von Ihnen ausgewählten nicht nach einem Datum zu öffnen, die Sie angeben. Sie werden weiterhin die ursprüngliche Datei öffnen, aber nach Mitternacht (die aktuelle Zeitzone), an dem Tag, den Sie angeben, anderen Benutzern nicht möglich, die Datei zu öffnen.<br /><br />Diese Option ist nicht verfügbar, wenn Sie eine Vorlage auswählen, die der Administrator konfiguriert.|
|**E-Mail-Benachrichtigung senden, wenn jemand versucht, diese Dokumente zu öffnen.**|**Note:** Diese Option ist derzeit in der Vorschau.<br />Wählen Sie diese Option, wenn Sie e-Mail-Benachrichtigungen erhalten, wenn jemand versucht, das Dokument zu öffnen, das Sie schützen möchten. Die e-Mail-Nachricht sagen, wer versucht hat, um sie zu öffnen, ob und wann erfolgreich waren.<br /><br />Diese Option ist nur verfügbar, wenn Ihre Organisation Azure RMS verwendet. Wenn die lokale Version der Verwaltung von Informationsrechten (AD RMS) in Ihrer Organisation verwendet wird, wird diese Option nicht angezeigt werden.|
|**Lassen Sie mich sofort den Zugriff auf diese Dokumente widerrufen**|Wählen Sie diese Option, wenn Sie möglicherweise den Zugriff auf die Dokumente später zu widerrufen, indem Sie das Dokument Website nachverfolgen müssen und Sperrung sofort wirksam muss. Benutzer benötigen jedoch Festlegen dieser Option bedeutet, während das Dokument nicht gesperrt ist, immer eine Verbindung zu das Dokument bei jedem Lesen sie darauf zugreifen. Möglicherweise gibt es einige Szenarien, in denen Benutzer können nicht ihr Gerät mit dem Internet verbinden, und Benutzer das Dokument wie beabsichtigt, können nicht gelesen werden.<br /><br />Wenn Sie diese Option nicht auswählen, können Sie weiterhin die Dokumente später widerrufen mithilfe der Nachverfolgungswebsite. Allerdings, da Benutzer nicht immer eine Internet-Verbindung zum Lesen des Dokuments benötigen, wird nicht sofort wissen, dass das Dokument gesperrt wird und weiterhin kann zu lesen, bis sie als Nächstes mit Azure RMS zu authentifizieren. Standardmäßig die maximale Anzahl von Tagen, an denen jemand könnte ein geschütztes Dokument lesen, das Sie aufgehoben haben weiterhin ist 30 Tage, aber der Administrator kann dieser Wert weniger oder mehr als 30 Tage ändern.<br /><br />Diese Option ist nur verfügbar, wenn Ihre Organisation Azure RMS verwendet. Wenn die lokale Version der Verwaltung von Informationsrechten (AD RMS) in Ihrer Organisation verwendet wird, wird diese Option nicht angezeigt werden.|

## <a name="BKMK_GenericNative"></a>Was ist der Unterschied zwischen generischen Schutz und integrierte (systemeigenen)?

-   Wenn Sie **schützen i. d. r. eine Datei**, nicht autorisierte Personen die Datei können nicht geöffnet werden. Aber nach dem autorisierte Benutzer die Datei öffnen, könnte dann ungeschützt an andere Personen weiterleiten oder speichern Sie sie an einem Ort, den andere Benutzer zugreifen können. Sie tun, jedoch eine Meldung, die sie mitteilt, welche Berechtigungen für die Datei sehen und werden sie aufgefordert, diese bleiben, aber dieser Schutz nicht erzwungen werden. Wenn Sie i. d. r. eine Datei schützen, können Sie darüber hinaus nicht die Berechtigungen weiter als Autorisierung einschränken. Beispielsweise können nicht den Inhalt auf schreibgeschützt einschränken, oder nicht gedruckt.:

    > [!NOTE]
    > Eine allgemein geschützte Datei verfügt immer über eine Erweiterung des Dateinamens **"pFile"**.

-   Im Gegensatz dazu bei Verwendung der **integrierten (systemeigenen) Schutz** Rights Management für Programme, die das (z. B. Office-Dateien) unterstützen, gilt der Schutz für die Datei selbst, wenn die Datei gesendet wird an jemand anderen oder an einem anderen Speicherort gespeichert. Wenn Sie diese Dateien schützen, können Sie eingeschränkte Berechtigungen wie verwenden schreibgeschützt, oder die Berechtigung zum Bearbeiten, aber nicht drucken oder kopieren. Sie könnten z. B. auswählen **Viewer – nur Ansicht**, sodass der Inhalt bearbeitet werden kann, gedruckt oder kopiert.

Zusätzliche technische Informationen finden Sie in der [Levels of protection – native and generic](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md#BKMK_LevelsofProtection) im Abschnitt der [Rights Management freigabeanwendung – Administratorhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md).

## <a name="BKMK_PPDF"></a>Was ist die .ppdf-Datei, die automatisch erstellt wird?

-   Wenn Sie eine geschützte Datei per e-Mail (geschütztes freigeben) freigeben, die RMS-Freigabe automatisch erstellt eine **.ppdf** Version der Datei für Word, Excel, PowerPoint und PDF. Dies ist eine schreibgeschützte geschützte Version der Datei, die nur autorisierte Personen öffnen können, und es wird sichergestellt, dass der Empfänger die Anlage immer lesen können, selbst wenn sie ein mobiles Gerät verwenden, der eine Anwendung nicht, die systemeigene Unterstützung für die Verwaltung von Informationsrechten. Bereitstellen der Personen, die RMS-Freigabe-app installiert haben, werden sie die Anlage lesen können.

    In diesem Szenario wird im Gegensatz zu einer allgemein geschützte Datei wird die Einschränkung der Verwendung erzwungen. Der Empfänger nicht möglich sein, diese Version der Datei zu speichern, und wenn sie die Anlage eines anderen Benutzers weitergeleitet werden, bleiben die ursprünglichen Einschränkungen mit dem Dokument. Nur Personen, die für die geschützten Dokuments autorisiert wurden werden mehr geöffnet.

    > [!NOTE]
    > Eine .ppdf-Datei wird automatisch erstellt, wenn Sie geschützte (Freigabe per e-Mail) freigeben, aber nicht erstellt werden, wenn Sie direkte schützen.

## Beispiele und andere Informationen
Beispiele für die Verwendung der Verwaltung von Informationsrechten Freigeben von Anwendung und schrittweise Anleitung finden Sie in den folgenden Abschnitten aus der Rights Management-freigabeanwendung – Benutzerhandbuch:

-   [Examples for using the RMS sharing application](../../ems/RMS_Client/Rights-Management-sharing-application-user-guide.md#BKMK_SharingExamples)

-   [What do you want to do?](../../ems/RMS_Client/Rights-Management-sharing-application-user-guide.md#BKMK_SharingInstructions)

## Siehe auch
[Rights Management freigabeanwendung – Benutzerhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-user-guide.md)

