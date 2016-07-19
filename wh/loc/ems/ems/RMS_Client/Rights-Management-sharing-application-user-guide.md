---
title: Rights Management freigabeanwendung – Benutzerhandbuch
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eaf6d02c-aa36-4915-856e-49bb71ab1484
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - tr-tr
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
# Rights Management freigabeanwendung – Benutzerhandbuch
Die Microsoft Rights Management-Freigabeanwendung (RMS) für Windows hilft Ihnen, wichtige Dokumente und Bilder vor Personen zu schützen, die diese Dateien nicht sehen dürfen, sogar, wenn Sie die Dateien per E-Mail senden oder auf einem anderen Gerät speichern. Sie können mit dieser Anwendung auch Dateien öffnen und verwenden, die von anderen Personen mit derselben Rights Management-Technologie geschützt wurden.

Alles, was Sie hierfür benötigen, ist ein Computer, auf dem mindestens Windows 7 mit Service Pack 1 ausgeführt wird, sowie ein lokales Administratorkonto zum Installieren der RMS-Freigabeanwendung. Anschließend können diese kostenlose Anwendung von Microsoft [herunterladen und installieren](http://go.microsoft.com/fwlink/?LinkId=303970).

Wenn Sie Fragen haben, die in diesem Handbuch nicht beantwortet werden, lesen Sie [Häufig gestellte Fragen zur Microsoft Rights Management-Freigabeanwendung für Windows](http://go.microsoft.com/fwlink/?LinkId=303971).

## <a name="BKMK_SharingExamples"></a>Beispiele für die Nutzung der RMS-Freigabeanwendung
Hier einige Beispiele für die mögliche Nutzung der RMS-Freigabeanwendung zum Schutz Ihrer Dateien.

|Ziel ...|Vorgehensweise|
|------------|------------------|
|**… Ich möchte Finanzinformationen auf sichere Weise für Personen meines Vertrauens freigeben, die in einer anderen Organisation arbeiten**<br /><br />Sie arbeiten mit einem Partnerunternehmen zusammen und möchten eine Excel-Tabelle per E-Mail senden, die geplante Vertriebszahlen enthält. Sie möchten, dass die Empfänger die Zahlen anzeigen, jedoch nicht ändern können.|Klicken Sie auf die Schaltfläche **Geschützt freigeben** im Excel-Menüband, geben Sie die E-Mail-Adressen der beiden Personen im Partnerunternehmen ein, mit denen Sie zusammenarbeiten, wählen Sie **Anzeigender Benutzer – Nur anzeigen** aus, und klicken Sie auf **Senden**.<br /><br />Wenn die E-Mail im Partnerunternehmen ankommt, können nur die Empfänger der E-Mail die Tabelle anzeigen, können diese jedoch nicht speichern, bearbeiten, drucken oder weiterleiten.<br /><br />Schrittweise Anleitung: [Schützen Sie eine Datei, die Sie mithilfe von Rights Management-freigabeanwendung per e-Mail freigeben](../../ems/RMS_Client/Protect-a-file-that-you-share-by-email-by-using-the-Rights-Management-sharing-application.md).|
|**… Ich möchte auf sichere Weise ein Dokument an eine Person senden, die ein iOS-Gerät verwendet**<br /><br />Sie können ein streng vertrauliches Word-Dokument an einen Kollegen senden, von dem Sie wissen, dass er regelmäßig seine E-Mails auf seinem iOS-Gerät abruft.|Sie verwenden den Datei-Explorer, klicken mit der rechten Maustaste auf die Datei und wählen dann **Geschützt freigeben** aus, um die Datei als Anlage an Ihren Kollegen zu senden.<br /><br />Der Empfänger erhält die E-Mail auf seinem iOS-Gerät, klickt auf den Link in der E-Mail, wird informiert, wie er die Freigabeanwendung herunterladen kann, installiert die Version für iOS-Geräte und zeigt das Dokument an¹.<br /><br />Schrittweise Anleitung: [Schützen Sie eine Datei, die Sie mithilfe von Rights Management-freigabeanwendung per e-Mail freigeben](../../ems/RMS_Client/Protect-a-file-that-you-share-by-email-by-using-the-Rights-Management-sharing-application.md).|
|**… Ich möchte überprüfen, wer wann meine geschützten Dokumente geöffnet hat und den Zugriff bei Bedarf widerrufen**<br /><br />Sie haben ein vertrauliches Entwurfsdokument auf sichere Weise für potenzielle Anbieter freigegeben und möchten nun wissen, wer wann und von wo auf das Dokument zugegriffen hat. Nachdem Sie dann einem der Anbieter den Zuschlag für das Projekt erteilt haben, möchten Sie den Zugriff auf das ursprüngliche Dokument widerrufen, sodass es von den Personen, für die Sie das Dokument freigegeben haben, nicht mehr gelesen werden kann.|Nachdem Sie ein Dokument per E-Mail freigegeben haben, wechseln Sie zur [Website zum Nachverfolgen von Dokumenten](http://go.microsoft.com/fwlink/?LinkId=529562), um zu sehen, wer wann auf das Dokument zugegriffen hat. Wenn Sie die Freigabe beenden möchten, wählen Sie die Option zum Widerrufen des Zugriffs aus.<br /><br />Schrittweise Anleitung: [Verfolgen Sie und aufzuheben Sie Ihre Dokumente, wenn Sie die RMS-Freigabe verwenden](../../ems/RMS_Client/Track-and-revoke-your-documents-when-you-use-the-RMS-sharing-application.md).|
|**… Sie möchten ein Dokument lesen, das Sie als eine auf sichere Weise freigegebene E-Mail-Anlage erhalten haben, können es jedoch nicht lesen, da Ihr Unternehmen nicht mit Rights Management arbeitet.**<br /><br />Der Absender der E-Mail ist eine Person Ihres Vertrauens, da Sie schon früher geschäftliche Kontakte zu der Person gepflegt haben, und Sie nehmen an, dass die Person Ihnen Informationen zu einer neuen potenziellen Geschäftschance senden möchte.|Sie folgen den Anleitungen in der E-Mail und klicken auf den Link, um sich für Microsoft Rights Management anzumelden. Microsoft bestätigt, dass Ihre Organisation nicht über ein Abonnement verfügt, das Azure Rights Management umfasst, sendet Ihnen eine E-Mail, mit der Sie das kostenlose Anmeldeverfahren abschließen können, und Sie melden sich mit Ihrem neuen Konto an. Sie klicken auf den zweiten Link in der E-Mail, um die Rights Management-Freigabeanwendung zu installieren, und können anschließend die E-Mail-Anlage lesen und sich zu der neuen Geschäftschance informieren.<br /><br />Schrittweise Anleitung: [Anzeigen und Verwenden von Dateien, die durch Rights Management geschützt sind](../../ems/RMS_Client/View-and-use-files-that-have-been-protected-by-Rights-Management.md).|
|**… Ich möchte die vertraulichen Unternehmensdateien auf meinem Laptop schützen, damit keine Personen von außerhalb des Unternehmens darauf zugreifen können**<br /><br />Sie sind häufig auf Reisen und verwenden Ihren Laptop, um auf Dateien in einem Ordner zuzugreifen und diese zu aktualisieren, der vor unbefugtem Zugriff geschützt werden muss.|Auf Ihrem Laptop ist die RMS-Freigabeanwendung installiert. Sie verwenden den Datei-Explorer, um die Dateien mithilfe einer Vorlage zu schützen, mit der alle Dateien im Handumdrehen geschützt werden können. Auch wenn Ihr Laptop gestohlen wird, müssen Sie sich nun keine Sorgen darüber machen, dass Personen von außerhalb des Unternehmens auf diese Dokumente zugreifen könnten.<br /><br />Schrittweise Anleitung: [Schützen eine Datei auf einem Gerät &#40;direkt schützen&#41; mithilfe von Rights Management-freigabeanwendung](../../ems/RMS_Client/Protect-a-file-on-a-device--protect-in-place--by-using-the-Rights-Management-sharing-application.md).|
¹ PDF-Rendering unterstützt von Foxit. Copyright © 2003–2014, Foxit Corporation.

## <a name="BKMK_SharingInstructions"></a>Was möchten Sie tun?
> [!NOTE]
> Weitere technische Informationen wie die unterstützten Dateitypen sowie Informationen zum Installieren der Anwendung in einem Firmennetzwerk finden Sie im [Rights Management freigabeanwendung – Administratorhandbuch](../../ems/RMS_Client/Rights-Management-sharing-application-administrator-guide.md).

-   [Herunterladen und Installieren der Freigabeanwendung](https://technet.microsoft.com/library/dn574734.aspx)

-   [Schützen einer Datei auf einem Gerät (direkt schützen)](https://technet.microsoft.com/library/dn574733.aspx)

-   [Schützen einer Datei, die Sie per E-Mail freigeben](https://technet.microsoft.com/library/dn574735.aspx)

-   [Nachverfolgen und Widerrufen Ihrer Dokumente](https://technet.microsoft.com/library/dn986611.aspx)

-   [Anzeigen und Verwenden von Dateien, die geschützt wurden](https://technet.microsoft.com/library/dn574741.aspx)

-   [Entfernen des Schutzes von einer Datei](https://technet.microsoft.com/library/dn574739.aspx)

-   [Verwenden von Tastenkombinationen](https://technet.microsoft.com/library/dn574737.aspx)

-   [Festlegen von Einstellungen im Dialogfeld](https://technet.microsoft.com/library/dn574738.aspx)

## Siehe auch
[Schützen Sie Ihre Dokumente!](http://curah.microsoft.com/60308/protect-your-docs)

