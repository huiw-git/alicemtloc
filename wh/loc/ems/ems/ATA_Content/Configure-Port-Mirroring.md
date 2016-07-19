---
title: Konfigurieren Sie die Port-Spiegelung
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
ms.assetid: cdaddca3-e26e-4137-b553-8ed3f389c460
---
# Konfigurieren Sie die Port-Spiegelung
Die primären Datenquelle verwendet, die für ATA ist deep Packet Inspection des Netzwerkverkehrs zu und von den Domänencontrollern. Für ATA den Netzwerkdatenverkehr zu sehen muss Port Spiegelung konfiguriert werden. Port-mirroring kopiert den Datenverkehr auf einem Port, den Quellport genannt, um einen anderen Port als den Zielport bezeichnet. ATA funktioniert mit den meisten Lösungen, die Datenverkehr - widerspiegeln, können der Datenverkehr Port auf ATA-gespiegelt werden, kann verwendet werden um Gefahren für Ihr System zu analysieren. Port-mirroring konfigurieren, finden Sie in der Dokumentation des Herstellers.

> [! HINWEIS:]
> ATA unterstützt einige Szenarien für die Verwendung von Drittanbietern Network Sichtbarkeit Solutions, z. B. ein Netzwerk TIPPEN.

Der Domänencontroller und ATA-Gateways kann entweder physisch oder virtuell sein. Es folgen einige Aspekte und allgemeine Methoden für die Spiegelung Port. Finden Sie in der Switch oder Virtualization Server-Produktdokumentation für Weitere Informationen. Der switchhersteller möglicherweise unterschiedliche Terminologie zu verwenden.

**Switched Port Analyzer (Zeitraum)** – Kopien Netzwerkdatenverkehr aus einem oder mehreren Switchports zu einem anderen Port auf demselben Switch. Sowohl die ATA-Gateway und Domänencontroller müssen mit demselben physischen Switch verbunden sein.

**Remote Switch Port Analyzer (RSPAN)** – ermöglicht die zum Überwachen des Netzwerkverkehrs von Quelle über mehrere physische Switches verteilt. RSPAN Kopien die Quelle in einer speziellen RSPAN Datenverkehr konfiguriert VLAN. Dieses VLAN muss mit den anderen Beteiligten Switches gebündeltes sein. RSPAN arbeitet auf Layer 2.

**Gekapselt Remote Switch Port Analyzer (ERSPAN)** – ist eine proprietäre Cisco-Technologie in Schicht 3 arbeitet. ERSPAN können Sie den Datenverkehr über Switches, ohne die Notwendigkeit von VLAN-Trunks zu überwachen. ERSPAN verwendet generic routing Encapsulation (GRE) zum überwachten Netzwerkverkehr zu kopieren. ATA kann keine derzeit direkt ERSPAN Datenverkehr empfangen. Für ATA ERSPAN Datenverkehr arbeiten muss einen Switch oder Router, der wie folgt entkapseln des Datenverkehrs können als Ziel für ERSPAN konfiguriert werden, wo der Datenverkehr Kapsel werden sollen. Der Switch oder Router müssen konfiguriert werden, um es dem ATA-Gateway mit SPANNE oder RSPAN weiterzuleiten.

> [! HINWEIS:]
> Stellen Sie der Domänencontroller Port gespiegelt wird über eine WAN-Verbindung verbunden ist, sicher, dass die WAN-Verbindung die zusätzliche Last für den ERSPAN-Datenverkehr verarbeiten kann.


## Unterstützte Spiegelungsoptionen port

| ATA-Gateway<br /><br />| Domänencontroller<br /><br />| Aspekte<br /><br />|
|---------------|---------------------|------------------|
| Virtuelle<br /><br />| Virtuelle auf demselben host<br /><br />| Der virtuelle Switch muss Port Spiegelung unterstützen.<br /><br />Verschieben einen virtuellen Computer auf einen anderen Host selbst kann die Spiegelung Port.<br /><br />|
| Virtuelle<br /><br />| Virtuelle auf verschiedenen hosts<br /><br />| Stellen Sie sicher, dass Ihre virtuelle Switch dieses Szenario unterstützt.<br /><br />|
| Virtuelle<br /><br />| Physische<br /><br />| Erfordert einen dedizierten Netzwerkadapter, den andernfalls ATA angezeigt wird, den gesamten Datenverkehr über des Hosts und sogar den Datenverkehr, die an die ATA-Center.<br /><br />|
| Physische<br /><br />| Virtuelle<br /><br />| Stellen Sie sicher, Ihre virtuelle Switch unterstützt dieses Szenario- und Port Spiegelungskonfiguration Ihrer physischen Switches auf Grundlage dieses Szenarios:<br /><br />ist der virtuelle Host auf demselben physischen Switch, müssen Sie einen Switch konfigurieren Ebene span.<br /><br />Wenn der virtuelle Host auf einem anderen Switch ist, müssen Sie RSPAN oder ERSPAN & #42; konfigurieren.<br /><br />|
| Physische<br /><br />| Physisch auf demselben switch<br /><br />| Physischen Switch muss die Spiegelung SPANNE/Port unterstützen.<br /><br />|
| Physische<br /><br />| Physisch auf einem anderen switch<br /><br />| Erfordert physikalischen Switches zur Unterstützung von RSPAN oder ERSPAN & #42;.<br /><br />|
& #42; ERSPAN wird nur unterstützt, wenn Decapsulation ausgeführt wird, bevor der Datenverkehr von ATA analysiert wird.


## Siehe auch

[Überprüfen Sie die Port-Spiegelung](/Topic/Validate+Port+Mirroring.md)
[ATA-Installation](/Topic/ATA+Installation.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





