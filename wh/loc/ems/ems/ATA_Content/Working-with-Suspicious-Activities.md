---
title: Arbeiten mit verd&#228;chtigen Aktivit&#228;ten
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
ms.assetid: 44d7c899-816c-4f7f-91d3-84a09d291a24
---
# Arbeiten mit verd&#228;chtigen Aktivit&#228;ten
Dieses Thema erläutert die Grundlagen der Arbeit mit erweiterten Threat-Analyse.


## Überprüfen Sie verdächtige Aktivitäten auf der Zeitachse Angriff

Nach der Anmeldung an der Konsole ATA automatisch gelangen Sie zu öffnen **verdächtige Aktivitäten Zeitachse**. Verdächtige Aktivitäten werden in der zeitlichen Reihenfolge mit den neuesten verdächtigen Aktivitäten am oberen Rand der zeitliche aufgeführt.
Jede verdächtige Aktivitäten enthält die folgenden Informationen:


- Entitäten, einschließlich Benutzer, Computer, Server, Domänencontroller und Ressourcen.

- Die Uhrzeiten und Zeitrahmen der verdächtigen Aktivitäten.

- Schweregrad der verdächtige Aktivitäten, hoch, Mittel oder niedrig.

- Status: Geöffnet, behoben oder geschlossen.

- Fähigkeit
    
    - Senden Sie verdächtige Aktivitäten an andere Personen in Ihrer Organisation per e-Mail. Dies erfordert einen e-Mail-Client auf dem Computer installiert sein, von dem Sie durchsuchen.

    - Exportieren Sie verdächtige Aktivitäten nach Excel.

    - Fügen Sie eine Anmerkung auf verdächtige Aktivitäten.

    - Mitteilen Sie, verdächtige Aktivitäten.

- Leitfaden für die Reaktion auf verdächtige Aktivitäten.

> [! HINWEIS:]
> - Wenn Sie die Maus auf einen Benutzer oder Computer zeigen, wird eine Entität Mini-Profil angezeigt bietet zusätzliche Informationen über die Entität enthält die Anzahl der verdächtigen Aktivitäten, denen die Entität verknüpft ist.
> - Wenn Sie auf ein Element klicken, dauert es Sie auf das Entity-Profil des Benutzers oder Computers.

![](/Image/ATA+Suspicious+Activity+Timeline.JPG)


## Filtern der Liste der verdächtigen Aktivitäten

So filtern Sie die Liste der verdächtigen Aktivitäten:


1. In der **Filtern, indem Sie** Bereich auf der linken Seite des Bildschirms, wählen Sie eine der folgenden: **alle**, **Öffnen**, **gelöst**, oder **Dismissed**.

2. Um die Liste weiter zu filtern, wählen Sie **hohe**, **Mittel** oder **Niedrig**.

**Verdächtige Aktivitäten Schweregrad**


- **Niedrig**

    Gibt an, verdächtige Aktivitäten, die auf Angriffe, mit denen böswillige Benutzer oder Software für den Zugriff auf Unternehmensdaten führen können.

- **Mittel**

    Gibt an, verdächtige Aktivitäten, die bestimmte Identitäten Risiko für Angriffe schwerwiegendere einfügen können, die Identitätsdiebstahl oder Ausweitung von Berechtigungen führen

- **Hoch**

    Gibt an, verdächtige Aktivitäten, die zu Identitätsdiebstahl, Ausweitung von Berechtigungen oder andere Angriffe wirkungsvolle führen kann

**Verdächtige Aktivitäten-status**


- **Öffnen Sie den**

    Alle neue verdächtige Aktivitäten in dieser Liste angezeigt.

- **Resolved**

    Wird verwendet, um verdächtige Aktivitäten nachzuverfolgen identifiziert, untersucht und behoben für verringert.

    > [! HINWEIS:]
    > ATA kann eine Aktivität aufgelöste erneut öffnen, ist die gleiche Aktivität innerhalb kurzer Zeit wieder erkannt.

- **Geschlossen**

    Aktivitäten, die Sie manuell geschlossen sind. Wenn ATA eine ähnliche verdächtige Aktivitäten erkannt werden neue Erkennung erstellt werden.


## Mitteilen Sie, eine verdächtige Aktivität

Um ATA Informationen zu Ihrem Netzwerk mit Ihnen zu aktivieren, Anforderungstyp einige verdächtigen Aktivitäten (DNS-Erkundung, übergeben Sie das Ticket anormales Verhalten und Remoteausführung) die Eingabe für die Erkennung von verdächtigen Aktivitäten, die für die Zukunft verbessern kann.


1. Auf verdächtige Aktivitäten, die Ihnen ermöglichen, Eingaben vornehmen, wird die Eingabe Frage automatisch geöffnet. Sie werden aufgefordert, das Beantworten von Fragen zu Aktivitäten in Ihrem Netzwerk und davon, ob sie als verdächtig angesehen werden sollte. In dem folgenden Beispiel können Sie werden wird gefragt, ob Scantools Ausführen von einem bestimmten Computer zugelassen wird.

    ![](/Image/ATA+Input.JPG)

2. Wenn Sie mit Nein antworten, diese Aktivität verdächtig betrachtet und jederzeit ATA diese Aktivität auf diesem Computer entdeckt werden Sie benachrichtigt.

3. Jedoch wenn Sie "Ja" beantworten, verdächtige Aktivitäten geschlossen werden kann und zukünftige Aktivitäten dieses Typs von diesem Computer eine verdächtige Aktivität können nicht generiert oder generiert eine Aktivität, die automatisch geschlossen wird.

4. Wenn Sie nicht wissen, können Sie klicken **Abbrechen**.


## Ändern des Status einer verdächtige Aktivitäten

Sie können den Status eine verdächtige Aktivität ändern, indem der aktuelle Status der verdächtige Aktivitäten und einen der folgenden **Öffnen**, **gelöst** oder **Dismissed**.


## Siehe auch

[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)
[Arbeiten mit Einstellungen für ATA-Erkennung](/Topic/Working+with+ATA+Detection+Settings.md)
[ATA-Konfiguration ändern](/Topic/Modifying+ATA+Configuration.md)





