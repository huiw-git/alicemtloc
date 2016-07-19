---
title: Konfigurieren der Ereignissammlung
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
ms.assetid: 3f0498f9-061d-40e6-ae07-98b8dcad9b20
---
# Konfigurieren der Ereignissammlung
Zur Erhöhung der ATA-Erkennung von Pass-the-Hash benötigt ATA Windows-Ereignisprotokoll-ID 4776. Dies kann durch Konfigurieren des Gateways ATA SIEM Ereignisse oder durch Lauschen an das Gateway ATA auf zwei Arten weitergeleitet werden [Konfigurieren von Windows-Ereignisweiterleitung](#ATA_event_WEF).


## Konfigurieren des Gateways ATA SIEM Ereignisse überwachen

1. Aktivieren Sie auf der ATA-Gateway-Konfiguration **Syslog-Listener UDP**.

    Legen Sie die Überwachung IP-Adresse, wie in der Abbildung unten beschrieben. Der Standardport ist 514.

    ![](/Image/ATA+enable+siem+forward+events.png)

2. Konfigurieren des Servers SIEM oder Syslog zum Weiterleiten von Windows-Ereignis-ID 4776 an der oben ausgewählten IP-Adresse. Weitere Informationen zum Konfigurieren Ihrer SIEM finden Sie in Ihrer SIEM-Onlinehilfe oder technischen Support-Optionen für die Formatierung Vorgaben für jeden SIEM-Server.


### SIEM-Unterstützung

ATA werden SIEM-Ereignisse in den folgenden Formaten unterstützt:


#### RSA Security-Analysen

& Lt; Syslog-Header & Gt; RsaSA\n2015 als 19. Mai 09:07:09\n4776\nMicrosoft-Windows-Security-Auditing\nSecurity\XXXXX.subDomain.domain.org.il\nYYYYY$\nMMMMM \n0x0


- Syslog-Header ist optional.

- Es ist "\n" Zeichen als Trennzeichen zwischen alle Felder erforderlich.

- Die Felder in der Reihenfolge, sind:
    
    1. RsaSA-Konstante (muss angezeigt werden).

    2. Der Zeitstempel des tatsächlichen (Stellen Sie sicher, dass es ist nicht der Zeitstempel für den Eingang der SIEM oder wenn es auf ATA gesendet wird). In Millisekunden-Genauigkeit ist dies vorzugsweise sehr wichtig.

    3. Die Windows-Ereignis-ID

    4. Der Anbietername für Windows-Ereignis

    5. Der Name des Windows-Ereignisprotokolls

    6. Der Name des Computers des Ereignisses (in diesem Fall den DC)

    7. Der Name des zu authentifizierenden Benutzers

    8. Der Name des Hostnamens Quelle

    9. Der Ergebniscode des NTLM-

- Die Reihenfolge ist wichtig, und nichts anderes in der Nachricht eingeschlossen werden soll.


#### HP Arcsight

CEF:0| Microsoft| Microsoft-Windows|| Microsoft-Windows-Security-Überwachung: 4776| Der Domänencontroller, die zur Überprüfung der Anmeldeinformationen für ein Konto versucht. | Niedrig|} ExternalId = 4776 Cat Sicherheit rt = = 1426218619000 Shost = KKKKKK dhost=YYYYYY.subDomain.domain.com Duser = XXXXXX cs2 = Security cs3 = Microsoft-Windows-Security-Überwachung cs4 = 0 x 0-cs3Label = EventSource cs4Label Grund oder Fehlercode =


- Die Protokolldefinition entsprechen muss.

- Keine Syslog-Header.

- Der Headerteil (der Teil, der durch einen senkrechten Strich getrennt ist) muss vorhanden sein (wie im Protokoll angegeben ist).

- Die folgenden Schlüssel in der _Erweiterung_ Teil in das Ereignis vorhanden sein:
    
    - ExternalId = Windows-Ereignis-ID

    - RT = den Zeitstempel des tatsächlichen (Stellen Sie sicher, dass es ist nicht der Zeitstempel für den Eingang der SIEM oder wenn es an uns gesendet wird). In Millisekunden-Genauigkeit ist dies vorzugsweise sehr wichtig.

    - CAT = der Name des Windows-Ereignisprotokolls

    - Shost = der Hostname

    - Dhost = den Computer mit dem Empfang des Ereignisses (in diesem Fall den DC)

    - DUser = der Benutzerauthentifizierung

- Die Reihenfolge spielt keine Rolle, für die _Erweiterung_ Teil

- Ein benutzerdefinierter Product Key und KeyLable für diese zwei Felder müssen vorhanden sein:
    
    - "EventSource"

    - "Grund oder Fehlercode" den Ergebniscode des NTLM-=


#### Splunk

& Lt; Syslog-Kopf- und gt;\r\nEventCode=4776\r\nLogfile=Security\r\nSourceName=Microsoft-Windows-Security-Auditing\r\nTimeGenerated=20150310132717.784882-000\r\ComputerName=YYYYY\r\nMessage=

Der Computer versucht, die Anmeldeinformationen für ein Konto zu überprüfen.

Authentifizierungspaket: MICROSOFT_Authentifizierung_Paket_V1_0

Anmeldekonto: Administrator

Quelle der Arbeitsstation: SIEM

Fehlercode: 0 x 0


- Syslog-Header ist optional.

- Es ist eine "\r\n" Zeichen als Trennzeichen zwischen alle erforderlichen Felder.

- Die Felder sind im Schlüssel = Wertformat.

- Die folgenden Schlüssel muss vorhanden und über einen Wert verfügen:
    
    - Ereigniscode = Windows-Ereignis-ID

    - LogFile = der Name des Windows-Ereignisprotokolls

    - SourceName = Anbieternamen für das Windows-Ereignis

    - TimeGenerated = den Zeitstempel des tatsächlichen (Stellen Sie sicher, dass es ist nicht der Zeitstempel für den Eingang der SIEM oder wenn es auf ATA gesendet wird). Das Format sollte yyyyMMddHHmmss.FFFFFF, vorzugsweise in Millisekunden-Genauigkeit übereinstimmen, dies ist sehr wichtig.

    - ComputerName = Name der Host

    - Nachricht = der ursprünglichen Ereignistext aus dem Windows-Ereignis

- Die Nachricht-Schlüssel und Wert müssen letzten sein.

- Die Reihenfolge ist nicht wichtig, dass die Schlüssel = Wert-Paare.


## < a Name = "ATA_event_WEF" >< / a > Konfigurieren von Windows-Ereignisweiterleitung

Wenn Sie nicht über einen SIEM-Server verfügen, können Sie Ihrer Domänencontroller zum Weiterleiten von Windows-Ereignis-ID 4776 direkt an eines der ATA-Gateways konfigurieren.


1. Aktivieren Sie auf der ATA-Gateway-Konfiguration **Weiterleiten von Windows-Ereignissammlung**.

    > [! HINWEIS:]
    > Wenn Sie diese Einstellung aktivieren sieht des ATA-Gateways im Protokoll weitergeleitete Ereignisse für Windows-Ereignisse, die von Domänencontrollern an sie weitergeleitet wurden.
    
    - [Konfigurieren Sie den Computer zum Weiterleiten und Sammeln von Ereignissen](https://technet.microsoft.com/en-us/library/cc748890).

2. Konfigurieren Sie Ihre Domänencontroller zum Weiterleiten von Windows-Ereignis-ID 4776 an die ATA-Gateways. Weitere Informationen zu Windows-Ereignis weiterleiten, finden Sie unter [Einrichten von Computern zum Weiterleiten und Sammeln von Ereignissen](https://technet.microsoft.com/en-us/library/cc748890).


## Siehe auch

[ATA-Installation](/Topic/ATA+Installation.md)
[Testen Sie das Forum für die Unterstützung!](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)





