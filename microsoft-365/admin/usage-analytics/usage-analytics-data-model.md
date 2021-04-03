---
title: Microsoft 365 Gegevensmodel gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Meer informatie over hoe gebruiksanalyse verbinding maakt met een API en de maandelijkse trend van het gebruik van verschillende Microsoft 365-services biedt.  '
ms.openlocfilehash: 877ad005e3ff7f7537247963fafcab5fb1ff6c74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580748"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 Gegevensmodel gebruiksanalyse

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Gegevens voor de Microsoft 365 Gebruiksanalysetabellen

Microsoft 365 Gebruiksanalyse maakt verbinding met een API die een multidimensionaal gegevensmodel blootstelt. De API's die door Microsoft 365 gebruiksanalyse worden gebruikt om de gegevens te genereren, zijn afkomstig van de verschillende, algemeen beschikbare, Graph-API's. De functie van de Microsoft 365 Usage Analytics API op zich is niet algemeen beschikbaar.
  
> [!NOTE]
> Zie Werken met [Gebruiksrapporten van Microsoft 365 in Microsoft Graph voor meer informatie.](/graph/api/resources/report) 
  
Deze API bevat informatie over de maandelijkse trend van het gebruik van de verschillende Microsoft 365-services. Raadpleeg de tabel in de volgende sectie voor de exacte gegevens die worden geretourneerd door de API.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Gegevenstabellen die zijn geretourneerd door de Microsoft 365 Reporting API

|**Tabelnaam**|**Informatie in de tabel**|**Datumbereik**|
|:-----|:-----|:-----|
|Tenant Product Usage  <br/> |Bevat maandelijkse totalen van ingeschakelde, actieve gebruikers, maand-op-maand behouden gebruikers, nieuwe gebruikers en de cumulatieve actieve gebruikers.  <br/> |Bevat maandelijkse samengevoegde gegevens voor een rollende periode van 12 maanden inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Product Activity  <br/> |Bevat maandelijkse totalen van activiteiten en actieve gebruikerstelling voor verschillende activiteiten binnen de producten.  <br/> Zie [definitie actieve gebruikers](active-user-in-usage-reports.md) voor informatie over de activiteiten binnen een product die in deze gegevenstabel worden weergegeven.  <br/> |Bevat maandelijkse samengevoegde gegevens voor een rollende periode van 12 maanden inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Office Licenses  <br/> |Bevat gegevens over het aantal Microsoft Office-abonnementen dat is toegewezen aan gebruiker.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Mailbox Usage  <br/> |Bevat gegevens over het postvak van de gebruiker, voor het totale aantal postvakken en de manier waarop opslag wordt gebruikt.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Client Usage  <br/> |Bevat gegevens over het aantal gebruikers dat actief gebruikmaakt van clients en apparaten om verbinding te maken met Exchange Online, Skype voor Bedrijven en Yammer.  <br/> |Bevat maandelijkse samengevoegde gegevens voor een rollende periode van 12 maanden inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant SharePoint Online Usage  <br/> |Bevat gegevens over de SharePoint-team- en groepssites, zoals totaalaantal sites, aantal documenten per site, aantal bestanden per activiteitstype en gebruikte opslagruimte.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant OneDrive for Business Usage  <br/> |Bevat gegevens over de OneDrive-accounts, zoals het aantal accounts, aantal documenten in de OneDrive-accounts, de gebruikte opslagruimte en aantal bestanden per activiteitstype.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Microsoft 365 Groups Usage  <br/> |Bevat gegevens over het gebruik van Microsoft 365 Groepen, waaronder Postvak, SharePoint en Yammer.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|Tenant Office Activation  <br/> |Bevat gegevens over het aantal activeringen van Office-abonnementen, het aantal activeringen per apparaat (Android/iOS/Mac/PC), activeringen per serviceplan, bijvoorbeeld Microsoft 365 Apps voor ondernemingen, Visio, Project.  <br/> |Bevat gegevens over de status van het einde van de maand voor een lopende periode van twaalf maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|User State  <br/> |Bevat metagegevens over gebruikers, waaronder de weergavenaam van de gebruiker, producten die zijn toegewezen, locatie, afdeling, functie en bedrijf. Deze gegevens gaan over gebruikers die tijdens de laatste volledige maand een licentie hebben gekregen. Elke gebruiker wordt uniek vertegenwoordigd door een gebruikers-id.  <br/> |Deze gegevens betreffen gebruikers aan wie in de afgelopen volledige maand een licentie is toegewezen.  <br/> |
|User Activity  <br/> |Bevat informatie op gebruikersniveau over activiteiten die zijn uitgevoerd door gebruikers met een licentie.  <br/> Zie [definitie actieve gebruikers](active-user-in-usage-reports.md) voor informatie over de activiteiten binnen een product die in deze gegevenstabel worden weergegeven.  <br/> |Deze gegevens betreffen gebruikers die een activiteit hebben uitgevoerd in een van de services in de afgelopen volledige maand.  <br/> |
   
Vouw de volgende secties uit om gedetailleerde informatie te zien voor elke gegevenstabel.
  
### <a name="data-table---user-state"></a>Gegevenstabel - User State

Deze tabel bevat details op gebruikersniveau voor alle gebruikers die een licentie aan hen hebben toegewezen tijdens de laatste volledige maand. Deze gegevens zijn afkomstig uit Azure Active Directory.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|UserId  <br/> |Unieke gebruikers-id die een gebruiker vertegenwoordigt en waarmee u kunt deelnemen aan andere gegevenstabellen in de gegevensset.  <br/> |
|Timeframe  <br/> |De waarde van de maand waarvoor deze tabel gegevens bevat.  <br/> |
|UPN  <br/> |User Principal Name, een unieke aanduiding van de gebruiker waarmee een koppeling kan worden gemaakt met andere externe gegevensbronnen.  <br/> |
|Weergavenaam  <br/> |De weergavenaam van de gebruiker.  <br/> |
|IDType  <br/> |Id-type is ingesteld op 1 als de gebruiker een Yammer-gebruiker is die verbinding maakt met behulp van hun Yammer-id of 0 als ze verbinding maken met Yammer met hun Microsoft 365-id.  <br/> Waarde is 1 om aan te geven dat deze gebruiker verbinding maakt met Yammer met hun Yammer-id en niet met hun Microsoft 365-id  <br/> |
|HasLicenseEXO  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van Exchange en deze licentie is ingeschakeld.  <br/> |
|HasLicenseODB  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van OneDrive voor Bedrijven en deze licentie is ingeschakeld.  <br/> |
|HasLicenseSPO  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van SharePoint Online en deze licentie is ingeschakeld.  <br/> |
|HasLicenseYAM  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van Yammer en deze licentie is ingeschakeld.  <br/> |
|HasLicenseSFB  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van Skype voor Bedrijven en deze licentie is ingeschakeld.  <br/> |
|HasLicenseTeams  <br/> |Dit veld bevat True als aan de gebruiker een licentie is toegewezen voor gebruik van Microsoft Teams en deze licentie is ingeschakeld.  <br/> |
|Company  <br/> |De bedrijfsgegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|Department  <br/> |De afdelingsgegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|LocationCity  <br/> |De plaatsgegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|LocationCountry  <br/> |De landgegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|LocationState  <br/> |De staatgegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|LocationOffice  <br/> |Het kantoor van de gebruiker.  <br/> |
|Title  <br/> |De functiegegevens die voor deze gebruiker zijn vermeld in Azure Active Directory.  <br/> |
|Deleted  <br/> |Waar als de gebruiker in die laatste volledige maand is verwijderd uit Microsoft 365.  <br/> |
|Verwijderde datum  <br/> |Datum waarop de gebruiker is verwijderd uit Microsoft 365.  <br/> |
|YAM_State  <br/> |De staten van de gebruiker in het Yammer-systeem kunnen actief, verwijderd of opgeschort zijn.  <br/> |
|YAM_ActivationDate  <br/> |De datum waarop de gebruiker de status Active heeft gekregen in Yammer.  <br/> |
|YAM_DeletionDate  <br/> |De datum waarop de gebruiker de status Deleted heeft gekregen in Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |De datum waarop de gebruiker de status Suspended heeft gekregen in Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Gegevenstabel - User Activity

Deze tabel bevat gegevens over elke gebruiker die in een van de services een activiteit heeft uitgevoerd in de afgelopen maand.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|UserID  <br/> |Unieke gebruikers-id die een gebruiker vertegenwoordigt en waarmee u kunt deelnemen aan andere gegevenstabellen in de gegevensset.  <br/> |
|IDType  <br/> |Id-type is ingesteld op 1 als de gebruiker een Yammer-gebruiker is die verbinding maakt met behulp van hun Yammer-id of 0 als ze verbinding maken met Yammer met hun Microsoft 365-id.  <br/> Waarde is 1 om aan te geven dat deze gebruiker verbinding maakt met Yammer met hun Yammer-id en niet met hun Microsoft 365-id  <br/> |
|Timeframe  <br/> |De waarde van de maand waarvoor deze tabel gegevens bevat.  <br/> |
|EXO_EmailSent  <br/> |Het aantal verzonden e-mailberichten.  <br/> |
|EXO_EmailReceived  <br/> |Het aantal ontvangen e-mailberichten.  <br/> |
|EXO_EmailRead  <br/> |Het aantal e-mailberichten dat de gebruiker heeft gelezen, kan meerdere keren een al gelezen e-mailbericht lezen of een e-mail die eerder is ontvangen.  <br/> |
|EXO_AppointmentCreated  <br/> |Het aantal afspraken dat is aangemaakt.  <br/> |
|EXO_MeetingAccepted  <br/> |Het aantal geaccepteerde uitnodigingen.  <br/> |
|EXO_MeetingCancelled  <br/> |Aantal geannuleerde vergaderingen.  <br/> |
|EXO_MeetingDeclined  <br/> |Het aantal geweigerde uitnodigingen.  <br/> |
|EXO_MeetingSent  <br/> |Het aantal verzonden uitnodigingen.  <br/> |
|ODB_FileViewedModified  <br/> |Het aantal bestanden waarmee deze gebruiker een activiteit heeft uitgevoerd via OneDrive voor Bedrijven (zoals maken, bijwerken, verwijderen, weergeven of downloaden).  <br/> |
|ODB_FileSynched  <br/> |Het aantal bestanden dat deze gebruiker heeft gesynchroniseerd via OneDrive voor Bedrijven.  <br/> |
|ODB_FileSharedInternally  <br/> |Het aantal bestanden dat deze gebruiker intern heeft gedeeld vanuit OneDrive voor Bedrijven of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> |
|ODB_FileSharedExternally  <br/> |Het aantal bestanden dat deze gebruiker extern heeft gedeeld vanaf OneDrive voor Bedrijven.  <br/> |
|ODB_AccessByOwner  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op de eigen OneDrive voor Bedrijven.  <br/> |
|ODB_AccessOthers  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op de OneDrive voor Bedrijven van een andere gebruiker.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad via een groepssite.  <br/> |
|SPO_GroupFileSynched  <br/> |Het aantal bestanden dat door deze gebruiker is gesynchroniseerd via een groepssite.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Het aantal bestanden dat deze gebruiker extern heeft gedeeld vanaf een groepssite.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een groepssite waarvan hij of zij de eigenaar is.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een groepssite waarvan een andere gebruiker de eigenaar is.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad via een andere site.  <br/> |
|SPO_OtherFileSynched  <br/> |Het aantal bestanden dat deze gebruiker heeft gesynchroniseerd via een andere site.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Het aantal bestanden dat deze gebruiker intern heeft gedeeld vanaf een andere site of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Het aantal bestanden dat deze gebruiker extern heeft gedeeld vanaf een andere site.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Het aantal sites waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een andere site waarvan hij of zij de eigenaar is.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Het aantal sites waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een andere site waarvan een andere gebruiker de eigenaar is.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad via een teamsite.  <br/> |
|SPO_TeamFileSynched  <br/> |Het aantal bestanden dat deze gebruiker heeft gesynchroniseerd via een teamsite.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Het aantal bestanden dat deze gebruiker intern heeft gedeeld vanaf een teamsite of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Het aantal bestanden dat deze gebruiker extern heeft gedeeld vanaf een teamsite.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een teamsite waarvan hij of zij de eigenaar is.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Het aantal bestanden waarmee deze gebruiker interactie heeft gehad dat is opgeslagen op een teamsite waarvan een andere gebruiker de eigenaar is.  <br/> |
|Teams_ChatMessages  <br/> |Het aantal verzonden chatberichten.  <br/> |
|Teams_ChannelMessage  <br/> |Het aantal berichten gepubliceerd op kanalen.  <br/> |
|Teams_CallParticipate  <br/> |Het aantal oproepen waar de gebruiker aan heeft deelgenomen.  <br/> |
|Teams_MeetingParticipate  <br/> |Het aantal vergaderingen waar de gebruiker aan heeft deelgenomen.  <br/> |
|Teams_HasOtherAction  <br/> |Booleaanse waarde als de gebruiker andere acties heeft uitgevoerd in Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Het aantal Yammer-berichten dat deze gebruiker heeft gepost.  <br/> |
|YAM_MessageLiked  <br/> |Het aantal Yammer-berichten dat deze gebruiker leuk vond.  <br/> |
|YAM_MessageRead  <br/> |Het aantal Yammer-berichten dat deze gebruiker heeft gelezen.  <br/> |
|SFB_P2PSummary  <br/> |Het aantal peer-to-peer-sessies waaraan deze gebruiker heeft deelgenomen.  <br/> |
|SFB_ConfOrgSummary  <br/> |Het aantal telefonische vergaderingen dat deze gebruiker heeft georganiseerd.  <br/> |
|SFB_ConfPartSummary  <br/> |Het aantal telefonische vergaderingen waaraan deze gebruiker heeft deelgenomen.  <br/> |

> [!NOTE]
> Teams_HasOtherAction betekent dat de gebruiker als actief wordt beschouwd, maar een nulwaarde heeft voor de chatberichten, 1:1-oproepen, Kanaalberichten, Totaal aantal vergaderingen en vergaderingen georganiseerd.
   
### <a name="data-table---tenant-product-usage"></a>Gegevenstabel - Tenant Product Usage

Deze tabel bevat maand-op-maand-acceptatiegegevens in termen van inschakelen, actieve, terugkerende en nieuwe gebruikers voor elk product binnen Microsoft 365. De Microsoft 365-waarden vertegenwoordigen actief gebruik in een van de producten.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|Product  <br/> |Naam van het product waarvoor de gebruiksinformatie wordt samengevat. Microsoft 365-waarde in de productkolom vertegenwoordigt activiteit in een van de producten  <br/> |
|Timeframe  <br/> |Maandwaarde. Er is een rij per product per maand voor de laatste 12 maanden inclusief de huidige gedeeltelijke maand.  <br/> |
|EnabledUsers  <br/> |Het aantal gebruikers dat is ingeschakeld om het product te gebruiken voor de tijd-framewaarde, als een gebruiker is ingeschakeld voor een gedeelte van de maand, wordt nog steeds meegetelde.  <br/> |
|ActiveUsers  <br/> |Het aantal gebruikers dat een opzettelijke activiteit in het product heeft uitgevoerd voor de tijd-framewaarde.  <br/> Gebruikers worden geteld als actief voor een product in een bepaalde maand als ze een van de hoofdactiviteiten hebben uitgevoerd in het product. De hoofdactiviteiten zijn te vinden in de tabel **Tenant Product Activity**.  <br/> |
|CumulatieveactiveUsers  <br/> |Het aantal gebruikers dat is ingeschakeld voor het gebruik van een product, en dat het product ten minste eenmaal heeft gebruikt in de bij Timeframe vermelde maand sinds de start van de gegevensverzameling in het nieuwe gebruikssysteem.  <br/> |
|MoMReturningUsers  <br/> |Het aantal gebruikers dat actief was in de bij Timeframe vermelde waarde en in de maand daarvoor.  <br/> |
|FirstTimeUsers  <br/> |Het aantal gebruikers dat voor het eerst actief werd in de bij Timeframe vermelde waarde sinds de gegevensverzameling in het nieuwe gebruikssysteem.  <br/> Gebruikers worden geteld als nieuwe gebruikers in een bepaalde maand, als hun activiteit voor het eerst wordt gedetecteerd sinds de start van de gegevensverzameling met dit nieuwe rapportagesysteem. Als deze gebruiker eenmaal wordt geteld als een nieuwe gebruiker, zelfs als deze gebruiker een grote kloof in zijn of haar activiteit heeft, wordt deze nooit meer als een nieuwe gebruiker geteld  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Gegevenstabel - Tenant Product Activity

Deze tabel bevat maandelijkse totalen van activiteiten en actieve gebruikerstellingen voor verschillende activiteiten binnen de producten.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|Timeframe  <br/> |Maandwaarde. Er is een rij per product per maand voor de laatste 12 maanden inclusief de huidige gedeeltelijke maand.  <br/> |
|Product  <br/> |Naam van het product in Microsoft 365 waarvoor gebruiksgegevens beschikbaar zijn.  <br/> |
|Activity  <br/> |De naam van de activiteit in een product dat wordt gebruikt om het actieve gebruik van het product te laten zien.  <br/> |
|ActivityCount  <br/> |Het totale aantal acties die zijn geteld voor elke activiteit die is uitgevoerd binnen het product door alle actieve gebruikers.  <br/> **Opmerking:** Bij activiteiten binnen SharePoint Online en OneDrive voor Bedrijven geeft deze waarde het aantal unieke documenten aan waarmee gebruikers interactie hebben gehad.  <br/> |
|ActiveUserCount  <br/> |Het aantal gebruikers dat de activiteit binnen het product heeft uitgevoerd.  <br/> |
|TotalDurationInMinute  <br/> |De totale duur in minuten voor alle gebruikers die een audio- of videosessie hebben gebruikt in een toepasselijke Skype voor Bedrijven-activiteit.  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Gegevenstabel - Tenant Mailbox Usage

Deze tabel bestaat uit overzichtsgegevens voor alle gelicentieerde Exchange Online-gebruikers met een gebruikerspostvak. De tabel bevat de status van alle gebruikerspostvakken aan het einde van de maand. De gegevens in deze tabel zijn geen optelling van meerdere maanden. De gegevens van de afgelopen maand in deze tabel vertegenwoordigen de recentste status.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|TotalMailboxes  <br/> |Aantal gebruikerspostvakken voor Microsoft 365-abonnement.  <br/> |
|IssueWarningQuota  <br/> |Totaal quotum voor het geven van een waarschuwing in alle postvakken van alle gebruikers.  <br/> |
|ProhibitSendQuota  <br/> |Totaal quotum voor het verbieden van verzenden voor alle gebruikerspostvakken.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Totaal quotum voor het verbieden van ontvangen voor alle gebruikerspostvakken.  <br/> |
|TotalItemBytes  <br/> |De hoeveelheid opslagruimte in bytes die wordt gebruikt door alle gebruikerspostvakken.  <br/> |
|PostvakkenNoWarning  <br/> |Het aantal gebruikerspostvakken dat zich onder de waarschuwingslimiet voor opslagruimte bevindt.  <br/> |
|PostvakkenIssueWarning  <br/> |Het aantal gebruikerspostvakken dat een waarschuwing heeft ontvangen met betrekking tot het opslagquotum.  <br/> |
|PostvakkenExceedSendQuota  <br/> |Het aantal gebruikerspostvakken dat het verzendquotum heeft overschreden.  <br/> |
|PostvakkenExceedSendReceiveQuota  <br/> |Het aantal gebruikerspostvakken dat het quotum voor verzenden/ontvangen heeft overschreden.  <br/> |
|Verwijderde e-mailboxen  <br/> |Het aantal gebruikerspostvakken dat in de periode is verwijderd.  <br/> |
|Timeframe  <br/> |Maandwaarde.  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Gegevenstabel - Tenant Client Usage

Deze tabel bevat overzichtsgegevens over de maand-op-maand over de clients die de gebruikers gebruiken om verbinding te maken met Exchange Online, Skype voor Bedrijven en Yammer. Deze tabel bevat nog geen gegevens over de clients die worden gebruikt met SharePoint Online en OneDrive voor Bedrijven.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|Product  <br/> |Naam van het product in Microsoft 365 waarvoor klantgebruiksgegevens beschikbaar zijn.  <br/> |
|ClientId  <br/> |Naam van het apparaat waarmee verbinding wordt gemaakt met het product.  <br/> |
|UserCount  <br/> |Het aantal gebruikers dat elk van de clients voor elk product heeft gebruikt.  <br/> |
|Timeframe  <br/> |Maandwaarde  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Gegevenstabel - Tenant SharePoint Online Usage

Deze tabel bestaat uit maand-op-maandoverzichtsgegevens over het gebruik of de activiteit van SharePoint Online-sites. Dit geldt alleen voor teamsites en groepssites. De status einde van de maand van SharePoint Online-sites wordt weergegeven in deze kolom, bijvoorbeeld als een gebruiker vijf documenten heeft gemaakt en 10 MB voor totale opslag heeft gebruikt, en vervolgens enkele bestanden heeft verwijderd en meer bestanden heeft toegevoegd, zodat aan het einde van de maand de status voor bestanden zeven totaal is waarin vijf MB opslagruimte wordt gebruikt, is de waarde van die in deze tabel de status einde van de maand. Deze tabel is verborgen om dubbele aggregaties te voorkomen en wordt gebruikt als bron om twee verwijzingstabellen te maken.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|SiteType  <br/> |Waarde voor het sitetype (any/team/group) ('any' kan staan voor elk van de 2 sitetypen).  <br/> |
|TotalSites  <br/> |Het aantal sites aan het einde van de periode.  <br/> |
|DocumentTelling  <br/> |Het totaalaantal documenten op de site aan het einde van de periode.  <br/> |
|Diplansed  <br/> |De totale gebruikte opslagruimte voor alle sites aan het einde van de periode.  <br/> |
|ActivityType  <br/> |Het aantal sites dat de verschillende soorten bestandsactiviteit (any/active files/ files shared EXT/INT/files synched) heeft geregistreerd.  <br/> Vertegenwoordigt een van de bestandsactiviteit die is uitgevoerd.  <br/> |
|SitesWithOwnerActivities  <br/> |Het aantal actieve sites waarop de site-eigenaar een bepaalde activiteit met bestanden heeft uitgevoerd op een eigen site. U kunt de site-eigenaar van de **PowerShell-opdracht get-sposite krijgen.** Dit is de persoon die verantwoordelijk is voor de site.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Het totaalaantal actieve sites waarop gebruikers anders dan de site-eigenaar een bepaalde activiteit met bestanden hebben uitgevoerd in een maand. U kunt de site-eigenaar van de **PowerShell-opdracht get-sposite krijgen.** Dit is de persoon die verantwoordelijk is voor de site. <br/> |
|ActivityTotalSites  <br/> |Het aantal sites waarop een activiteit is uitgevoerd in de periode. Als er aan het begin van de periode activiteit heeft plaatsgevonden op een site die later in de periode is verwijderd, wordt die activiteit toch meegeteld voor het totaal voor die periode.  <br/> |
|Timeframe  <br/> |Deze kolom bevat de datumwaarde. Wordt gebruikt als veel-op-een-relatie met tabel Calendar.  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Gegevenstabel - Tenant OneDrive-gebruik

Deze tabel bevat gegevens over de OneDrive-accounts zoals het aantal accounts, het aantal documenten in de OneDrive-accounts, de gebruikte opslag en het aantal bestanden per type activiteit. Deze tabel bevat de status van het OneDrive voor Bedrijven-account aan het einde van de maand. Als een gebruiker bijvoorbeeld een Vijf documenten heeft gemaakt waarin 10 MB opslagruimte is gebruikt, en vervolgens een paar bestanden heeft verwijderd en meer bestanden heeft toegevoegd, zodat ze aan het einde van de maand zeven bestanden hebben die vijf MB opslagruimte gebruiken, wordt het einde van de maandwaarde weergegeven in deze tabel aan het einde van de maand.
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|SiteType  <br/> |Waarde is 'OneDrive'.  <br/> |
|TotalSites  <br/> |Het aantal OneDrive voor Bedrijven-accounts aan het einde van de periode.  <br/> |
|DocumentTelling  <br/> |Het aantal documenten in alle OneDrive voor Bedrijven-accounts aan het einde van de periode.  <br/> |
|Diplansed  <br/> |De totale gebruikte opslagruimte wordt opgeteld in alle OneDrive-account aan het einde van de periode.  <br/> |
|ActivityType  <br/> |Het aantal accounts dat de verschillende soorten bestandsactiviteit (any/active files/ files shared EXT/INT/files synched) heeft geregistreerd.  <br/> Any geeft aan dat een van de bestandsactiviteiten is uitgevoerd  <br/> |
|SitesWithOwnerActivities  <br/> |Het aantal actieve OneDrive voor Bedrijven-accounts waarbinnen de accounteigenaar een bepaalde bestandsactiviteit heeft uitgevoerd voor het eigen account.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Het aantal OneDrive voor Bedrijven-accounts waarmee bestandsactiviteit is uitgevoerd door andere gebruikers dan de eigenaar van het account.  <br/> |
|ActivityTotalSites  <br/> |Het aantal OneDrive voor Bedrijven-accounts waarvoor activiteiten zijn geregistreerd in de periode. Als er aan het begin van de periode activiteit is geregistreerd voor het OneDrive voor Bedrijven-account, en het account is aan het einde van de periode is verwijderd, wordt het toch meegeteld voor de actieve OneDrive voor Bedrijven-accounts in die periode.  <br/> |
|Timeframe  <br/> |Deze kolom bevat de datumwaarde. Wordt gebruikt als veel-op-een-relatie met tabel Calendar.  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Gegevenstabel - Tenant Microsoft 365 Groups Usage

Deze tabel bevat gegevens over hoe Microsoft 365 Groepen in de hele organisatie worden gebruikt.
  
****

|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|Tijdsbestek  <br/> |Maandwaarde. Er is een rij per product per maand voor de laatste 12 maanden, inclusief de huidige gedeeltelijke maand.  <br/> |
|GroupType  <br/> |Het type groep (privé/openbaar/beide).  <br/> |
|TotalGroups  <br/> |Aantal groepen in elk groepstype.  <br/> |
|ActiveGroups  <br/> |Aantal actieve gebruikers.  <br/> |
|MBX_TotalGroups  <br/> |Aantal mailbox-groepen.  <br/> |
|MBX_ActiveGroups  <br/> |Aantal actieve mailbox-groepen.  <br/> |
|MBX_TotalActivities  <br/> |Aantal mailbox-activiteiten.  <br/> |
|MBX_TotalItems  <br/> |Aantal mailbox-items.  <br/> |
|MBX_StorageUsed  <br/> |Hoeveelheid gebruikte e-mailopslag.  <br/> |
|SPO_TotalGroups  <br/> |Aantal SharePoint-groepen.  <br/> |
|SPO_ActiveGroups  <br/> |Aantal actieve SharePoint-groepen.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Aantal SharePoint-groepen met activiteiten die zijn toegankelijk voor bestanden.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Aantal SharePoint-groepen met bestandsgesynchroniseerde activiteiten.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Aantal SharePoint-groepen met gedeelde activiteiten intern of met groepen (waaronder mogelijk externe gebruikers).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Aantal SharePoint-groepen met activiteiten van externe deling.  <br/> |
|SPO_TotalActivities  <br/> |Aantal SharePoint-activiteiten.  <br/> |
|SPO_FileAccessedActivities  <br/> |Aantal SharePoint-activiteiten van openen van bestanden.  <br/> |
|SPO_FileSyncedActivities  <br/> |Aantal SharePoint-activiteiten van synchronisatie van bestanden.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Het aantal gedeelde sharepoint-activiteiten in een SharePoint-bestand of met groepen (waaronder mogelijk externe leden).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Aantal SharePoint-activiteiten van extern gedeelde bestanden.  <br/> |
|SPO_TotalFiles  <br/> |Aantal SharePoint-bestanden.  <br/> |
|SPO_ActiveFiles  <br/> |Aantal actieve SharePoint-bestanden.  <br/> |
|SPO_StorageUsed  <br/> |Hoeveelheid gebruikte SharePoint-opslag.  <br/> |
|YAM_TotalGroups  <br/> |Het aantal Yammer-groepen.  <br/> |
|YAM_ActiveGroups  <br/> |Het aantal actieve Yammer-groepen.  <br/> |
|YAM_LikedActiveGroups  <br/> |Het aantal Yammer-groepen met vind-ik-leuk-activiteiten.  <br/> |
|YAM_PostedActiveGroups  <br/> |Het aantal Yammer-groepen met publiceer-activiteiten.  <br/> |
|YAM_ReadActiveGroups  <br/> |Het aantal Yammer-groepen met lees-activiteiten.  <br/> |
|YAM_TotalActivities  <br/> |Het aantal Yammer-activiteiten.  <br/> |
|YAM_LikedActivities  <br/> |Het aantal Yammer vind-ik-leuk-activiteiten.  <br/> |
|YAM_PostedActivties  <br/> |Het aantal Yammer publiceer-activiteiten.  <br/> |
|YAM_ReadActivites  <br/> |Het aantal Yammer lees-activiteiten.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Gegevenstabel - Tenant Office Activation

De tabel bevat gegevens over het aantal activeringen van Office-abonnementen in de serviceabonnementen, bijvoorbeeld Microsoft 365 Apps voor ondernemingen, Visio, Project. De tabel bevat ook gegevens over het aantal activeringen per apparaat (Android/iOS/Mac/pc).
  
|**Kolomnaam**|**Kolombeschrijving**|
|:-----|:-----|
|ServicePlanName  <br/> |Een lijst met de naamwaarden van serviceplannen en het aantal activeringen per apparaat, zoals weergegeven in de onderstaande kolommen.  <br/> |
|TotalEnabled  <br/> |Het totaalaantal ingeschakelde gebruikers per serviceplan aan het einde van de periode.  <br/> |
|TotalActivatedUsers  <br/> |Het aantal gebruikers dat elk serviceplan heeft geactiveerd aan het einde van de periode.  <br/> |
|AndroidCount  <br/> |Het aantal activeringen voor een Android-apparaat per serviceplan aan het einde van de periode.  <br/> |
|iOSCount  <br/> |Het aantal activeringen voor een iOS-apparaat per serviceplan aan het einde van de periode.  <br/> |
|MacCount  <br/> |Het aantal activeringen voor een Mac-apparaat per serviceplan aan het einde van de periode.  <br/> |
|PcCount  <br/> |Het aantal activeringen voor een pc-apparaat per serviceplan aan het einde van de periode.  <br/> |
|WinRtCount  <br/> |Het aantal activeringen voor een Windows Mobile-apparaat per serviceplan aan het einde van de periode.  <br/> |
|Timeframe  <br/> |Deze kolom bevat de datumwaarde. Wordt gebruikt als veel-op-een-relatie met tabel Calendar.  <br/> |
|Content date  <br/> |Als het veld Timeframe de huidige maand bevat, geeft deze waarde de laatste datum in de huidige maand aan waarvoor gegevens beschikbaar zijn.  <br/> Als het veld Timeframe de vorige maand bevat, geeft deze waarde de laatste datum van die maand aan.  <br/> |
