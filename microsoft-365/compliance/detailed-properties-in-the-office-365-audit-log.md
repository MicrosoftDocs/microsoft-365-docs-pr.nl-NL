---
title: Gedetailleerde eigenschappen in het auditlogboek
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Dit artikel bevat beschrijvingen van extra eigenschappen die zijn opgenomen wanneer u resultaten exporteert voor Office 365 auditlogboekrecord.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69a34f4de948bc9533ef2872d94171134e50ffea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162164"
---
# <a name="detailed-properties-in-the-audit-log"></a>Gedetailleerde eigenschappen in het auditlogboek

Wanneer u de resultaten van een zoekopdracht in een auditlogboek exporteert vanuit het Beveiligings- & Compliancecentrum, hebt u de optie om alle resultaten te downloaden die voldoen aan uw zoekcriteria. U doet dit door Resultaten **exporteren te selecteren** Alle resultaten \> **downloaden** op de **zoekpagina** auditlogboek. Zie Het [auditlogboek doorzoeken voor meer informatie.](search-the-audit-log-in-security-and-compliance.md)
  
 Wanneer u alle resultaten exporteert voor een zoekopdracht in een auditlogboek, worden de onbewerkte gegevens uit het geïntegreerde auditlogboek gekopieerd naar een CSV-bestand (door komma's gescheiden waarden) dat naar uw lokale computer wordt gedownload. Dit bestand bevat aanvullende informatie uit elke auditrecord in een kolom met de naam **AuditData.** Deze kolom bevat een eigenschap met meerdere waarden voor meerdere eigenschappen uit de auditlogboekrecord. Elk van de **eigenschap: waardeparen** in deze eigenschap met meerdere waarden worden gescheiden door een komma. 
  
In de volgende tabel worden de eigenschappen beschreven die zijn opgenomen (afhankelijk van de service waarin een gebeurtenis plaatsvindt) in de kolom **AuditData met meerdere** eigenschappen. De Office 365 met deze **eigenschapskolom** geeft de service en het type activiteit (gebruiker of beheerder) aan dat de eigenschap bevat. Zie Management Activity API Schema voor meer informatie over deze eigenschappen of over eigenschappen die mogelijk niet in dit onderwerp [worden vermeld.](/office/office-365-management-api/office-365-management-activity-api-schema)
  
> [!TIP]
> U kunt de functie JSON-transformatie in Power Query in Excel gebruiken om de **kolom AuditData** te splitsen in meerdere kolommen, zodat elke eigenschap een eigen kolom heeft. Hiermee kunt u sorteren en filteren op een of meer van deze eigenschappen. Zie Auditlogboekrecords [exporteren, configureren](export-view-audit-log-records.md)en weergeven voor meer informatie over hoe u dit doet. 
  
|**Eigenschap**|**Beschrijving**|**Microsoft 365 service met deze eigenschap**|
|:-----|:-----|:-----|
|Actor|Het gebruikers- of serviceaccount dat de actie heeft uitgevoerd.|Microsoft Azure Active Directory|
|AddOnName|De naam van een invoeg die is toegevoegd, verwijderd of bijgewerkt in een team. Het type invoegtoepassingen in Microsoft Teams is een bot, een verbindingslijn of een tabblad.|Microsoft Teams|
|AddOnType|Het type add-on dat is toegevoegd, verwijderd of bijgewerkt in een team. De volgende waarden geven het type invoegvoeging aan.  <br/> **1** - Geeft een bot aan.<br/> **2** - Geeft een verbindingslijn aan.<br/> **3** - Geeft een tabblad aan.|Microsoft Teams|
|AzureActiveDirectoryEventType|Het type Azure Active Directory gebeurtenis. De volgende waarden geven het type gebeurtenis aan.  <br/> **0** - Geeft een aanmeldingsgebeurtenis voor een account aan.<br/> **1** - Geeft een beveiligingsgebeurtenis voor Azure-toepassingen aan.|Microsoft Azure Active Directory|
|ChannelGuid|De id van een Microsoft Teams kanaal. Het team waarin het kanaal zich bevindt, wordt geïdentificeerd door de **eigenschappen Teamnaam** en **TeamGuid.**|Microsoft Teams|
|Kanaalnaam|De naam van een Microsoft Teams kanaal. Het team waarin het kanaal zich bevindt, wordt geïdentificeerd door de **eigenschappen Teamnaam** en **TeamGuid.**|Microsoft Teams|
|Client|Het clientapparaat, het apparaat-besturingssysteem en de apparaatbrowser die voor de aanmeldingsgebeurtenis wordt gebruikt (bijvoorbeeld Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Microsoft Azure Active Directory|
|ClientInfoString|Informatie over de e-mailclient die is gebruikt om de bewerking uit te voeren, zoals een browserversie, Outlook versie en gegevens over mobiele apparaten|Exchange (postvakactiviteit)|
|ClientIP|Het IP-adres van het apparaat dat is gebruikt toen de activiteit werd geregistreerd. Het IP-adres wordt weergegeven in een IPv4- of IPv6-adresindeling.<br/><br/> Voor sommige services kan de waarde die in deze eigenschap wordt weergegeven, het IP-adres zijn voor een vertrouwde toepassing (bijvoorbeeld webversie van Office-apps) die namens een gebruiker bij de service belt en niet het IP-adres van het apparaat dat wordt gebruikt door de persoon die de activiteit heeft uitgevoerd. <br/><br/>Voor beheerdersactiviteit (of activiteit die wordt uitgevoerd door een systeemaccount) voor Azure Active Directory-gerelateerde gebeurtenissen, wordt het IP-adres niet geregistreerd en is de waarde voor de eigenschap ClientIP `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|De datum en tijd in Coordinated Universal Time (UTC) wanneer de gebruiker de activiteit heeft uitgevoerd.|Alles|
|DestinationFileExtension|De bestandsextensie van een bestand dat wordt gekopieerd of verplaatst. Deze eigenschap wordt alleen weergegeven voor de gebruikersactiviteiten FileCopied en FileMoved.|SharePoint|
|DestinationFileName|De naam van het bestand wordt gekopieerd of verplaatst. Deze eigenschap wordt alleen weergegeven voor de acties FileCopied en FileMoved.|SharePoint|
|DestinationRelativeUrl|De URL van de doelmap waarin een bestand wordt gekopieerd of verplaatst. De combinatie van de waarden voor **de eigenschap SiteURL,** **DestinationRelativeURL** en **DestinationFileName** is hetzelfde als de waarde voor de **eigenschap ObjectID,** de volledige padnaam voor het bestand dat is gekopieerd. Deze eigenschap wordt alleen weergegeven voor de gebruikersactiviteiten FileCopied en FileMoved.|SharePoint|
|EventSource|Hiermee wordt aangegeven dat er een gebeurtenis heeft plaatsgevonden in SharePoint. Mogelijke waarden zijn **SharePoint** **objectmodel.**|SharePoint|
|ExternalAccess|Voor Exchange beheerdersactiviteit geeft u aan of de cmdlet is uitgevoerd door een gebruiker in uw organisatie, door personeel van het Microsoft-datacenter of een datacenterserviceaccount of door een gedelegeerde beheerder. De waarde **Onwaar** geeft aan dat de cmdlet is uitgevoerd door iemand in uw organisatie. De waarde **Waar** geeft aan dat de cmdlet is uitgevoerd door datacenterpersoneel, een datacenterserviceaccount of een gedelegeerde beheerder.  <br/> Voor Exchange postvakactiviteit geeft u aan of een postvak is gebruikt door een gebruiker buiten uw organisatie.|Exchange|
|ExtendedProperties|De uitgebreide eigenschappen voor een Azure Active Directory gebeurtenis.|Microsoft Azure Active Directory|
|ID|De id van het rapportinvoer. De id identificeert de rapportinvoer op unieke manier.|Alles|
|InternalLogonType|Gereserveerd voor intern gebruik.|Exchange (postvakactiviteit)|
|ItemType|Het type object dat is toegankelijk of gewijzigd. Mogelijke waarden zijn **Bestand**, **Map**, **Web**, **Site**, **Tenant** en **DocumentLibrary**.|SharePoint|
|LoginStatus|Identificeert aanmeldingsfouten die mogelijk zijn opgetreden.|Microsoft Azure Active Directory|
|Aanmeldingstype|Het type postvaktoegang. De volgende waarden geven het type gebruiker aan dat toegang heeft tot het postvak.  <br/><br/> **0** - Geeft een eigenaar van een postvak aan.<br/> **1** : geeft een beheerder aan.<br/> **2** - Geeft een gemachtigde aan. <br/>**3:** geeft de transportservice aan in het Microsoft-datacenter.<br/> **4** - Geeft een serviceaccount aan in het Microsoft-datacenter. <br/>**6** : geeft een gedelegeerde beheerder aan.|Exchange (postvakactiviteit)|
|Postvakgids|De Exchange GUID van het postvak dat is toegankelijk.|Exchange (postvakactiviteit)|
|PostvakEigenaarUPN|Het e-mailadres van de eigenaar van het postvak dat is toegankelijk.|Exchange (postvakactiviteit)|
|Leden|Hiermee worden de gebruikers vermeld die zijn toegevoegd of verwijderd uit een team. De volgende waarden geven het type Rol aan dat aan de gebruiker is toegewezen.  <br/><br/> **1** : geeft de rol Eigenaar aan.<br/> **2** : geeft de rol Lid aan.<br/> **3** : geeft de rol Gast aan. <br/><br/>De eigenschap Leden bevat ook de naam van uw organisatie en het e-mailadres van het lid.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|De eigenschap is opgenomen voor beheerdersgebeurtenissen, zoals het toevoegen van een gebruiker als lid van een site of een siteverzamelingsbeheerdergroep. De eigenschap bevat de naam van de eigenschap die is gewijzigd (bijvoorbeeld de groep Sitebeheerder) de nieuwe waarde van de gewijzigde eigenschap (zoals de gebruiker die is toegevoegd als sitebeheerder en de vorige waarde van het gewijzigde object.|Alles (beheerdersactiviteit)|
|ObjectId|Voor Exchange beheerauditregistratie, de naam van het object dat is gewijzigd door de cmdlet.  <br/> Voor SharePoint activiteit, de volledige URL-padnaam van het bestand of de map die door een gebruiker is toegankelijk.  <br/> Voor Azure AD-activiteit, de naam van het gebruikersaccount dat is gewijzigd.|Alles|
|Bewerking|De naam van de activiteit van de gebruiker of beheerder. De waarde van deze eigenschap komt overeen met de waarde die is geselecteerd in **de** vervolgkeuzelijst Activiteiten. Als **Resultaten voor alle activiteiten tonen** is geselecteerd, worden in het rapport vermeldingen opgenomen voor alle gebruikers- en beheeractiviteiten voor alle services. Zie het tabblad Gecontroleerde activiteiten in Het auditlogboek zoeken  in het auditlogboek voor een beschrijving van de bewerkingen/activiteiten die in het auditlogboek [zijn Office 365.](search-the-audit-log-in-security-and-compliance.md)  <br/> Voor Exchange beheerderactiviteit wordt met deze eigenschap de naam geïdentificeerd van de cmdlet die is uitgevoerd.|Alles|
|OrganizationId|De GUID voor uw organisatie.|Alles|
|Pad|De naam van de postvakmap waar het bericht dat is weergegeven zich bevindt. Met deze eigenschap wordt ook de map aangegeven waarin een bericht is gemaakt of gekopieerd of verplaatst.|Exchange (postvakactiviteit)|
|Parameters|Voor Exchange beheeractiviteit, de naam en waarde voor alle parameters die zijn gebruikt met de cmdlet die is geïdentificeerd in de eigenschap Bewerking.|Exchange (beheerdersactiviteit)|
|RecordType|Het type bewerking dat door de record wordt aangegeven. Deze eigenschap geeft de service of functie aan waarin de bewerking is geactiveerd. Zie Recordtype auditlogboek voor een lijst met recordtypen en de bijbehorende ENUM-waarde (de waarde die wordt weergegeven in de eigenschap **RecordType** in een [auditrecord).](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)| 
|ResultStatus|Hiermee geeft u aan of de actie (opgegeven in de eigenschap **Bewerking)** al dan niet is geslaagd.  <br/> Voor Exchange beheerderactiviteit is de waarde **Waar** (geslaagd) of **Onwaar** (mislukt).|Alles  <br/>|
|SecurityComplianceCenterEventType|Geeft aan dat de activiteit een gebeurtenis & compliancecentrum was. Alle activiteiten & compliancecentrum hebben een waarde **van 0** voor deze eigenschap.|Beveiligings- en compliancecentrum|
|SharingType|Het type machtigingen voor delen dat is toegewezen aan de gebruiker met welke de resource is gedeeld. Deze gebruiker wordt geïdentificeerd in de **eigenschap UserSharedWith.**|SharePoint|
|Site|De GUID van de site waar het bestand of de map die door de gebruiker wordt gebruikt zich bevindt.|SharePoint|
|SiteUrl|De URL van de site waar het bestand of de map die door de gebruiker is toegankelijk, zich bevindt.|SharePoint|
|SourceFileExtension|De bestandsextensie van het bestand dat door de gebruiker is gebruikt. Deze eigenschap is leeg als het object dat is toegankelijk een map is.|SharePoint|
|SourceFileName|De naam van het bestand of de map die door de gebruiker is toegankelijk.|SharePoint|
|SourceRelativeUrl|De URL van de map met het bestand dat door de gebruiker is toegankelijk. De combinatie van de waarden voor **de eigenschap SiteURL**, de eigenschap **SourceRelativeURL** en **SourceFileName** is hetzelfde als de waarde voor de eigenschap **ObjectID,** de volledige padnaam voor het bestand dat door de gebruiker wordt gebruikt.|SharePoint|
|Onderwerp|De onderwerpregel van het bericht dat is weergegeven.|Exchange (postvakactiviteit)|
|TabType| Het type tabblad dat is toegevoegd, verwijderd of bijgewerkt in een team. De mogelijke waarden voor deze eigenschap zijn:  <br/><br/> **Excel vastmaken** - Een Excel tabblad.  <br/> **Extensie** - Alle apps van eerste en derde partij; zoals Klasplanning, VSTS en Formulieren.  <br/> **Notities** - OneNote tabblad.  <br/> **Pdfpin** : een PDF-tabblad.  <br/> **Powerbi** - Een Power BI tabblad.  <br/> **Powerpointpin** - een PowerPoint tabblad.  <br/> **Sharepointfiles** : een SharePoint tabblad.  <br/> **Webpagina:** een vastgemaakt websitetabblad.  <br/> **Wiki-tab** - Een wikitabblad.  <br/> **Wordpin** - Een Word-tabblad.|Microsoft Teams|
|Doel|De gebruiker op de actie (die is geïdentificeerd in de eigenschap **Bewerking)** is uitgevoerd. Als een gastgebruiker bijvoorbeeld wordt toegevoegd aan SharePoint of een Microsoft-team, wordt deze gebruiker in deze eigenschap vermeld.|Microsoft Azure Active Directory|
|TeamGuid|De id van een team in Microsoft Teams.|Microsoft Teams|
|Teamnaam|De naam van een team in Microsoft Teams.|Microsoft Teams|
|UserAgent|Informatie over de browser van de gebruiker. Deze informatie wordt verstrekt door de browser.|SharePoint|
|UserDomain|Identiteitsgegevens over de tenantorganisatie van de gebruiker (actor) die de actie heeft uitgevoerd.|Microsoft Azure Active Directory|
|UserID|De gebruiker die de actie heeft uitgevoerd (opgegeven in de eigenschap **Bewerking)** waardoor de record is vastgelegd. Auditrecords voor activiteiten die worden uitgevoerd door systeemaccounts (zoals SHAREPOINT\system of NT AUTHORITY\SYSTEM) worden ook opgenomen in het auditlogboek. Een andere veelgebruikte waarde voor de eigenschap UserId is app@sharepoint. Dit geeft aan dat de 'gebruiker' die de activiteit heeft uitgevoerd, een toepassing is met de benodigde machtigingen in SharePoint om acties voor de hele organisatie uit te voeren (zoals zoeken op een SharePoint-site of OneDrive-account) namens een gebruiker, beheerder of service. Zie [De gebruiker app\@sharePoint in auditrecords](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records) voor meer informatie. |Alles|
|UserKey|Een alternatieve id voor de gebruiker die is geïdentificeerd in de **eigenschap UserID.** Deze eigenschap wordt bijvoorbeeld gevuld met de unieke paspoort-id (PUID) voor gebeurtenissen die worden uitgevoerd door gebruikers in SharePoint. Deze eigenschap kan ook dezelfde waarde opgeven als de **eigenschap UserID** voor gebeurtenissen in andere services en gebeurtenissen die worden uitgevoerd door systeemaccounts.|Alles|
|UserSharedWith|De gebruiker met een resource die is gedeeld. Deze eigenschap wordt opgenomen als de waarde voor de eigenschap **Bewerking** **SharingSet is.** Deze gebruiker wordt ook weergegeven in de kolom Gedeeld **met** in het rapport.|SharePoint|
|UserType|Het type gebruiker dat de bewerking heeft uitgevoerd. De volgende waarden geven het gebruikerstype aan. <br/> <br/> **0** - Een gewone gebruiker. <br/>**2** - Een beheerder in uw Microsoft 365 organisatie. <sup>1</sup> <br/>**3** - Een Microsoft-datacenterbeheerder of datacentersysteemaccount. <br/>**4** - Een systeemaccount. <br/>**5** - Een toepassing. <br/>**6** - Een service-principal.<br/>**7** - Een aangepast beleid.<br/>**8** - Een systeembeleid.|Alles|
|Versie|Geeft het versienummer aan van de activiteit (geïdentificeerd door de eigenschap **Operation)** die is geregistreerd.|Alles|
|Workload|De Microsoft 365 service waar de activiteit heeft plaatsgevonden.|Alles|
||||

> [!NOTE]
><sup>1</sup> Voor Azure Active Directory gerelateerde gebeurtenissen wordt de waarde voor een beheerder niet gebruikt in een auditrecord. Controlerecords voor activiteiten die door beheerders worden uitgevoerd, geven aan dat een gewone gebruiker (bijvoorbeeld **UserType: 0)** de activiteit heeft uitgevoerd. De **eigenschap UserID** identificeert de persoon (gewone gebruiker of beheerder) die de activiteit heeft uitgevoerd.<br/>

De hierboven beschreven eigenschappen worden ook weergegeven wanneer u op **Meer** informatie klikt bij het weergeven van de details van een specifieke gebeurtenis.
  
![Klik op Meer informatie om de gedetailleerde eigenschappen van de gebeurtenisrecord in het auditlogboek weer te geven.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)