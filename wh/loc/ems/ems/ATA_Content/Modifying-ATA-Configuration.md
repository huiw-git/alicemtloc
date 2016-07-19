---
title: ATA-Konfiguration &#228;ndern
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
ms.assetid: bcf0f7d3-8027-45c0-8002-19f71fcb30a6
---
# ATA-Konfiguration &#228;ndern
Wenn Sie Ihre Konfiguration nach der ersten Installation und Bereitstellung von ATA aktualisieren müssen, verwenden Sie in diesem Thema als Leitfaden.


## Ändern die Konfiguration des ATA-Center

Nach der ersten Bereitstellung sollte an das Rechenzentrum ATA sorgfältig geändert werden. Gehen Sie folgendermaßen vor, wenn die IP-Adresse und Anschluss oder das Zertifikat zu aktualisieren.


### Ändern die IP-Adresse vom ATA-Center-Server verwendet wird

Wenn Sie die ATA-Center IP-Adresse und Anschluss oder Zertifikat ändern müssen, nehmen Sie Folgendes in Erwägung.

Die ATA-Gateways lokal speichern die IP-Adresse des ATA-Center an die sie eine Verbindung herstellen müssen. In regelmäßigen Abständen sie Herstellen einer Verbindung mit dem ATA-Center und Dropdown-Konfiguration geändert wird. Eine Änderung für die Verbindung wie die ATA-Gateways im ATA-Center ist geschehen zwei Phasen.


- Erste Phase – Aktualisierung der IP-Adresse und den Port an, dass die ATA-Center-Dienst der ATA-Center-Dienst verwendet werden soll. An diesem Punkt im ATA-Center weiterhin die ursprüngliche IP-Adresse überwacht, und der ATA-Gateway synchronisiert seine Konfiguration wird beim nächsten hat zwei IP-Adressen für die ATA-Center. Solange das ATA-Gateway herstellen können, die ursprüngliche (erste) IP-Adresse wird nicht die neue IP-Adresse und Port versucht.

- Stufe – nachdem die ATA-Gateways mit der aktualisierten Konfiguration synchronisiert haben, aktivieren Sie die neue IP-Adresse und den Port, der die ATA-Center überwacht. Beim Aktivieren der neuen IP-Adresse wird das ATA-Sicherheitscenter an die neue IP-Adresse gebunden. ATA-Gateways werden nicht mit der ursprünglichen Adresse verbinden und nun die Verbindung mit der zweiten (neu) IP-Adresse für die ATA-Center versucht. Nach dem Herstellen einer Verbindung mit dem ATA-Center mit der neuen IP-Adresse des ATA-Gateways wird die aktuelle Konfiguration ermöglichte und müssen eine einzelne IP-Adresse für die ATA-Center. (Es sei denn, Sie den Prozess erneut gestartet.)

> [! HINWEIS:]
> - Wenn ein ATA-Gateway offline, während der ersten Phase war und die aktualisierte Konfiguration nicht erhalten zu haben, müssen Sie die JSON-Konfigurationsdatei auf dem Gateway ATA manuell aktualisieren.
> - Wenn die neue IP-Adresse auf dem ATA-Center-Server installiert ist, können Sie es aus der Liste der IP-Adressen auswählen, wenn die Änderung vornehmen. Wenn aus irgendeinem Grund die IP-Adresse auf dem ATA-Center-Server installieren können können Sie jedoch benutzerdefinierte IP-Adresse auswählen und manuell hinzufügen. Sie werden nicht in der Lage, die neue IP-Adresse zu aktivieren, bis die IP-Adresse auf dem Server installiert ist.
> - Wenn Sie ein neues ATA-Gateway nach der Aktivierung der neuen IP-Adresse bereitstellen müssen, müssen Sie das ATA-Gateway-Setup-Paket erneut herunterladen.


1. Öffnen Sie die ATA-Konsole.

2. Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](/Image/ATA+config+icon.JPG)

3. Wählen Sie **ATA-Center**.

4. Klicken Sie unter **ATA-Center-Dienst-IP-Adresse: Port**, wählen Sie eine vorhandene IP-Adressen, oder wählen Sie **Hinzufügen von benutzerdefinierten IP-Adresse** und geben Sie eine IP-Adresse.

5. Klicken Sie auf **Speichern**.

6. Sehen Sie eine Benachrichtigung über wie viele ATA-Gateways synchronisiert wurden, um die aktuelle Konfiguration.

    ![](/Image/ATA+chge+IP+after+clicking+save.png)

7. Nachdem die ATA-Gateways synchronisiert haben, klicken Sie auf **aktivieren** um die neue IP-Adresse zu aktivieren.

    > [! HINWEIS:]
    > Wenn Sie eine benutzerdefinierte IP-Adresse eingegeben haben, werden Sie nicht klicken Sie auf **aktivieren** bis Sie die IP-Adresse im ATA-Center installiert.

8. Stellen Sie sicher, dass die ATA-Gateways können ihre Konfigurationen zu synchronisieren, nachdem die Änderung aktiviert wurde. Die Benachrichtigung Leiste anzugeben wie viele ATA-Gateways erfolgreich synchronisiert ihre Konfiguration.


### Ändern des Zertifikats ATA-Center

Wenn Ihre Zertifikate ablaufen und erneuert oder nach der Installation des neuen Zertifikats in den lokalen Computerspeicher auf dem Server ATA-Center ersetzt werden müssen, ersetzen Sie das Zertifikat anhand dieser zwei Schritten:


- Erste Phase – Update des Zertifikats der ATA-Center-Dienst verwendet werden soll. An diesem Punkt ist das ATA-Sicherheitscenter weiterhin an das ursprüngliche Zertifikat gebunden. Wenn die ATA-Gateways ihre Konfiguration synchronisiert haben sie zwei mögliche Zertifikate, die für die gegenseitige Authentifizierung gültig sein soll. Solange das ATA-Gateway herstellen können, verwenden das ursprüngliche Zertifikat wird die neue Datenbank nicht versucht.

- In der zweiten Phase – nachdem die ATA-Gateways mit der aktualisierten Konfiguration synchronisiert können Sie aktivieren "das neue Zertifikat, dem das ATA-Sicherheitscenter gebunden ist. Bei der Aktivierung des neuen Zertifikats wird das ATA-Sicherheitscenter auf das Zertifikat gebunden. ATA-Gateways werden nicht die ATA-Center-Verwaltungsdienst ordnungsgemäß gegenseitig authentifizieren und versucht, das zweite Zertifikat zu authentifizieren. Nachdem Sie eine Verbindung mit dem Dienst ATA-Center, ATA-Gateway wird die aktuelle Konfiguration ermöglichte und müssen ein einzelnes Zertifikat für die ATA-Center. (Es sei denn, Sie den Prozess erneut gestartet.)

> [! HINWEIS:]
> - Wenn ein ATA-Gateway offline, während der ersten Phase war und die aktualisierte Konfiguration nicht erhalten zu haben, müssen Sie die JSON-Konfigurationsdatei auf dem Gateway ATA manuell aktualisieren.
> - Das Zertifikat, das Sie verwenden muss die ATA-Gateways vertrauenswürdig sein.
> - Wenn Sie ein neues ATA-Gateway nach der Aktivierung des neuen Zertifikats bereitstellen müssen, müssen Sie das ATA-Gateway-Setup-Paket erneut herunterladen.


1. Öffnen Sie die ATA-Konsole.

2. Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](/Image/ATA+config+icon.JPG)

3. Wählen Sie **ATA-Center**.

4. Klicken Sie unter **Zertifikat**, wählen Sie eines der Zertifikate in der Liste.

5. Klicken Sie auf **Speichern**.

6. Sie erhalten eine Benachrichtigung über wie viele ATA-Gateways, die synchronisiert werden, um die aktuelle Konfiguration.

7. Nachdem alle ATA-Gateways synchronisiert wurden, klicken Sie auf **aktivieren** aktivieren Sie das neue Zertifikat.

8. Stellen Sie sicher, dass die ATA-Gateways können ihre Konfigurationen zu synchronisieren, nachdem die Änderung aktiviert wurde.


### Ändern die ATA-Konsole IP-Adresse

Standardmäßig ist die URL des ATA-Konsole die IP-Adresse für die ATA-Konsole IP-Adresse ausgewählt werden, bei der Installation der ATA-Center.

Die URL wird in den folgenden Szenarien verwendet:


- Installation des ATA-Gateways – Wenn ein ATA-Gateway installiert ist, registriert er sich selbst mit dem ATA-Center. Dieses Registrierungsprozesses wird durch Herstellen einer Verbindung mit der Konsole ATA erreicht. Wenn Sie einen FQDN für die ATA-Webkonsolen-URL eingeben, müssen Sie sicherstellen, dass die ATA-Gateway den FQDN der IP-Adresse auflösen kann, dass die ATA-Konsole auf einem IIS gebunden ist. Darüber hinaus wird die URL verwendet, die Verknüpfung in der ATA-Konsole auf den ATA-Gateways zu erstellen.

- Warnungen – Wenn ATA ein SIEM oder per e-Mail sendet eine Warnung ausgegeben, es einen Link zu der verdächtige Aktivitäten enthält. Der Hostteil des Links ist die ATA-Webkonsolen-URL-Einstellung.

- Wenn Sie ein Zertifikat von Ihrer internen Zertifizierungsstelle (CA) installiert haben, möchten Sie wahrscheinlich die URL der Antragstellername im Zertifikat übereinstimmen, damit der Benutzer eine Warnung nicht erhalten, bei der Herstellung der ATA-Konsole.

- Mit einem FQDN für die URL des ATA-Konsole können Sie so ändern Sie die IP-Adresse, mit der von IIS für die ATA-Konsole ohne wichtige Warnungen, die in der Vergangenheit gesendet wurden oder müssen erneut herunterladen des Pakets ATA-Gateway. Sie müssen nur das DNS mit der neuen IP-Adresse zu aktualisieren.

> [! HINWEIS:]
> Nach dem Ändern der ATA-Webkonsolen-URL, sollten Sie das ATA-Gateway-Setup-Paket herunterladen, vor der Installation von neuen ATA-Gateways.

Ändern Sie die IP-Adresse, die von IIS für die ATA-Konsole verwendet werden sollen, gehen Sie auf dem Server ATA-Center.


1. Installieren Sie die IP-Adresse auf dem Server ATA-Center.

2. Öffnen Sie das Dialogfeld „Internetinformationsdienste-Manager“.

3. Erweitern Sie den Namen des Servers und **Sites**.

4. Wählen Sie die Website Microsoft ATA-Konsole und in die **Aktionen** auf **Bindungen**.

    ![](/Image/ATA+console+change+IP+bindings.jpg)

5. Wählen Sie **HTTP** und klicken Sie auf **Bearbeiten** die neue IP-Adresse aus. Gehen Sie genauso für **HTTPS** die IP-Adresse auswählen.

    ![](/Image/ATA+change+console+IP.jpg)

6. In der **Aktion** auf **Starten** unter **Website verwalten**.

7. Öffnen Sie eine Administratorbefehlszeile, und geben Sie die folgenden Befehle zum Aktualisieren von HTTP. SYS-Treiber:
    
    - Hinzufügen die neue IP-Adresse - **Netsh http hinzufügen Iplisten Ipaddress = Newipaddress**

    - Um festzustellen, ob die neue Adresse verwendet wird - **Netsh http Show Iplisten**

    - So löschen Sie die alte IP-Adresse – **Netsh http delete Iplisten Ipaddress = Oldipaddress**

8. Wenn ATA-Webkonsolen-URL nach wie vor eine IP-Adresse verwendet, ATA-Webkonsolen-URL der neuen IP-Adresse zu aktualisieren, und der ATA-Gateway-Setup-Paket vor dem Bereitstellen der neuen ATA-Gateways.

9. Wenn ATA-Webkonsolen-URL einen FQDN handelt, aktualisieren Sie DNS mit der neuen IP-Adresse für den FQDN.


## Ändern das IIS-Zertifikat

In der Konsole können Sie auswählen, und ändern Sie das Zertifikat für den Dienst ATA-Center, aber das von IIS verwendete Zertifikat kann nicht geändert werden.

Wenn Sie ändern möchten, verwenden Sie das folgende Verfahren:

> [! HINWEIS:]
> Nach dem Ändern des IIS-Zertifikats sollten Sie das ATA-Gateway-Setup-Paket herunterladen, vor der Installation von neuen ATA-Gateways.

Wenn Sie das Zertifikat, das von IIS für die ATA-Center verwendeten ändern müssen, folgendermaßen Sie vom Server ATA-Center.


1. Installieren Sie das neue Zertifikat auf dem Server ATA-Center.

2. Öffnen Sie das Dialogfeld „Internetinformationsdienste-Manager“.

3. Erweitern Sie den Namen des Servers und **Sites**.

4. Wählen Sie die Website Microsoft ATA-Konsole und in die **Aktionen** auf **Bindungen**.

    ![](/Image/ATA+console+change+IP+bindings.jpg)

5. Wählen Sie **HTTPS** und klicken Sie auf **Bearbeiten**.

6. Klicken Sie unter **SSL-Zertifikat**, wählen Sie das neue Zertifikat.

7. Herunterladen Sie das ATA-Gateway-Setup-Paket vor der Installation eines neuen ATA-Gateways.


## Ändern das Domänenkennwort-Konnektivität

Wenn Sie das Domänenkennwort für die Konnektivität ändern, stellen Sie sicher, dass das eingegebene Kennwort korrekt ist. Ist dies nicht, wird der ATA-Dienst beendet, die auf die ATA-Gateways ausgeführt.

Wenn Sie vermuten, dass dies, auf dem Gateway ATA geschehen betrachten Sie die Datei "Microsoft.Tri.Gateway-c:\tests" für die folgenden:
**Die angegebene Anmeldeinformationen ist ungültig.**

Um dies zu beheben, gehen Sie zum Aktualisieren des Kennworts Verbindung zur Domäne auf der ATA-Gateway:


1. Öffnen Sie die ATA-Konsole auf dem ATA-Gateway.

2. Wählen Sie die Einstellungsoption "auf der Symbolleiste, und wählen Sie **Konfiguration**.

    ![](/Image/ATA+config+icon.JPG)

3. Wählen Sie **ATA-Gateway**.

    ![](/Image/ATA+GW+change+DC+password.JPG)

4. Klicken Sie unter **Domäne Konnektivitätseinstellungen**, das Kennwort zu ändern.

5. Klicken Sie auf **Speichern**.

6. Nach dem Ändern des Kennworts, manuell überprüfen Sie, ob der ATA-Dienst auf den ATA-Gateway-Servern ausgeführt wird.


## Siehe auch

[Arbeiten mit der ATA-Konsole](/Topic/Working+with+the+ATA+Console.md)
[ATA-Installation](/Topic/ATA+Installation.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





