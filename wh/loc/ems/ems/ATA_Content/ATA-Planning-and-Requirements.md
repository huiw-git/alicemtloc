---
title: ATA-Planung und Anforderungen
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
ms.assetid: a5f90544-1c70-4aff-8bf3-c59dd7abd687
translation.priority.mt: 
  - de-de
  - ja-jp
---
# ATA-Planung und Anforderungen
Dieser Abschnitt beschreibt die Anforderungen der ATA-Center und ATA-Gateway in Ihrer Umgebung erfolgreich bereitgestellt und enthält die folgenden Abschnitte:

[Active Directory Domain Services (AD DS)](#ATAADDS)

[SEIM/Syslog](#ATASIEM)

[ATA Center](#ATAcenter)

[ATA Console](#ATAconsole)

[ATA Gateway](#ATAgateway)

[Additional items](#ATAmisc)

## <a name="ATAADDS"></a>Active Directory-Domänendienste (AD DS)
Im folgende Abschnitt wird beschrieben, die das ATA-Center und das ATA-Gateway in Ihrer Umgebung erfolgreich bereitzustellen.

### Allgemein

-   Domänencontroller unter Windows Server 2008 und höher ausgeführt.

-   Benutzerkonto und Kennwort mit Lesezugriff auf **alle Objekte** in den Domänen, die überwacht werden.

    > [!NOTE]
    > Wenn Sie benutzerdefinierte ACLs auf verschiedene Organisationseinheiten Einheiten (OU) in Ihrer Domäne eingerichtet haben, stellen Sie sicher, dass es sich bei der ausgewählte Benutzer zu diesen Organisationseinheiten über Leseberechtigungen verfügt.

    Optional: Benutzer sollten nur Berechtigungen für den Container für gelöschte Objekte gelesen haben. Dadurch können ATA massenlöschung von Objekten in der Domäne zu erkennen. Informationen zum Konfigurieren von Leseberechtigungen nur für Container der gelöschten Objekte finden Sie unter der **Ändern von Berechtigungen für einen Container des gelöschten Objekts** im Abschnitt der [anzeigen oder Festlegen von Berechtigungen für ein Verzeichnisobjekt](https://technet.microsoft.com/library/cc816824%28v=ws.10%29.aspx) Thema.

-   Optional: Ein Benutzerkonto eines Benutzers ohne Netzwerk Aktivitäten. Dieses Konto wird als ATA-Honeytoken Benutzer konfiguriert werden. Zum Konfigurieren des Honeytoken Benutzers benötigen Sie die SID des Benutzerkontos und nicht den Benutzernamen.

### Netzwerk
Die ATA-Gateway muss alle Netzwerkdatenverkehr zu und von jedem überwachten Domänencontroller finden Sie unter. Konfigurieren Sie **Port-mirroring** für jeden Domänencontroller überwacht werden soll, als die **Quelle** des Netzwerkverkehrs. Finden Sie unter [Konfigurieren Sie die Port-Spiegelung](../../ems/ATA_Content/Configure-Port-Mirroring.md) Weitere Informationen. In der Regel müssen Sie mit der Netzwerk- oder Virtualization Team Port-mirroring konfigurieren.

## <a name="ATASIEM"></a>Ereignissammlung
Zusätzlich zum Sammeln und Analysieren des Netzwerkverkehrs zu und von den Domänencontrollern, können ATA Windows-Ereignis 4776 um weiter ATA Pass-the-Hash-Erkennung zu verbessern. Dies kann aus der SIEM oder indem Sie die Windows-Ereignisweiterleitung von Ihrem Domänencontroller empfangen werden. Gesammelten Ereignisse bieten ATA mit zusätzlichen Informationen, die nicht über das Netzwerkdatenverkehr auf dem Domänencontroller verfügbar ist.

### SIEM/Syslog
Für ATA, um Daten aus einem Syslog-Server verwenden zu können müssen Sie Folgendes konfigurieren:

-   Konfigurieren Sie einen der ATA-Gateway-Server zum Abhören von und akzeptieren die Ereignisse, die vom Server SIEM/Sylog weitergeleitet.

-   Konfigurieren Sie den SIEM/Syslog-Server zum Weiterleiten von bestimmter Ereignissen zum ATA-Gateway.

> [!IMPORTANT]
> -   Nicht alle Syslog-Daten an das ATA-Gateway weitergeleitet.
> -   ATA unterstützt UDP-Datenverkehr vom SIEM/Syslog-Server.

Verweisen Sie auf Ihre SIEM/Syslog-Server-Produktdokumentation für Informationen zum Weiterleiten von bestimmten Ereignissen an einen anderen Server zu konfigurieren. Weitere Informationen über die weitergeleiteten auf ATA-Ereignisse finden Sie unter [Konfigurieren der Ereignissammlung](../../ems/ATA_Content/Configure-Event-Collection.md).

### Weiterleiten von Windows-Ereignissen
Wenn Sie keinen SIEM/Syslog-Server verwenden, können Sie Ihre Windows-Domänencontroller zum Weiterleiten von Windows-Ereignis-ID 4776 gesammelt und analysiert von ATA konfigurieren. Windows-Ereignis-ID 4776 enthält Daten im Zusammenhang mit NTLM-Authentifizierungen.

Weitere Informationen finden Sie unter:  [Configuring Windows Event Forwarding](http://msdn.microsoft.com/en-us/library/1608e89e-0d73-499e-a603-8c540b6f5b9d).

## <a name="ATAmisc"></a>Kurzfristige Lease Subnetze
Identifizieren Sie die Subnetze, IP-Adressen zwischen Geräten innerhalb kurzer Zeit (Sekunden oder Minuten) erneut zugewiesen werden. ATA verringert die Cachelebensdauer für alle IP-Adressen in den Subnetzen, um die schnelle erneute Zuweisung zwischen Geräten zu berücksichtigen. VPN- oder Wi-Fi-Netzwerke sind Beispiele für kurzfristige Lease Subnetze. Finden Sie unter [ATA-Installation](../../ems/ATA_Content/ATA-Installation.md) für kurzfristige Lease Subnetzkonfiguration.

## <a name="ATAcenter"></a>ATA-Center
In diesem Abschnitt werden die Anforderungen für die ATA-Center aufgeführt.

### Betriebssystem:
Die ATA-Center unterstützt die Installation auf einem Server mit Windows Server 2012 R2. Führen Sie Windows Update, und stellen Sie sicher, dass alle wichtigen Updates installiert sind.

> [!NOTE]
> Die ATA-Center kann auf einem Server installiert werden, die Mitglied einer Domäne oder Arbeitsgruppe ist.

### Synchronisierung
Der ATA-Center-Server und dem ATA-Gatewayserver benötigen Zeit innerhalb von 5 Minuten mit synchronisiert.

### BIOS-Einstellungen
Die ATA-Datenbank erfordert, die Sie deaktivieren Non-Uniform Memory Access (NUMA) im BIOS. Das System bezieht sich möglicherweise auf NUMA als Knoten überlappen, in diesem Fall müssen Sie die Knoten-Interleaving aktivieren. Finden Sie weitere Informationen der BIOS-Dokumentation.

### Hardwareanforderungen:
Die Anzahl der Domänencontroller, die Sie überwachen und die Last auf jedem Domänencontroller schreibt vor, die bezüglich der Hardware.

**Mindestanforderungen**

> [!NOTE]
> Wenn Sie ATA in einem Labor mit einigen virtuellen Computern installieren möchten, wird empfohlen, Sie über mindestens 2 Kerne, 4 GB verfügen RAM und 100GB Speicher ermöglicht es Ihnen, mit der ATA-Konsole ohne Unterstützung für die Bereitstellung in der Produktion zu interagieren.

-   CPU - Kerne von 8

-   Speicher – 48 GB

-   Speicher – 1000 GB pro Monat 2 leicht überwachen geladen Domänencontroller

Die ATA-Center erfordert mindestens 21 Tage von Daten für Benutzer im Verhalten Analysen. Weitere Informationen zu Hardware finden Sie unter [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md).

### Netzwerk

#### Netzwerkadapter:
Anforderungen:

-   Ein Netzwerkadapter

-   Zwei IP-Adressen

Kommunikation zwischen dem ATA- und das ATA-Gateway ist verschlüsselt mithilfe von SSL an Port 443. Darüber hinaus wird die ATA-Konsole wird auf IIS ausgeführt und mithilfe von SSL an Port 443.**Zwei IP-Adressen** werden empfohlen. Das ATA-Sicherheitscenter wird Port 443 an die erste IP-Adresse gebunden, und IIS wird Port 443 auf die zweite IP-Adresse gebunden.

> [!NOTE]
> Eine einzelne IP-Adresse mit zwei verschiedene Ports verwendet werden kann, aber zwei IP-Adressen werden empfohlen.

#### Ports:
In der folgende Tabelle sind die Mindestanforderungen Ports aufgeführt, die für die ATA-Center ordnungsgemäß geöffnet werden.

In dieser Tabelle IP-Adresse 1 an das ATA-Sicherheitscenter gebunden ist, und IP-Adresse 2 an den IIS-Dienst für die ATA-Konsole gebunden ist.

|Protokoll|Transport|Port|In|Richtung|IP-Adresse|
|-------------|-------------|--------|------|------------|--------------|
|**SSL** (ATA-Kommunikation)|TCP|443 oder konfigurierbare|ATA-Gateway|Eingehende|IP-Adresse 1|
|**HTTP**|TCP|80|Unternehmensnetzwerk|Eingehende|IP-Adresse 2|
|**HTTPS**|TCP|443|Unternehmensnetzwerk und ATA-Gateway|Eingehende|IP-Adresse 2|
|**SMTP** (optional)|TCP|25|SMTP-Server|Ausgehende|IP-Adresse 2|
|**SMTPS** (optional)|TCP|465|SMTP-Server|Ausgehende|IP-Adresse 2|
|**Syslog** (optional)|TCP|514|Syslog-server|Ausgehende|IP-Adresse 2|

### Zertifikate (optional):
Um die Installation des ATA-Center zu erleichtern, können Sie während der Installation des Mittelpunkts ATA selbstsignierte Zertifikate installieren. Nach der Bereitstellung, die Sie mit einem Zertifikat von einer internen Zertifizierungsstelle von ATA-Gateway zu verwendende selbstsignierte ersetzen können.

> [!NOTE]
> Selbstsignierte Zertifikate sollten nur für die Lab-Bereitstellung verwendet werden.

Die ATA-Center benötigt Zertifikate für die folgenden Dienste:

-   Internet-Informationsdienste (IIS) – Webserverzertifikats

-   ATA-Sicherheitscenter – Serverauthentifizierungszertifikat

> [!NOTE]
> Wenn Sie beabsichtigen, die ATA-Konsole von anderen Computern aus zugreifen, stellen Sie sicher, dass diese Computer von IIS verwendeten Zertifikats vertrauen andernfalls erhalten einer Warnseite Sie, dass vor dem Abrufen auf der Anmeldeseite ein Problem mit dem Sicherheitszertifikat der Website vorliegt.

### Virtualisierung:
Installation des ATA-Center als virtueller Computer wird unterstützt.

> [!NOTE]
> Wenn Sie die ATA-Center als virtuellen Computer ausführen, den Server Herunterfahren Sie vor dem Erstellen eines neuen Prüfpunkts um eine mögliche Beschädigung der Datenbank zu vermeiden.

### Bei der Installation installierte Komponenten
Die folgenden Komponenten installiert und konfiguriert während der Installation des ATA-Center:

-   Internetinformationsdienste (IIS)

-   MongoDB

-   ATA-Center- und ATA-Konsole IIS-Website

-   Benutzerdefinierten Systemmonitor Datensammlungssatz

-   Selbstsignierte Zertifikate (falls während der Installation ausgewählt)

> [!NOTE]
> Zur Problembehandlung und Produkt-Erweiterung zu erleichtern, wird empfohlen, dass Sie MongoVue und alle anderen MongoDB-add-in oder jedem anderen Drittanbieter-Tool Ihrer Wahl installieren. MongoVue erfordert .net Framework 3.5 installiert sein.

## <a name="ATAconsole"></a>ATA-Konsole
Zugriff auf die ATA-Konsole erfolgt über einen Browser. Die folgenden Browser werden unterstützt:

-   Internet Explorer Version 10 und höher

-   Google Chrome 40 und höher

-   Breite mindestbildschirmauflösung von 1700 Pixel

## <a name="ATAgateway"></a>ATA-Gateway

### Betriebssystem
Die ATA-Gateway unterstützt die Installation auf einem Server mit Windows Server 2012 R2.

Führen Sie Windows Update, und stellen Sie sicher, dass alle **Wichtig** Updates installiert wurden. Vor der Installation von ATA-Gateways zu bestätigen, dass das folgende Update installiert wurde: [KB2919355](https://support.microsoft.com/en-us/kb/2919355/).

Führen Sie das folgende PowerShell-Cmdlet, um festzustellen, ob der Hotfix installiert ist, `[Get-HotFix -Id kb2919355]`.

> [!NOTE]
> -   Die ATA-Gateway kann auf einem Server installiert werden, die Mitglied einer Domäne oder Arbeitsgruppe ist.
> -   Die ATA-Gateway kann nicht werden auf einem Domänencontroller installiert.

### Energieoptionen
Legen Sie für eine optimale Leistung der **Power-Option** des ATA-Gateways zu **hohe Leistung**.

### Synchronisierung
Der ATA-Center-Server und dem ATA-Gatewayserver benötigen Zeit innerhalb von 5 Minuten mit synchronisiert.

### Hardwareanforderungen:
Ein Gateway ATA unterstützen mehrere Domänencontroller, abhängig von der Menge des Netzwerkverkehrs zu und von den Domänencontrollern überwachen.

**Mindestanforderungen:**

-   CPU - Kerne 4

-   Speicher – 8 GB

-   Speicher – genug für die OS + 10GB für ATA / Crash dumps = mindestens 100 GB

Weitere Informationen finden Sie unter [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md).

### Netzwerk

#### Netzwerkadapter:
Die ATA-Gateway erfordert mindestens zwei Netzwerkadapter.

-   **Verwaltungsadapter** – für die Kommunikation im Unternehmensnetzwerk verwendet werden. Dieser Adapter sollten wie folgt konfiguriert werden:

    -   Statische IP-Adresse, einschließlich des Standard-gateway

    -   Bevorzugte und alternative DNS-Server

    -   Die **DNS-Suffix für diese Verbindung** sollten der DNS-Namen der Domäne für jede Domäne, die überwacht werden.

        > [!NOTE]
        > Wenn das ATA-Gateway ein Mitglied der Domäne ist, wird dies automatisch konfiguriert.
        > 
        > ![](../Image/ATA%20DNS%20Suffix.png)

-   **-Capture-Adapter** – wird verwendet, um den Datenverkehr zu und von den Domänencontrollern zu erfassen.

    > [!IMPORTANT]
    > -   Konfigurieren Sie die Port-Spiegelung für die Capture-Adapter als Ziel des Netzwerkverkehrs Domain Controller. Finden Sie unter [Konfigurieren Sie die Port-Spiegelung](../../ems/ATA_Content/Configure-Port-Mirroring.md)  Weitere Informationen. In der Regel müssen Sie mit der Netzwerk- oder Virtualization Team Port-mirroring konfigurieren.
    > -   Konfigurieren Sie eine statische nicht routbare IP-Adresse für Ihre Umgebung ohne Standardgateway und keine DNS-Serveradressen. Beispielsweise 1.1.1.1/32. Dadurch wird sichergestellt, dass der Capture-Netzwerkadapter die maximale Menge an Datenverkehr erfassen kann und der Management-Netzwerkadapter zum Senden und Empfangen von den erforderlichen Netzwerkdatenverkehr verwendet wird.

#### Ports:
Die folgende Tabelle enthält die Mindestanforderungen des ATA-Gateways benötigten Ports auf dem Managementadapter konfiguriert.

|Protokoll|Transport|Port|In|Richtung|
|-------------|-------------|--------|------|------------|
|LDAP|TCP und UDP|389|Domänencontroller|Ausgehende|
|Sicheres LDAP (LDAPS)|TCP|636|Domänencontroller|Ausgehende|
|LDAP für globalen Katalog|TCP|3268|Domänencontroller|Ausgehende|
|LDAPS zum globalen Katalog|TCP|3269|Domänencontroller|Ausgehende|
|Kerberos|TCP und UDP|88|Domänencontroller|Ausgehende|
|Netlogon|TCP und UDP|445|Domänencontroller|Ausgehende|
|Windows-Zeitdienst|UDP|123|Domänencontroller|Ausgehende|
|DNS|TCP und UDP|53|DNS-Server|Ausgehende|
|NTLM über RPC|TCP|135|Alle Geräte im Netzwerk|Ausgehende|
|NetBIOS|UDP|137|Alle Geräte im Netzwerk|Ausgehende|
|SSL|TCP|443 oder so konfiguriert ist, für das Sicherheitscenter|ATA-Center:<br /><br />-   Center-Dienst-IP-Adresse<br />-   IIS-IP-Adresse|Ausgehende|
|Syslog (optional)|UDP|514|SIEM-Server|Eingehende|
> [!NOTE]
> Im Rahmen der Lösung erreicht, indem die ATA-Gateway müssen die folgenden Ports öffnen auf eingehende Geräte im Netzwerk aus den ATA-Gateways sein.
> 
> -   NTLM über RPC
> -   NetBIOS

### Virtualisierung:
Informationen zur Verwendung von virtuellen Maschinen mit ATA-Gateways finden Sie unter [Konfigurieren Sie die Port-Spiegelung](../../ems/ATA_Content/Configure-Port-Mirroring.md).

> [!NOTE]
> Wenn das Ausführen des ATA-Gateways als virtuellen Computer Herunterfahren des Servers vor dem Erstellen eines neuen Prüfpunkts um eine mögliche Beschädigung der Datenbank zu vermeiden.

### Zertifikate:
Um die Installation des ATA-Center zu vereinfachen, können Sie während der Installation des Mittelpunkts ATA selbstsignierte Zertifikate installieren. Nach der Bereitstellung, die Sie mit einem Zertifikat von einer internen Zertifizierungsstelle von ATA-Gateway zu verwendende selbstsignierte ersetzen können.

> [!NOTE]
> Selbstsignierte Zertifikate sollten nur für die Lab-Bereitstellung verwendet werden.

Zertifikat unterstützenden **Server-Authentifizierung** muss installiert werden im Computerspeicher des ATA-Gateways in den Speicher des lokalen Computers. Dieses Zertifikat muss von der Mitte ATA vertrauenswürdig sein.

### Während des Setups installierte Komponenten
Die folgenden Komponenten installiert und konfiguriert während der Installation des ATA-Gateways:

-   KB 3047154

    > [!IMPORTANT]
    > -   KB-3047154 darf nicht auf einem Virtualisierungshost installiert werden. Dadurch kann Port Spiegelung nicht mehr ordnungsgemäß funktioniert.
    > -   Installieren Sie Message Analyzer, Wireshark oder andere Netzwerksoftware für die Erfassung nicht auf das ATA-Gateway. Wenn Sie Netzwerkverkehr erfasst werden müssen, installieren und Verwenden von Microsoft Network Monitor 3.4.

-   ATA-Gatewaydienst

-   Microsoft Visual C++ 2013 Redistributable

-   Benutzerdefinierten Systemmonitor Datensammlungssatz

## Siehe auch
[ATA-Architektur](../../ems/ATA_Content/ATA-Architecture.md)
 [ATA-Installation](../../ems/ATA_Content/ATA-Installation.md)
 [Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)

