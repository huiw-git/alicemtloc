---
title: Planen der ATA-Kapazit&#228;t
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
ms.assetid: 279d79f2-962c-4c6f-9702-29744a5d50e2
---
# Planen der ATA-Kapazit&#228;t
In diesem Thema können Sie ermitteln, wie viele ATA-Server benötigt werden, um Ihr Netzwerk zu unterstützen.


## ATA-Center-Größe

Die ATA-Center erfordert eine empfohlene Mindestwert von 30 Tagen von Daten für Benutzer Verhaltensunterschiede Analysen. Der erforderliche Speicherplatz für die ATA-Datenbank auf einer pro Domänencontroller Basis unten definiert ist. Wenn Sie mehrere Domänencontroller haben, Summe der benötigten Speicherplatz pro Domänencontroller berechnet die gesamte Menge an Speicherplatz, die für die ATA-Datenbank erforderlich.



| Pakete pro Sekunde & #42;<br /><br />| CPU (Kerne & #42; #42;)<br /><br />| Speicher (GB)<br /><br />| Betriebssystem-Speicher (GB)<br /><br />| Datenbankspeicher pro Tag (GB)<br /><br />| Datenbankspeicher pro Monat (GB)<br /><br />|
|---------------------------|-------------------------|---------------|-------------------|---------------------------------|-----------------------------------|
| 1,000<br /><br />| 4<br /><br />| 48<br /><br />| 200<br /><br />| 1.5<br /><br />| 45<br /><br />|
| 10,000<br /><br />| 4<br /><br />| 48<br /><br />| 200<br /><br />| 15<br /><br />| 450<br /><br />|
| 40,000<br /><br />| 8<br /><br />| 64<br /><br />| 200<br /><br />| 60<br /><br />| 1,800<br /><br />|
| 100,000<br /><br />| 12<br /><br />| 96<br /><br />| 200<br /><br />| 150<br /><br />| 4,500<br /><br />|
| 200,000<br /><br />| 16<br /><br />| 128<br /><br />| 200<br /><br />| 300<br /><br />| 9,000<br /><br />|
& #42; Tägliche durchschnittliche Gesamtanzahl der Pakete pro Sekunde von allen Domänencontrollern, die durch alle ATA-Gateways überwacht wird.

& #42; & #42; Dies schließt physische Kernen, nicht mit Hyperthreading Kerne.

> [! HINWEIS:]
> - Die ATA-Center kann eine aggregierte bis zu 200.000 Bilder pro Sekunde (FPS) aller überwachten Domänencontroller behandeln.
> - Für große Bereitstellungen (beginnend bei ca. 100.000 Pakete pro Sekunde) erforderlich ist, dass die Erfassung der Datenbank die Datenbank auf einem anderen Datenträger gespeichert werden.
> - Die Menge an Speicher vorgegeben sind hier net Werte, Sie sollten immer ein künftiges Wachstum berücksichtigen und um sicherzustellen, dass die Datenbank auf dem Datenträger befindet sich wurde mindestens 20 % freier Speicherplatz.
> - Wenn der freie Speicherplatz mindestens entweder 20 % erreicht oder 100 GB und die ältesten 24 Stunden an Daten werden gelöscht. Dies weiterhin auftreten, bis nur zwei Tage Daten oder entweder 5 % oder 50 GB freien Speicherplatz bleibt bei der Datensammlung wird angehalten.


## ATA-Gateway-Größe

Ein ATA-Gateway können Unterstützung für die Überwachung von mehreren Domänencontrollern, abhängig von der Menge des Netzwerkverkehrs der überwachten Domänencontroller.



| Pakete pro Sekunde & #42;<br /><br />| CPU (Kerne & #42; #42;)<br /><br />| Speicher (GB)<br /><br />| Betriebssystem-Speicher (GB)<br /><br />|
|---------------------------|-------------------------|---------------|-------------------|
| 10,000<br /><br />| 4<br /><br />| 12<br /><br />| 80<br /><br />|
| 20,000<br /><br />| 8<br /><br />| 24<br /><br />| 100<br /><br />|
| 40,000<br /><br />| 16<br /><br />| 64<br /><br />| 200<br /><br />|
& #42; Die Gesamtzahl der Pakete pro Sekunde von allen Domänencontrollern, die vom bestimmten ATA-Gateway überwacht wird.

& #42; Die Größe des gesamten Datenverkehr auf Domänencontroller Port gespiegelten darf die Kapazität der Erfassung NIC auf dem ATA-Gateway nicht überschreiten.

& #42; & #42; Hyper-threading muss deaktiviert werden.


## Schätzung der Domain Controller-Datenverkehr

Es gibt verschiedene Tools, die Sie verwenden können, um die durchschnittliche Pakete pro Sekunde der Domänencontroller zu ermitteln. Wenn Sie keine Tools, mit die dieser Leistungsindikator verfolgt verfügen, können Systemmonitor Sie um die erforderliche Informationen zu sammeln.

Um Pakete pro Sekunde zu ermitteln, führen Sie die folgenden auf jedem Domänencontroller:


1. Öffnen Sie den Systemmonitor.

    ![](/Image/ATA+traffic+estimation+1.png)

2. Erweitern Sie **Data Collector Sets**.

    ![](/Image/ATA+traffic+estimation+2.png)

3. Klicken Sie mit der rechten Maustaste auf **benutzerdefinierte** und wählen Sie **Neu** & Gt; **Sammlungssatz**.

    ![](/Image/ATA+traffic+estimation+3.png)

4. Geben Sie einen Namen für die Sammlung ein, und wählen Sie **manuell (Erweitert) erstellen**.

5. Unter **welche Art von Daten sollen?**, auf  **Daten Protokolle und Leistungsindikator erstellen**.

    ![](/Image/ATA+traffic+estimation+5.png)

6. Klicken Sie unter **welche Leistungsindikatoren möchten Sie protokollieren** klicken Sie auf **Hinzufügen**.

7. Erweitern Sie **Netzwerkadapter** und wählen Sie **Pakete/Sek.** und wählen Sie die richtige Instanz. Wenn Sie nicht sicher sind, können Sie auswählen, dass **& Lt; Alle Instanzen & Gt;** und klicken Sie auf **Hinzufügen** und **OK**.

    > [! HINWEIS:]
    > Klicken Sie dazu in einer Befehlszeile ausführen **Ipconfig/all** um den Namen des Adapters und der Konfiguration anzuzeigen.

    ![](/Image/ATA+traffic+estimation+7.png)

8. Ändern der **Abtastintervalls** auf **1 Sekunde**.

9. Legen Sie den Speicherort, in dem die Daten gespeichert werden sollen.

10. Unter **erstellen die Datensammlergruppe** auswählen **diesen Sammlungssatz jetzt starten** und klicken Sie auf **Fertig stellen**.

    Jetzt sollte der Sammlungssatz Sie gerade erstellt haben, mit einem grünen Dreieck gibt an, dass es funktioniert.

11. Beenden Sie nach 24 Stunden von der rechten Maustaste auf den Sammlungssatz und auswählen den Sammlungssatz **Beenden**

    ![](/Image/ATA+traffic+estimation+12.png)

12. Klicken Sie im Datei-Explorer navigieren zu dem Ordner, in dem die .blg-Datei gespeichert wurde, und doppelklicken Sie auf, um im Systemmonitor zu öffnen.

13. Wählen Sie den Leistungsindikator Pakete/s, und notieren Sie die durchschnittlichen und maximalen Werte.

    ![](/Image/ATA+traffic+estimation+14.png)


## Siehe auch

[ATA-Planung und Anforderungen](/Topic/ATA+Planning+and+Requirements.md)
[ATA-Architektur](/Topic/ATA+Architecture.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





