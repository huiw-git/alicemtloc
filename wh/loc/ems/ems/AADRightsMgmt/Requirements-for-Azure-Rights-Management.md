---
title: Anforderungen f&#252;r Azure Rights Management
ms.custom: na
ms.date: 03/02/2016
ms.reviewer: na
ms.service: rights-management
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dc78321d-d759-4653-8818-80da74b6cdeb
translation.priority.ht: 
  - es-es
  - fr-fr
  - it-it
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - de-de
  - ja-jp
---
# Anforderungen f&#252;r Azure Rights Management
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="de-DE">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="4593739fb104567a5116d465bff5a356" id="tgt1" class="tgtSentence">Zum Bereitstellen von Microsoft Azure Rights Management (Azure RMS) in Ihrer Organisation sicher, dass Sie die folgenden erforderlichen Komponenten verfügen.</caps:sentence>
          <caps:sentence sentenceid="fef1364f715270ff51ab4339bfaad86c" id="tgt2" class="tgtSentence"> Anschließend können Sie die <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> Rights Management für Ihre Organisation bereitstellen.</caps:sentence>
        </para>
        <table>
          <thead>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="ba12fb48e2d23bb2bd2819f64d02ec7e" id="tgt3" class="tgtSentence">Anforderung</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt4" class="tgtSentence">Weitere Informationen</caps:sentence>
                </para>
              </TD>
            </tr>
          </thead>
          <tbody>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="66807d3b911cd140d0bcd36a2ec4ed81" id="tgt5" class="tgtSentence">Ein Cloud-Abonnement für RMS</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="cc6e5ba80ff6dd04d114a94ae26d0535" id="tgt6" class="tgtSentence">Ihre Organisation muss ein Cloud-Abonnement verfügen, das RMS unterstützt.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="bd8b31a59407af0b9fe86b1c2e4e7337" id="tgt7" class="tgtSentence">Informationen zur Lizenzierung, finden Sie unter den <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> in diesem Thema.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="8132a6b7e45298a974e7ec497472d32c" id="tgt8" class="tgtSentence">Azure AD-Verzeichnis </caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="62b2bedd06b5251680fe61a9c7e5a7de" id="tgt9" class="tgtSentence">Ihre Organisation benötigen Sie ein Windows Azure AD-Benutzerauthentifizierung für RMS zu unterstützen.</caps:sentence>
                  <caps:sentence sentenceid="f57a36ab3f0a5bb2ea803eeff4d2023e" id="tgt10" class="tgtSentence"> Darüber hinaus, wenn Sie Ihre Benutzerkonten aus Ihrem lokalen Verzeichnis (AD DS) verwenden möchten, müssen Sie auch Verzeichnisintegration konfigurieren.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="9789392d6ff7f7b72b718513881a8621" id="tgt11" class="tgtSentence">Mehrstufige Authentifizierung (MFA) wird mit Azure RMS unterstützt, wenn Sie die erforderliche Clientsoftware und ordnungsgemäß konfigurierten MFA unterstützende Infrastruktur haben.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt12" class="tgtSentence">Weitere Informationen finden Sie im Abschnitt <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_AzureADTenant">Azure AD directory</link> dieses Themas.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="90322c2094b3c5003a01d95a934ed98b" id="tgt13" class="tgtSentence">Client-Geräte</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="36e5fad901784d2212dfb70a52a32a10" id="tgt14" class="tgtSentence">Benutzer müssen Clientgeräte (Computer oder mobilen Gerät) verfügen, die ein Betriebssystem ausgeführt, das RMS unterstützt.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt15" class="tgtSentence">Weitere Informationen finden Sie im Abschnitt <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedDevices">Client devices that support Azure RMS</link> dieses Themas.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="b5fba9ff24d0045d1377a05a46b32f68" id="tgt16" class="tgtSentence">Applications</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="773a885c92513b099511207194161e6d" id="tgt17" class="tgtSentence">Benutzer müssen Programme ausführen, die RMS unterstützen.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt18" class="tgtSentence">Weitere Informationen finden Sie im Abschnitt <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link> dieses Themas.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="c6febfa6c911988de87d9fb5f76791c9" id="tgt19" class="tgtSentence">Infrastruktur, die Konnektivität mit dem Internet und abhängige Cloud-Dienste unterstützt.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="e2dcaee14c473720ed8c768b1791e462" id="tgt20" class="tgtSentence">Wenn Sie eine Firewall oder ähnliche dazwischen liegenden Netzwerk-Geräte, die konfiguriert werden müssen, bestimmte Verbindungen zulassen, finden Sie unter <externalLink><linkText>Office 356 URLs und IP-Adressbereiche</linkText><linkUri>https://support.office.com/en-US/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="0d7de949ecbdf4c05eeaee0601a75229" id="tgt21" class="tgtSentence">Die Liste der URLs und IP-Adressen in der <embeddedLabel>Office 356 Portal und Identität</embeddedLabel> Bereich für die Office 365-Portal, Azure Active Directory-Ressourcen und Azure Rights Management gelten.</caps:sentence>
                  <caps:sentence sentenceid="0e3c8c9c168c16ffdc9123895b08c5be" id="tgt22" class="tgtSentence"> Verwenden Sie die Anweisungen in diesem Artikel auf diese Informationen auf dem neuesten Stand mit Änderungen beibehalten eines RSS-Feeds abonnieren.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a4e9e6460b1c4699370fb6f6c8468679" id="tgt23" class="tgtSentence">Zusätzlich zu den Informationen im Azure RMS für Office-Artikel:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="3ff280c40a80758d7b7a16335dbe9b56" id="tgt24" class="tgtSentence">Die TLS-Client-zu-Dienst-Verbindung (z. B. Führen Sie die Prüfung auf Paketebene) nicht beendet werden.</caps:sentence>
                      <caps:sentence sentenceid="2f3480f40b2c078fdbdddacab91d72bf" id="tgt25" class="tgtSentence"> Auf diese Weise wird das Zertifikat, das festhalten, dass RMS-Clients mit Zertifizierungsstellen von Microsoft verwalteten verwenden um zu schützen die Kommunikation mit Azure RMS unterbrochen.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="8d973ad53dc25dc8519abe58902b4d25" id="tgt26" class="tgtSentence">Verwenden Sie eine Web-Proxy-Konfiguration, die im Auftrag eines Benutzers authentifiziert.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
          </tbody>
        </table>
        <para> </para>
        <para>
          <caps:sentence sentenceid="4f1f644c49ef280a12a9a3d25a656e99" id="tgt27" class="tgtSentence">Wenn Sie Azure RMS mit lokalen Servern verwenden möchten, werden folgende Produkte unterstützt:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence sentenceid="d225a194a33d72270b4540a445f24fdd" id="tgt28" class="tgtSentence">Exchange Server</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="591e07b21bbb685cb23b0c9a50de44fa" id="tgt29" class="tgtSentence">SharePoint Server</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="4f7e1857707e7964bce0f9aeec18143d" id="tgt30" class="tgtSentence">Windows Server-Dateiserver, die die Dateiklassifizierungsinfrastruktur unterstützen.</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence sentenceid="a23389702045bac0f8ac2a1b4b6d2fa3" id="tgt31" class="tgtSentence">Informationen zu den zusätzlichen Azure RMS-Anforderungen für dieses Szenario finden Sie unter den <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedServers">On-premises servers that support Azure RMS</link> in diesem Thema.</caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence sentenceid="134c3977ea00130e3db43ba06233914b" id="tgt32" class="tgtSentence">Das folgende Szenario wird nicht unterstützt: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="1f84219c5de679d41c1bf8e43cd1e6a5" id="tgt33" class="tgtSentence">AD RMS und Azure RMS Side-by-Side in derselben Organisation, außer während der Migration ausführen, wie unter <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="b3d3a12c2d964aa10e07c71c55cfb164" id="tgt34" class="tgtSentence">Es gibt ein unterstützten Migrationspfad <externalLink><linkText>von AD RMS in Azure RMS</linkText><linkUri>http://technet.microsoft.com/library/Dn858447.aspx</linkUri></externalLink>, und von <externalLink><linkText>Azure RMS auf AD RMS</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629429.aspx</linkUri></externalLink>.</caps:sentence>
            <caps:sentence sentenceid="2ae8c626aaba10ea8b62b689a3170728" id="tgt35" class="tgtSentence"> Wenn Sie Azure RMS bereitstellen und dann entscheiden, dass Sie nicht mehr verwenden möchten diesen Cloud-Dienst, finden Sie unter <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Deactivating Azure Rights Management</link>.</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence sentenceid="daef9f790c4c4a8e033b71c775f26b7f" id="tgt36" class="tgtSentence">Verwenden Sie in den folgenden Abschnitten erfahren Sie mehr über die Azure RMS-Anforderungen.</caps:sentence>
        </para>
      </introduction>
      <section address="BKMK_SupportedSubscriptions">
        <title address="BKMK_Subscriptions">
          <caps:sentence sentenceid="f1b6f39247dc57834ca77f021cce0460" id="tgt37" class="tgtSentence">Cloud-Abonnements, die Azure RMS unterstützen</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="51fd2815a1bdca49df84a4a9e00a1cd4" id="tgt38" class="tgtSentence">Um Azure RMS zu verwenden, muss die Organisation besitzen mindestens eines der folgenden Abonnements mit einer ausreichenden Anzahl von Lizenzen für Benutzer und Dienste, die e-Mail-Nachrichten und Dateien zu schützen.</caps:sentence>
            <caps:sentence sentenceid="27d3e663d60414e7a67598e5bc5d0730" id="tgt39" class="tgtSentence"> Wenn Sie einen Dienst, der für Benutzer (Besitzer der Dateien oder e-Mail-Nachrichten) angewendet wird verfügen, benötigen diese Benutzer eine dieser Lizenzen.</caps:sentence>
            <caps:sentence sentenceid="927fdb95afa5c403655d11ed6056b5d5" id="tgt40" class="tgtSentence"> Benutzer, die nur belegt werden (z. B. Lesen und bearbeiten) diese geschützten Daten eine Lizenz nicht erforderlich.</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="c0d0371d490a66b8406b8d078c55a438" id="tgt41" class="tgtSentence">Office 365</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="cec8c0ed11bd7312082cb4442485f425" id="tgt42" class="tgtSentence">Azure Rights Management Premium (ehemals Azure RMS eigenständig)</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="2f031859ec284e146d4b29a177763185" id="tgt43" class="tgtSentence">Enterprise Mobility Suite</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="b4c3de2ce51f65bbe518c354a7f3b1f7" id="tgt44" class="tgtSentence">RMS für Einzelpersonen</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="1b656085796f1e83cb6a53e2427e94fc" id="tgt45" class="tgtSentence">Verwenden Sie in den folgenden Abschnitten, um weitere Informationen und Registrierungsoptionen.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="c46835d8c09e657b497bfdd6f43b576f" id="tgt46" class="tgtSentence">Eine Lizenzierung Vergleich von Azure RMS-Funktionen für die kostenpflichtigen Abonnements finden Sie unter <externalLink><linkText>Vergleich von Rights Management Services (RMS) Angebote</linkText><linkUri>http://technet.microsoft.com/dn858608</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
        <sections>
          <section expanded="false">
            <title>
              <caps:sentence sentenceid="209cf56a7a83dad96e146a5b3c78cb34" id="tgt47" class="tgtSentence">Office 365-Abonnement</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="e33ffc5c23d9d8c4feae0b795c52c1bb" id="tgt48" class="tgtSentence">Kostenlose 30-Tage-Testversion: Enterprise E3</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/p/?LinkID=403802</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence sentenceid="de7912b4958f581527f60048c6e6e583" id="tgt49" class="tgtSentence">Dieses Abonnement ist auf Organisationen ausgelegt, die Verwendung der Office-online-Dienste und ihre Information Rights Management-Feature, das Azure RMS verwendet werden soll.</caps:sentence>
                <caps:sentence sentenceid="65ffeba1d9524ef001bcacc00844bbb1" id="tgt50" class="tgtSentence"> Nicht alle Office 365-Abonnements enthalten jedoch Azure RMS.</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="759c8194fabc6219800e2b55137ce57e" id="tgt51" class="tgtSentence">Lizenzierungsoption</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="99f81bbd133ffa639c3b6bd38e44f6b6" id="tgt52" class="tgtSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ec54b934773d3e61867cf495356e9bbd" id="tgt53" class="tgtSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f1a87875cd20ff5ca637ece8f2fd68da" id="tgt54" class="tgtSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="131d26d76d9e09dbfa36164306efb35a" id="tgt55" class="tgtSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0ad3acbd6296e919999d40b9ebbffcd8" id="tgt56" class="tgtSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="789dbeb13d727f29a9ebe85e13ab9be0" id="tgt57" class="tgtSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="69a207c7426bd6dbc9258848c33f2032" id="tgt58" class="tgtSentence">Office 365 Regierung G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ef591da14043d5b6e132ccd1bfe23bbc" id="tgt59" class="tgtSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="87884ed4009609faca3933688e306455" id="tgt60" class="tgtSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="3498b7e507f1befc1630e83ffc5d6b34" id="tgt61" class="tgtSentence">Office 365 Regierung G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ed5192f73aa753687e081dbcf8ee24df" id="tgt62" class="tgtSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="11b53325ee7ecb6fb04d70d04efffb9a" id="tgt63" class="tgtSentence">SharePoint-Plan 1<br /><br />SharePoint-Plan 2</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b60d4ca4da8d01e49c273d8599541f4d" id="tgt64" class="tgtSentence">Exchange Online-Plans 1<br /> <br />Exchange Online-Plans 2 </caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="09039a7d2d19a77306ab6aa77aa819fd" id="tgt65" class="tgtSentence">Von Informationsrechten (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7fa3b767c460b54a2be4d49030b349c7" id="tgt66" class="tgtSentence">Nein</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="98a728ddad0b2e701477c94d99f45bb5" id="tgt67" class="tgtSentence">Nein </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7fa3b767c460b54a2be4d49030b349c7" id="tgt68" class="tgtSentence">Nein</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt69" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt70" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7fa3b767c460b54a2be4d49030b349c7" id="tgt71" class="tgtSentence">Nein</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7fa3b767c460b54a2be4d49030b349c7" id="tgt72" class="tgtSentence">Nein</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7fa3b767c460b54a2be4d49030b349c7" id="tgt73" class="tgtSentence">Nein</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence sentenceid="0ce46df0914e79a0952f01e52b2d4160" id="tgt74" class="tgtSentence">Azure Rights Management Premium-Abonnement</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="812a6306d03d24eacf3a02664c504422" id="tgt75" class="tgtSentence">Kostenlose 30-Tage-Testversion</caps:sentence>
                  </linkText>
                  <linkUri>https://portal.microsoftonline.com/Signup/MainSignUp15.aspx?&amp;OfferId=A43415D3-404C-4df3-B31B-AAD28118A778&amp;dl=RIGHTSMANAGEMENT&amp;ali=1</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence sentenceid="68b0d96d4ce74dcb1dcd84f08373812f" id="tgt76" class="tgtSentence">Dieses Abonnement wurde früher als eigenständige von Azure RMS, und er eignet sich für Organisationen, die Azure RMS verwenden möchten, aber keine Abonnements, die Azure RMS umfassen.</caps:sentence>
                <caps:sentence sentenceid="5c79d904343611e0692321dc79e48138" id="tgt77" class="tgtSentence"> Z. B. Wenn Sie ein Abonnement für Office 365 Business Essentials oder Office 365 Enterprise E1 haben, diese Abonnements beinhalten keine Azure RMS (siehe die Tabelle im vorhergehenden Abschnitt).</caps:sentence>
                <caps:sentence sentenceid="f31454dd5abc74b6415b0386ff9c994c" id="tgt78" class="tgtSentence"> Um Azure RMS zu verwenden, könnten Sie erwerben Sie ein Abonnement für Azure Rights Management Premium (oder erwerben ein anderes Abonnement, wie z. B. Office 365 Enterprise E4, die Azure RMS).</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt79" class="tgtSentence">Weitere Informationen finden Sie unter <externalLink><linkText>Microsoft Azure Rights Management</linkText><linkUri>http://products.office.com/business/microsoft-azure-rights-management</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="ba0fb60651f662ee50d48736224fc7b9" id="tgt80" class="tgtSentence">Dieses Abonnement bietet außerdem einen Testzeitraum für Sie Azure RMS für 25 Benutzer kostenlos ausprobieren.</caps:sentence>
                <caps:sentence sentenceid="9fc037446dbad9c5c3f2ee29b6a269c7" id="tgt81" class="tgtSentence"> Wenn das Abonnement abläuft, bevor Sie einen ersatzabonnement erwerben, finden Sie im folgenden Abschnitt, "Was geschieht, wenn das Testabonnement abläuft?"</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="759c8194fabc6219800e2b55137ce57e" id="tgt82" class="tgtSentence">Lizenzierungsoption</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="99f81bbd133ffa639c3b6bd38e44f6b6" id="tgt83" class="tgtSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ec54b934773d3e61867cf495356e9bbd" id="tgt84" class="tgtSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f1a87875cd20ff5ca637ece8f2fd68da" id="tgt85" class="tgtSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="131d26d76d9e09dbfa36164306efb35a" id="tgt86" class="tgtSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0ad3acbd6296e919999d40b9ebbffcd8" id="tgt87" class="tgtSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="789dbeb13d727f29a9ebe85e13ab9be0" id="tgt88" class="tgtSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="69a207c7426bd6dbc9258848c33f2032" id="tgt89" class="tgtSentence">Office 365 Regierung G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ef591da14043d5b6e132ccd1bfe23bbc" id="tgt90" class="tgtSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="87884ed4009609faca3933688e306455" id="tgt91" class="tgtSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="3498b7e507f1befc1630e83ffc5d6b34" id="tgt92" class="tgtSentence">Office 365 Regierung G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ed5192f73aa753687e081dbcf8ee24df" id="tgt93" class="tgtSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="11b53325ee7ecb6fb04d70d04efffb9a" id="tgt94" class="tgtSentence">SharePoint-Plan 1<br /> <br />SharePoint-Plan 2 </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b60d4ca4da8d01e49c273d8599541f4d" id="tgt95" class="tgtSentence">Exchange Online-Plans 1<br /> <br />Exchange Online-Plans 2 </caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="09039a7d2d19a77306ab6aa77aa819fd" id="tgt96" class="tgtSentence">Von Informationsrechten (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt97" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="10bbdcc6dc85dae5826a43357d0c4c70" id="tgt98" class="tgtSentence">Yes <superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt99" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt100" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt101" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt102" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt103" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt104" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence sentenceid="ca4fa5d4a9119b57d5f5241bb4e8e1e2" id="tgt105" class="tgtSentence">
                  <superscript>1</superscript> für Business Premium, gelten einige Clienteinschränkungen: können Sie Inhalte zu schützen und geschützte Inhalte mit RMS mit Outlook Web App und die RMS-Freigabe-app benutzen.</caps:sentence>
                <caps:sentence sentenceid="3f4d5ff29bdf24d70ef64926fb6f2d95" id="tgt106" class="tgtSentence"> Sie können geschützten Inhalte nutzen, mit allen Office-Anwendungen, einschließlich Office Online und Clientanwendungen für Office 365 Business Premium.</caps:sentence>
              </para>
            </content>
            <sections>
              <section address="BKMK_TrialExpiryBehavior">
                <title>
                  <caps:sentence sentenceid="1a6504ce768a56eb97f02668cfe471c9" id="tgt107" class="tgtSentence">Was geschieht, wenn das Testabonnement abläuft?</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="332013c7e58b4a9a912e3e0254a00e68" id="tgt108" class="tgtSentence">Wenn Ihr Testabonnement abläuft, verlieren Sie den Zugriff auf Inhalte, die mit Ihr Testabonnement für Azure RMS geschützt wurde.</caps:sentence>
                    <caps:sentence sentenceid="0620410a42f5e6267d4bd527c9a10829" id="tgt109" class="tgtSentence"> Wenn Sie dann ein Abonnement, das Azure RMS unterstützt erwerben, ist jedoch Zugriff automatisch wiederhergestellt.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="51ef6ef2072f81a79916d7f638c66614" id="tgt110" class="tgtSentence">Eine Ausnahme Zugriffsverlust bei Ablauf ist, wenn Ihre Organisation Azure RMS mit dem RMS für Einzelpersonen-Abonnement verwendet, bevor Sie das Testabonnement erworben haben.</caps:sentence>
                    <caps:sentence sentenceid="b2b4f42f3943cc527a6895d21b82435f" id="tgt111" class="tgtSentence"> Klicken Sie dann, den Zugriff auf zuvor geschützte Inhalte bleiben, auch wenn das Testabonnement abläuft.</caps:sentence>
                  </para>
                </content>
              </section>
            </sections>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence sentenceid="e5a9366b3679d78699572fe20e520b91" id="tgt112" class="tgtSentence">Enterprise Mobility Suite-Abonnement</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="812a6306d03d24eacf3a02664c504422" id="tgt113" class="tgtSentence">Kostenlose 30-Tage-Testversion</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/?LinkId=615385</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence sentenceid="c1e72a66155d5a95ce7ae1b61810dae7" id="tgt114" class="tgtSentence">Dieses Abonnement ist auf Organisationen ausgelegt, die eine Kombination von Azure Active Directory Premium, Windows Intune und Azure Rights Management verwenden möchten.</caps:sentence>
                <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt115" class="tgtSentence"> Weitere Informationen finden Sie unter der <externalLink><linkText>Übersicht über Microsoft Enterprise-Mobilität</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=615386</linkUri></externalLink>.</caps:sentence>
              </para>
              <para></para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="759c8194fabc6219800e2b55137ce57e" id="tgt116" class="tgtSentence">Lizenzierungsoption</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="99f81bbd133ffa639c3b6bd38e44f6b6" id="tgt117" class="tgtSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ec54b934773d3e61867cf495356e9bbd" id="tgt118" class="tgtSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f1a87875cd20ff5ca637ece8f2fd68da" id="tgt119" class="tgtSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="131d26d76d9e09dbfa36164306efb35a" id="tgt120" class="tgtSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0ad3acbd6296e919999d40b9ebbffcd8" id="tgt121" class="tgtSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="789dbeb13d727f29a9ebe85e13ab9be0" id="tgt122" class="tgtSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="69a207c7426bd6dbc9258848c33f2032" id="tgt123" class="tgtSentence">Office 365 Regierung G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ef591da14043d5b6e132ccd1bfe23bbc" id="tgt124" class="tgtSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="87884ed4009609faca3933688e306455" id="tgt125" class="tgtSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="3498b7e507f1befc1630e83ffc5d6b34" id="tgt126" class="tgtSentence">Office 365 Regierung G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ed5192f73aa753687e081dbcf8ee24df" id="tgt127" class="tgtSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="11b53325ee7ecb6fb04d70d04efffb9a" id="tgt128" class="tgtSentence">SharePoint-Plan 1<br /> <br />SharePoint-Plan 2 </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b60d4ca4da8d01e49c273d8599541f4d" id="tgt129" class="tgtSentence">Exchange Online-Plans 1<br /> <br />Exchange Online-Plans 2 </caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="09039a7d2d19a77306ab6aa77aa819fd" id="tgt130" class="tgtSentence">Von Informationsrechten (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt131" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="10bbdcc6dc85dae5826a43357d0c4c70" id="tgt132" class="tgtSentence">Yes <superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt133" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt134" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt135" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt136" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt137" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a6105c0a611b41b08f1209506350279e" id="tgt138" class="tgtSentence">Ja</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence sentenceid="ca4fa5d4a9119b57d5f5241bb4e8e1e2" id="tgt139" class="tgtSentence">
                  <superscript>1</superscript> für Business Premium, gelten einige Clienteinschränkungen: können Sie Inhalte zu schützen und geschützte Inhalte mit RMS mit Outlook Web App und die RMS-Freigabe-app benutzen.</caps:sentence>
                <caps:sentence sentenceid="3f4d5ff29bdf24d70ef64926fb6f2d95" id="tgt140" class="tgtSentence"> Sie können geschützten Inhalte nutzen, mit allen Office-Anwendungen, einschließlich Office Online und Clientanwendungen für Office 365 Business Premium.</caps:sentence>
              </para>
            </content>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence sentenceid="3dada344d752db976eb36cfba1caa60e" id="tgt141" class="tgtSentence">RMS für Einzelpersonen-Abonnement</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="e0459ef23c7568dc7f1b7e6670f5e941" id="tgt142" class="tgtSentence">Dieses Abonnement ist für Personen in einer Organisation ausgelegt, die Azure RMS oder AD RMS bereitgestellt noch nicht.</caps:sentence>
                <caps:sentence sentenceid="c80028961c098d8bb9b6cd7f02b007bd" id="tgt143" class="tgtSentence"> Es ermöglicht diesen Personen, die das Lesen von Inhalt, der von einer Organisation geschützt wurden, die Azure RMS verwendet, und sie können auch ihre eigenen Inhalte schützen.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt144" class="tgtSentence">Weitere Informationen finden Sie unter <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>.</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_AzureADTenant">
        <title>
          <caps:sentence sentenceid="b328c43184d02a0b27f5674853141e17" id="tgt145" class="tgtSentence">Azure AD-Verzeichnis</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="9bd8893a6073e26a81814d2ed94e2276" id="tgt146" class="tgtSentence">Sie benötigen ein Windows Azure AD Azure RMS verwenden.</caps:sentence>
            <caps:sentence sentenceid="deff830ced0fd95992812309b5bbf1b7" id="tgt147" class="tgtSentence"> Sie verwenden Ihr Unternehmenskonto für dieses Verzeichnis im Azure-Verwaltungsportal anmelden, z. B. können Sie konfigurieren und Verwalten von Rights Management-Vorlagen.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="f323283adcc7c4d497a3c7488da0e3d0" id="tgt148" class="tgtSentence">Wenn Sie nicht bereits ein Azure-Abonnement für Ihre Organisation verfügen, erhalten Sie eine Anmeldung für eine kostenlose Testversion.: Wechseln Sie zu der <externalLink><linkText>Azure erste Schritte</linkText><linkUri>https://account.windowsazure.com/organization</linkUri></externalLink> Seite und führen Sie die Schritte.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e221d17daa908527d13b524a77b46764" id="tgt149" class="tgtSentence">Weitere Informationen finden Sie unter den folgenden Ressourcen in der Azure Active Directory-Dokumentation:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <legacyLink xlink:href="185da266-58a9-43e6-9c66-2c8f702545c6">
                  <caps:sentence sentenceid="9c31ccb68d9e34191a969d8226df35ad" id="tgt150" class="tgtSentence">Was ist ein Azure AD-Verzeichnis?</caps:sentence>
                </legacyLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <legacyLink xlink:href="edf05c2e-944a-4da5-a330-dc9dc479f127">
                  <caps:sentence sentenceid="f12e23101f4ed2bea7aa8d22a2fcd8cc" id="tgt151" class="tgtSentence">Wie Azure-Abonnements Azure AD zugeordnet sind</caps:sentence>
                </legacyLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="527336654b2a81cecdc18e07f406b5a6" id="tgt152" class="tgtSentence">Wenn Sie Ihre Azure AD-Verzeichnis in der lokalen integrieren möchten Active Directory-Gesamtstrukturen finden Sie unter <legacyLink xlink:href="bf82bdff-2467-403b-8c1a-0e9eebcf31e8">Verzeichnisintegration</legacyLink>.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="4e17081118ac7929bdcf29ec95bf2fc0" id="tgt153" class="tgtSentence">Wenn Sie mobile Geräte oder Macintosh-Computer, die lokal mit AD FS oder gleichwertige Authentifizierungsanbieter authentifizieren: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence sentenceid="b010c937525393425f999dc01fc5395c" id="tgt154" class="tgtSentence">Verwenden von AD FS muss auf die minimale Version der <embeddedLabel>Windows Server 2012 R2</embeddedLabel>, oder eine alternative Authentifizierungsanbieter das OAuth 2.0-Protokoll unterstützt.</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
        </content>
        <sections>
          <section address="BKMK_MFA">
            <title>
              <caps:sentence sentenceid="ee525442542c21e15c7c055d53a10ff7" id="tgt155" class="tgtSentence">Mehrstufige Authentifizierung (MFA) und Azure RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="6a21cd859b50308545db7b2b5719f38c" id="tgt156" class="tgtSentence">Verwendung von mehrstufigen erfordert die Authentifizierung (MFA) mit Azure RMS mindestens eines der folgenden: </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5ad99b8b2e1b9cdedf2a5685324574b1" id="tgt157" class="tgtSentence">Office 2013 (Mindestversion):</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="11c15ff19a7cf33378c00da69cb36c12" id="tgt158" class="tgtSentence">   Wenn Sie Office 2013 haben, müssen Sie auch Installieren der <externalLink><linkText>9 Juni 2015 aktualisieren für Office 2013 (KB3054853)</linkText><linkUri>https://support.microsoft.com/kb/3054853</linkUri></externalLink>.</caps:sentence>
                        <caps:sentence sentenceid="94a4a7a68e9630c59f7e197a0ee6afa7" id="tgt159" class="tgtSentence"> Weitere Informationen zu diesem aktualisieren und moderne Authentifizierung Active Directory-Authentifizierungsbibliothek ADAL basierende Anmeldung in Office 2013 bringt, finden Sie unter <externalLink><linkText>Office 2013 moderne Authentifizierung public Preview-Version angekündigt</linkText><linkUri>https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/</linkUri></externalLink>  im Office-Blog.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="1f7460a65ada82cad4a6fa20563665e3" id="tgt160" class="tgtSentence">Rights Management-freigabeanwendung für Windows: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="c8f2a5042cbd44816358c2c20d6673b5" id="tgt161" class="tgtSentence">Sie müssen die Mindestversion des 1.0.1908.0, installiert haben das bestätigt werden kann, mithilfe der Systemsteuerung unter Programme und Funktionen.</caps:sentence>
                        <caps:sentence sentenceid="64e49bbb03eb45c56672f4e0c57740a4" id="tgt162" class="tgtSentence"> Weitere Informationen zur freigabeanwendung finden Sie unter  <link xlink:href="7d8a8abe-6de1-4088-90ee-e0c4bd6deec8">Rights Management Sharing Application for Windows</link>.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="90f3b88216d7bae5b2efe55a6c9669cb" id="tgt163" class="tgtSentence">Verwaltung von Informationsrechten Freigabe-app für mobile Geräte und Macintosh-Computer: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ec6074f1dbb1b6b51ec229d91fd41d41" id="tgt164" class="tgtSentence">Stellen Sie sicher, dass Sie die neueste Version installiert haben.</caps:sentence>
                        <caps:sentence sentenceid="ef66e7ca4dbb7338c9b8895fa5d2ae30" id="tgt165" class="tgtSentence"> MFA-Unterstützung wurde in der September 2015 Version des RMS-Freigabe-app.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="837e9a1a4d03b2a5e5d0e4b553371972" id="tgt166" class="tgtSentence">Konfigurieren Sie dann die MFA-Lösung:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="93442e4f3433b2283fe1f2e3fdba8e8f" id="tgt167" class="tgtSentence">Microsoft verwaltet Mandanten (Sie haben Azure Active Directory oder Office 365):  </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="d6cca4f952abbbf49b56458a5d80afb9" id="tgt168" class="tgtSentence">Konfigurieren von Azure MFA um MFA für Benutzer zu erzwingen.</caps:sentence>
                        <caps:sentence sentenceid="dba73f72c649c5a7c9a7b7f3cb9b69ff" id="tgt169" class="tgtSentence"> Eine Anleitung finden Sie unter <externalLink><linkText>Erste Schritte mit Multi-Factor Authentication in der Cloud</linkText><linkUri>https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/</linkUri></externalLink> aus der Azure-Dokumentation.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="3dc72bfde9da2b5e4bb80ad0d1b5417d" id="tgt170" class="tgtSentence">Weitere Informationen zu Azure MFA, finden Sie unter <externalLink><linkText>Neuigkeiten von Multi-Factor Authentication?</linkText><linkUri>https://azure.microsoft.com/documentation/articles/multi-factor-authentication/</linkUri></externalLink></caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt171" class="tgtSentence">
                    <para>Verbundenen Mandanten (Sie betreiben Verbund lokal):  </para> <list class="bullet"><listItem><para>der Verbundserver für Azure Active Directory oder Office 365 konfigurieren. Z. B. Wenn Sie AD FS verwenden, finden Sie unter <externalLink><linkText>Konfigurieren zusätzlicher Authentifizierungsmethoden für AD FS</linkText><linkUri>https://technet.microsoft.com/library/dn758113.aspx</linkUri></externalLink> auf TechNet.  </para><para> Weitere Informationen zu diesem Szenario finden Sie unter  <externalLink><linkText>das funktioniert mit Office 365 – Identity-Programm jetzt optimierte</linkText><linkUri>https://blogs.office.com/2014/01/30/the-works-with-office-365-identity-program-now-streamlined/</linkUri></externalLink> im Office-Blog. </para></listItem></list></caps:sentence>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_SupportedDevices">
        <title>
          <caps:sentence sentenceid="8e22d2c73882e31e858720e2bddbf8d7" id="tgt172" class="tgtSentence">Client-Geräte, die Azure RMS unterstützen</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="773f675ac91c63242a4ff791228a7f2b" id="tgt173" class="tgtSentence">Verwenden Sie in den folgenden Abschnitten, um zu identifizieren, welche Geräte Azure Rights Management (RMS) unterstützen und welche RMS-Funktionen unterstützen:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_RMSSupportedComputers">Computers</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_RMSSupportedMobileDevices">Mobile devices</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link>
              </para>
            </listItem>
          </list>
        </content>
        <sections>
          <section address="BKMK_RMSSupportedComputers">
            <title>
              <caps:sentence sentenceid="524164822d03894ee68052e183e7ea36" id="tgt174" class="tgtSentence">Computer</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="b93d7de66bfeaa9451c786e46918fba6" id="tgt175" class="tgtSentence">Die folgende Computerbetriebssysteme unterstützen Azure Rights Management:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5d9525b0080c322804c52f61bda40f48" id="tgt176" class="tgtSentence">
                      <legacyBold>Windows 7</legacyBold> (X 86, X 64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5d9525b0080c322804c52f61bda40f48" id="tgt177" class="tgtSentence">
                      <legacyBold>Windows 8</legacyBold> (X 86, X 64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5d9525b0080c322804c52f61bda40f48" id="tgt178" class="tgtSentence">
                      <legacyBold>Windows 8.1</legacyBold> (X 86, X 64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5d9525b0080c322804c52f61bda40f48" id="tgt179" class="tgtSentence">
                      <legacyBold>Windows 10</legacyBold> (X 86, X 64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="b50f23a72df22c7776bd8726c7592447" id="tgt180" class="tgtSentence">
                      <legacyBold>Mac OS X</legacyBold>: Mindestversion von Mac OS X 10.8 (Mountain Lion)</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_RMSSupportedMobileDevices">
            <title>
              <caps:sentence sentenceid="09156eaf9ed2f5e3235fae84f05a0fad" id="tgt181" class="tgtSentence">Mobile Geräte</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="e19ad7621fb16405e830eaf225a99f2a" id="tgt182" class="tgtSentence">Die folgenden Betriebssysteme für mobile Geräte unterstützen Azure Rights Management:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="0f94e653367db79f409bd3589f554697" id="tgt183" class="tgtSentence">
                      <legacyBold>Windows Phone</legacyBold>: Windows Phone 8.1</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="c4a2774af623dc8aa90f7122df13dfc8" id="tgt184" class="tgtSentence">
                      <legacyBold>Android-Telefone und Tablets</legacyBold>: Mindestversion von Android 4.0.3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="7a41fd6d806cc8e2efd1925e47048d08" id="tgt185" class="tgtSentence">
                      <legacyBold>iPhone und iPad</legacyBold>: Mindestversion von iOS 7.0 </caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d12ed113430da5c28325293734dd9ddc" id="tgt186" class="tgtSentence">
                      <legacyBold>Windows RT-tablets</legacyBold>: Windows 8 RT, Windows 8.1 RT</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_ClientCapabilities">
            <title>
              <caps:sentence sentenceid="62d9babcd883c10ef00821f2eff3875d" id="tgt187" class="tgtSentence">Clientgerätefunktionen</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="3d08797feecd3411583b7766174d6602" id="tgt188" class="tgtSentence">Nicht alle unterstützten Clientgeräte unterstützen zurzeit alle RMS-Funktionen.</caps:sentence>
                <caps:sentence sentenceid="4ae3c1687697dc6219af9333884b1cf9" id="tgt189" class="tgtSentence"> Verwenden Sie die folgende Tabelle, um zu identifizieren, welche Anwendung die RMS-Funktionen sowie die Ausnahmen zu unterstützen.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="598bd16e11c930efe47b9576210230ca" id="tgt190" class="tgtSentence">Sofern nicht anders angegeben, gelten die unterstützten Funktionen zu Azure RMS und AD RMS.</caps:sentence>
                <caps:sentence sentenceid="1eda8696ca245ac284e77dc6525b01a8" id="tgt191" class="tgtSentence"> Außerdem erfordert das AD RMS-Unterstützung für iOS, Android, OS X und Windows Phone 8.1 <externalLink><linkText>Active Directory Rights Management Services Mobile Device Extension</linkText><linkUri>http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341</linkUri></externalLink>.</caps:sentence>
              </para>
              <para></para>
              <para>
                <caps:sentence sentenceid="5231ded67666805b5cb95edf8185602f" id="tgt192" class="tgtSentence">Informationen zu den Tabellenspalten:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="457ef3ff199bdfd658600a2da929466b" id="tgt193" class="tgtSentence">
                      <embeddedLabel>Geschützte PDF-</embeddedLabel>: Dateien, die Erweiterung .ppdf aufweisen und bei Verwendung die RMS-Freigabe von Office-Dateien und PDF-Dateien gemeinsam nutzen werden automatisch per e-Mail erstellt.</caps:sentence>
                    <caps:sentence sentenceid="e3dd543b342350cff5a6960597b45658" id="tgt194" class="tgtSentence"> Die RMS-freigabeanwendung enthält einen Reader für geschützte PDF-Dateien.</caps:sentence>
                    <caps:sentence sentenceid="00abeb1f2c210847fd0ba601762105fe" id="tgt195" class="tgtSentence"> Wenn Sie PDF-Dateien erstellt, die Sie mithilfe von Azure RMS oder AD RMS geschützt ist, können Sie zuvor weiterhin diese Dateien auf Windows-, IOS- und Android-Geräte mit Foxit Reader und Nitro Pro gelesen.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d6ec250d139538263889616f1fe8edb3" id="tgt196" class="tgtSentence">
                      <embeddedLabel>E-Mail:</embeddedLabel> aufgeführte e-Mail-Clients können die e-Mail-Nachricht, die angehängten Dateien automatisch schützen schützen.</caps:sentence>
                    <caps:sentence sentenceid="eb33614c3e5f923ea45df1a2add9feaf" id="tgt197" class="tgtSentence"> In diesem Szenario kann die Client-Vorschaufunktion autorisierte Empfänger den geschützten Inhalt (Nachrichten und Anlagen) anzeigen.</caps:sentence>
                    <caps:sentence sentenceid="2f65adb8791da12ba5845c844f9980da" id="tgt198" class="tgtSentence"> Jedoch nicht möglich, wenn eine e-Mail-Nachricht selbst ist nicht geschützt, aber die Anlage ist geschützt, Vorschaufunktion für den Client geschützte Anlage an autorisierte Empfänger angezeigt.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="531949b924e1f95982e408a05e44be54" id="tgt199" class="tgtSentence">
                      <embeddedLabel>Andere Dateitypen</embeddedLabel>: Text- und Image-Dateien sind Dateien, die eine wie z. B. txt, XML, JPG und Jpeg Erweiterung.</caps:sentence>
                    <caps:sentence sentenceid="eb97066399f8ac62b39a1a6190570be5" id="tgt200" class="tgtSentence"> Diese Dateien ihre Erweiterung ändern, nachdem diese systemintern durch RMS geschützt werden und sind schreibgeschützt.</caps:sentence>
                    <caps:sentence sentenceid="77d668d686c54814abbc582b8fa8c5c1" id="tgt201" class="tgtSentence"> Dateien, die nicht systemintern geschützt werden können haben die Erweiterung "pFile", nachdem sie i. d. r. durch RMS geschützt sind.</caps:sentence>
                    <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt202" class="tgtSentence"> Weitere Informationen finden Sie unter der <externalLink><linkText>Maß an Schutz – systemeigen und generisch</linkText><linkUri>https://technet.microsoft.com/library/dn339003.aspx#BKMK_LevelsofProtection</linkUri></externalLink> und <externalLink><linkText>unterstützte Dateitypen und Dateinamenerweiterungen</linkText><linkUri>https://technet.microsoft.com/library/dn339003.aspx#BKMK_SupportFileTypes</linkUri></externalLink> Abschnitte aus der <externalLink><linkText>Rights Management-freigabeanwendung – Administratorhandbuch</linkText><linkUri>http://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="4e93489ed32720f5b3b06378b95be14e" id="tgt203" class="tgtSentence">Betriebssystem des Geräts</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="13b9b5c6c817407657cf5d795276d9ec" id="tgt204" class="tgtSentence">Word, Excel, PowerPoint</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="3ece160efbb7bfeb1cc83781ee1e2cc8" id="tgt205" class="tgtSentence">Geschützte PDF-Datei</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0c83f57c786a0b4a39efab23731c7ebc" id="tgt206" class="tgtSentence">E-Mail</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="6ce506f4bfccfedd0b6188250fadfa14" id="tgt207" class="tgtSentence">Andere Dateitypen</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="0f4137ed1502b5045d6083aa258b5c42" id="tgt208" class="tgtSentence">Windows</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="88ba9a5db4381e67ac6a926dbf2d2731" id="tgt209" class="tgtSentence">Office 2010</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="5b55d95e99738893f9e21b8ab549a4d7" id="tgt210" class="tgtSentence">Office 2013</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="4ab49362a8083bb16a0ad41b09aee447" id="tgt211" class="tgtSentence">Office 2016</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="35211d695941bf971d1cd27dd99b7cff" id="tgt212" class="tgtSentence">Office Mobile apps (nur Azure RMS)<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0de9cd6748752e254c764f8901f6fd75" id="tgt213" class="tgtSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="4d3ff708a1209f84b9f45c80e9d5852c" id="tgt214" class="tgtSentence">Gaaiho-Dokument</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="fcb1f98c4b33c5ce44128d99d5b099a4" id="tgt215" class="tgtSentence">GigaTrust-Desktopclient-PDF-Datei für Adobe</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="5ce469159b01ddbda928094c54d38632" id="tgt216" class="tgtSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="85fb904711ece0c19939afe097d7c544" id="tgt217" class="tgtSentence">Nitro PDF-Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt218" class="tgtSentence">RMS-Freigabe-app</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="9593b9ad83ce1e6003a0470f68da36ad" id="tgt219" class="tgtSentence">Outlook 2010</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="543660823d2794011d7718bce38a22b5" id="tgt220" class="tgtSentence">Outlook 2013</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="4cbc27fd6367a7d4b74123fe966eda95" id="tgt221" class="tgtSentence">Outlook 2016</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a6f0a6603a27e44aee9f20ad820a3958" id="tgt222" class="tgtSentence">Outlook Web App (OWA)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="ce4ed4a40c6872d729ad2ab9523f2e3f" id="tgt223" class="tgtSentence">Windows Mail<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="a0357a7a9b5d88a591c9ae45d9aeea5a" id="tgt224" class="tgtSentence">RMS-freigabeanwendung für Windows: Text, Bilder, Pfile</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="f0b9438122f0000c2b214dbddc615906" id="tgt225" class="tgtSentence">Siemens JT2Go: JT-Dateien (nur Windows-10)</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="9e304d4e8df1b74cfa009913198428ab" id="tgt226" class="tgtSentence">iOS</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="a13da4635e41a9a7908df9bd7ab96e87" id="tgt227" class="tgtSentence">Office für iPad und iPhone<superscript>4</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0de9cd6748752e254c764f8901f6fd75" id="tgt228" class="tgtSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="082f7253a977de963f70f10dce33b3ec" id="tgt229" class="tgtSentence">TITUS Dokumente</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="8d702f925880c07f26abec7874fadf38" id="tgt230" class="tgtSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt231" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="082f7253a977de963f70f10dce33b3ec" id="tgt232" class="tgtSentence">TITUS Dokumente</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="3027dc3ef6ccf80cb15b57ee49993b03" id="tgt233" class="tgtSentence">NitroDesk</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="2e4e2f8679e652abac7579a15e3eef05" id="tgt234" class="tgtSentence">Outlook für iPad und iPhone<superscript>3</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="f8c00e44e7a1ffbe7fe6926e74289116" id="tgt235" class="tgtSentence">OWA für iOS </caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="cf3fce79947a9b027700dbdc54d21a03" id="tgt236" class="tgtSentence">Sichern von Inseln IQProtector<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="1c4d2875ff2c8902d3c578110a9ee564" id="tgt237" class="tgtSentence">TITUS Mail</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt238" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript>: Text, Bilder, Pfile</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="fe90a94383df165b267298c385fc6a3b" id="tgt239" class="tgtSentence">TITUS Dokumente: Pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="c31b32364ce19ca8fcd150a417ecce58" id="tgt240" class="tgtSentence">Android</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="5698f8cb4aee45f2a6cfc3efcde3740d" id="tgt241" class="tgtSentence">GigaTrust App für Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0de9cd6748752e254c764f8901f6fd75" id="tgt242" class="tgtSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="5698f8cb4aee45f2a6cfc3efcde3740d" id="tgt243" class="tgtSentence">GigaTrust App für Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="8d702f925880c07f26abec7874fadf38" id="tgt244" class="tgtSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt245" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="c06662ad06c9d97848e9745bae16a278" id="tgt246" class="tgtSentence">9Folders</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="5698f8cb4aee45f2a6cfc3efcde3740d" id="tgt247" class="tgtSentence">GigaTrust App für Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="3027dc3ef6ccf80cb15b57ee49993b03" id="tgt248" class="tgtSentence">NitroDesk</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="78a835e6a63076c593beb550cd83d5a3" id="tgt249" class="tgtSentence">OWA für Android<superscript>5</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="f67567a6a0b91bdcaf2a7baf149e0d27" id="tgt250" class="tgtSentence">Samsung Email (S3 und höher)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="cf3fce79947a9b027700dbdc54d21a03" id="tgt251" class="tgtSentence">Sichern von Inseln IQProtector<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c548ad86fd1d9102811036453a3772c9" id="tgt252" class="tgtSentence">TITUS Klassifizierung für mobile Geräte</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt253" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript>: Text, Bilder, Pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="e23d57179ebc32a0e320e72f42032c21" id="tgt254" class="tgtSentence">OS X</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <para></para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="f5030e69296aff3bba415d770f039780" id="tgt255" class="tgtSentence">Office 2011 (nur AD RMS)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0122fcadbca90628e8afc51ea472b9a1" id="tgt256" class="tgtSentence">2016 von Office für Mac</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0de9cd6748752e254c764f8901f6fd75" id="tgt257" class="tgtSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="8d702f925880c07f26abec7874fadf38" id="tgt258" class="tgtSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt259" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="6ad9105294bcc9179cef93964e2945b2" id="tgt260" class="tgtSentence">Outlook 2011 (nur AD RMS)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="e544789652a28d6c3d38515926350129" id="tgt261" class="tgtSentence">Outlook 2016 für Mac</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="fc7110617139d2ccf2013f6e1782f481" id="tgt262" class="tgtSentence">Outlook für Mac</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt263" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript>: Text, Bilder, Pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="94c0739f54e8886ceea4fe3078c068e3" id="tgt264" class="tgtSentence">Windows RT</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="650050f69b868a823c6b6132ebe9276a" id="tgt265" class="tgtSentence">Office 2013 RT</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0de9cd6748752e254c764f8901f6fd75" id="tgt266" class="tgtSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="cb3a4d67c4f997a68df8924b2b18d70d" id="tgt267" class="tgtSentence">Nicht unterstützt</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="e933860c9aa71845bfa634ade5eb8a0a" id="tgt268" class="tgtSentence">Outlook 2013 RT</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="d036fead104e3385f807517e047afff7" id="tgt269" class="tgtSentence">E-Mail-App für Windows</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="ce4ed4a40c6872d729ad2ab9523f2e3f" id="tgt270" class="tgtSentence">Windows Mail<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence sentenceid="75fee0e9488398f2247661c6357d312c" id="tgt271" class="tgtSentence">Siemens JT2Go: JT-Dateien</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt272" class="tgtSentence">
                          <embeddedLabel>Windows Phone 8.1</embeddedLabel> </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="4a602279385bfc03f86534cbbfaf00dd" id="tgt273" class="tgtSentence"> Office Mobile (nur AD RMS)</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt274" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="667da8107a5e99052f462cdc3c8633ea" id="tgt275" class="tgtSentence">Outlook Mobile</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a7b158a2d0974ff2cd00208291b28ea6" id="tgt276" class="tgtSentence">RMS-freigabeanwendung<superscript>1</superscript>: Text, Bilder, Pfile </caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="5054cf84f3f431856b927ec4615d80f6" id="tgt277" class="tgtSentence">BlackBerry 10</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="cb3a4d67c4f997a68df8924b2b18d70d" id="tgt278" class="tgtSentence">Nicht unterstützt</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="cb3a4d67c4f997a68df8924b2b18d70d" id="tgt279" class="tgtSentence">Nicht unterstützt</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="738702b3c65de8e89c1a97681a38ec16" id="tgt280" class="tgtSentence">BlackBerry-e-Mail<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="cb3a4d67c4f997a68df8924b2b18d70d" id="tgt281" class="tgtSentence">Nicht unterstützt</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence sentenceid="fd0a1e220f4796801ff2e8a37e68dc26" id="tgt282" class="tgtSentence">
                  <superscript>1</superscript> unterstützt geschützten Inhalte anzeigen.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="35d63adade823bb2d960264d01fad6a0" id="tgt283" class="tgtSentence">
                  <superscript>2</superscript> unterstützt die Anzeige von geschütztem Inhalt in SharePoint Online, OneDrive für Unternehmen und Outlook Web Access.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="5cc0b463c919e2d1af738b839da15323" id="tgt284" class="tgtSentence">
                  <superscript>3</superscript> verwendet Exchange ActiveSync IRM, der vom Exchange-Administrator aktiviert werden muss.</caps:sentence>
                <caps:sentence sentenceid="8434a0975516aac4d2d5e35ad3cf61a6" id="tgt285" class="tgtSentence"> Benutzer können anzeigen, Antworten und Antworten, dass alle für die geschützte e-Mail-Nachrichten aber Benutzer neue e-Mail-Nachrichten selbst nicht geschützt.</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="c004075b1eae82e10299b03cfb13d054" id="tgt286" class="tgtSentence">
                  <superscript>4</superscript> unterstützt das Anzeigen und Bearbeiten von geschützten Dokumenten.</caps:sentence>
                <caps:sentence sentenceid="120b427c64621a322ab92dcc3e4187e3" id="tgt287" class="tgtSentence"> Weitere Informationen finden Sie unter den folgenden Beitrag auf der Office-Blog: <externalLink><linkText>Azure Rights Management-Unterstützung darum geht, Office für iPad und iPhone</linkText><linkUri>https://blogs.office.com/2015/07/22/azure-rights-management-support-comes-to-office-for-ipad-and-iphone-2/</linkUri></externalLink></caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="6f8068403bd562e8caa6f43937cf8e0a" id="tgt288" class="tgtSentence">
                  <superscript>5</superscript> Weitere Informationen finden Sie unter den folgenden Beitrag auf der Office-Blog: <externalLink><linkText>OWA für Android jetzt verfügbar auf Medien auswählen</linkText><linkUri>http://blogs.office.com/2014/06/11/owa-for-android-now-available-on-select-devices/</linkUri></externalLink></caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence sentenceid="8ffea95f6af318e1890725f6451d0edd" id="tgt289" class="tgtSentence">Weitere Informationen über die bevorstehende RMS-Unterstützung in Office für verschiedene Plattformen finden Sie unter den folgenden Beitrag aus dem Office-Blog: <externalLink><linkText>Office überall, Verschlüsselung überall</linkText><linkUri>http://blogs.office.com/2015/02/18/office-everywhere-encryption-everywhere/</linkUri></externalLink></caps:sentence>
                </para>
              </alert>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_SupportedApplications">
        <title>
          <caps:sentence sentenceid="d3d6f5480f5ce788d09c906a6db21d4f" id="tgt290" class="tgtSentence">Clientanwendungen, die Azure RMS unterstützen</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="270325b16d84fd99e5b1841bf6e85626" id="tgt291" class="tgtSentence">Die folgenden Programme verfügen über systemeigene Unterstützung Azure RMS, was bedeutet, dass RMS eng in die Anwendung integriert ist, mithilfe von RMS-APIs zur Unterstützung von nutzungseinschränkungen.</caps:sentence>
            <caps:sentence sentenceid="7ab39079ea37a1fe9005603633cfabac" id="tgt292" class="tgtSentence"> Diese Programme werden auch als RMS-fähige bezeichnet:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="4538716ade865ed977129fff257f64a8" id="tgt293" class="tgtSentence">
                  <legacyBold>Microsoft Office-Anwendung</legacyBold> (Word, Excel, PowerPoint und Outlook) aus folgenden Suiten:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="ee54d000b635a58da2d2c3a0026c5cd2" id="tgt294" class="tgtSentence">Office 365 ProPlus</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="0ad3acbd6296e919999d40b9ebbffcd8" id="tgt295" class="tgtSentence">Office 365 Enterprise E3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="2fe02afc30d14eb1ab72b703add5d543" id="tgt296" class="tgtSentence">Office Professional 2016</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="19bb2a1fe0a286161d7e88c8c7d96997" id="tgt297" class="tgtSentence">Office Professional 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="622dd07f40f4452f57305fd73356f2c8" id="tgt298" class="tgtSentence">Office Professional 2010</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="942439d31c342f5de40971efec61f6e0" id="tgt299" class="tgtSentence">Spezifisch für Office Professional 2010: </caps:sentence>
                    </para>
                    <list class="bullet">
                      <listItem>
                        <para>
                          <caps:sentence sentenceid="fcda11d34633f7e89e9e9c19bac7662a" id="tgt300" class="tgtSentence">Windows-Computer müssen die Rights Management-freigabeanwendung für Windows installieren.</caps:sentence>
                        </para>
                      </listItem>
                      <listItem>
                        <para>
                          <caps:sentence sentenceid="07492f402cc55ea5340b3bfa82e59ad5" id="tgt301" class="tgtSentence">Diese Version von Office ist auf 10 von Windows nicht unterstützt.</caps:sentence>
                        </para>
                      </listItem>
                    </list>
                  </alert>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="695fd351d14b1b26c3ce588eff1e3ed3" id="tgt302" class="tgtSentence">Müssen Sie eine dieser Versionen Office zum Schützen von Inhalt, aber alle Versionen von Office 2016, Office 2013 oder Office 2010 können geschützte Inhalte benutzen.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <legacyBold>
                  <caps:sentence sentenceid="347cf84dae08a3d20cda58b732afc929" id="tgt303" class="tgtSentence">Die Rights Management-freigabeanwendung für Windows</caps:sentence>
                </legacyBold>
              </para>
              <para>
                <caps:sentence sentenceid="95440457835e887158c29f2f95455ad7" id="tgt304" class="tgtSentence">Weitere Informationen über die gemeinsame Nutzung von Rights Management-Anwendung für Windows finden Sie in den folgenden Ressourcen:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="45fd73cece8c888a3560a65a749417d4" id="tgt305" class="tgtSentence">Rights Management freigabeanwendung – Administratorhandbuch</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                    </externalLink>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="5a82d1d6328fcf4e332c7353808716e6" id="tgt306" class="tgtSentence">Rights Management freigabeanwendung – Benutzerhandbuch</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                    </externalLink>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <legacyBold>
                  <caps:sentence sentenceid="5d54b472c9702ad86de6d7dd29038fc3" id="tgt307" class="tgtSentence">Die Rights Management-freigabeanwendung für mobile Plattformen</caps:sentence>
                </legacyBold>
              </para>
              <para>
                <caps:sentence sentenceid="620c64b5a69fa119bc3106893d54d202" id="tgt308" class="tgtSentence">Weitere Informationen zur Rights Management-freigabeanwendung für mobile Plattformen finden Sie unter den folgenden Ressourcen:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="a61aff4e08fc69ae349966a0b85950cf" id="tgt309" class="tgtSentence">Laden Sie die relevante app über die Links auf der <externalLink><linkText>Microsoft Rights Management-Seite</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
                <!--Not to go live before  Intune goes out.-->
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="c969314f8b7fba2b561e01a2f472e2e1" id="tgt310" class="tgtSentence">Häufig gestellte Fragen zur Microsoft Rights Management-Freigabeanwendung für Mobile Plattformen</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/dn451248</linkUri>
                    </externalLink>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="853ae90f0351324bd73ea615e6487517" id="tgt311" class="tgtSentence">
                  <legacyBold>Andere Programme, die die RMS-APIs unterstützen</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="f10df79aefb2d37d058a1f9be29f3484" id="tgt312" class="tgtSentence">Line-of-Business-Anwendung, die intern mithilfe des RMS SDK geschrieben werden</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="fa1f88bd1cdca0b005dd65eda116f3ab" id="tgt313" class="tgtSentence">Anwendungen von Softwareherstellern, die mit dem RMS SDK geschrieben werden</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="ab67e2d027e033c41a44226f06bd9de6" id="tgt314" class="tgtSentence">Weitere Informationen zum SDK finden Sie unter der <externalLink><linkText>Microsoft Rights Management SDK</linkText><linkUri>http://msdn.microsoft.com/library/hh552972(v=vs.85).aspx</linkUri></externalLink>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="important">
            <para>
              <caps:sentence sentenceid="c69a78855f3cc328f1b36f147fe72eae" id="tgt315" class="tgtSentence">Die folgenden Programme sind nicht aktuell von Azure RMS unterstützt:</caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence sentenceid="dd9118f0e341d9f5cdcfc3a8c4221124" id="tgt316" class="tgtSentence">Microsoft Office für Mac 2011</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence sentenceid="c4b158c7a261ac44423975c60386e957" id="tgt317" class="tgtSentence">Microsoft OneDrive for Business für SharePoint Server 2013</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence sentenceid="6bbad4bd873b92c9eea6f68cdedbed37" id="tgt318" class="tgtSentence">XPS-Viewer </caps:sentence>
                </para>
              </listItem>
            </list>
            <para>
              <caps:sentence sentenceid="ecd8497ea6d0ddd6fbedfc6f8238ec3a" id="tgt319" class="tgtSentence">Darüber hinaus hat die RMS-Freigabe-Anwendung die folgenden Einschränkungen: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence sentenceid="b92436c0e21fa15e51af9088299e468d" id="tgt320" class="tgtSentence">Für Windows-Computer: erfordert eine minimale Version von Windows 7 Service Pack 1</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
          <para>
            <caps:sentence sentenceid="1448fffc95376631bd6e0b8da4af1bde" id="tgt321" class="tgtSentence">Weitere Informationen dazu, wie diese Anwendung für Azure RMS unterstützen, finden Sie unter <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="a0f847d1a3019b66f3de5359674ee82f" id="tgt322" class="tgtSentence">Weitere Informationen dazu, wie Sie diese konfigurieren, finden Sie unter <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_SupportedServers">
        <title>
          <caps:sentence sentenceid="d22971b31f07289c47db52c89e420051" id="tgt323" class="tgtSentence">Auf lokalen Servern, die Azure RMS unterstützen</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="022ee6e4743697c6f6c9c36eb9c9ba23" id="tgt324" class="tgtSentence">Die folgenden lokalen Serverprodukte werden mit Azure RMS unterstützt, bei Verwendung von Azure RMS-Verbindungsdienst als Kommunikationsschnittstelle (Relay) zwischen dem lokalen Server und Azure RMS fungiert.</caps:sentence>
            <caps:sentence sentenceid="59d0721e9792f307d170e678a53b334c" id="tgt325" class="tgtSentence"> Diese Konfiguration ist außerdem erforderlich, dass Sie verzeichnissynchronisierung zwischen Ihren Active Directory-Gesamtstrukturen und Azure Active Directory konfigurieren.</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="853ae90f0351324bd73ea615e6487517" id="tgt326" class="tgtSentence">
                  <legacyBold>Exchange Server</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="6f17073a076d1ff64e48c91e4ed251f5" id="tgt327" class="tgtSentence">Exchange Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="4217917de6c688f8299332f87a88efbf" id="tgt328" class="tgtSentence">Exchange Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="853ae90f0351324bd73ea615e6487517" id="tgt329" class="tgtSentence">
                  <legacyBold>Office SharePoint Server</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="e98cf53ecb231010049de77a49956da0" id="tgt330" class="tgtSentence">Office SharePoint Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="7ecb93c078d5936d9bf6465ca938c6e5" id="tgt331" class="tgtSentence">Office SharePoint Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="853ae90f0351324bd73ea615e6487517" id="tgt332" class="tgtSentence">
                  <legacyBold>Datei-Servern, die unter Windows Server ausgeführt, und verwenden die Datei Klassifizierung Infrastruktur (FCI)</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="6a1ce5410a25455ba96c0039133a4184" id="tgt333" class="tgtSentence">Windows Server 2012 R2</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="10232bdd21fab9e807ecb09c39a95b20" id="tgt334" class="tgtSentence">Windows Server 2012 R2</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="788813301daca0ca05789e2340451881" id="tgt335" class="tgtSentence">Da Dateiserver, auf denen Windows Server 2008 R2 ausgeführt wird, keinen integrierten Management Task Dateivorgang RMS-Schutz angewendet haben, kann nicht der RMS-Verbindungsdienst für dieses Szenario verwendet werden.</caps:sentence>
                  <caps:sentence sentenceid="b43a622bac008ce7e2d62835d7bdb3eb" id="tgt336" class="tgtSentence"> Allerdings können Dateiklassifizierungsinfrastruktur und Azure RMS unter diesen Betriebssystemen Sie konfigurieren eine benutzerdefinierten Dateiverwaltungsaufgabe zum Ausführen einer ausführbaren Datei oder ein Skript, das Dateien mithilfe von Azure RMS schützen kann.</caps:sentence>
                  <caps:sentence sentenceid="c95cf0d81c905621fa8a3d34c45baf3a" id="tgt337" class="tgtSentence"> Beispielsweise ein Windows PowerShell-Skript, verwendet die <externalLink><linkText>RMS-Schutz Cmdlets</linkText><linkUri>https://msdn.microsoft.com/library/azure/mt433195.aspx</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="0c05bce2a2fbb97338316cd135307c48" id="tgt338" class="tgtSentence">Sie können diese Cmdlets auch mit Servern, die mit höheren Versionen von Windows Server mit den Vorteil, dass diese Cmdlets alle Dateitypen schützen können.</caps:sentence>
                  <caps:sentence sentenceid="9f4ba09ccff25700777f8383a4691c5a" id="tgt339" class="tgtSentence"> Der RMS-Verbindungsdienst schützt nur Office-Dateien.</caps:sentence>
                  <caps:sentence sentenceid="0cfc1d81f3cb999091b03248c9c1bcfe" id="tgt340" class="tgtSentence"> Schrittweise Anleitung finden Sie unter <link xlink:href="9aa693db-9727-4284-9f64-867681e114c9">RMS Protection with Windows Server File Classification Infrastructure (FCI)</link>.</caps:sentence>
                </para>
              </alert>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="1eb2616fc6d3a12aaa2b91b8eca3dfab" id="tgt341" class="tgtSentence">Der RMS-Verbindungsdienst wird unter Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 unterstützt.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e15a068a45afeb6ffe9cca55a23d57c4" id="tgt342" class="tgtSentence">Weitere Informationen dazu, wie Sie den RMS-Verbindungsdienst für diese lokalen Server konfigurieren, finden Sie unter <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">To deploy Microsoft Azure Rights Management (Azure RMS) in your organization, make sure that you have the following prerequisites.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> You can then use the <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> to deploy Rights Management for your organization.</caps:sentence>
        </para>
        <table>
          <thead>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src3" class="srcSentence">Requirement</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src4" class="srcSentence">More information</caps:sentence>
                </para>
              </TD>
            </tr>
          </thead>
          <tbody>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src5" class="srcSentence">A cloud subscription for RMS</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src6" class="srcSentence">Your organization must have a cloud subscription that supports RMS.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src7" class="srcSentence">For licensing information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in this topic.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src8" class="srcSentence">Azure AD directory </caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src9" class="srcSentence">Your organization must have an Azure AD directory to support user authentication for RMS.</caps:sentence>
                  <caps:sentence id="src10" class="srcSentence"> In addition, if you want to use your user accounts from your on-premises directory (AD DS), you must also configure directory integration.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src11" class="srcSentence">Multi-factor authentication (MFA) is supported with Azure RMS when you have the required client software and correctly configured     MFA supporting infrastructure.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src12" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_AzureADTenant">Azure AD directory</link> section in this topic.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src13" class="srcSentence">Client devices</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src14" class="srcSentence">Users must have a client devices (computer or mobile device) that run an operating system that supports RMS.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src15" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedDevices">Client devices that support Azure RMS</link> section in this topic.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src16" class="srcSentence">Applications</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src17" class="srcSentence">Users must run applications that support RMS.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src18" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link> section in this topic.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src19" class="srcSentence">Infrastructure that supports connectivity to the Internet and dependent cloud services</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src20" class="srcSentence">If you have a firewall or similar intervening network devices that must be configured to allow specific connections, see <externalLink><linkText>Office 356 URLs and IP address ranges</linkText><linkUri>https://support.office.com/en-US/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src21" class="srcSentence">The list of URLs and IP addresses in the <embeddedLabel>Office 356 portal and identity</embeddedLabel> section apply to the Office 365 portal, Azure Active Directory resources, and Azure Rights Management.</caps:sentence>
                  <caps:sentence id="src22" class="srcSentence"> Use the instructions in this article to keep up-to-date with changes to this information, by subscribing to an RSS feed.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src23" class="srcSentence">In addition to the information in the Office article, specific to Azure RMS:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src24" class="srcSentence">Do not terminate the TLS client-to-service connection (for example, to do packet-level inspection).</caps:sentence>
                      <caps:sentence id="src25" class="srcSentence"> Doing so breaks the certificate pinning that RMS clients use with Microsoft-managed CAs to help secure their communication with Azure RMS.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src26" class="srcSentence">Do not use a web proxy configuration that authenticates on behalf of a user.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
          </tbody>
        </table>
        <para> </para>
        <para>
          <caps:sentence id="src27" class="srcSentence">If you want to use Azure RMS with on-premises servers, the following products are supported:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence id="src28" class="srcSentence">Exchange Server</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src29" class="srcSentence">SharePoint Server</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src30" class="srcSentence">Windows Server file servers that support File Classification Infrastructure</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence id="src31" class="srcSentence">For information about the additional Azure RMS requirements for this scenario, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedServers">On-premises servers that support Azure RMS</link> section in this topic.</caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence id="src32" class="srcSentence">The following deployment scenario is not supported: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src33" class="srcSentence">Running AD RMS and Azure RMS side-by-side in the same organization, except during migration, as described in <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src34" class="srcSentence">There is a supported migration path <externalLink><linkText>from AD RMS to Azure RMS</linkText><linkUri>http://technet.microsoft.com/library/Dn858447.aspx</linkUri></externalLink>, and from <externalLink><linkText>Azure RMS to AD RMS</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629429.aspx</linkUri></externalLink>.</caps:sentence>
            <caps:sentence id="src35" class="srcSentence"> If you deploy Azure RMS and then decide that you no longer want to use this cloud service, see <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Deactivating Azure Rights Management</link>.</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence id="src36" class="srcSentence">Use the following sections to learn more about the Azure RMS requirements.</caps:sentence>
        </para>
      </introduction>
      <section address="BKMK_SupportedSubscriptions">
        <title address="BKMK_Subscriptions">
          <caps:sentence id="src37" class="srcSentence">Cloud subscriptions that support Azure RMS</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src38" class="srcSentence">To use Azure RMS, your organization must have at least one of the following subscriptions with a sufficient number of licenses for users and services that will protect files and email messages.</caps:sentence>
            <caps:sentence id="src39" class="srcSentence"> If you have a service that will apply protection for users (owners of the files or email messages), those users require one of these licenses.</caps:sentence>
            <caps:sentence id="src40" class="srcSentence"> Users who will only consume (for example, read and edit) this protected data do not need a license.</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src41" class="srcSentence">Office 365</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src42" class="srcSentence">Azure Rights Management Premium (formerly Azure RMS Standalone)</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src43" class="srcSentence">Enterprise Mobility Suite</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src44" class="srcSentence">RMS for individuals</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src45" class="srcSentence">Use the following sections for more information and sign up options.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src46" class="srcSentence">For a licensing comparison of the Azure RMS capabilities for the paid subscriptions, see <externalLink><linkText>Comparison of Rights Management Services (RMS) Offerings</linkText><linkUri>http://technet.microsoft.com/dn858608</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
        <sections>
          <section expanded="false">
            <title>
              <caps:sentence id="src47" class="srcSentence">Office 365 subscription</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src48" class="srcSentence">Free 30-day trial: Enterprise E3</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/p/?LinkID=403802</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence id="src49" class="srcSentence">This subscription is designed for organizations who want to use the Office online services and use their Information Rights Management feature, which uses Azure RMS.</caps:sentence>
                <caps:sentence id="src50" class="srcSentence"> However, not all Office 365 subscriptions include Azure RMS.</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src51" class="srcSentence">Licensing option</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src52" class="srcSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src53" class="srcSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src54" class="srcSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src55" class="srcSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src56" class="srcSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src57" class="srcSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src58" class="srcSentence">Office 365 Government G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src59" class="srcSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src60" class="srcSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src61" class="srcSentence">Office 365 Government G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src62" class="srcSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src63" class="srcSentence">SharePoint Plan 1<br /><br />SharePoint Plan 2</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src64" class="srcSentence">Exchange Online Plan 1<br /> <br />Exchange Online Plan 2</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src65" class="srcSentence">Information Rights Protection (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src66" class="srcSentence">No</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src67" class="srcSentence">No </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src68" class="srcSentence">No</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src69" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src70" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src71" class="srcSentence">No</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src72" class="srcSentence">No</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src73" class="srcSentence">No</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence id="src74" class="srcSentence">Azure Rights Management Premium subscription</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src75" class="srcSentence">Free 30-day trial</caps:sentence>
                  </linkText>
                  <linkUri>https://portal.microsoftonline.com/Signup/MainSignUp15.aspx?&amp;OfferId=A43415D3-404C-4df3-B31B-AAD28118A778&amp;dl=RIGHTSMANAGEMENT&amp;ali=1</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence id="src76" class="srcSentence">This subscription was formerly known as Azure RMS Standalone and it is designed for organizations that want to use Azure RMS but don’t have subscription that includes Azure RMS.</caps:sentence>
                <caps:sentence id="src77" class="srcSentence"> For example, if you have a subscription for Office 365 Business Essentials or Office 365 Enterprise E1, these subscriptions do not include Azure RMS (see the table in the preceding section).</caps:sentence>
                <caps:sentence id="src78" class="srcSentence"> To use Azure RMS, you could purchase a subscription for Azure Rights Management Premium (or purchase another subscription, such as Office 365 Enterprise E4, that includes Azure RMS).</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src79" class="srcSentence">For more information, see <externalLink><linkText>Microsoft Azure Rights Management</linkText><linkUri>http://products.office.com/business/microsoft-azure-rights-management</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src80" class="srcSentence">This subscription also offers a trial period for you to try out Azure RMS for 25 users, at no charge.</caps:sentence>
                <caps:sentence id="src81" class="srcSentence"> If the subscription expires before you purchase a replacement subscription, see the following section, “What happens when the trial subscription expires?”</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src82" class="srcSentence">Licensing option</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src83" class="srcSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src84" class="srcSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src85" class="srcSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src86" class="srcSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src87" class="srcSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src88" class="srcSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src89" class="srcSentence">Office 365 Government G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src90" class="srcSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src91" class="srcSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src92" class="srcSentence">Office 365 Government G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src93" class="srcSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src94" class="srcSentence">SharePoint Plan 1<br /> <br />SharePoint Plan 2</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src95" class="srcSentence">Exchange Online Plan 1<br /> <br />Exchange Online Plan 2</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src96" class="srcSentence">Information Rights Protection (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src97" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src98" class="srcSentence">Yes <superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src99" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src100" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src101" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src102" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src103" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src104" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence id="src105" class="srcSentence">
                  <superscript>1</superscript> For Business Premium, there are some client restrictions: You can protect content and consume protected content with RMS by using the Outlook Web App and the RMS sharing app.</caps:sentence>
                <caps:sentence id="src106" class="srcSentence"> You can consume protected content by using all other Office applications, which includes Office Online and the client applications for Office 365 Business Premium.</caps:sentence>
              </para>
            </content>
            <sections>
              <section address="BKMK_TrialExpiryBehavior">
                <title>
                  <caps:sentence id="src107" class="srcSentence">What happens when the trial subscription expires?</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src108" class="srcSentence">If your trial subscription expires, you will lose access to content that was protected by using your trial subscription for Azure RMS.</caps:sentence>
                    <caps:sentence id="src109" class="srcSentence"> However, if you then purchase a subscription that supports Azure RMS, access is automatically restored.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src110" class="srcSentence">An exception to losing access upon expiry is if your organization used Azure RMS with the RMS for individuals subscription before you obtained the trial subscription.</caps:sentence>
                    <caps:sentence id="src111" class="srcSentence"> Then, access to previously protected content remains, even after the trial subscription expires.</caps:sentence>
                  </para>
                </content>
              </section>
            </sections>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence id="src112" class="srcSentence">Enterprise Mobility Suite subscription</caps:sentence>
            </title>
            <content>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src113" class="srcSentence">Free 30-day trial</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/?LinkId=615385</linkUri>
                </externalLink>
              </para>
              <para>
                <caps:sentence id="src114" class="srcSentence">This subscription is designed for organizations who want to use a combination of Azure Active Directory Premium, Windows Intune, and Azure Rights Management.</caps:sentence>
                <caps:sentence id="src115" class="srcSentence"> For more information, see the <externalLink><linkText>Microsoft Enterprise Mobility Overview</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=615386</linkUri></externalLink>.</caps:sentence>
              </para>
              <para></para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src116" class="srcSentence">Licensing option</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src117" class="srcSentence">Office 365 Business Essentials</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src118" class="srcSentence">Office 365 Business Premium</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src119" class="srcSentence">Office 365 Enterprise E1<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src120" class="srcSentence">Office 365 Education A1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src121" class="srcSentence">Office 365 Enterprise E3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src122" class="srcSentence">Office 365 Education A3<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src123" class="srcSentence">Office 365 Government G3</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src124" class="srcSentence">Office 365 Enterprise E4<br /> <br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src125" class="srcSentence">Office 365 Education A4<br /><br /></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src126" class="srcSentence">Office 365 Government G4</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src127" class="srcSentence">Office 365 Enterprise K1</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src128" class="srcSentence">SharePoint Plan 1<br /> <br />SharePoint Plan 2</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src129" class="srcSentence">Exchange Online Plan 1<br /> <br />Exchange Online Plan 2</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src130" class="srcSentence">Information Rights Protection (IRM) </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src131" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src132" class="srcSentence">Yes <superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src133" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src134" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src135" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src136" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src137" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src138" class="srcSentence">Yes</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence id="src139" class="srcSentence">
                  <superscript>1</superscript> For Business Premium, there are some client restrictions: You can protect content and consume protected content with RMS by using the Outlook Web App and the RMS sharing app.</caps:sentence>
                <caps:sentence id="src140" class="srcSentence"> You can consume protected content by using all other Office applications, which includes Office Online and the client applications for Office 365 Business Premium.</caps:sentence>
              </para>
            </content>
          </section>
          <section expanded="false">
            <title>
              <caps:sentence id="src141" class="srcSentence">RMS for individuals subscription</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src142" class="srcSentence">This subscription is designed for individuals in an organization that hasn’t deployed Azure RMS or AD RMS.</caps:sentence>
                <caps:sentence id="src143" class="srcSentence"> It lets these people read content that has been protected by an organization that is using Azure RMS, and they can also protect their own content.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src144" class="srcSentence">For more information, see <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>.</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_AzureADTenant">
        <title>
          <caps:sentence id="src145" class="srcSentence">Azure AD directory</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src146" class="srcSentence">You must have an Azure AD directory to use Azure RMS.</caps:sentence>
            <caps:sentence id="src147" class="srcSentence"> You use your organization account for this directory to sign in to the Azure Management Portal, where, for example, you can configure and manage Rights Management templates.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src148" class="srcSentence">If you do not already have an Azure subscription for your organization, you can get one by signing up for a free trial.: Go to the <externalLink><linkText>Azure Get started</linkText><linkUri>https://account.windowsazure.com/organization</linkUri></externalLink> page and follow the instructions.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src149" class="srcSentence">For more information, see the following resources in the Azure Active Directory documentation:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <legacyLink xlink:href="185da266-58a9-43e6-9c66-2c8f702545c6">
                  <caps:sentence id="src150" class="srcSentence">What is an Azure AD directory?</caps:sentence>
                </legacyLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <legacyLink xlink:href="edf05c2e-944a-4da5-a330-dc9dc479f127">
                  <caps:sentence id="src151" class="srcSentence">How Azure subscriptions are associated with Azure AD</caps:sentence>
                </legacyLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src152" class="srcSentence">If you want to integrate your Azure AD directory with your on-premises AD forests, see <legacyLink xlink:href="bf82bdff-2467-403b-8c1a-0e9eebcf31e8">Directory integration</legacyLink>.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src153" class="srcSentence">If you have mobile devices or Mac computers that authenticate on-premises by using AD FS or an equivalent authentication provider: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence id="src154" class="srcSentence">You must use AD FS on the minimum server version of <embeddedLabel>Windows Server 2012 R2</embeddedLabel>, or an alternative authentication provider that supports the OAuth 2.0 protocol.</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
        </content>
        <sections>
          <section address="BKMK_MFA">
            <title>
              <caps:sentence id="src155" class="srcSentence">Multi-factor authentication (MFA) and Azure RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src156" class="srcSentence">To use multi-factor authentication (MFA) with Azure RMS requires at least one of the following: </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src157" class="srcSentence">Office 2013 (minimum version):</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src158" class="srcSentence">   If you have Office 2013, you must also install the <externalLink><linkText>June 9, 2015, update for Office 2013 (KB3054853)</linkText><linkUri>https://support.microsoft.com/kb/3054853</linkUri></externalLink>.</caps:sentence>
                        <caps:sentence id="src159" class="srcSentence"> For more information about this update and how modern authentication brings Active Directory Authentication Library (ADAL)-based sign in to Office 2013, see <externalLink><linkText>Office 2013 modern authentication public preview announced</linkText><linkUri>https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/</linkUri></externalLink>  on the Office blog.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src160" class="srcSentence">Rights Management sharing application for Windows: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src161" class="srcSentence">You must have installed the minimum version of 1.0.1908.0, which can be confirmed by using Control Panel, Programs and Features.</caps:sentence>
                        <caps:sentence id="src162" class="srcSentence"> For more information about the sharing application, see  <link xlink:href="7d8a8abe-6de1-4088-90ee-e0c4bd6deec8">Rights Management Sharing Application for Windows</link>.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src163" class="srcSentence">Rights Management sharing app for mobile devices and Mac computers: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src164" class="srcSentence">Make sure that you have the latest version installed.</caps:sentence>
                        <caps:sentence id="src165" class="srcSentence"> MFA support went into the September 2015 release of the RMS sharing app.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src166" class="srcSentence">Then, configure your MFA solution:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src167" class="srcSentence">For Microsoft-managed tenants (you have Azure Active Directory or Office 365):  </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src168" class="srcSentence">Configure Azure MFA to enforce MFA for users.</caps:sentence>
                        <caps:sentence id="src169" class="srcSentence"> For instructions, see <externalLink><linkText>Getting started with Azure Multi-Factor Authentication in the cloud</linkText><linkUri>https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/</linkUri></externalLink> from the Azure documentation.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src170" class="srcSentence">For more information about Azure MFA, see <externalLink><linkText>What is Azure Multi-Factor Authentication?</linkText><linkUri>https://azure.microsoft.com/documentation/articles/multi-factor-authentication/</linkUri></externalLink></caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <caps:sentence id="src171" class="srcSentence">
                    <para>For federated tenants (you operate federation servers on-premises):  </para> <list class="bullet"><listItem><para>Configure your federation servers for Azure Active Directory or Office 365. For example, if you are using AD FS, see <externalLink><linkText>Configure Additional Authentication Methods for AD FS</linkText><linkUri>https://technet.microsoft.com/library/dn758113.aspx</linkUri></externalLink> on TechNet.  </para><para> For more information about this scenario, see  <externalLink><linkText>The Works with Office 365 – Identity program now streamlined</linkText><linkUri>https://blogs.office.com/2014/01/30/the-works-with-office-365-identity-program-now-streamlined/</linkUri></externalLink> on the Office blog. </para></listItem></list></caps:sentence>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_SupportedDevices">
        <title>
          <caps:sentence id="src172" class="srcSentence">Client devices that support Azure RMS</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src173" class="srcSentence">Use the following sections to identify which devices support Azure Rights Management (RMS), and which RMS capabilities they support:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_RMSSupportedComputers">Computers</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_RMSSupportedMobileDevices">Mobile devices</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link>
              </para>
            </listItem>
          </list>
        </content>
        <sections>
          <section address="BKMK_RMSSupportedComputers">
            <title>
              <caps:sentence id="src174" class="srcSentence">Computers</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src175" class="srcSentence">The following computer operating systems support Azure Rights Management:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src176" class="srcSentence">
                      <legacyBold>Windows 7</legacyBold> (x86, x64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src177" class="srcSentence">
                      <legacyBold>Windows 8</legacyBold> (x86, x64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src178" class="srcSentence">
                      <legacyBold>Windows 8.1</legacyBold> (x86, x64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src179" class="srcSentence">
                      <legacyBold>Windows 10</legacyBold> (x86, x64)</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src180" class="srcSentence">
                      <legacyBold>Mac OS X</legacyBold>: Minimum version of Mac OS X 10.8 (Mountain Lion)</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_RMSSupportedMobileDevices">
            <title>
              <caps:sentence id="src181" class="srcSentence">Mobile devices</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src182" class="srcSentence">The following mobile device operating systems support Azure Rights Management:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src183" class="srcSentence">
                      <legacyBold>Windows Phone</legacyBold>: Windows Phone 8.1</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src184" class="srcSentence">
                      <legacyBold>Android phones and tablets</legacyBold>: Minimum version of Android 4.0.3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src185" class="srcSentence">
                      <legacyBold>iPhone and iPad</legacyBold>: Minimum version of iOS 7.0 </caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src186" class="srcSentence">
                      <legacyBold>Windows RT tablets</legacyBold>: Windows 8 RT, Windows 8.1 RT</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_ClientCapabilities">
            <title>
              <caps:sentence id="src187" class="srcSentence">Client device capabilities</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src188" class="srcSentence">Not all supported client devices currently support all RMS capabilities.</caps:sentence>
                <caps:sentence id="src189" class="srcSentence"> Use the following table to identify which applications support the RMS capabilities, and the exceptions.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src190" class="srcSentence">Unless stated otherwise, the supported capabilities apply to both Azure RMS and AD RMS.</caps:sentence>
                <caps:sentence id="src191" class="srcSentence"> In addition, AD RMS support on iOS, Android, OS X, and Windows Phone 8.1 requires <externalLink><linkText>Active Directory Rights Management Services Mobile Device Extension</linkText><linkUri>http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341</linkUri></externalLink>.</caps:sentence>
              </para>
              <para></para>
              <para>
                <caps:sentence id="src192" class="srcSentence">Information about the table columns:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src193" class="srcSentence">
                      <embeddedLabel>Protected PDF</embeddedLabel>: Files that have a .ppdf file name extension and that are automatically created when you use the RMS sharing application to share Office files and PDF files by email.</caps:sentence>
                    <caps:sentence id="src194" class="srcSentence"> The RMS sharing application includes a reader for protected PDF files.</caps:sentence>
                    <caps:sentence id="src195" class="srcSentence"> Previously, if you created PDF files that you protected by using Azure RMS or AD RMS, you can continue to read these files on Windows, iOS, and Android devices by using Foxit Reader and Nitro Pro.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src196" class="srcSentence">
                      <embeddedLabel>Email:</embeddedLabel> The email clients listed can protect the email message itself, which will automatically protect any attached files.</caps:sentence>
                    <caps:sentence id="src197" class="srcSentence"> In this scenario, the client’s preview feature can display the protected content (message and attachment) to authorized recipients.</caps:sentence>
                    <caps:sentence id="src198" class="srcSentence"> However, if an email message itself is not protected but the attachment is protected, the client’s preview feature cannot display the protected attachment to authorized recipients.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src199" class="srcSentence">
                      <embeddedLabel>Other file types</embeddedLabel>: Text and image files include files that have a file name extension such as .txt, .xml, .jpg, .and jpeg.</caps:sentence>
                    <caps:sentence id="src200" class="srcSentence"> These files change their file name extension after they are natively protected by RMS, and become read-only.</caps:sentence>
                    <caps:sentence id="src201" class="srcSentence"> Files that cannot be natively protected have a .pfile file name extension after they are generically protected by RMS.</caps:sentence>
                    <caps:sentence id="src202" class="srcSentence"> For more information, see the <externalLink><linkText>Levels of protection – native and generic</linkText><linkUri>https://technet.microsoft.com/library/dn339003.aspx#BKMK_LevelsofProtection</linkUri></externalLink> and <externalLink><linkText>Supported file types and file name extensions</linkText><linkUri>https://technet.microsoft.com/library/dn339003.aspx#BKMK_SupportFileTypes</linkUri></externalLink> sections from the <externalLink><linkText>Rights Management sharing application administrator guide</linkText><linkUri>http://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src203" class="srcSentence">Device operating system</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src204" class="srcSentence">Word, Excel, PowerPoint</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src205" class="srcSentence">Protected PDF</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src206" class="srcSentence">Email</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src207" class="srcSentence">Other file types</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src208" class="srcSentence">Windows</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src209" class="srcSentence">Office 2010</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src210" class="srcSentence">Office 2013</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src211" class="srcSentence">Office 2016</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src212" class="srcSentence">Office Mobile apps (Azure RMS only)<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src213" class="srcSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src214" class="srcSentence">Gaaiho Doc</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src215" class="srcSentence">GigaTrust Desktop PDF Client for Adobe</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src216" class="srcSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src217" class="srcSentence">Nitro PDF Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src218" class="srcSentence">RMS sharing app</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src219" class="srcSentence">Outlook 2010</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src220" class="srcSentence">Outlook 2013</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src221" class="srcSentence">Outlook 2016</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src222" class="srcSentence">Outlook Web App (OWA)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src223" class="srcSentence">Windows Mail<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src224" class="srcSentence">RMS sharing application for Windows: Text, images, pfile</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src225" class="srcSentence">Siemens JT2Go: JT files (Windows 10 only)</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src226" class="srcSentence">iOS</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src227" class="srcSentence">Office for iPad and iPhone<superscript>4</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src228" class="srcSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src229" class="srcSentence">TITUS Docs</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src230" class="srcSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src231" class="srcSentence">RMS sharing app<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src232" class="srcSentence">TITUS Docs</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src233" class="srcSentence">NitroDesk</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src234" class="srcSentence">Outlook for iPad and iPhone<superscript>3</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src235" class="srcSentence">OWA for iOS </caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src236" class="srcSentence">Secure Islands IQProtector<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src237" class="srcSentence">TITUS Mail</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src238" class="srcSentence">RMS sharing app<superscript>1</superscript>: Text, images, pfile</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src239" class="srcSentence">TITUS Docs: Pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src240" class="srcSentence">Android</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src241" class="srcSentence">GigaTrust App for Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src242" class="srcSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src243" class="srcSentence">GigaTrust App for Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src244" class="srcSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src245" class="srcSentence">RMS sharing app<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src246" class="srcSentence">9Folders</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src247" class="srcSentence">GigaTrust App for Android</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src248" class="srcSentence">NitroDesk</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src249" class="srcSentence">OWA for Android<superscript>5</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src250" class="srcSentence">Samsung Email (S3 and later)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src251" class="srcSentence">Secure Islands IQProtector<superscript>1</superscript></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src252" class="srcSentence">TITUS Classification for Mobile</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src253" class="srcSentence">RMS sharing app<superscript>1</superscript>: Text, images, pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src254" class="srcSentence">OS X</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <para></para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src255" class="srcSentence">Office 2011 (AD RMS only)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src256" class="srcSentence">Office 2016 for Mac</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src257" class="srcSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src258" class="srcSentence">Foxit Reader</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src259" class="srcSentence">RMS sharing app<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src260" class="srcSentence">Outlook 2011 (AD RMS only)</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src261" class="srcSentence">Outlook 2016 for Mac</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src262" class="srcSentence">Outlook for Mac</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src263" class="srcSentence">RMS sharing app<superscript>1</superscript>: Text, images, pfile</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD rowspan="1">
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src264" class="srcSentence">Windows RT</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src265" class="srcSentence">Office 2013 RT</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src266" class="srcSentence">Office Online<superscript>2</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src267" class="srcSentence">Not supported</caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src268" class="srcSentence">Outlook 2013 RT</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src269" class="srcSentence">Mail app for Windows</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src270" class="srcSentence">Windows Mail<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD rowspan="1">
                      <para>
                        <caps:sentence id="src271" class="srcSentence">Siemens JT2Go: JT files</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src272" class="srcSentence">
                          <embeddedLabel>Windows Phone 8.1</embeddedLabel> </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src273" class="srcSentence"> Office Mobile (AD RMS only)</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src274" class="srcSentence">RMS sharing app<superscript>1</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src275" class="srcSentence">Outlook Mobile</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src276" class="srcSentence">RMS sharing app<superscript>1</superscript>: Text, images, pfile </caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src277" class="srcSentence">Blackberry 10</caps:sentence>
                        </embeddedLabel>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src278" class="srcSentence">Not supported</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src279" class="srcSentence">Not supported</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src280" class="srcSentence">Blackberry email<superscript>3</superscript></caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src281" class="srcSentence">Not supported</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence id="src282" class="srcSentence">
                  <superscript>1</superscript> Supports viewing protected content.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src283" class="srcSentence">
                  <superscript>2</superscript> Supports viewing protected content in SharePoint Online, OneDrive for Business, and Outlook Web Access.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src284" class="srcSentence">
                  <superscript>3</superscript> Uses Exchange ActiveSync IRM, which must be enabled by the Exchange administrator.</caps:sentence>
                <caps:sentence id="src285" class="srcSentence"> Users can view, reply, and reply all for protected email messages but users cannot protect new email messages themselves.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src286" class="srcSentence">
                  <superscript>4</superscript> Supports viewing and editing protected documents.</caps:sentence>
                <caps:sentence id="src287" class="srcSentence"> For more information, see the following post on the Office blog: <externalLink><linkText>Azure Rights Management support comes to Office for iPad and iPhone</linkText><linkUri>https://blogs.office.com/2015/07/22/azure-rights-management-support-comes-to-office-for-ipad-and-iphone-2/</linkUri></externalLink></caps:sentence>
              </para>
              <para>
                <caps:sentence id="src288" class="srcSentence">
                  <superscript>5</superscript> For more information, see the following post on the Office blog: <externalLink><linkText>OWA for Android now available on select devices</linkText><linkUri>http://blogs.office.com/2014/06/11/owa-for-android-now-available-on-select-devices/</linkUri></externalLink></caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence id="src289" class="srcSentence">For more information about upcoming RMS support in Office for different platforms, see the following post from the Office blog: <externalLink><linkText>Office everywhere, encryption everywhere</linkText><linkUri>http://blogs.office.com/2015/02/18/office-everywhere-encryption-everywhere/</linkUri></externalLink></caps:sentence>
                </para>
              </alert>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_SupportedApplications">
        <title>
          <caps:sentence id="src290" class="srcSentence">Applications that support Azure RMS</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src291" class="srcSentence">The following applications natively support Azure RMS, which means that RMS is tightly integrated into these applications by using RMS APIs to support usage restrictions.</caps:sentence>
            <caps:sentence id="src292" class="srcSentence"> These applications are also known as RMS-enlightened:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src293" class="srcSentence">
                  <legacyBold>Microsoft Office applications</legacyBold> (Word, Excel, PowerPoint, and Outlook) from the following suites:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src294" class="srcSentence">Office 365 ProPlus</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src295" class="srcSentence">Office 365 Enterprise E3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src296" class="srcSentence">Office Professional 2016</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src297" class="srcSentence">Office Professional 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src298" class="srcSentence">Office Professional 2010</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src299" class="srcSentence">Specific to Office Professional 2010: </caps:sentence>
                    </para>
                    <list class="bullet">
                      <listItem>
                        <para>
                          <caps:sentence id="src300" class="srcSentence">Windows computers must install the Rights Management sharing application for Windows</caps:sentence>
                        </para>
                      </listItem>
                      <listItem>
                        <para>
                          <caps:sentence id="src301" class="srcSentence">This version of Office is not supported on Windows 10</caps:sentence>
                        </para>
                      </listItem>
                    </list>
                  </alert>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src302" class="srcSentence">You must have one of these Office versions to protect content, but any version of Office 2016, Office 2013, or Office 2010 can consume protected content.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <legacyBold>
                  <caps:sentence id="src303" class="srcSentence">The Rights Management sharing application for Windows</caps:sentence>
                </legacyBold>
              </para>
              <para>
                <caps:sentence id="src304" class="srcSentence">For more information about the Rights Management sharing application for Windows, see the following resources:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src305" class="srcSentence">Rights Management sharing application administrator guide</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                    </externalLink>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src306" class="srcSentence">Rights Management sharing application user guide</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                    </externalLink>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <legacyBold>
                  <caps:sentence id="src307" class="srcSentence">The Rights Management sharing application for mobile platforms</caps:sentence>
                </legacyBold>
              </para>
              <para>
                <caps:sentence id="src308" class="srcSentence">For more information about the Rights Management sharing application for mobile platforms, see the following resources:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src309" class="srcSentence">Download the relevant app by using the links on the <externalLink><linkText>Microsoft Rights Management page</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
                <!--Not to go live before  Intune goes out.-->
                <listItem>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src310" class="srcSentence">FAQ for Microsoft Rights Management Sharing Application for Mobile Platforms</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/dn451248</linkUri>
                    </externalLink>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src311" class="srcSentence">
                  <legacyBold>Other applications that support the RMS APIs</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src312" class="srcSentence">Line-of-business applications that are written in-house by using the RMS SDK</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src313" class="srcSentence">Applications from software vendors that are written by using the RMS SDK</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src314" class="srcSentence">For more information about the SDK, see the <externalLink><linkText>Microsoft Rights Management SDK</linkText><linkUri>http://msdn.microsoft.com/library/hh552972(v=vs.85).aspx</linkUri></externalLink>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="important">
            <para>
              <caps:sentence id="src315" class="srcSentence">The following applications are not currently supported by Azure RMS:</caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence id="src316" class="srcSentence">Microsoft Office for Mac 2011</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence id="src317" class="srcSentence">Microsoft OneDrive for Business for SharePoint Server 2013</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence id="src318" class="srcSentence">XPS Viewer </caps:sentence>
                </para>
              </listItem>
            </list>
            <para>
              <caps:sentence id="src319" class="srcSentence">In addition, the RMS sharing application has the following restrictions: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence id="src320" class="srcSentence">For Windows computers: Requires a minimum version of Windows 7 Service Pack 1</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
          <para>
            <caps:sentence id="src321" class="srcSentence">For more information about how these applications support Azure RMS, see <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src322" class="srcSentence">For information about how to configure them, see <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_SupportedServers">
        <title>
          <caps:sentence id="src323" class="srcSentence">On-premises servers that support Azure RMS</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src324" class="srcSentence">The following on-premises server products are supported with Azure RMS when you use the Azure RMS connector, which acts as a communications interface (a relay) between the on-premises servers and Azure RMS.</caps:sentence>
            <caps:sentence id="src325" class="srcSentence"> In addition, this configuration requires that you configure directory synchronization between your Active Directory forests and Azure Active Directory.</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src326" class="srcSentence">
                  <legacyBold>Exchange Server</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src327" class="srcSentence">Exchange Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src328" class="srcSentence">Exchange Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src329" class="srcSentence">
                  <legacyBold>Office SharePoint Server</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src330" class="srcSentence">Office SharePoint Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src331" class="srcSentence">Office SharePoint Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src332" class="srcSentence">
                  <legacyBold>File servers that run Windows Server and use File Classification Infrastructure (FCI)</legacyBold>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src333" class="srcSentence">Windows Server 2012 R2</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src334" class="srcSentence">Windows Server 2012</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="note">
                <para>
                  <caps:sentence id="src335" class="srcSentence">Because file servers that run Windows Server 2008 R2 do not have a built-in file management task action to apply RMS protection, you cannot use the RMS connector for this scenario.</caps:sentence>
                  <caps:sentence id="src336" class="srcSentence"> However, you can use File Classification Infrastructure and Azure RMS on these operating systems if you configure a custom file management task to run an executable or script that can protect files by using Azure RMS.</caps:sentence>
                  <caps:sentence id="src337" class="srcSentence"> For example, a Windows PowerShell script that uses the <externalLink><linkText>RMS Protection cmdlets</linkText><linkUri>https://msdn.microsoft.com/library/azure/mt433195.aspx</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src338" class="srcSentence">You can also use these cmdlets with servers running later versions of Windows Server, with the benefit that these cmdlets can protect all file types.</caps:sentence>
                  <caps:sentence id="src339" class="srcSentence"> The RMS connector protects Office files only.</caps:sentence>
                  <caps:sentence id="src340" class="srcSentence"> For how-to instructions, see <link xlink:href="9aa693db-9727-4284-9f64-867681e114c9">RMS Protection with Windows Server File Classification Infrastructure (FCI)</link>.</caps:sentence>
                </para>
              </alert>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src341" class="srcSentence">The RMS connector is supported on Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src342" class="srcSentence">For more information about how to configure the RMS connector for these on-premises servers, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>