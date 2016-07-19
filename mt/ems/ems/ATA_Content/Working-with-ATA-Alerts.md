---
title: Arbeiten mit Warnungen ATA
ms.custom: 
  - ATA
ms.date: 12/22/2015
ms.prod: identity-ata
ms.reviewer: na
ms.suite: na
ms.technology: 
  - security
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 14cb7513-5dc8-49cb-b3e0-94f469c443dd
translation.priority.mt: 
  - de-de
  - ja-jp
---
# Arbeiten mit Warnungen ATA
ATA kann Sie warnen, wenn eine verdächtige Aktivitäten, per e-Mail oder durch Senden der Warnung an Syslog-Server erkannt wird. Wenn Sie eine oder beide dieser Arten von Warnungen aktivieren, können Sie die folgenden dafür festlegen.

> [!NOTE]
> -   Die Benachrichtigungen enthalten einen Link, mit denen den Benutzer direkt auf verdächtige Aktivitäten, die erkannt wurde. Die Einstellung der URL ATA-Konsole auf der Seite ATA-Center wird der Hostteil der Name des Links entnommen. Standardmäßig ist die ATA-Webkonsolen-URL die IP-Adresse, die während der Installation des Mittelpunkts ATA ausgewählt.  Wenn Sie beabsichtigen, konfigurieren Sie die e-Mail-Adresse oder Syslog gewarnt, sobald wird empfohlen, einen FQDN als ATA-Webkonsolen-URL verwenden.
> -   System Health Alert Warnungen werden nur per e-Mail gesendet.

## Einstellung Sprache und Ausführlichkeit
Die **Language** und **Ausführlichkeit** Einstellungen gelten für Benachrichtigungen per e-Mail gesendet und Benachrichtigung an das Syslog-Server gesendet.

1.  Öffnen Sie die ATA-Konsole.

2.  Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

3.  Wählen Sie **Warnungen**.

4.  Klicken Sie unter **Language**, wählen Sie die Sprache Ihrer Wahl.

5.  Unter **Ausführlichkeit**, auf **Niedrig** Sie ggf. eine kurze Benachrichtigung nur, wenn Sie eine neue Warnung generiert wird. Wählen Sie **hohe** eine detaillierte Benachrichtigung erhalten, wenn eine neue Warnung generiert wird, sowie die Änderung von vorhandener Warnungen werden sollen.

    ![](../Image/ATA%20alerts%20verbosity%20language.JPG)

6.  Klicken Sie auf **Speichern**.

## Einrichten von e-Mail-Benachrichtigungen
ATA kann Sie warnen, wenn eine verdächtige Aktivitäten erkannt wird. Wenn Sie e-Mail-Benachrichtigungen aktivieren, können Sie die folgenden dafür festlegen.

1.  Klicken Sie auf dem Server ATA-Center auf der **Microsoft Advanced Bedrohung Analytics Management** Symbol auf dem Desktop.

2.  Geben Sie Ihren Benutzernamen und Ihr Kennwort ein, und klicken Sie auf **Anmelden**.

3.  Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

4.  Wählen Sie **Warnungen**.

5.  Schalten Sie **Mail** e-Mail-Benachrichtigungen zu aktivieren, und geben die folgende Informationen:

    |Feld|Beschreibung|Wert|
    |--------|----------------|--------|
    |Endpunkt des SMTP-Servers (erforderlich)|Geben Sie den vollqualifizierten Domänennamen des SMTP-Servers.|Beispiel: smtp.contoso.com|
    |SSL|SSL zu wechseln, wenn der SMTP-Server SSL erforderlich. **Note:** Wenn Sie SSL aktivieren müssen Sie auch die Portnummer ändern.|Es ist standardmäßig deaktiviert.|
    |Authentifizierung|Aktivieren Sie, wenn Ihr SMTP-Server Authentifizierung erfordert. **Note:** Wenn Sie Authentifizierung aktivieren, müssen Sie angeben, einen Benutzernamen und das Kennwort eines Kontos mit der Berechtigung für die Verbindung zum SMTP-Server-e-Mail.|Es ist standardmäßig deaktiviert.|
    |Senden von (erforderlich)|Geben Sie eine e-Mail-Adresse aus, an den die e-Mail von gesendet werden soll.|Beispiel: ATA@contoso.com|
    |Senden Sie an (erforderlich)|Geben Sie die e-Mail-Adressen der Benutzer oder e-Mail-Gruppen, die e-Mail-Nachrichten abrufen soll, wenn ATA eine verdächtige Aktivität entdeckt. **Note:** Geben Sie eine e-Mail-Adresse zu einem Zeitpunkt, und klicken Sie auf das Pluszeichen, um ihn hinzuzufügen.|Beispiel: securityteam@contoso.com|

## Syslog-Warnungen einrichten
ATA kann Sie warnen, wenn eine verdächtige Aktivität durch Senden der Warnung an Syslog-Server erkannt. Wenn Sie Syslog-Warnungen aktivieren, können Sie Folgendes für sie festlegen.

1.  Vor dem Konfigurieren der Syslog-Warnungen, arbeiten Sie mit Ihren SIEM-Administrator, um herauszufinden, die folgenden Informationen:

    -   FQDN- oder IP-Adresse des Servers SIEM

    -   Port auf dem Server SIEM wartet

    -   Transporttyp UDP- oder TCP- oder TCP gesichert

    -   Formatieren Sie, in dem die Daten RFC 3164 oder 5424 senden

2.  Klicken Sie auf dem Server ATA-Center auf der **Microsoft Advanced Bedrohung Analytics Management** Symbol auf dem Desktop.

3.  Geben Sie Ihren Benutzernamen und Ihr Kennwort ein, und klicken Sie auf **Anmelden**.

4.  Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](../Image/ATA%20config%20icon.JPG)

5.  Wählen Sie **Warnungen**.

6.  Schalten Sie **Syslog** zum Aktivieren von Warnungen über verdächtige Aktivitäten auf Ihren Syslog-Server gesendet werden, und geben die folgende Informationen:

    |Feld|Beschreibung|
    |--------|----------------|
    |Syslog-Endpunkt|FQDN des Syslog-server|
    |Transport|UDC, TCP oder Secure TCP möglich|
    |Format|Dies ist das Format, das ATA verwendet, um Ereignisse an den Server SIEM - RFC 5424 oder RFC 3164 senden.|

## Siehe auch
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)

