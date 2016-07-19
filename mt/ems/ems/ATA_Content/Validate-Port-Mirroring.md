---
title: &#220;berpr&#252;fen Sie die Port-Spiegelung
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
ms.assetid: ebd41719-c91a-4fdd-bcab-2affa2a2cace
---
# &#220;berpr&#252;fen Sie die Port-Spiegelung
Die folgenden Schritte führen Sie durch den Prozess zum Überprüfen der Spiegelung Port ordnungsgemäß konfiguriert ist.


1. Installieren Sie [Microsoft Network Monitor 3.4](http://www.microsoft.com/download/details.aspx?id=4865) oder ein anderes Netzwerk sniffing Tool.

    > [! WICHTIGE]
    > Installieren Sie Microsoft Message Analyzer oder anderer Datenverkehr Capture Software nicht auf das ATA-Gateway.

2. Öffnen Sie den Netzwerkmonitor, und erstellen Sie eine neue Registerkarte für die Erfassung.
    
    1. Wählen Sie nur die **erfassen** Netzwerkadapter oder der Netzwerkadapter, die mit den Switch-Port verbunden ist, der als Ziel Spiegelung Port konfiguriert ist.

    2. Stellen Sie sicher, dass P-Modus aktiviert ist.

    3. Klicken Sie auf **neue Aufzeichnung**.

        ![](/Image/ATA+Port+Mirroring+Capture.jpg)

3. Geben Sie im Fenster Filter anzeigen, den folgenden Filter: **KerberosV5 oder LDAP** und klicken Sie dann auf **Übernehmen**.

    ![](/Image/ATA+Port+Mirroring+filter+settings.jpg)

4. Klicken Sie auf **Starten** die Capture-Sitzung zu starten. Wenn Datenverkehr zum und vom Domänencontroller nicht angezeigt wird, überprüfen Sie den Anschluss Spiegelungskonfiguration.

    > [! HINWEIS:]
    > Es ist wichtig, um sicherzustellen, dass Sie Datenverkehr zu und von Domänencontrollern finden Sie unter.
    > 
    >     ![](/Image/ATA+Port+Mirroring+Capture+traffic.jpg)
    > 


## Siehe auch

[Konfigurieren Sie die Port-Spiegelung](/Topic/Configure+Port+Mirroring.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





