---
title: Protokollieren und Analysieren von Azure Rights Management-Nutzung
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e
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
# Protokollieren und Analysieren von Azure Rights Management-Nutzung
Die Informationen in diesem Thema sollen Ihnen bei einem besseren Verständnis helfen, wie Sie die Protokollierung mit Azure Rights Management (RMS) verwenden können. RMS kann jede Anforderung protokollieren, die für Ihre Organisation durchgeführt wird. Hierzu gehören Anforderungen von Benutzern, von RMS-Administratoren in Ihrer Organisation ausgeführte Aktionen und von Microsoft-Mitarbeitern ausgeführte Aktionen, um Ihre RMS-Bereitstellung zu unterstützen.

Sie können dann mithilfe der RMS-Protokolle die folgenden Geschäftsszenarios unterstützen:

- Analyse hinsichtlich geschäftlicher Erkenntnisse

   RMS schreibt Protokolle im erweiterten W3C-Protokollformat in ein Azure-Speicherkonto, das von Ihnen bereitgestellt wird. Sie können diese Protokolle dann in ein Repository Ihrer Wahl leiten (z. B. eine Datenbank, ein OLAP-System (Online Analytical Processing) oder ein MapReduce-System), um die Informationen zu analysieren und Berichte zu erstellen. Beispielsweise könnten Sie identifizieren, wer auf Ihre RMS-geschützten Daten zugreift. Sie können bestimmen, auf welche RMS-geschützten Daten Benutzer zugreifen, von welchen Geräten aus und von wo. Sie können herausfinden, ob Benutzer geschützte Inhalte erfolgreich lesen können. Sie können ferner identifizieren, welche Personen ein wichtiges Dokument gelesen haben, das geschützt it.

- Überwachung auf Missbrauch

   RMS-Protokollierungsinformationen stehen Ihnen praktisch in Echtzeit zur Verfügung, sodass Sie die Verwendung von RMS in Ihrem Unternehmens kontinuierlich überwachen können. 99,9 % der Protokolle sind innerhalb von 15 Minuten nach einer RMS-ausgelösten Aktion verfügbar.

   Beispielsweise können Sie sich benachrichtigen lassen, wenn ein plötzlicher Anstieg der Personen zu verzeichnen ist, die RMS-geschützte Daten außerhalb der Standardarbeitszeiten lesen, was darauf hindeuten kann, dass ein bösartiger Benutzer Informationen sammelt, um sie an die Konkurrenz zu verkaufen. Oder wenn derselbe Benutzer innerhalb eines kurzen Zeitraums offensichtlich von zwei verschiedenen IP-Adressen aus auf Daten zugreift, was darauf hindeuten kann, dass ein Benutzerkonto kompromittiert wurde.

- Ausführen forensischer Analysen

   Wenn Sie ein Informationsleck haben, werden Sie wahrscheinlich gefragt, wer in der jüngsten Zeit auf bestimmte Dokumente zugegriffen hat, und auf welche Informationen eine verdächtigte Person zuletzt zugegriffen hat. Sie können diese Arten von Fragen beantworten, wenn Sie RMS und Protokollierung verwenden, weil Personen, die geschützte Inhalte verwenden, immer eine RMS-Lizenz abrufen müssen, um Dokumente und Bilder zu öffnen, die mit RMS geschützt sind, auch wenn diese Dateien per E-Mail verschoben oder auf USB-Laufwerke oder andere Speichergeräte kopiert werden. Dies bedeutet, dass Sie RMS-Protokolle als definitive Quelle für Informationen zur forensischen Analyse verwenden können, wenn Sie Ihre Daten mithilfe von RMS schützen.

> [!NOTE]
> Wenn Sie daran interessiert sind, administrative Aufgaben für RMS zu protokollieren, aber nicht verfolgen möchten, wie Benutzer RMS verwenden, können Sie das RMS-Cmdlet [Get-AadrmAdminLog](http://msdn.microsoft.com/library/windowsazure/dn629430.aspx) der Windows PowerShell verwenden.
> 
> Sie können im Azure-Portal auch allgemeine Verwendungsberichte zur **RMS-Nutzung**, zu den **aktivsten RMS-Benutzern**, zur **RMS-Geräteverwendung** und **RMS-fähigen Anwendungsnutzung** erstellen. Klicken Sie für den Zugriff auf diese Berichte im Azure-Portal auf **Active Directory**, wählen und öffnen Sie ein Verzeichnis, und klicken Sie dann auf **BERICHTE**.

Weitere Informationen zur RMS-Protokollierung finden Sie in den folgenden Abschnitten.

- [How to enable RMS logging](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_EnableRMSLogging)

- [How to access and use your RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_AccesAndUseLogs)

- [How to manage your RMS log storage](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_ManageStorage)

- [How to delegate access to your RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_Delegate)

- [How to interpret your RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_Interpret)

- [Windows PowerShell reference](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_PowerShell)

## <a name="BKMK_EnableRMSLogging"></a>Aktivieren der RMS-Protokollierung
Die RMS-Protokollierung ist optional, sodass Sie, wenn Sie sie verwenden möchten, bestimmte Schritte unternehmen müssen. Wenn Sie RMS-Protokollierung verwenden, erfolgt keine Änderung in der Art, wie RMS funktioniert, und der Protokollierungsprozess selbst ist kostenfrei. Sie müssen aber ein Azure-Speicherkonto für die Protokolle angeben, und für diesen Speicher fallen Kosten an.

Stellen Sie vor Beginn sicher, dass Sie folgende Voraussetzungen für die Verwendung der RMS-Protokollierung erfüllen:

|Anforderung <br /> <br />|Weitere Informationen <br /> <br />|
|---------------|-------------------------|
|Ein von der IT verwaltetes Abonnement einschließlich Azure Rights Management <br /> <br />|Sie müssen ein Microsoft RMS-Abonnement besitzen, das von Ihrem Unternehmen verwaltet wird. Organisationen, die RMS for Individuals verwenden, können keine RMS-Protokollierung verwenden. <br /> <br />Wenn es in Ihrer Organisation Benutzer gibt, die RMS for Individuals verwenden, bietet die RMS-Protokollierung einen sehr bestechenden geschäftlichen Grund für die Umwandlung von RMS for Individuals in ein Microsoft RMS-Abonnement. <br /> <br />Weitere Informationen zu den Abonnements mit enthaltenem Azure RMS finden Sie im Thema [Anforderungen für Azure Rights Management](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md) in Abschnitt [Cloud subscriptions that support Azure RMS](../../ems/AADRightsMgmt/Requirements-for-Azure-Rights-Management.md#BKMK_SupportedSubscriptions). <br /> <br />Weitere Informationen zu RMS for Individuals finden Sie unter [RMS für Einzelpersonen und Azure Rights Management](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md). <br /> <br />|
|Azure-Abonnement <br /> <br />|Sie müssen ein Abonnement von Azure sowie ausreichenden Speicherplatz auf Azure besitzen, um Ihre RMS-Protokolle zu speichern. <br /> <br />|
|Windows PowerShell für Azure Rights Management <br /> <br />|Falls noch nicht geschehen, müssen Sie Windows PowerShell für Rights Management herunterladen und installieren. Sie verwenden Windows PowerShell-Cmdlets zum Konfigurieren und Verwalten Ihrer RMS-Protokolle. <br /> <br />Weitere Informationen finden Sie unter [Installieren WindowsPowerShell für Azure Rights Management](../../ems/AADRightsMgmt/Installing-Windows-PowerShell-for-Azure-Rights-Management.md). <br /> <br />|
Verwenden Sie das folgende Verfahren, um die RMS-Protokollierung zu aktivieren Es enthält auch Schritte, um ein Azure-Speicherkonto zu erstellen und dann Azure für die Verwendung dieses Speicherkontos für Ihre RMS-Protokolle zu konfigurieren.

> [!NOTE]
> Dieses Verfahren setzt voraus, dass Sie ein Azure-Konto besitzen. Die RMS-Protokollierung unterstützt Einzelkonten, aber als bewährte Methode sollten Arbeits- oder Schulkonten verwendet werden. Zusätzlich wird empfohlen, ein dediziertes Speicherkonto für Ihre RMS-Protokolle zu erstellen. Sie müssen die Speicherzugriffsschlüssel für RMS und potenziell für andere Personen freigeben, wenn diese ebenfalls die Protokolldateien verwenden können sollen.
> 
> Weitere Informationen zum Azure-Speicher finden Sie in der [Azure-Dokumentation zu Speicher](http://azure.microsoft.com/documentation/services/storage/).

1. Melden Sie sich beim [Azure-Portal](https://manage.windowsazure.com/) an.

2. Wählen Sie **Speicher** aus.

   > [!TIP]
   >    Wenn Sie diese Option nicht sehen, prüfen Sie, ob Sie zusätzlich zu Ihrem Rights Management-Abonnement über ein Azure-Abonnement verfügen.

3. Klicken Sie auf **SPEICHERKONTO ERSTELLEN**, und geben Sie als **URL** einen eindeutigen Namen für das Speicherkonto ein, und, falls notwendig, ändern Sie die Option **STANDORT/AFFINITÄTSGRUPPE** so, dass sie Ihrer Region entspricht.

4. Klicken Sie auf **OK**, und warten Sie, bis für Ihren Speichernamen der Status **Online** angezeigt wird.

5. Klicken Sie auf **Zugriffsschlüssel verwalten**.

6. Kopieren Sie aus dem Dialogfeld **Zugriffsschlüssel verwalten**, in dem Ihr primärer und sekundärer Zugriffsschlüssel angezeigt werden, den primären Zugriffsschlüssel in die Zwischenablage, und schließen Sie das Dialogfeld.

7. Starten Sie die Windows PowerShell mit der Option **Als Administrator ausführen**. Führen Sie den Befehl [Connect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629415.aspx) aus, um eine Verbindung mit dem RMS-Dienst herzustellen:

   ```
   Connect-AadrmService
   ```

8. Verwenden Sie den Befehl [Set-AadrmUsageLogStorageAccount](http://msdn.microsoft.com/library/windowsazure/dn629426.aspx), um anzugeben, wo Ihre RMS-Protokolle aufbewahrt werden sollen, indem Sie *&lt;Access_Key&gt;* durch den primären Zugriffsschlüssel ersetzen, den Sie in Schritt 6 kopiert haben, und *&lt;StorageAccount&gt;* durch den Namen des Speicherkontos, das Sie in Schritt 3 erstellt haben:

   ```
   $accesskey = convertto-securestring -asplaintext -force –string <Access_Key>
   Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <StorageAccount>
   ```

9. Verwenden Sie den Befehl [Enable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629421.aspx), um die RMS-Protokollierung zu aktivieren:

   ```
   Enable-AadrmUsageLogFeature
   ```
   Folgende Meldung sollte angezeigt werden: **Das Verwendungsprotokollfeature ist für den Rights Management-Dienst aktiviert.**

Nachdem jetzt die RMS-Protokollierung aktiviert ist, beginnt RMS, alle Aktionen für Ihre Organisation zu protokollieren, und speichert diese Informationen in Ihrem Speicherkonto. Vor diesem Zeitpunkt sind keine Protokollierungsinformationen verfügbar.

## <a name="BKMK_AccesAndUseLogs"></a>Zugreifen auf und Verwenden von RMS-Protokollen
RMS schreibt Protokolle als eine Serie von BLOBs in Ihr Azure-Speicherkonto. Jedes BLOB enthält mindestens einen Protokolldatensatz im erweiterten W3C-Protokollformat. Die BLOB-Namen sind Zahlen in der Reihenfolge ihrer Erstellung. Im Abschnitt [How to interpret the RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_Interpret) weiter unten in diesem Dokument erhalten Sie weitere Informationen zu den Protokollinhalten und deren Erstellung.

Es kann einen Moment dauern, bis nach einer RMS-Aktion Protokolle in Ihrem Speicherkonto angezeigt werden. Die meisten Protokolle werden innerhalb von 15 Minuten angezeigt.

Das Speicherkonto, das Sie für Ihre RMS-Protokolle erstellt haben, ist wie ein Postfach, und es unterstützt das direkte Lesen aus dem Speicherkonto, ist aber nicht für eine solche Verwendung optimiert. Stattdessen empfehlen wir für beste Leistung und zur Verringerung der Kosten, dass Sie die Protokolle in den lokalen Speicher herunterladen, z. B. einen lokalen Ordner, eine Datenbank oder ein MapReduce-Repository.

Es gibt zwei Möglichkeiten, um Ihre Protokolle herunterzuladen:

- Verwenden Sie das Windows PowerShell-Cmdlet [Get-AadrmUsageLog](http://msdn.microsoft.com/library/windowsazure/dn629401.aspx).

   Dies ist die einfachste Methode, um auf Ihre Protokolle zuzugreifen. Dieses Cmdlet lädt Protokolle auf Ihren Computer herunter, wobei jedes BLOB als Datei an einen von Ihnen angegebenen Speicherort heruntergeladen wird.

- Verwenden Sie das [Azure Storage SDK](http://www.windowsazure.com/en-us/develop/net/), um Ihre eigene benutzerdefinierte Anwendung zum Herunterladen der Protokolle zu schreiben.

   Eine benutzerdefinierte Anwendung kann höhere Flexibilität als das Cmdlet „Get-AadrmUsageLogs“ bieten. Vielleicht möchten Sie beispielsweise das Herunterladen von Protokollen an jemanden oder einen Prozess delegieren, der Ihre administrativen RMS-Anmeldeinformationen nicht verwenden darf. Oder Sie möchten die Protokolle in Echtzeit abrufen, weil Sie auf Missbrauch überwachen möchten.

- Starten Sie Windows PowerShell mit der Option **Als Administrator ausführen**, und führen Sie **Get-AadrmUsageLog –Path &lt;Speicherort&gt;** aus. Beispielsweise nach dem Erstellen eines Ordners mit dem Namen **logs** auf Laufwerk E:

   - So laden Sie alle verfügbaren Protokolle in Ihren Ordner "E:\logs" herunter: **Get-AadrmUsageLog -Path "e:\logs"**

   - So laden Sie einen bestimmten Bereich von Blobs herunter: **Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047**

Wenn Sie diese Cmdlets ausführen, zeigt die Windows PowerShell den Namen des letzten BLOBs an, der heruntergeladen wurde. Sie können diesen Namen einer Variablen zuweisen, mit der Sie „Get-AadrmUsageLog“ in einer Schleife oder einem geplanten Auftrag ausführen können, wobei jedes Mal nur die inkrementellen Protokolle heruntergeladen werden.

Beispiel:

**PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"**

**1527**

**PS C:\&gt; $LastBlobName**

**1527**

> [!TIP]
> Sie können alle Ihre heruntergeladenen Protokolldateien in einem CSV-Format aggregieren, indem Sie [Microsofts Protokollparser](http://www.microsoft.com/download/details.aspx?id=24659) verwenden, bei dem es sich um ein Tool zum Konvertieren zwischen bekannten Protokollformaten handelt. Sie können mit diesem Tool auch Daten in das SYSLOG-Format konvertieren oder in eine Datenbank importieren. Nachdem Sie das Tool installiert haben, führen Sie **LogParser.exe /?** aus, um Hilfe- und Syntaxinformationen zu diesem Tool anzuzeigen. Beispielsweise können Sie folgenden Befehl ausführen, um alle Informationen in eine Datei im LOG-Format zu importieren: **logparser –i:w3c –o:csv “SELECT &#42; INTO AllLogs.csv FROM &#42;.log”**.

Sie können die Protokollierung anhalten und fortsetzen. Wenn Sie die Protokollierung anhalten, behält RMS Ihre Speicherkontoinformationen, sodass Sie die Protokollierung ganz einfach wieder fortsetzen können.

- Verwenden Sie zum Anhalten der Protokollierung folgendes Cmdlet: [Disable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629404.aspx)

- Verwenden Sie zum Fortsetzen der Protokollierung folgendes Cmdlet: [Enable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629421.aspx)

- Verwenden Sie zum Überprüfen, ob die Protokollierung aktiviert oder deaktiviert ist, folgendes Cmdlet: [Get-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629425.aspx)

   Der Wert **True** bedeutet, dass die Protokollierung aktiviert ist, während der Wert „False“ anzeigt, dass die Protokollierung deaktiviert ist.

## <a name="BKMK_ManageStorage"></a>Verwalten Ihres RMS-Protokollspeichers
Für den Speicherplatz, den Sie zum Aufbewahren Ihrer RMS-Protokolle verwenden, werden Ihnen Kosten berechnet.

RMS übernimmt nicht automatisch die Verwaltung Ihrer RMS-Protokolldateien. Wenn Sie keine Maßnahmen ergreifen, bleiben sie in Ihrem Speicherkonto. Um aber Speicherplatz zu erhalten und die Speicherkosten zu reduzieren, könnten Sie sie nach dem Herunterladen löschen. Oder Sie können auswählen, welche Dateien gelöscht werden sollen. Mit einer Ausnahme verwendet RMS diese Protokolldateien nicht, weshalb es keine Einschränkungen dafür gibt, wann Sie sie löschen können.

Die Datei, die Sie nicht löschen (oder ändern) dürfen heißt **metadata** und befindet sich im Container **rms-metadata**. RMS verwendet dieses BLOB, um die letzte verwendete BLOB-Nummer zu erfassen. Wenn diese Datei gelöscht wird, beginnt RMS einen neuen Container für Protokolle mit einer BLOB-Nummer, die wieder bei 1 beginnt, und alle zukünftigen Downloads, das Cmdlet „Get-AadrmUsageLog“ verwenden, verwenden diesen Container zum Herunterladen von Protokolldateien. Hieraus folgt, dass zwar alle Protokolle im Originalcontainer erhalten bleiben, aber verwaist sind. Die einzige Möglichkeit zum Herunterladen dieser verwaisten Protokolle besteht darin, das Azure Storage SDK zu verwenden.

> [!TIP]
> Statt Ihren RMS-Protokollspeicher selbst zu verwalten, können Sie diese Verwaltungsfunktion an ein anderes Unternehmen delegieren, indem Sie Ihren Speicherkontonamen und den Zugriffsschlüssel freigeben. Weitere Informationen finden Sie im Abschnitt [How to delegate access to your RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_Delegate) weiter unten in diesem Thema.

Unter bestimmten Umständen möchten Sie eventuell Ihre Speicherkontoschlüssel neu generieren. Beispiel:

- Sie wechseln das Unternehmen, das Ihre RMS-Protokolle verwaltet.

- Sie haben den Verdacht, dass Ihr Speicherzugriffsschlüssel kompromittiert wurde.

Wenn dies eintritt, verwenden Sie den sekundären Zugriffsschlüssel (unter der Voraussetzung, dass Sie zuvor den primären Zugriffsschlüssel verwendet haben), um die Dienstkontinuität zu gewährleisten. Wenn Sie den Zugriffsschlüssel neu generieren, den Sie zuvor nicht verwendet haben, konfigurieren Sie dann RMS für die Verwendung des neuen Schlüssels. Verwenden Sie das folgende Verfahren, um den sekundären Zugriffsschlüssel neu zu generieren und RMS für dessen Verwendung zu konfigurieren:

1. Melden Sie sich bei Ihrem [Azure-Verwaltungsportal](https://manage.windowsazure.com/) an.

2. Wählen Sie **Speicher** aus.

3. Klicken Sie auf **Zugriffsschlüssel verwalten**.

4. Klicken Sie im Dialogfeld **Zugriffsschlüssel verwalten** neben dem sekundären Zugriffsschlüssel auf **Neu generieren**, und kopieren Sie den neuen sekundären Zugriffsschlüssel in die Zwischenablage.

5. Starten Sie die Windows PowerShell mit der Option **Als Administrator ausführen**, und verwenden Sie das Cmdlet [Set-AadrmUsageLogConfig](http://msdn.microsoft.com/library/windowsazure/dn629426.aspx), um RMS für die Verwendung dieses neuen Zugriffsschlüssels zu konfigurieren, indem Sie *&lt;StorageAccount&gt;* durch den Namen Ihres Speicherkontos ersetzen und *&lt;Access_Key&gt;* durch den neu generierten sekundären Zugriffsschlüssel, den Sie gerade kopiert haben:

   ```
   Set-AadrmUsageLogConfig -StorageAccount <StorageAccount>-AccessKey <Access_Key>
   ```
   > [!WARNING]
   >    Obwohl Sie zu einem anderen Speicherkonto wechseln können, wenn Sie diesen Befehl ausführen, werden durch diese Aktion Ihre vorherigen Protokolle verwaist, und es kann nicht mehr mit dem Cmdlet „Get-AadrmUsageLogConfig“ oder ähnlichen Verwaltungsbefehlen und -funktionen darauf zugegriffen werden.

6. Zurück im Dialogfeld **Zugriffsschlüssel verwalten** generieren Sie Ihren primären Zugriffsschlüssel neu.

## <a name="BKMK_Delegate"></a>Delegieren des Zugriffs auf Ihre RMS-Protokolle
Sie können den Zugriff auf Ihre RMS-Protokolle delegieren, indem Sie Ihren Speicherkontonamen und den Zugriffsschlüssel freigeben. Sie können den Zugriff auch an einen anderen Administrator, einen Entwickler innerhalb Ihrer Organisation oder einen unabhängigen Softwarehersteller delegieren. Da diese nicht über Ihre RMS-Administratoranmeldeinformationen verfügen, können sie nicht das Cmdlet „Get-AardrmUsageLog“ verwenden, um die RMS-Protokolle herunterzuladen. Stattdessen müssen sie das Windows Storage SDK verwenden, um die Protokolle herunterzuladen. Alternativ können sie eine Anwendung schreiben, die die Protokolle direkt aus dem Azure-Speicher liest.

Das Freigeben Ihres Speicherkontonamens und des Zugriffsschlüssels auf diese Weise ist sicher, wenn das Speicherkonto dediziert für Ihre RMS-Protokolle bestimmt ist. Obgleich andere Personen auch Ihren Zugriffsschlüssel besitzen, können sie damit nicht auf ein anderes Speicherkonto zugreifen oder Ihr RMS-Mandantenkonto verwenden.

## <a name="BKMK_Interpret"></a>Interpretieren Ihrer RMS-Protokolle
Verwenden Sie folgende Informationen als Hilfestellung bei der Interpretation der RMS-Protokolle.

Beim ersten Schreiben von Protokollen in Ihr Speicherkonto erstellt RMS die folgenden beiden Container:

- **Rms-metadata**: Dieser Container ist für RMS reserviert. Dieser Container darf nicht geändert oder gelöscht werden.

- **Rms-logs-&lt;GUID&gt;**: In diesem Container erstellt und speichert RMS die Protokolle. Sie können alle Dateien in diesem Container problemlos löschen, wenn Sie die darin enthaltenen Protokollinformationen nicht mehr benötigen.

Im Laufe der Zeit erstellt RMS möglicherweise zusätzliche **Rms-logs-&lt;GUID&gt;**-Container. Wenn beispielsweise der Container **Rms-metadata** beschädigt oder versehentlich gelöscht wird, setzt RMS seinen Inhalt zurück, und erstellt einen neuen Container **Rms-logs-&lt;GUID&gt;** für alle künftigen Protokolle. Die alten Protokolle im alten Container werden nicht gelöscht, sondern sind dann verwaist.

RMS schreibt die Protokolle als eine Serie von BLOBs. Jedes BLOB enthält mindestens einen Protokolldatensatz im erweiterten W3C-Protokollformat.

Der Name jedes BLOBs ist eine Nummer. Innerhalb jedes Protokollcontainers erhält das erste BLOB den Namen „000000001“. Jedes BLOB wird sequenziell in der Reihenfolge seiner Erstellung benannt. Jedes BLOB enthält mindestens einen Protokolldatensatz. Jeder Protokolldatensatz enthält einen UTC-Zeitstempel, der angibt, wann die entsprechende Anforderung von RMS verarbeitet wurde.

> [!IMPORTANT]
> Das RMS-Protokollierungssystem ist so optimiert, dass es die Protokolle schnell zur Verfügung stellt, statt in strikter Reihenfolge. Die Reihenfolge der BLOBs sowie die Reihenfolge der Protokolldatensätze in einem BLOB kann nicht chronologisch sein. Der einzige Grund für die sequenzielle Benennung der BLOBs liegt darin, Ihnen das effiziente inkrementelle Herunterladen der Protokolle zu ermöglichen.
> 
> Zwei Beispiel für potenzielle Protokollsequenzergebnisse:
> 
> - Die Protokolldatensätze in BLOB 000000004 können chronologisch mit den Protokolldatensätze in BLOB 000000003 überlappen. In Extremfällen können alle Protokolldatensätze in BLOB 000000004 vor allen Protokolldatensätze in BLOB 000000003 generiert worden sein.
> - Der zweite Protokolldatensatz in einem BLOB kann vor dem ersten Protokolldatensatz generiert worden sein, wurde aber in umgekehrter Reihenfolge in den Speicher geschrieben.

Bevor Sie Ihre RMS-Protokolle analysieren, empfehlen wir Ihnen, das Protokoll in ein Repository herunterzuladen und zu importieren, wo Sie die Protokolle anhand ihrer Zeitstempel sortieren können. Weitere Informationen zum Herunterladen der Protokolle finden Sie in diesem Thema im Abschnitt [How to access and use your RMS logs](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md#BKMK_AccesAndUseLogs).

Da die Protokolle nicht notwendigerweise in chronologischer Reihenfolge sind, aber ihre Mehrheit innerhalb von 15 Minuten nach der Anforderung geschrieben werden, fügen Sie bei der Identifizierung der zu verwendenden Protokolle anhand ihres Zeitstempels 15 Minuten zu der Zeit, an der Sie interessiert sind, hinzu. Laden Sie dann diese Protokolle herunter. Diese Strategie sollte sicherstellen, dass Sie fast alle Protokolle erhalten.

Woran Sie noch denken sollten, ist, dass der Zeitstempel jedes Protokolldatensatzes in lokaler Zeit des RMS-Servers ist, von dem die Anforderung verarbeitet wurde. Da RMS auf mehreren Servern in mehreren Rechenzentren ausgeführt wird, scheinen die Protokolle manchmal nicht in der richtigen Reihenfolge zu sein, auch wenn sie nach Zeitstempel sortiert sind. Die Abweichung ist jedoch in der Regel gering und liegt im Bereich von einer Minute. In den meisten Fällen ist dies kein Problem, das sich nachteilig bei der Protokollanalyse manifestieren würde.

Jedes BLOB ist im erweiterten W3C-Protokollformat. Es beginnt mit den folgenden zwei Zeilen:

**#Software: RMS**

**#Version: 1.0**

Die erste Zeile zeigt an, dass es sich um RMS-Protokolle handelt. Die zweite Zeile gibt an, dass der Rest des BLOBs die Spezifikation der Version 1.0 einhält. Wir empfehlen, dass alle Anwendungen, die diese Protokolle analysieren, diese beiden Zeilen überprüfen, bevor sie die Analyse des Rests des BLOBs fortsetzen.

In der dritten Zeile wird eine Liste von Feldnamen aufgezählt, die durch Tabstopps voneinander getrennt sind:

**#Fields: date     time     row-id     request-type     user-id     result     correlation-id     content-id     c-info     c-ip**

Jede der folgenden Zeilen stellt einen Protokolldatensatz dar. Die Werte der Felder sind in derselben Reihenfolge wie die vorangehende Zeile, auch durch Tabstopps getrennt. Verwenden Sie die folgende Tabelle, um die Felder zu interpretieren.

|Feldname <br /> <br />|W3C-Datentyp <br /> <br />|Beschreibung <br /> <br />|Beispielwert <br /> <br />|
|------------|----------------|----------------|----------------|
|date <br /> <br />|Datum <br /> <br />|Das UTC-Datum, an dem die Anforderung verarbeitet wurde. <br /> <br />Die Quelle ist die lokale Uhr auf dem Server, von dem die Anforderung bearbeitet wurde. <br /> <br />|2013-06-25 <br /> <br />|
|time <br /> <br />|Zeit <br /> <br />|Die UTC-Zeit im 24-Stunden-Format, zu der die Anforderung verarbeitet wurde. <br /> <br />Die Quelle ist die lokale Uhr auf dem Server, von dem die Anforderung bearbeitet wurde. <br /> <br />|21:59:28 <br /> <br />|
|row-id <br /> <br />|Text <br /> <br />|Eindeutige GUID für diesen Protokolldatensatz. <br /> <br />Dieser Wert ist hilfreich, wenn Sie Protokolle aggregieren oder in ein anderes Format kopieren. <br /> <br />|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63 <br /> <br />|
|request-type <br /> <br />|Name <br /> <br />|Der Name der angeforderten RMS-API. <br /> <br />|AcquireLicense <br /> <br />|
|user-id <br /> <br />|"String" <br /> <br />|Der Benutzer, der die Anforderung gesendet hat. <br /> <br />Der Wert steht in einfachen Anführungszeichen. Manche Anforderungstypen sind anonym, wobei der Wert dann "" ist. <br /> <br />|'joe@contoso.com' <br /> <br />|
|result <br /> <br />|"String" <br /> <br />|„Success“, wenn die Anforderung erfolgreich verarbeitet wurde. <br /> <br />Der Fehlertyp in einfachen Anführungszeichen zeigt an, wenn die Anforderung fehlgeschlagen ist. <br /> <br />|'Success' <br /> <br />|
|correlation-id <br /> <br />|Text <br /> <br />|Eine GUID, die das RMS-Clientprotokoll und das Serverprotokoll für eine bestimmte Anforderung gemeinsam haben. <br /> <br />Dieser Wert kann bei der Behandlung von Clientproblemen hilfreich sein. <br /> <br />|cab52088-8925-4371-be34-4b71a3112356 <br /> <br />|
|content-id <br /> <br />|Text <br /> <br />|Eine GUID in geschweiften Klammern, die den geschützten Inhalt identifiziert (z. B. ein Dokument). <br /> <br />Dieses Feld hat nur dann einen Wert, wenn „request-type“ den Wert „AcquireLicense“ hat, und ist bei allen anderen Anforderungstypen leer. <br /> <br />|{bb4af47b-cfed-4719-831d-71b98191a4f2} <br /> <br />|
|c-info <br /> <br />|"String" <br /> <br />|Informationen zur Clientplattform, von der die Anforderung gesendet wird. <br /> <br />Die spezifische Zeichenfolge variiert in Abhängigkeit von der Anwendung (z. B. Betriebssystem oder Browser). <br /> <br />|'MSIPC;version=1.0.622.36;AppName=IPViewer.exe;AppVersion=1.0.1127.0;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64' <br /> <br />|
|c-ip <br /> <br />|Adresse <br /> <br />|Die IP-Adresse des Clients, von dem die Anforderung stammt. <br /> <br />|64.51.202.144 <br /> <br />|
Obgleich das Feld „user-id“ normalerweise den Benutzer angibt, von dem die Anforderung stammt, gibt es zwei Ausnahmen, bei denen der Wert keinem echten Benutzer entspricht:

- Der Wert **'microsoftrmsonline@&lt;IhreMandantenID&gt;.rms.&lt;Region&gt;.aadrm.com'**.

   Dies zeigt an, dass die Anforderung von einem Office 365-Dienst wie Exchange Online oder SharePoint Online stammt. In der Zeichenfolge steht *&lt;IhreMandantenID&gt;* für die GUID Ihres Mandanten und *&lt;Region&gt;* für die Region, in der Ihr Mandant registriert ist.**na** steht beispielsweise für Nordamerika, **eu** für Europa und **ap** für Asien.

- Wenn Sie den RMS-Connector verwenden.

   Anforderungen von diesem Connector werden mit dem Dienstprinzipalnamen protokolliert, der von RMS automatisch generiert wird, wenn Sie den RMS-Connector installieren.

Es gibt zahlreiche Anforderungstypen in RMS, aber die folgende Tabelle identifiziert einige der am häufigsten verwendeten Anforderungstypen.

|Anforderungstyp <br /> <br />|Beschreibung <br /> <br />|
|-------------------|----------------|
|AcquireLicense <br /> <br />|Der Client fordert von einem Windows-basierten Computer aus eine Lizenz für ein bestimmtes Inhaltselement an. <br /> <br />|
|FECreateEndUserLicenseV1 <br /> <br />|Ähnlich wie bei der „AcquireLicense“-Anforderung, aber von mobilen Geräten aus. <br /> <br />|
|Certify <br /> <br />|Der Client fordert von einem Windows-basierten Computer aus ein Zertifikat an (das später zum Abrufen einer Lizenz verwendet wird). <br /> <br />|
|GetClientLicensorCert <br /> <br />|Der Client fordert von einem Windows-basierten Computer aus ein Veröffentlichungszertifikat an (das später zum Schützen von Inhalt verwendet wird). <br /> <br />|
|FECreatePublishingLicenseV1 <br /> <br />|Identisch mit „Certify“ und „GetClientLicensorCert“ in Kombination, von mobilen Clients aus. <br /> <br />|
|FindServiceLocationsForUser <br /> <br />|Manchmal anonym, manchmal mit Authentifizierung. Diese Anforderung fragt die URLs zum Zertifizieren und Abrufen von Lizenzen ab. <br /> <br />|
|Entschlüsseln <br /> <br />|Nur gültig für BYOK-Szenarios (Bring Your Own Key). RMS protokolliert, wenn Ihr Schlüssel zum Entschlüsseln verwendet wird, was normalerweise einmal pro „AcquireLicence“ (oder „FECreateEndUserLicenseV1“) der Fall ist. <br /> <br />|
|SignDigest <br /> <br />|Nur gültig für BYOK-Szenarios (Bring Your Own Key). RMS protokolliert, wenn Ihr Schlüssel zum Signieren verwendet wird, was normalerweise einmal pro „AcquireLicence“ (oder „FECreateEndUserLicenseV1“), „Certify“ und „GetClientLicensorCert“ („FECreatePublishingLicenseV1“) der Fall ist. <br /> <br />|

## <a name="BKMK_PowerShell"></a>Windows PowerShell-Referenz
Verwenden Sie folgende Windows PowerShell-Cmdlets als Hilfe bei der Konfiguration und Verwendung der RMS-Protokollierung:

- [Disable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629404.aspx)

- [Enable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629421.aspx)

- [Get-AadrmUsageLog](http://msdn.microsoft.com/library/windowsazure/dn629401.aspx)

- [Get-AadrmUsageLogFeature](http://msdn.microsoft.com/library/windowsazure/dn629425.aspx)

- [Get-AadrmUsageLogLastCounterValue](http://msdn.microsoft.com/library/windowsazure/dn629423.aspx)

- [Get-AadrmUsageLogStorageAccount](http://msdn.microsoft.com/library/windowsazure/dn629419.aspx)

- [Set-AadrmUsageLogStorageAccount](http://msdn.microsoft.com/library/windowsazure/dn629426.aspx)

Weitere Informationen zur Windows PowerShell für Rights Management finden Sie unter [Verwalten von Azure Rights Management mithilfe von WindowsPowerShell](../../ems/AADRightsMgmt/Administering-Azure-Rights-Management-by-Using-Windows-PowerShell.md).

## Siehe auch
[Mithilfe von Azure Rights Management](../../ems/AADRightsMgmt/Using-Azure-Rights-Management.md)

