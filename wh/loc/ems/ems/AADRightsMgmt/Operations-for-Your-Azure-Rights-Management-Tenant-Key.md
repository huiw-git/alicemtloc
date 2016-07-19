---
title: Vorg&#228;nge f&#252;r Ihren Azure Rights Management-Mandantenschl&#252;ssel
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
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
# Vorg&#228;nge f&#252;r Ihren Azure Rights Management-Mandantenschl&#252;ssel
Abhängig von der Mandantenschlüsseltopologie (von Microsoft oder vom Kunden verwaltet), besitzen Sie verschiedene Stufen der Kontrolle und Verantwortlichkeit für Ihren Microsoft Azure Rights Management-Mandantenschlüssel (Azure RMS), nachdem er implementiert wurde.

Wenn Sie Ihren eigenen Mandantenschlüssel verwalten, wird dies häufig als „Bring Your Own Key“ (BYOK) bezeichnet. Weitere Informationen zu diesem Szenario und wie Sie zwischen den beiden Mandantenschlüsseltopologien auswählen, finden Sie unter [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

In der folgenden Tabelle werden die Vorgänge identifiziert, die Sie in der jeweiligen Topologie, die Sie für Ihren Azure RMS-Mandantenschlüssel ausgewählt haben, ausführen können.

|Lebenszyklusvorgang|Von Microsoft verwaltet (Standard)|Kundenverwaltet (BYOK)|
|-----------------------|--------------------------------------|--------------------------|
|Widerrufen Ihres Mandantenschlüssels|Nein (automatisch)|Nein (automatisch)|
|Neuvergabe (Rollover) Ihres Mandantenschlüssels|Ja|Ja|
|Sicherung und Wiederherstellung Ihres Mandantenschlüssels|Nein|Ja|
|Exportieren Ihres Mandantenschlüssels|Ja|Nein|
|Reaktion auf eine Sicherheitsverletzung|Ja|Ja|
Nachdem Sie identifiziert haben, welche Topologie Sie implementiert haben, finden Sie in einem der folgenden Abschnitte weitere Informationen zu diesen Vorgängen für Ihren Azure RMS-Mandantenschlüssel.

## <a name="BKMK_MSManagedOperations"></a>Von Microsoft verwaltet: Lebenszyklusvorgänge für Mandantenschlüssel
Wenn Ihr Mandantenschlüssel für Azure RMS von Microsoft verwaltet wird (Standard), finden Sie in den folgenden Abschnitten weitere Informationen zu den Lebenszyklusvorgängen, die für diese Topologie relevant sind:

-   [Revoke your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSRevoke)

-   [Re-key your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSRekey)

-   [Backup and recover your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSBackup)

-   [Export your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSExport)

-   [Respond to a breach](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSBreach)

### <a name="BKMK_MSRevoke"></a>Widerrufen Ihres Mandantenschlüssels
Wenn Sie Ihr Abonnement von Azure RMS kündigen, beendet Azure RMS die Verwendung Ihres Mandantenschlüssels, und von Ihnen ist keine weitere Aktion mehr erforderlich.

### <a name="BKMK_MSRekey"></a>Neuvergabe (Rollover) Ihres Mandantenschlüssels
Die Neuvergabe Ihres Schlüssels wird auch als „Rollover“ bezeichnet. Führen Sie eine Neuvergabe Ihres Mandantenschlüssels nur durch, wenn es wirklich notwendig ist. Ältere Clients wie Office 2010 wurden nicht darauf ausgelegt, problemlos mit Schlüsseländerungen umzugehen. In diesem Szenario müssen Sie den RMS-Zustand auf Computern löschen, indem Sie eine Gruppenrichtlinie oder einen entsprechenden Mechanismus verwenden. Es gibt jedoch einige berechtigte Ereignisse, die Sie zwingen können, Ihren Mandantenschlüssel neu zu vergeben. Beispiel:

-   Ihr Unternehmen wurde in zwei oder mehr Unternehmen aufgeteilt. Wenn Sie Ihren Mandantenschlüssel neu vergeben, hat das neue Unternehmen keinen Zugriff auf neue Inhalte, die von Ihren Mitarbeitern veröffentlicht werden. Sie können auf den alten Inhalt zugreifen, wenn sie eine Kopie des alten Mandantenschlüssels besitzen.

-   Sie glauben, dass die Masterkopie Ihres Mandantenschlüssels (die in Ihrem Besitz befindliche Kopie) kompromittiert wurde.

Sie können Ihren Mandantenschlüssel neu vergeben, indem Sie den Microsoft-Kundendienst (CSS) anrufen und nachweisen, dass Sie der Mandantenadministrator sind.

Wenn Sie Ihren Mandantenschlüssel neu vergeben, wird neuer Inhalt unter Verwendung des neuen Mandantenschlüssels geschützt. Dies geschieht in einer gestaffelten Weise, sodass für einen gewissen Zeitraum neue Inhalte noch teilweise durch den alten Mandantenschlüssel geschützt sind. Zuvor geschützte Inhalte bleiben durch den alten Mandantenschlüssel geschützt. Um dieses Szenario zu unterstützen, behält Azure RMS Ihren alten Mandantenschlüssel bei, damit es Lizenzen für alte Inhalte erteilen kann.

### <a name="BKMK_MSBackup"></a>Sicherung und Wiederherstellung Ihres Mandantenschlüssels
Microsoft ist für die Sicherung Ihres Mandantenschlüssels verantwortlich, sodass von Ihnen keine weitere Aktion erforderlich ist.

### <a name="BKMK_MSExport"></a>Exportieren Ihres Mandantenschlüssels
Sie können Ihre Azure RMS-Konfiguration und den Mandantenschlüssel anhand der folgenden Anleitung mit diesen drei Schritten exportieren:

##### Schritt 1: Initiieren des Exports

-   Hierzu kontaktieren Sie den Microsoft-Kundendienst (CSS). Sie müssen nachweisen, dass Sie ein Administrator für Ihren Azure RMS-Mandanten sind.

##### Schritt 2: Warten auf Überprüfung

-   Microsoft überprüft, ob Ihre Anfrage zum Freigeben Ihres RMS-Mandantenschlüssels legitim ist. Der Vorgang kann bis zu drei Wochen dauern.

##### Schritt 3: Erhalten von Schlüsselanweisungen vom Kundendienst (CSS)

-   Der Microsoft-Kundendienst (CSS) sendet Ihren Ihre Azure RMS-Konfiguration und den Mandantenschlüssel als verschlüsselte, kennwortgeschützte Datei mit der Dateinamenerweiterung „TPD“ zu. Hierzu sendet Ihnen (als der Person, die den Export initiiert hat) der Kundendienst zuerst per E-Mail ein Tool. Sie müssen das Tool wie folgt an einer Eingabeaufforderung ausführen:

    ```
    AadrmTpd.exe -createkey
    ```
    Hierdurch wird ein RSA-Schlüsselpaar generiert, und die öffentliche und private Hälfte wird jeweils als Datei im aktuellen Ordner gespeichert. Beispiel: **PublicKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt** und **PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt**.

    Antworten Sie auf die E-Mail des Kundendiensts, wobei Sie die Datei anfügen, deren Name mit **PublicKey** beginnt. Der Kundendienst sendet Ihnen als Nächstes eine TPD-Datei als XML-Datei, die mit Ihrem RSA-Schlüssel verschlüsselt ist. Kopieren Sie diese Datei in den Ordner, in dem Sie das Tool „AadrmTpd“ ursprünglich ausgeführt haben, und führen Sie das Tool erneut aus, wobei Sie Ihre Datei, die mit **PrivateKey** beginnt, und die Datei vom Kundendienst verwenden. Beispiel:

    ```
    AadrmTpd.exe -key PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt -target TPD-77172C7B-8E21-48B7-9854-7A4CEAC474D0.xml
    ```
    Die Ausgabe dieses Befehls sollte aus zwei Dateien bestehen: Eine enthält das Klartextkennwort für die kennwortgeschützte TPD-Datei und die andere die kennwortgeschützte TPD-Datei selbst. Zu Querverweiszwecken sollten beide dieselbe GUID wie die öffentliche und die private Schlüsseldatei haben, als Sie den Befehl „AadrmTpd.exe -createkey“ ausgeführt haben:

    -   Password-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt

    -   ExportedTPD-FA29D0FE-5049-4C8E-931B-96C6152B0441.xml

    Sichern Sie diese Dateien, und speichern Sie sie sicher, um zu gewährleisten, dass Sie weiterhin Inhalte entschlüsseln können, die mit diesem Mandantenschlüssel geschützt wurden. Zusätzlich können Sie, wenn Sie zu AD RMS migrieren, diese TPD-Datei (die Datei, die mit **ExportedTDP** beginnt) in Ihren AD RMS-Server importieren.

##### Schritt 4: Fortlaufend: Schützen Ihres Mandantenschlüssels

-   Nachdem Sie Ihren Mandantenschlüssel erhalten haben, bewahren Sie ihn sicher auf, weil jede Person, die darauf zugreifen kann, alle Dokumente entschlüsseln kann, die mithilfe dieses Schlüssels geschützt werden.

    Wenn der Grund für das Exportieren Ihres Mandantenschlüssels darin besteht, dass Sie Azure RMS nicht mehr verwenden möchten, sollten Sie als bewährte Methode Ihren RMS-Mandanten nun deaktivieren. Führen Sie diesen Vorgang unmittelbar nach dem Erhalt des Mandantenschlüssels aus, weil diese Vorsichtsmaßnahme die möglichen Konsequenzen minimiert, wenn auf Ihren Mandantenschlüssel durch eine Person zugegriffen wird, die nicht über diesen Schlüssel verfügen sollte. Anweisungen finden Sie unter [Außerbetriebsetzen und Deaktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Decommissioning-and-Deactivating-Azure-Rights-Management.md).

### <a name="BKMK_MSBreach"></a>Reaktion auf eine Sicherheitsverletzung
Kein Sicherheitssystem, egal wie stark es ist, kommt vollständig ohne einen Prozess für Reaktion auf eine Sicherheitsverletzung aus. Ihr Mandantenschlüssel könnte kompromittiert oder gestohlen werden. Auch wenn er gut geschützt ist, können Sicherheitslücken in der HSM-Technologie der aktuellen Generation oder bei aktuellen Schlüssellängen und Algorithmen gefunden werden.

Microsoft hat ein dediziertes Team, um auf Sicherheitsvorfälle bei eigenen Produkten und Diensten zu reagieren. Sobald ein glaubhafter Bericht über einen Vorfall vorliegt, kümmert sich dieses Team um die Untersuchung des Umfangs, der Ursache und um Abhilfen. Wenn sich dieser Vorfall auf Ihre Objekte auswirkt, wird Ihr Azure RMS-Mandantenadministrator per E-Mail von Microsoft unter der Adresse benachrichtig, die Sie beim Abschluss des Abonnements angegeben haben.

Wenn bei Ihnen eine Sicherheitsverletzung aufgetreten ist, hängt die beste Vorgehensweise auf Ihrer und auf Microsofts Seite vom Umfang der Sicherheitsverletzung ab. Microsoft führt diesen Prozess gemeinsam mit Ihnen durch. In der folgenden Tabelle finden Sie einige typische Situationen und die wahrscheinliche Reaktion darauf, obgleich die exakte Reaktion immer von allen Informationen abhängt, die im Rahmen der Untersuchung gewonnen werden.

|Beschreibung des Vorfalls|Wahrscheinliche Reaktion|
|-----------------------------|----------------------------|
|Ihr Mandantenschlüssel wurde abgegriffen.|Vergeben Sie Ihren Mandantenschlüssel neu. Weitere Informationen finden Sie im Abschnitt [Re-key your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_MSRekey) in diesem Thema.|
|Eine nicht autorisierte Person oder Schadsoftware hat Rechte zur Verwendung Ihres Mandantenschlüssels erlangt, aber nicht den Schlüssel selbst.|Die Neuvergabe (Rollover) Ihres Mandantenschlüssels schafft hierbei keine Abhilfe und erfordert eine Ursachenanalyse. Wenn ein Prozess- oder Softwarefehler dafür verantwortlich war, dass die nicht autorisierte Person Zugriff erlangt hat, muss dieser Zustand behoben werden.|
|Im RSA-Algorithmus oder bei der Schlüssellänge entdeckte Sicherheitslücken oder auch Brute-Force-Angriffe werden von der Rechenleistung her möglich.|Microsoft muss den Azure RMS so aktualisieren, dass neue Algorithmen und längere Schlüssellängen unterstützt werden, die robust sind, und alle Kunden anweisen, ihre Mandantenschlüssel zu erneuern.|

## <a name="BKMK_BYOKManagedOperations"></a>Vom Kunden verwaltet: Lebenszyklusvorgänge für Mandantenschlüssel
Wenn Ihr Mandantenschlüssel für Azure RMS von Ihnen verwaltet wird (BYOK-Szenario, „Bring Your Own Key“), finden Sie in den folgenden Abschnitten weitere Informationen zu den Lebenszyklusvorgängen, die für diese Topologie relevant sind:

-   [Revoke your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKRevoke)

-   [Re-key your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKRekey)

-   [Backup and recover your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKBackup)

-   [Export your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKExport)

-   [Respond to a breach](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKBreach)

### <a name="BKMK_BYOKRevoke"></a>Widerrufen Ihres Mandantenschlüssels
Wenn Sie Ihr Abonnement von Azure RMS kündigen, beendet Azure RMS die Verwendung Ihres Mandantenschlüssels, und von Ihnen ist keine weitere Aktion mehr erforderlich.

### <a name="BKMK_BYOKRekey"></a>Neuvergabe (Rollover) Ihres Mandantenschlüssels
Die Neuvergabe Ihres Schlüssels wird auch als „Rollover“ bezeichnet. Führen Sie eine Neuvergabe Ihres Mandantenschlüssels nur durch, wenn es wirklich notwendig ist. Ältere Clients wie Office 2010 wurden nicht darauf ausgelegt, problemlos mit Schlüsseländerungen umzugehen. In diesem Szenario müssen Sie den RMS-Zustand auf Computern löschen, indem Sie eine Gruppenrichtlinie oder einen entsprechenden Mechanismus verwenden. Es gibt jedoch einige berechtigte Ereignisse, die Sie zwingen können, Ihren Mandantenschlüssel neu zu vergeben. Beispiel:

-   Ihr Unternehmen wurde in zwei oder mehr Unternehmen aufgeteilt. Wenn Sie Ihren Mandantenschlüssel neu vergeben, hat das neue Unternehmen keinen Zugriff auf neue Inhalte, die von Ihren Mitarbeitern veröffentlicht werden. Sie können auf den alten Inhalt zugreifen, wenn sie eine Kopie des alten Mandantenschlüssels besitzen.

-   Sie glauben, dass die Masterkopie Ihres Mandantenschlüssels (die in Ihrem Besitz befindliche Kopie) kompromittiert wurde.

Wenn Sie Ihren Mandantenschlüssel neu vergeben, wird neuer Inhalt unter Verwendung des neuen Mandantenschlüssels geschützt. Dies geschieht in einer gestaffelten Weise, sodass für einen gewissen Zeitraum neue Inhalte noch teilweise durch den alten Mandantenschlüssel geschützt sind. Zuvor geschützte Inhalte bleiben durch den alten Mandantenschlüssel geschützt. Um dieses Szenario zu unterstützen, behält Azure RMS Ihren alten Mandantenschlüssel bei, damit es Lizenzen für alte Inhalte erteilen kann.

Wenn Sie Ihren Mandantenschlüssel neu vergeben möchten, generieren und erstellen Sie über das Internet oder persönlich einen neuen Schlüssel, indem Sie die im Abschnitt [Implementing bring your own key (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ImplementBYOK) beschriebenen Verfahren aus dem Thema [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md) verwenden.

### <a name="BKMK_BYOKBackup"></a>Sicherung und Wiederherstellung Ihres Mandantenschlüssels
Sie sind für das Sichern Ihres Mandantenschlüssels verantwortlich. Wenn Sie Ihren Mandantenschlüssel in einem Thales HSM generiert haben, sichern Sie einfach die Tokenschlüsseldatei, die World-Datei und die Administrator Cards, um den Mandantenschlüssel zu sichern.

Wenn Sie Ihren Schlüssel unter Einhaltung der im Abschnitt [Implementing bring your own key (BYOK)](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_ImplementBYOK) des Themas [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md) aufgeführten Verfahren übertragen haben, speichert Azure RMS die Tokenschlüsseldatei dauerhaft, um Schutz vor Ausfällen jeglicher Azure RMS-Knoten zu bieten. Sie sollten dies aber nicht als vollwertige Sicherung ansehen. Wenn Sie nämlich jemals eine Klartextkopie Ihres Schlüssels zur Verwendung außerhalb eines Thales HSM benötigen, kann Azure RMS diese nicht abrufen, weil er lediglich über eine nicht wiederherstellbare Kopie verfügt.

### <a name="BKMK_BYOKExport"></a>Exportieren Ihres Mandantenschlüssels
Wenn Sie BYOK verwenden, können Sie Ihren Mandantenschlüssel nicht aus Azure RMS exportieren. Die Kopie in Azure RMS ist nicht wiederherstellbar. Wenn Sie diesen Schlüssel löschen möchten, sodass er nicht mehr verwendet werden kann, wenden Sie sich an Microsoft-Kundendienst und -Support (CSS).

### <a name="BKMK_BYOKBreach"></a>Reaktion auf eine Sicherheitsverletzung
Kein Sicherheitssystem, egal wie stark es ist, kommt vollständig ohne einen Prozess für Reaktion auf eine Sicherheitsverletzung aus. Ihr Mandantenschlüssel könnte kompromittiert oder gestohlen werden. Auch wenn er gut geschützt ist, können Sicherheitslücken in der HSM-Technologie der aktuellen Generation oder bei aktuellen Schlüssellängen und Algorithmen gefunden werden.

Microsoft hat ein dediziertes Team, um auf Sicherheitsvorfälle bei eigenen Produkten und Diensten zu reagieren. Sobald ein glaubhafter Bericht über einen Vorfall vorliegt, kümmert sich dieses Team um die Untersuchung des Umfangs, der Ursache und um Abhilfen. Wenn sich dieser Vorfall auf Ihre Objekte auswirkt, wird Ihr Azure RMS-Mandantenadministrator per E-Mail von Microsoft unter der Adresse benachrichtig, die Sie beim Abschluss des Abonnements angegeben haben.

Wenn bei Ihnen eine Sicherheitsverletzung aufgetreten ist, hängt die beste Vorgehensweise auf Ihrer und auf Microsofts Seite vom Umfang der Sicherheitsverletzung ab. Microsoft führt diesen Prozess gemeinsam mit Ihnen durch. In der folgenden Tabelle finden Sie einige typische Situationen und die wahrscheinliche Reaktion darauf, obgleich die exakte Reaktion immer von allen Informationen abhängt, die im Rahmen der Untersuchung gewonnen werden.

|Beschreibung des Vorfalls|Wahrscheinliche Reaktion|
|-----------------------------|----------------------------|
|Ihr Mandantenschlüssel wurde abgegriffen.|Vergeben Sie Ihren Mandantenschlüssel neu. Weitere Informationen finden Sie im Abschnitt [Re-key your tenant key](../../ems/AADRightsMgmt/Operations-for-Your-Azure-Rights-Management-Tenant-Key.md#BKMK_BYOKRekey) in diesem Thema.|
|Eine nicht autorisierte Person oder Schadsoftware hat Rechte zur Verwendung Ihres Mandantenschlüssels erlangt, aber nicht den Schlüssel selbst.|Die Neuvergabe (Rollover) Ihres Mandantenschlüssels schafft hierbei keine Abhilfe und erfordert eine Ursachenanalyse. Wenn ein Prozess- oder Softwarefehler dafür verantwortlich war, dass die nicht autorisierte Person Zugriff erlangt hat, muss dieser Zustand behoben werden.|
|Entdeckte Sicherheitslücke in HSM-Technologie der aktuellen Generation.|Microsoft muss die HSMs aktualisieren. Wenn es Anlass gibt, zu glauben, dass durch die Sicherheitslücke Schlüssel kompromittiert wurden, wird Microsoft alle Kunden anweisen, ihre Mandantenschlüssel zu erneuern.|
|Im RSA-Algorithmus oder bei der Schlüssellänge entdeckte Sicherheitslücken oder auch Brute-Force-Angriffe werden von der Rechenleistung her möglich.|Microsoft muss den Azure RMS so aktualisieren, dass neue Algorithmen und längere Schlüssellängen unterstützt werden, die robust sind, und alle Kunden anweisen, ihre Mandantenschlüssel zu erneuern.|

## Siehe auch
[Mithilfe von Azure Rights Management](../../ems/AADRightsMgmt/Using-Azure-Rights-Management.md)

