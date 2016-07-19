---
title: Konfigurieren von Nutzungsrechte f&#252;r Azure Rights Management
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 97ddde38-b91b-42a5-8eb4-3ce6ce15393d
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
# Konfigurieren von Nutzungsrechte f&#252;r Azure Rights Management
Wenn Sie Schutz für Dateien oder E-Mails mithilfe von Azure Rights Management (Azure RMS) festlegen und keine Vorlage verwenden, müssen Sie die Nutzungsrechte selbst konfigurieren. Wenn Sie benutzerdefinierte Vorlagen für Azure RMS konfigurieren, wählen Sie außerdem die Nutzungsrechte, die dann automatisch angewendet werden, wenn die Vorlage von Benutzern, Administratoren oder konfigurierten Diensten ausgewählt wird. Im Azure-Portal können Sie beispielsweise Rollen auswählen, die eine logische Gruppierung von Nutzungsrechte konfigurieren, oder Sie können die einzelnen Berechtigungen konfigurieren:

Verwenden Sie dieses Thema, um die gewünschten Nutzungsrechte für die verwendete Anwendung zu konfigurieren und um zu verstehen, wie diese Rechte von den Anwendungen interpretiert werden.

## Nutzungsrechte und Beschreibungen
In der folgende Tabelle werden die von Rights Management unterstützten Benutzerrechte aufgezählt und beschrieben und wird beschrieben, wie sie genutzt und interpretiert werden. In dieser Tabelle ist **Allgemeiner Name** in der Regel das, was Sie als das Nutzungsrecht sehen, das als die benutzerfreundlichere Version des Einzelwortwerts angezeigt oder referenziert wird, der im Code verwendet wird (der **Richtliniencodierung**-Wert). Die **API-Konstante oder der API-Wert** ist der SDK-Name für einen MSIPC API-Aufruf, der verwendet wird, wenn Sie eine RMS-fähige Anwendung schreiben, die auf ein Nutzungsrecht überprüft oder einer Richtlinie ein Nutzungsrecht hinzufügt.

|Allgemeiner Name|Richtliniencodierung|Beschreibung|Implementierung in benutzerdefinierten Office-Rechten|Name des Azure-Portals|Name in den AD RMS-Vorlagen|API-Konstante oder API-Wert|Zusätzliche Informationen|
|--------------------|------------------------|----------------|---------------------------------------------------------|--------------------------|-------------------------------|-------------------------------|-----------------------------|
|Inhalt bearbeiten, Bearbeiten|DOCEDIT|Ermöglicht es dem Benutzer, den Inhalt in der Anwendung zu ändern, neu anzuordnen, zu formatieren oder zu filtern. Gewährt nicht das Recht, die bearbeitete Kopie speichern zu können.|Als Teil der Optionen **Ändern** und **Vollzugriff**.|**Inhalt bearbeiten**|**Bearbeiten**|Nicht verfügbar|In Office-Anwendungen ermöglicht dieses Recht es den Benutzern auch, das Dokument zu speichern.|
|Speichern|BEARBEITEN|Ermöglicht es dem Benutzer, das Dokument am aktuellen Speicherort zu speichern.|Als Teil der Optionen **Ändern** und **Vollzugriff**.|**Datei speichern**|**Speichern**|IPC_GENERIC_WRITEL"EDIT"|In Office-Anwendungen ermöglicht dieses Recht es den Benutzern auch, das Dokument zu ändern.|
|Kommentar|COMMENT|Aktiviert die Option, dem Inhalt Anmerkungen oder Kommentare hinzufügen zu können.|Nicht implementiert.|Nicht implementiert.|Nicht implementiert.|IPC_GENERIC_COMMENTL"COMMENT"|Dieses Recht ist im SDK verfügbar, ist als eine Ad-hoc-Richtlinie im RMS-Schutz-Modul (RMSProtection) für Windows PowerShell verfügbar und wurde in einigen Anwendungen von Softwarelieferanten implementiert. Es wird allerdings nicht häufig verwendet und wird derzeit nicht vom Office-Anwendungen unterstützt.|
|Speichern unter, Exportieren|EXPORTIEREN|Aktiviert die Option zum Speichern des Inhalts unter einem anderen Dateinamen (Speichern unter). Je nach Anwendung kann die Datei ohne Schutz gespeichert werden.|Als Teil der Optionen **Ändern** und **Vollzugriff**.|**Inhalt exportieren (Speichern unter)**|**Exportieren (Speichern unter)**|IPC_GENERIC_EXPORTL"EXPORT"|Durch dieses Recht hat der Benutzer auch die Möglichkeit, andere Exportoptionen in Anwendungen auszuführen, beispielsweise **An OneNote senden**.|
|Weiterleiten|WEITERLEITEN|Aktiviert die Option zum Weiterleiten einer E-Mail-Nachricht und zum Hinzufügen von Empfängern in den Zeilen **An** und **Cc**.|Verweigert, wenn die Standardrichtlinie **Nicht weiterleiten** verwendet wird.|**Weiterleiten**|**Weiterleiten**|IPC_EMAIL_FORWARDL"FORWARD"|Gestattet es dem Weiterleiter nicht, anderen Benutzern Berechtigungen als Teil des Weiterleitungsvorgangs zu gewähren.|
|Vollständige Kontrolle|OWNER|Gewährt alle Berechtigungen für das Dokument, und alle verfügbaren Aktionen können ausgeführt werden.|Als benutzerdefinierte **Vollzugriff**-Option.|**Vollständige Kontrolle**|**Vollständige Kontrolle**|IPC_GENERIC_ALLL"OWNER"|Umfasst die Möglichkeit, den Schutz zu entfernen.|
|Drucken|PRINT|Aktiviert die Optionen zum Drucken des Inhalts.|Als Option **Inhalt drucken** in benutzerdefinierten Berechtigungen. Keine Pro-Empfänger-Einstellung.|**Drucken**|**Drucken**|IPC_GENERIC_PRINTL"PRINT|Keine weiteren Informationen|
|Antwort|ANTWORTEN|Aktiviert die Option „Antwort“ in einem E-Mail-Client, ohne Änderungen in der Zeile **An** oder **Cc** zuzulassen.|Nicht verfügbar|**Antwort**|**Antwort**|IPC_EMAIL_REPLY|Keine weiteren Informationen|
|Allen antworten|REPLYALL|Aktiviert die Option **Allen antworten** in einem E-Mail-Client, ermöglicht es dem Benutzer jedoch nicht, der Zeile **An** oder **Cc** Empfänger hinzuzufügen.|Nicht verfügbar|**Allen antworten**|**Allen antworten**|IPC_EMAIL_REPLYALLL"REPLYALL"|Keine weiteren Informationen|
|Anzeigen, Öffnen, Lesen|ANZEIGEN|Ermöglicht es dem Benutzer, das Dokument zu öffnen und den Inhalt zu sehen.|Als benutzerdefinierte Richtlinie **Lesen**, Option **Anzeigen**.|**Inhalt anzeigen**|**Anzeigen**|IPC_GENERIC_READL"VIEW"|Keine weiteren Informationen|
|Kopieren|EXTRACT|Aktiviert Optionen zum Kopieren von Daten aus dem Dokument in dasselbe oder ein anderes Dokument.|Als benutzerdefinierte Richtlinienoption **Benutzern mit Lesezugriff das Kopieren des Inhalts erlauben**.|**Inhalt kopieren und extrahieren**|**Extract**|IPC_GENERIC_EXTRACTL"EXTRACT"|In einigen Anwendungen ermöglicht es auch, dass das gesamte Dokument ungeschützt gespeichert werden kann.|
|Rechte anzeigen|VIEWRIGHTSDATA|Ermöglicht es dem Benutzer, die auf das Dokument angewendete Richtlinie anzuzeigen.|Nicht implementiert.|**Zugewiesene Rechte anzeigen**|**Rechte anzeigen**|IPC_READ_RIGHTSL"VIEWRIGHTSDATA"|Von einigen Anwendungen ignoriert.|
|Rechte ändern|EDITRIGHTSDATA|Ermöglicht es dem Benutzer, die auf das Dokument angewendete Richtlinie zu ändern. Beinhaltet das Entfernen des Schutzes.|Nicht implementiert.|**Rechte ändern**|**Rechte bearbeiten**|IPC_WRITE_RIGHTSL"EDITRIGHTSDATA"|Keine weiteren Informationen|
|Makros zulassen|OBJMODEL|Aktiviert die Option, Makros oder anderen programmgesteuerten oder remoten Zugriff auf den Inhalt eines Dokuments ausführen zu können.|Als benutzerdefinierte Richtlinienoption zum **Zulassen von programmgesteuertem Zugriff**. Keine Pro-Empfänger-Einstellung.|**Makros zulassen**|**Makros zulassen**|Nicht verfügbar|Keine weiteren Informationen|

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

