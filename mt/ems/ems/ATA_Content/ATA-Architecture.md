---
title: ATA-Architektur
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
ms.assetid: 892b16d2-58a6-49f9-8693-1e5f69d8299c
translation.priority.mt: 
  - de-de
  - ja-jp
---
# ATA-Architektur
In diesem Diagramm wird die Architektur für erweiterte Threat-Analyse beschrieben:

![](../Image/ATA%20architecture%20topology.jpg)

ATA besteht aus zwei Komponenten - ATA-Gateway und das ATA-Center.

Diese Verbindung zu Ihrem vorhandenen Netzwerk spiegeln den Netzwerkdatenverkehr zu und von den Domänencontrollern und Windows-Ereignisse (weitergeleitet direkt von den Domänencontrollern oder einem Server SIEM) ansehen und Analysieren der Daten für Angriffe und Sicherheitsrisiken.

Dieser Abschnitt beschreibt den Ablauf des Netzwerks erfassen und verarbeiten und einen Drilldown in die Hauptkomponenten des ATA-Gateway und dem ATA-Center und ihrer Funktionalität.

![](../Image/ATA%20traffic%20flow.jpg)

## ATA-Komponenten
ATA umfasst Folgendes:

-   Eine oder mehrere ATA-Gateways

-   Ein ATA-Center

## ATA-Gateway
Die **ATA-Gateway** führt die folgenden Funktionen:

-   Erfasst und überprüft Domain Controller-Netzwerkdatenverkehr über Port Spiegelung

-   Windows-Ereignisse empfängt, SIEM oder Syslog-Server oder Domänencontroller unter Verwendung der Windows-Ereignisweiterleitung

-   Ruft Daten über Benutzer und Computer aus Active Directory-Domäne

-   Führt die Auflösung von Netzwerkidentitäten (Benutzer, Gruppen und Computer)

-   Überträgt die relevante Daten an das Rechenzentrum ATA

-   Überwacht mehrere Domänencontroller über ein einzelnes ATA-Gateway

Die ATA-Gateway empfängt die gespiegelte Netzwerkverkehr und Windows-Ereignisse aus dem Netzwerk und verarbeitet sie in den folgenden Komponenten:

|||
|-|-|
|Netzwerk-Listener|Der Netzwerk-Listener ist verantwortlich für den Netzwerkdatenverkehr zu erfassen und Analysieren des Datenverkehrs. Dieser Task ist ein CPU, hoch, daher ist es besonders wichtig, überprüfen Sie [ATA-Planung und Anforderungen](../../ems/ATA_Content/ATA-Planning-and-Requirements.md) bei der Planung Ihrer ATA-Gateway.|
|Ereignis-Listener|Der Ereignis-Listener ist verantwortlich für das Erfassen und Analysieren von Windows-Ereignisse, die von einem SIEM-Server in Ihrem Netzwerk weitergeleitet.|
|Reader für Windows-Ereignisprotokoll|Windows Event Log Reader ist verantwortlich für das Lesen und Analysieren von Windows-Ereignisse, die in den ATA-Gateway Windows-Ereignisprotokoll von Domänencontrollern weitergeleitet.|
|Entitätsresolver|Die Entitätsresolver die analysierten Daten (Netzwerkverkehr und Ereignisse) und löst die Daten mit Active Directory finden Konto-und Identität und die IP-Adressen finden Sie in der analysierten Daten zuordnen.  Darüber hinaus den Entitätsresolver die Paket-Headern effizient untersucht, ermöglicht das Analysieren von Authentifizierungspaketen für Computernamen, Eigenschaften und Identitäten und kombiniert sie mit den Daten im aktuellen Paket haben.|
|Entity-Absender|Absender Entität ist verantwortlich für die analysierten und abgeglichenen Daten an das Rechenzentrum ATA senden.|
Beachten Sie Folgendes bei der Entscheidung, wie viele ATA-Gateways in Ihrem Netzwerk bereitstellen:

-   Active Directory-Gesamtstrukturen und Domänen

    ATA-Gateways kann Datenverkehr aus mehreren Domänen aus einer einzelnen Active Directory-Gesamtstruktur zu überwachen.   Überwachung mehrerer Active Directory-Gesamtstrukturen erfordert separate ATA-Bereitstellungen. ATA-Gateways sollte nicht zum Überwachen des Netzwerkverkehrs von Domänencontrollern in unterschiedlichen Gesamtstrukturen konfiguriert werden.

-   Port-Spiegelung

    Port Spiegelung Aspekte müssen Sie mindestens ein ATA-Gateway pro Active Directory-Standort bereitstellen.

-   Kapazität

    Jedes ATA-Gateway kann analysieren und eine bestimmte Menge an Datenverkehr pro Sekunde senden. Wenn die Domänencontroller, die Sie überwachen senden und Empfangen von mehr Datenverkehr als das ATA-Gateway verarbeiten kann, müssen Sie zusätzliche ATA-Gateways gemäß Ihrer Datenvolumen hinzufügen. Weitere Informationen finden Sie unter [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md).

## ATA-Center
Die **ATA-Center** führt die folgenden Funktionen:

-   Verwaltet die ATA-Gateway-Konfigurationen

-   Empfängt Daten von ATA-Gateways

-   Erkennt die verdächtige Aktivitäten

-   Führt verschiedene Verhaltensunterschiede Machine Learning-Module

-   Führt die ATA-Konsole

-   Optional: Die ATA-Center kann konfiguriert werden zum Senden von e-Mail-Nachrichten und Ereignisse aus, wenn eine verdächtige Aktivitäten erkannt werden.

Die ATA-Center analysierte Datenverkehr vom ATA-Gateway empfängt, führt der Profilerstellungstools, deterministisch Erkennung ausgeführt und maschinelles lernen und erfahren Sie mehr über das Netzwerk aktivieren Sie die Erkennung von Anomalien und warnt vor verdächtigen Aktivitäten Verhaltensunterschiede Algorithmen ausgeführt.

|||
|-|-|
|Entity-Empfänger|Empfängt Daten aus dem ATA-Gateway, und für die Verarbeitung und das Profil verwendet. Diese Daten werden dann in die Datenbank einfügt.|
|Datenbank|ATA nutzt MongoDB Zwecken alle Daten in das System zu speichern:<br /><br />-   Netzwerkaktivität<br />-   Ereignisaktivität<br />-   Eindeutige Entitäten<br />-   Verdächtige Aktivitäten<br />-   ATA-Konfiguration|
|Erkennungsmodule|Die Erkennungsmodule auf den analysierten Datenverkehr ausgeführt und mithilfe von Algorithmen für maschinelles lernen und deterministisch Regeln auf um verdächtige Aktivitäten und Benutzer in Ihrem Netzwerk zu suchen.|
|ATA-Konsole|Sie verwenden die Konsole ATA ATA konfigurieren und überwachen verdächtige Aktivitäten von ATA in Ihrem Netzwerk erkannt. ATA-Konsole ist nicht das ATA-Sicherheitscenter abhängig und wird ausgeführt, auch wenn der Dienst beendet wird, solange er mit der Datenbank kommunizieren kann.|
Beachten Sie Folgendes bei der Entscheidung, wie viele ATA-Ressourcen in Ihrem Netzwerk bereitstellen:

-   Ein ATA-Center kann es sich um eine Active Directory-Gesamtstruktur überwachen. Wenn Sie mehr als eine Active Directory-Gesamtstruktur verfügen, benötigen Sie mindestens ein ATA-Center pro Active Directory-Gesamtstruktur.

    In umfangreichen Active Directory-Bereitstellungen einem Center ATA, behandeln den gesamten Datenverkehr von allen Domänencontrollern möglicherweise nicht. In diesem Fall werden mehrere ATA-Rechenzentren erforderlich und ATA-Erkennung werden weniger effektiv sein. Die Anzahl der ATA-Ressourcen sollten von vorgegeben werden [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md).

## Netzwerkkomponenten
Arbeit mit ATA Sie Ihr vorhandenes Netzwerk nur sehr geringe ändern müssen, jedoch müssen Sie Folgendes sicherstellen.

### Port-Spiegelung
Für ATA arbeiten müssen Sie zum Aktivieren der Port Spiegelung für alle Domänencontroller in der Active Directory-Gesamtstruktur überwacht wird. ATA ist funktionsfähig, wenn einige müssen nicht alle Domänencontroller Port Spiegelung auf ATA aktiviert, sondern Erkennung wird weniger effektiv sein.

Richten Sie Port-mirroring aus Ihrer Domänencontroller zum ATA-Gateway. Während dies alle dann der Domain Controller-Netzwerkverkehr zum ATA-Gateway nur ein sehr kleiner Prozentsatz dieses Datenverkehrs gesendet wird spiegelt, komprimiert der ATA-Center für die Analyse.

Die Domänencontroller und die ATA-Gateways kann physisch oder virtuell, siehe [Konfigurieren Sie die Port-Spiegelung](../../ems/ATA_Content/Configure-Port-Mirroring.md) Weitere Informationen.

### Ereignisse
Zur Erhöhung der ATA-Erkennung von Pass-the-Hash benötigt ATA Windows-Ereignisprotokoll-ID 4776. Dies kann zum ATA-Gateway auf zwei Arten Konfigurieren des Gateways ATA zum Überwachen von Ereignissen SIEM oder mithilfe der Windows-Ereignisweiterleitung weitergeleitet werden.

-   Konfigurieren des Gateways ATA SIEM Ereignisse überwachen

    Konfigurieren Sie Ihre SIEM zum Weiterleiten von bestimmter Windows-Ereignissen auf ATA. ATA unterstützt eine Anzahl von SIEM-Anbietern. Weitere Informationen finden Sie unter [Konfigurieren der Ereignissammlung](../../ems/ATA_Content/Configure-Event-Collection.md).

-   Konfigurieren der Weiterleitung von Windows-Ereignis

    Eine andere Möglichkeit, ATA Ereignisse abrufen kann, ist durch Domänencontroller zu forward Windows-Ereignis 4776 Ihrem ATA-Gateway konfigurieren. Dies ist besonders nützlich, wenn Sie eine SIEM haben oder Ihre SIEM durch ATA derzeit nicht unterstützt wird. Weitere Informationen zu Windows-Ereignis im ATA weiterleiten, finden Sie unter [Configuring Windows Event Forwarding](../../ems/ATA_Content/Configure-Event-Collection.md#ATA_event_WEF).

## Siehe auch
[ATA-Planung und Anforderungen](../../ems/ATA_Content/ATA-Planning-and-Requirements.md)
 [Planen der ATA-Kapazität](../../ems/ATA_Content/ATA-Capacity-Planning.md)
 [Konfigurieren der Ereignissammlung](../../ems/ATA_Content/Configure-Event-Collection.md)
 [Configuring Windows Event Forwarding](../../ems/ATA_Content/Configure-Event-Collection.md#ATA_event_WEF)
 [Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)

