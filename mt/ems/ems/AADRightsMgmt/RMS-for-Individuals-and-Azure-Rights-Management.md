---
title: RMS f&#252;r Einzelpersonen und Azure Rights Management
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2efcb440-fefd-45e9-872b-f471573aadf2
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
# RMS f&#252;r Einzelpersonen und Azure Rights Management
RMS for Individuals (RMS für Einzelpersonen) ist ein kostenloses Self-Service-Abonnement für Benutzer in einer Organisation, denen vertrauliche Dateien zugesandt wurden, die durch Microsoft Azure Rights Management (Azure RMS) geschützt sind, die aber nicht authentifiziert werden können, weil deren IT-Abteilung kein Konto für sie in Azure verwaltet. Dies ist z. B. der Fall, wenn die IT-Abteilung Office 365 nicht abonniert hat oder keine Azure-Dienste verwendet.

Diese Benutzer können sich für ein kostenloses Geschäfts- oder -Schulkonto registrieren, das mit Azure RMS verwendet wird, und können die Rights Management-Freigabeanwendung herunterladen und installieren. Danach können sich diese Benutzer authentifizieren, um nachzuweisen, dass sie die jeweilige Person sind, an die die geschützten Dateien gesendet wurden, und können dann die geschützten Dateien auf Computern oder mobilen Geräten lesen.

Mithilfe der Rights Management-Freigabeanwendung auf Windows-Computern können diese Benutzer außerdem Dateien lokal schützen oder geschützte Dateien per E-Mail an Personen innerhalb oder außerhalb ihrer Organisation senden. Wenn die Empfänger einer solchen E-Mail zu einer Organisation gehören, die ebenfalls keine Benutzerkonten in Azure verwaltet, können sich auch die Empfänger für ein RMS for Individuals-Konto anmelden, damit sie die geschützte E-Mail-Anlage lesen können.

> [!IMPORTANT]
> Dieses kostenlose Abonnement stellt sicher, dass autorisierte Personen Dateien immer lesen können, die geschützt wurden. Zurzeit können Sie dieses kostenlose Abonnement auch zum Schützen von Dokumenten verwenden. Dies dient jedoch nur Testzwecken. Weitere Informationen und Änderungen zur Verwendung von RMS für Einzelpersonen zum Schützen von Dokumenten finden Sie in den [Microsoft Rights Management-Nutzungsbedingungen](https://portal.aadrm.com/Legal/Service).

Weitere Informationen dazu, wie Sie Dateien mithilfe der kostenlosen Rights Management-Freigabeanwendung schützen können, finden Sie im [Rights Management-Freigabeanwendung – Benutzerhandbuch für Benutzer](http://technet.microsoft.com/library/dn339006.aspx).

RMS for Individuals ist ein Beispiel für eine Self-Service-Anmeldung, die von Azure Active Directory unterstützt wird. Weitere Informationen dazu, wie dies funktioniert, finden Sie unter [Was ist die Self-Service-Registrierung für Azure?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/) in der Dokumentation zu Microsoft Azure. In den folgenden Abschnitten finden Sie weitere Informationen, die speziell für RMS for Individuals (RMS für Einzelpersonen) gelten:

-   [How users sign up for RMS for individuals](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md#BKMK_SignUp)

    -   [Technical overview](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md#BKMK_TechnicalOverview)

-   [How administrators can control the accounts created for RMS for individuals](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md#BKMK_TakeControlofAccounts)

-   [How to find out if your users have signed up for RMS for individuals](#BKMK_Detect)

## <a name="BKMK_SignUp"></a>Registrieren für RMS für Einzelpersonen
Um sich für dieses kostenlose Konto zu registrieren, fordern Sie auf der [Microsoft Rights Management-Seite](https://portal.aadrm.com/) an, und geben Sie die E-Mail-Adresse Ihrer Arbeit oder Schule an. Der üblichste Auslöser dafür, dass Sie zu dieser Anmeldeseite weitergeleitet werden, besteht darin, dass Sie eine E-Mail-Nachricht mit einer geschützten Anlage empfangen haben, die Anweisungen enthält, wie eine Registrierung erfolgt. Sie erhalten eine E-Mail als Antwort von Microsoft und können den Registrierungsprozess dann abschließen, indem Sie Details eingeben, um Ihr Konto zu erstellen. Wenn Sie eine E-Mail-Bestätigung von Microsoft erhalten, leitet diese letzte E-Mail-Nachricht Sie zu einer Seite, von der Sie die Freigabeanwendung für verschiedene Geräte herunterladen können. Außerdem enthält diese E-Mail-Nachricht einen Link zum Benutzerhandbuch.

#### So registrieren Sie sich für RMS für Einzelpersonen

1.  Wechseln Sie auf einem Windows- oder Mac-Computer zur Seite [Microsoft Rights Management](https://portal.aadrm.com).

2.  Geben Sie die E-Mail-Adresse ein, die Sie für Ihre Organisation verwenden, z. B. **janetm@contoso.com** oder **p.dover@fabrikam.com**.

    > [!IMPORTANT]
    > Private E-Mail-Konten werden nicht unterstützt. Geben Sie also kein Microsoft-Konto (früher Microsoft Live ID-Konto) oder ein anderes privates Konto ein, das Sie zu Hause von Ihrem Internetanbieter verwenden.

3.  Klicken Sie auf **Erste Schritte**.

    Microsoft prüft anhand Ihrer E-Mail-Adresse, ob Ihre Organisation bereits ein [kostenpflichtiges Abonnement hat, das Azure RMS umfasst](https://technet.microsoft.com/library/dn655136.aspx#BKMK_SupportedSubscriptions). Wenn dies der Fall ist, benötigen Sie RMS for Individuals nicht, und Sie werden sofort angemeldet, und die Self-Service-Registrierung für RMS for Individuals wird abgebrochen. Wird kein kostenpflichtiges Abonnement für Azure RMS gefunden, führen Sie den nächsten Schritt aus.

4.  Warten Sie darauf, dass eine Bestätigungs-E-Mail an die von Ihnen angegebene Adresse gesendet wird. Sie stammt von Microsoft (DoNotReply@microsoft.com) und hat den Betreff **Microsoft RMS**.

5.  Wenn Sie die E-Mail empfangen, klicken Sie auf den Link in den Anweisungen, um den Registrierungsprozess abzuschließen.

6.  Der Link leitet Sie zu einer neuen Seite **Microsoft Rights Management**, wo Sie Details zu Ihrem Konto angeben können. Geben Sie Ihren Vornamen, Ihren Nachnamen und ein Kennwort Ihrer Wahl ein, bestätigen Sie das Kennwort, wählen Sie Ihr Land (oder das nächstgelegene Land, wenn Ihr Land nicht aufgelistet ist) in der Dropdownliste aus, und klicken Sie auf **Erstellen**.

7.  Warten Sie auf eine weitere E-Mail von Microsoft, die jetzt bestätigt, dass Ihr Konto zur Verwendung bereit ist.

8.  Wenn Sie die E-Mail erhalten, klicken Sie auf den Link, um sich anzumelden, und lesen Sie die Anweisungen, um die Freigabeanwendung herunterzuladen und zu installieren, oder klicken Sie auf den Hilfelink, um das Benutzerhandbuch zur Freigabeanwendung zu lesen.

Nun ist Ihr Konto erstellt, und Sie sind bereit, um Dateien zu schützen und von anderen geschützte Dateien zu lesen. Wenn Sie aufgefordert werden, sich anzumelden, um Dateien zu schützen oder geschützte Dateien zu lesen, geben Sie Ihre E-Mail-Adresse und Ihr Kennwort ein, mit denen Sie das Konto für RMS für Einzelpersonen erstellt haben.

### <a name="BKMK_TechnicalOverview"></a>Technische Übersicht
RMS for Individuals (RMS für Einzelpersonen) verwendet einen Self-Service-Registrierungsprozess, der auch von anderen Diensten verwendet wird, die Cloudtechnologie von Microsoft zur Authentifizierung von Benutzern verwenden.

Dies geschieht im Hintergrund, wenn sich ein Benutzer für RMS für Einzelpersonen registriert und seine Organisation kein Office 365-Abonnement oder Azure-Abonnement besitzt und daher auch kein Verzeichnis in Azure, um Benutzer zu authentifizieren:

1.  Wenn der erste Benutzer einer Organisation ein Abonnement für RMS for Individuals anfordert, wird der in der E-Mail-Adresse angegebene Domänenname überprüft, um festzustellen, ob er bereits einem Azure-Mandanten zugeordnet ist. Ist kein Mandant vorhanden, wird automatisch ein neuer Mandant und ein neues Azure-Verzeichnis für die Organisation erstellt, die ein Konto für diesen ersten Benutzer enthält. Im Gegensatz zu einem kostenpflichtigen Abonnement für Azure ist dieses erste Konto kein globaler Administrator, sondern ein Standardbenutzer. Das neue Konto verwendet die E-Mail-Adresse und das Kennwort, das der Benutzer angegeben hat.

    > [!NOTE]
    > Manche Domänennamen können nicht zum Erstellen des Verzeichnisses verwendet werden, weshalb sie auch nicht für RMS für Einzelpersonen verwendet werden können. Die Liste der blockierten Domänennamen kann mithilfe der folgenden JSON-Datei (JavaScript Object Notation) angezeigt werden: [http://portal.aadrm.com/content/blocked_domains.json](http://portal.aadrm.com/content/blocked_domains.json)

    Wurde ein vorhandener Mandant gefunden, wird er überprüft, um zu festzustellen, ob er bereits ein Abonnement für Azure RMS hat. Wird kein Abonnement gefunden, kann das kostenlose RMS for Individuals-Abonnement hinzugefügt werden.

2.  Der Organisation wird das RMS for Individuals-Abonnement gewährt. Nun kann dieser Benutzer von Azure authentifiziert werden und Azure Rights Management dazu verwenden, Dateien zu schützen sowie Dateien zu lesen, die von anderen geschützt wurden. Um Dateien zu schützen und geschützte Dateien zu lesen, muss der Benutzer eine RMS-fähige Anwendung haben, beispielsweise die kostenlose [Rights Management-Freigabeanwendung](https://technet.microsoft.com/library/dn919648.aspx).

3.  Wenn der zweite Benutzer aus derselben Organisation ein "RMS für Einzelpersonen"-Abonnement anfordert, wird dem zuvor erstellten Azure-Verzeichnis ein neues Benutzerkonto hinzugefügt, indem das „RMS für Einzelpersonen“-Abonnement der Organisation verwendet wird. Dieser zweite Benutzer kann alle Aktionen ausführen, die auch der erste Benutzer ausführen kann (Dateien schützen und geschützte Dateien lesen), aber zusätzlich können diese beiden Benutzer nun einfacher sicher zusammenarbeiten, weil sie schnell Standardvorlagen auf Dateien anwenden können, die den Zugriff auf Konten im Azure-Verzeichnis ihrer Organisation einschränken.

4.  Nachfolgende Benutzer aus derselben Organisation folgen demselben Muster, und dem Azure-Verzeichnis der Organisation werden (wenn sich neue Benutzer registrieren) Benutzerkonten hinzugefügt. Je mehr Konten dem Verzeichnis hinzugefügt werden, desto mehr Benutzer können sicher mit Kollegen und Partnern zusammenarbeiten und einfacher verhindern, dass nicht autorisierte Personen ihre Dateien lesen, die keinen Zugriff darauf haben sollten.

Während des gesamten Prozesses fallen keine Kosten für die Organisation an, und es ist keine Arbeit seitens der IT-Abteilung erforderlich. Die IT-Abteilung kann allerdings, wenn sie möchte, die folgenden Aktionen ausführen:

-   **Verwalten der Konten und des Anmeldevorgangs**: IT-Administratoren können den Besitz der automatisch erstellten Verzeichnisse und Konten in Azure übernehmen. Sie können dann die Konten verwalten, indem sie Verzeichnisintegrationslösungen wie Kennwortsynchronisierung und einmaliges Anmelden implementieren. Oder sie können Benutzer daran hindern, Konten zu erstellen oder sich für RMS for Individuals zu registrieren.

    Weitere Informationen finden Sie im folgenden Abschnitt, [How administrators can control the accounts created for RMS for individuals](../../ems/AADRightsMgmt/RMS-for-Individuals-and-Azure-Rights-Management.md#BKMK_TakeControlofAccounts).

-   **Verwalten von Rights Management**: IT-Administratoren können das "RMS für Einzelpersonen"-Abonnement für die Organisation in ein kostenpflichtiges Abonnement umwandeln, das Azure Rights Management enthält. Wenn sie dies tun, bleiben das vorhandene Azure-Verzeichnis und die Konten erhalten, um einen nahtlosen Übergang von vorhandenen Benutzern, die bisher RMS für Einzelpersonen verwendet haben, zu gewährleisten. Alle Dateien, die zuvor geschützt waren, bleiben mit denselben Richtlinien geschützt, und die Personen, denen Berechtigungen für die Nutzung der Dateien gewährt wurden, können die Dateien weiterhin auf dieselbe Weise verwenden.

    Wenn Sie so vorgehen, profitiert Ihre Organisation davon, dass sie in der Lage ist, Rights Management in die eigenen Workflows, Dienste und Datenspeicher zu integrieren. Zusätzlich können Sie dann Rights Management verwalten, weil Sie die Kontrolle über den Mandantenschlüssel Ihrer Organisation für Azure Rights Management haben. Sie können jetzt Folgendes machen:

    -   Exchange und SharePoint so konfigurieren, dass sie Azure Rights Management unterstützen, auch wenn sie lokal ausgeführt werden. Exchange und SharePoint werden für die Online Services systemeigen unterstützt sowie von einem Connector für die lokalen Server. Weitere Informationen finden Sie unter den folgenden Links:

        -   In den Exchange Online- und SharePoint Online-Abschnitten aus [Office 365: Configuration for clients and online services](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md#BKMK_O365) im Thema [Konfigurieren von Clientanwendungen für Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Applications-for-Azure-Rights-Management.md).

        -   [Bereitstellen von Azure Rights Management-Connector](../../ems/AADRightsMgmt/Deploying-the-Azure-Rights-Management-Connector.md)

    -   Führen Sie eine eDiscovery in den unternehmenseigenen Daten durch, damit Sie ggf. Dateien entschlüsseln können, die mithilfe von Rights Management geschützt wurden. Weitere Informationen finden Sie unter [Konfigurieren von Administratoren für Azure Rights Management und Discovery Services oder Wiederherstellen von Daten](../../ems/AADRightsMgmt/Configuring-Super-Users-for-Azure-Rights-Management-and-Discovery-Services-or-Data-Recovery.md).

    -   Alle Aktivitäten für Rights Management protokollieren, wie sie in Ihrer Organisation verwendet werden. Dies ist sehr leistungsfähig, weil Sie nicht nur überwachen können, welche Dateien geschützt werden und wer erfolgreich auf diese geschützten Dateien zugreift, sondern auch potenziell verdächtiges Verhalten nicht autorisierter Personen identifizieren können, die versuchen, auf geschützte Dateien zuzugreifen. Weitere Informationen finden Sie unter [Protokollieren und Analysieren von Azure Rights Management-Nutzung](../../ems/AADRightsMgmt/Logging-and-Analyzing-Azure-Rights-Management-Usage.md).

    -   Geben Sie Benutzern die Möglichkeit, ihre geschützten Dokumente nachzuverfolgen und zu widerrufen, sofern diese Features von Ihrem [Azure RMS-Abonnement](https://technet.microsoft.com/dn858608) unterstützt werden. Weitere Informationen finden Sie unter [Nachverfolgen und Widerrufen von Dateien](https://technet.microsoft.com/library/dn986611.aspx) im [Rights Management-Freigabeanwendung – Benutzerhandbuch](https://technet.microsoft.com/library/dn339006.aspx).

    -   Eine BYOK-Lösung (Bring Your Own Key) implementieren, sodass Ihr Mandantenschlüssel für Azure Rights Management lokal und gemäß Ihren IT-Richtlinien generiert und sicher unter Verwendung eines HSM (Hardwaresicherheitsmodul) an Microsoft übertragen wird. Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../../ems/AADRightsMgmt/Planning-and-Implementing-Your-Azure-Rights-Management-Tenant-Key.md).

## <a name="BKMK_TakeControlofAccounts"></a>Möglichkeiten der Kontrolle über die für RMS für Einzelpersonen erstellten Konten durch Administratoren
Wenn Sie das „RMS für Einzelpersonen“-Abonnement Ihrer Organisation nicht in ein kostenpflichtiges Abonnement umwandeln möchten, können Sie immer noch die Benutzerkonten im Azure-Verzeichnis, das für Ihre Organisation erstellt wurde, auf die folgenden Arten kontrollieren:

-   Implementieren Sie Verzeichnisintegrationslösungen für Azure Active Directory und Ihre Active Directory-Domänendienste-Infrastruktur. Sie können Konten und Kennwörter synchronisieren, sodass Benutzer keine neuen Konten für die Verwendung von Rights Management erstellen müssen, und Ihre lokalen Kennwortrichtlinien gelten weiterhin auch für die neuen Azure-Benutzerkonten. Sie können auch Kennwörter synchronisieren, sodass Benutzer sich kein anderes Kennwort für die Verwendung von Rights Management merken müssen.

-   Sie könnten Benutzer daran hindern, sich anzumelden, um Azure Rights Management mit dem RMS for Individuals-Abonnement zu verwenden. In den meisten Fällen bringt dies kaum Vorteile, weil Benutzer dann Dateien ohne Schutz freigeben (was ein Risiko für Ihr Unternehmen bedeuten kann) oder einen anderen Dateischutzmechanismus verwenden werden, der der IT-Abteilung nicht die Möglichkeit für den Zugriff auf die Daten bietet. Wenn Sie jedoch Benutzer an der Registrierung für die Verwendung von RMS for Individuals hindern möchten, führen Sie eine der folgenden Aktionen aus, nachdem Sie in Azure den Besitz des Verzeichnisses Ihrer Organisation übernommen haben:

    -   Hindern Sie alle Benutzer daran, sich für Self-Service-Abonnements zu registrieren, die RMS for Individuals umfassen.  Derzeit kann dies nicht nach Dienst festgelegt werden, sondern die Einstellung wird auf alle Azure-Abonnements angewendet, die den Self-Service-Prozess nutzen. Legen Sie hierzu den Parameter **AllowAdHocSubscriptions** mit dem Cmdlet [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) aus dem Windows PowerShell-Modul für Azure Active Directory auf „false“ fest. Beispiel: **Set-MsolCompanySettings -AllowAdHocSubscriptions $false**

    -   Hindern Sie Benutzer an der Erstellung eines neuen Kontos in Azure, was bedeutet, dass nur Benutzer, die bereits ein Konto in Azure haben, sich für Self-Service-Abonnements registrieren können, wozu auch RMS for Individuals gehört.  Legen Sie hierzu den Parameter **AllowEmailVerifiedUsers** mit dem Cmdlet [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) aus dem Windows PowerShell-Modul für Azure Active Directory auf „false“ fest. Beispiel: **Set-MsolCompanySettings -AllowEmailVerifiedUsers $false -AllowAdHocSubscriptions $true**

    -   Synchronisieren Sie Ihre Active Directory-Domänendienste-Infrastruktur mit Azure Active Directory. Diese Aktion verhindert, dass neue Konten erstellt werden, wenn sich Benutzer für Self-Service-Abonnements wie RMS for Individuals registrieren, und Sie können Konten löschen oder deaktivieren, die zuvor im Azure-Verzeichnis erstellt wurden.

Um die Benutzerkonten im Azure-Verzeichnis zu kontrollieren oder Benutzer daran zu hindern, sich für RMS für Einzelpersonen zu registrieren, müssen Sie ein Azure-Abonnement besitzen und Besitzer des Verzeichnisses sein. Wenn Sie noch kein Azure-Abonnement haben, können Sie sich eines beschaffen, für das keine Kosten anfallen. Wenn während des Self-Service-Prozesses automatisch ein Verzeichnis für Sie erstellt wurde, übernehmen Sie den Besitz der Domäne, die zu dessen Erstellung verwendet wurde. Wenn Sie bereits ein Verzeichnis in Azure besitzen, Benutzer aber eine neue Domäne angegeben haben, die Sie in Ihrer Organisation verwenden, führen Sie diese Domäne mit Ihrem vorhandenen Verzeichnis zusammen. Weitere Informationen finden Sie in den Anweisungen in [Was ist die Self-Service-Registrierung für Azure?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)

## <a name="BKMK_Detect"></a>So ermitteln Sie, ob Ihre Benutzer sich für RMS for Individuals registriert haben
Wie erfahren Sie als Administrator, ob Ihre Benutzer sich für RMS für Einzelpersonen registriert haben? Sie können eine bzw. eine beliebige Kombination der folgenden Methoden verwenden:

-   Fragen Sie Benutzer, wie sie sehr vertrauliche Dateien schützen, insbesondere bei der Zusammenarbeit mit anderen Personen außerhalb der Organisation.

-   Wenn Sie ein Azure-Abonnement für Ihre Organisation besitzen, verwenden Sie das Cmdlet [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx), um festzustellen, ob **RIGHTSMANAGEMENT_ADHOC** als eines der Abonnements zurückgegeben wird. Ist dies der Fall, ist dies das "RMS für Einzelpersonen"-Abonnement, das der Organisation gewährt wurde, mit einem Pool aktiver Einheiten, die Benutzern zur Verfügung stehen, um den Self-Service-Anmeldevorgang zu verwenden.

-   Verwenden Sie eine Systemvewaltungslösung wie System Center Configuration Manager, um installierte und in Verwendung befindliche Software zu inventarisieren. Die Rights Management-Freigabeanwendung mithilfe des **ipviewer.exe**-Programms ausgeführt, und Sie können [die Anwendung kostenlos herunterladen und installieren die Anwendung](http://go.microsoft.com/fwlink/?LinkId=303970), um andere Eigenschaften dieser Anwendung zu identifizieren, die Sie dann für Ihren Softwarebestand nutzen.

-   Achten Sie auf Dateinamenerweiterungen, die von der Rights Management-Freigabeanwendung erstellt werden. Die Dateinamenerweiterungen „PFILE“ und „PPDF“ sind die offensichtlichsten Beispiele, doch es gibt noch andere Dateien, die ihre Dateinamenerweiterung ändern, wenn sie durch Rights Management systemeigen geschützt sind. Weitere Informationen finden Sie im Abschnitt [Unterstützte Dateitypen und Dateinamenerweiterungen](http://technet.microsoft.com/library/dn339003.aspx) im [Rights Management-Freigabeanwendung – Administratorhandbuch](http://technet.microsoft.com/library/dn339003.aspx).

## Siehe auch
[Erste Schritte mit Azure Rights Management](../../ems/AADRightsMgmt/Getting-Started-with-Azure-Rights-Management.md)

