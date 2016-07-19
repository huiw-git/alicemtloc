---
title: Vorbereiten f&#252;r Azure Rights Management
ms.custom: na
ms.date: 12/22/2015
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc
translation.priority.ht: 
  - bg-bg
  - de-de
  - el-gr
  - es-es
  - et-ee
  - fi-fi
  - fr-fr
  - hr-hr
  - it-it
  - ja-jp
  - kk-kz
  - ko-kr
  - lt-lt
  - lv-lv
  - pt-br
  - ro-ro
  - ru-ru
  - sk-sk
  - sl-si
  - sr-latn-cs
  - th-th
  - tr-tr
  - uk-ua
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - da-dk
  - hu-hu
  - nb-no
  - nl-nl
  - pl-pl
  - pt-pt
  - sv-se
---
# Vorbereiten f&#252;r Azure Rights Management
Nachdem Sie sich für ein Cloud-Abonnement registriert und Ihre Organisation mit einem Konto für [!INCLUDE[o365_1](../../ems/AADRightsMgmt/includes/o365_1_md.md)] oder Azure Active Directory eingerichtet haben, sind Sie bereit, um den [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)]-Dienst zu aktivieren.

Vergewissern Sie sich aber vorher, dass folgende Punkte vorhanden sind:

-   Benutzerkonten und -gruppen in der Cloud, die Sie manuell erstellt haben oder die aus den Active Directory-Domänendiensten (AD DS) automatisch erstellt und synchronisiert wurden. Verwenden Sie [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), um Ihre lokalen Verzeichnisse mit Azure Active Directory zu verbinden.

-   E-Mail-aktivierte Gruppen in der Cloud, die Sie für Rights Management verwenden möchten. Das können integrierte oder manuell erstellte Gruppen sein, die Benutzer enthalten, die Rights Management verwenden werden.

    Wenn Sie über Exchange Online verfügen, können Sie im Exchange Admin Center E-Mail-fähige Gruppen erstellen und nutzen. Wenn Sie AD DS haben und die Synchronisierung mit Azure AD vornehmen, können Sie E-Mail-fähige Gruppen erstellen und verwenden, die entweder Sicherheits- oder Verteilergruppen sind.

## Aktivieren von Rights Management
Standardmäßig ist [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] deaktiviert, wenn Sie sich für Ihr [!INCLUDE[o365_2](../../ems/AADRightsMgmt/includes/o365_2_md.md)]- oder Azure AD-Konto registrieren. Um [!INCLUDE[aad_rightsmanagement_2](../../ems/AADRightsMgmt/includes/aad_rightsmanagement_2_md.md)] für Ihre Organisation zu aktivieren, müssen Sie den Dienst aktivieren. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../../ems/AADRightsMgmt/Activating-Azure-Rights-Management.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../../ems/AADRightsMgmt/Configuring-Azure-Rights-Management.md)

