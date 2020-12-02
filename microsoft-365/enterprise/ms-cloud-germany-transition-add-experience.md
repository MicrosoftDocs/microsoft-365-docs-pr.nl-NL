---
title: Aanvullende informatie over de ervaring voor de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: aanvullende informatie over de gebruikerservaring wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551873"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende informatie over de ervaring voor de migratie van Microsoft Cloud Deutschland 

In de volgende secties vindt u aanvullende informatie over de ervaringen van klanten.

## <a name="services"></a>Services

### <a name="azure-ad"></a>Azure AD

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Azure AD-Tenant in Microsoft Cloud Deutschland gekopieerd naar Office 365-Services. | Azure AD kopieert de Tenant naar Office 365-Services. Tenant-en gebruikers-id's blijven behouden. Azure AD-serviceoproepen worden doorgestuurd van Microsoft Cloud Deutschland naar Office 365-Services en zijn transparant voor de services. | Alle Office-klanten | -De algemene informatie beschermings verordening (AVG) data subject requests (DSRs) worden uitgevoerd vanuit de Azure-beheerportal voor toekomstige aanvragen. Verouderde of niet-klant diagnostische gegevens die ingezetene zijn van Microsoft Cloud Deutschland, worden op of vóór 30 dagen verwijderd. <br><br> -Klanten die gebruikmaken van federatieve authenticaties met Active Directory Federation Services (AD FS), mogen geen wijzigingen aanbrengen in de instellingen van de Issuer die worden gebruikt voor alle authenticaties met on-premises Active Directory tijdens het migreren. Het wijzigen van de uitgevers van de uitgevers heeft tot Verificatiefouten voor gebruikers in het domein tot gevolg. Uri's van de Issuer kunnen rechtstreeks in AD FS worden gewijzigd of wanneer een domein wordt geconverteerd van _beheerd_ naar _federatief_ en vice versa. U wordt aangeraden geen federatief domein toe te voegen, te verwijderen of te converteren in de Azure AD-Tenant die is gemigreerd. U kunt Uri's van de Issuer wijzigen na voltooiing van de migratie. <br><br> -Aanvragen van multi-factor Authentication (MFA) die gebruikmaken van Microsoft Authenticator, worden weergegeven als de gebruikers-id (GUID) terwijl de Tenant wordt gekopieerd naar Office 365-Services. MFA-aanvragen worden uitgevoerd zoals verwacht, ondanks dit scherm gedrag.  Accounts van Microsoft Authenticator die zijn geactiveerd met Office 365-service-eindpunten, geven de UPN (User Principal Name) weer.  Accounts die met behulp van Microsoft Cloud Deutschland-eindpunten zijn toegevoegd, geven de gebruikers-ObjectID weer, maar werken met zowel Microsoft Cloud Deutschland als Office 365 service-eindpunten.  |
| Breng AuthServer on-premises gerichte gerichte service voor internationale STS. | Hierdoor wordt voorkomen dat aanvragen van gebruikers die naar Microsoft Cloud Deutschland worden gemigreerd naar Microsoft Cloud beschikbaarheids verzoeken die de hybride on-premises omgeving bedoelen, worden geverifieerd om toegang te krijgen tot de on-premises service. Op deze manier zorgt u ervoor dat aanvragen van on-premises naar Office 365-Services-eindpunten worden geverifieerd. | Exchange Online-klanten met hybride implementaties (on-premises) | Wanneer Azure AD-migratie is voltooid, moet de beheerder van de hybride topologie voor Exchange (hybride) een nieuw eindpunt voor verificatieservice toevoegen voor de Office 365-Services. Met deze opdracht van Exchange PowerShell vervangt `<TenantID>` u de naam van de Tenant-id van uw organisatie (gevonden in azure-Portal op **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Als u deze taak niet voltooit, kan dit leiden tot hybride beschikbaarheidsinfo die niet meer informatie levert voor Postvak gebruikers die zijn gemigreerd van Microsoft Cloud Deutschland naar Office 365-Services.  |
| Migratie van Azure-bronnen. | Voor klanten die gebruikmaken van Office 365 en Azure-bronnen (bijvoorbeeld netwerken, compute en opslag), wordt de migratie van bronnen naar het Office 365 Services-service-exemplaar uitgevoerd. Deze migratie is verantwoordelijk voor klanten. Berichten in het berichtencentrum signaleren het begin. De migratie moet worden voltooid vóór voltooiing van de Azure AD-organisatie in de Office 365-service omgeving. | Azure-klanten | Voor Azure-migraties raadpleegt u de Azure Migration Playbook, [overzicht van migratie richtlijnen voor Azure Duitsland](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

Met **set-UserPhoto**:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| De nieuwe Duitse regio wordt toegevoegd aan een bestaande organisatie-instelling, en postvakken worden verplaatst naar Office 365-Services. | Exchange Online-configuratie voegt de nieuwe Go-Local Duitse regio toe aan de overgangs organisatie. Deze regio van Office 365-Services wordt ingesteld als standaard, zodat de interne taakverdelingsservice postvakken opnieuw kan distribueren naar het juiste standaardgebied in Office 365-Services. In deze overgang bevinden gebruikers aan de kant (Duitsland of Office 365-Services) zich in dezelfde organisatie en kunnen beide URL-eindpunten gebruiken. |  Exchange Online | Als het postvak van een gebruiker is gemigreerd, maar het postvak van een beheerder niet is gemigreerd, of andersom, kunnen beheerders de PowerShell-cmdlet **UserPhoto** niet uitvoeren. In deze situatie moet een beheerder een extra tekenreeks `ConnectionUri` tijdens de verbinding opgeven met behulp van de volgende syntaxis: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> waar `<user_email>` is de tijdelijke aanduiding voor de e-mail-id van de gebruiker van wie de foto moet worden gewijzigd met behulp van **set-UserPhoto**. |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

Als u een hybride, on-premises implementatie gebruikt:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
|Onboarding of offboarding-verplaatsingen van postvakken stoppen of verwijderen.  | Hierdoor wordt voorkomen dat verplaatsings aanvragen een fout veroorzaakt. | Exchange Online-klanten met hybride implementaties (on-premises) | Vereiste actie. Dit kan wel, vanwege storing van de service of van software-clients. |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamiek

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bronnen voor Microsoft Dynamics | Klanten met Microsoft Dynamics worden gecommuniceerd via engineering of FastTrack voor het overstappen van een dynamiek naar het Office 365-service-exemplaar. * | Microsoft Dynamics 365-klanten | -Na migratie is de beheerder in de organisatie gevalideerd. <br><br> -De beheerder wijzigt de werkstromen, indien nodig. <br><br> -De beheerder wist de AdminOnly-modus, indien van toepassing. <br><br> -De beheerder wijzigt de naam van het organisatietype van de _sandbox_, indien van toepassing <br><br> -Meld eindgebruikers van de nieuwe URL om toegang te krijgen tot het exemplaar (organisatie). <br><br> -Alle inkomende verbindingen bijwerken naar de nieuwe eindpunt-URL. <br><br> -De Dynamics-service is tijdens de overgang niet beschikbaar voor gebruikers. <br><br> -Gebruikers moeten de gezondheid en de functies van de organisatie na de migratie van elke organisatie valideren.  |
|||||

\* (i) klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd door het migratieproces. (II) de klant kon een actie ondernemen om actie te ondernemen, zodat Microsoft de migratie niet kan voltooien. (III) wanneer Microsoft de migratie niet kan voltooien vanwege de inactief van de klant, verloopt het abonnement van de klant op 29 oktober 2021. 


### <a name="power-bi"></a>Power BI

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Power BI-bronnen | Klanten met Microsoft Power BI worden onderbouwd via engineering of FastTrack, nadat ze handmatig een bestaand PBI-migratieprogramma hebben geactiveerd, zodat Power BI naar het Office 365 service-exemplaar wordt overgezet.\*\* | Klanten van Microsoft Power BI | -De volgende Power BI-items worden _niet_ overgezet en ze moeten opnieuw worden gemaakt: <br><br> -Realtime gegevenssets (bijvoorbeeld streaming of push datasets). <br> -Power BI on-premises configuratie van gegevensgateway en gegevensbron. <br> -Rapporten die worden gebouwd boven de realtime-gegevenssets, zijn na de migratie niet beschikbaar en moeten opnieuw worden gemaakt. <br><br> Power BI-Services zijn tijdens de overgang niet beschikbaar voor gebruikers. De service mag niet langer dan 24 uur duren. <br><br> -Gebruikers moeten gegevensbronnen en hun on-premises gegevensgateway opnieuw configureren met de Power BI-service na de migratie.  En als u dat doet, kunnen gebruikers deze gegevensbronnen niet gebruiken voor het uitvoeren van geplande vernieuwingen en/of direct queries voor deze gegevensbronnen. <br><br> -Capaciteiten en Premium-werkruimten kunnen niet worden gemigreerd. Klanten moeten alle capaciteiten verwijderen voordat ze worden gemigreerd en opnieuw maken na migratie. Verplaats werkruimten naar de gewenste capaciteit.  |
|||||

\*\* (i) klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd door het migratieproces. (II) de klant kon een actie ondernemen om actie te ondernemen, zodat Microsoft de migratie niet kan voltooien. (III) wanneer Microsoft de migratie niet kan voltooien vanwege de inactief van de klant, verloopt het abonnement van de klant op 29 oktober 2021. 


### <a name="office-apps"></a>Office-apps

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Klanten, Office Online tijdens Office-client cutover, voltooit Azure AD het Tenant bereik zodat ze verwijzen naar de Office 365-Services.<!--v-gmoor: What?--> | Met deze configuratiewijziging kunt u Office-clients bijwerken en de eindpunten van Office 365 services aanwijzen. | Alle Office-klanten | -Verwijder MSOID CName uit de klant die de eigenaar is van de klant, indien aanwezig. <br><br> -Gebruikers informeren om _alle_ Office-apps te sluiten en vervolgens aan te melden (of clients geforceerd opnieuw te starten en gebruikers aan te melden) als u wilt dat Office-clients de wijziging kunnen overnemen. <br><br> -Waarschuw gebruikers en helpdesk-medewerkers die gebruikers *kunnen* zien dat ze vragen om Office-apps binnen 72 uur na de cutover te activeren. <br><br> -Alle Office-toepassingen op persoonlijke apparaten moeten worden gesloten en gebruikers moeten zich afmelden en vervolgens weer aanmelden. Meld u op de gele activeringsbalk aan om opnieuw te activeren voor Office 365-Services. <br><br> Voor gedeelde computers zijn acties vereist die lijken op pc's die vergelijkbaar zijn met persoonlijke machines en waarvoor geen speciale procedure is vereist. <br><br> -Op mobiele apparaten moeten gebruikers zich afmelden bij apps, ze sluiten en opnieuw aanmelden. |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>Tijdens de migratie


### <a name="exchange-online"></a>Exchange Online

Voor eDiscovery:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Tijdens het migratieproces worden eDiscovery-zoekopdrachten mislukt of worden deze geretourneerd door de SharePoint Online-, OneDrive voor bedrijven-en Exchange Online-locaties die zijn gemigreerd. | Tijdens de migratie kunnen klanten het nalevings centrum voor de beveiliging en de functies voor de & beveiliging van de inhoud van de gebruikers blijven maken.  Zoekopdrachten naar SharePoint Online, OneDrive voor bedrijven en Exchange Online-locaties die zijn gemigreerd, leveren echter 0 resultaten op of veroorzaken een fout. Zie de kolom _impact_ voor herstel. | Alle klanten die eDiscovery gebruiken |  Wanneer een zoekopdracht 0 resultaten of een fout tijdens de migratie oplevert, kunt u de volgende actie ondernemen voor SharePoint Online: <br><br>  Download sites rechtstreeks vanuit de SharePoint Online-OneDrive voor bedrijven-site door de instructies te volgen in [bestanden en mappen downloaden vanuit OneDrive of SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Voor deze methode zijn beheerdersmachtigingen voor SharePoint Online of alleen-lezen machtigingen voor de site vereist. <br><br> Als de limieten worden overschreden, zoals wordt uitgelegd in [bestanden en mappen downloaden vanuit OneDrive of SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), kunnen klanten de Synchronisatieclient van OneDrive voor bedrijven gebruiken aan de hand van de richtlijnen in [SharePoint-en teams-bestanden synchroniseren met uw computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88). <br><br> -Exchange Online <br><br> - [In-place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| SharePoint en OneDrive worden doorgeschakeld. | SharePoint en OneDrive worden gemigreerd van Microsoft Cloud Deutschland naar Office 365-Services in deze fase. Bestaande Url's voor Microsoft Cloud Deutschland blijven behouden ( `contoso.sharepoint.de` ). Tokens die worden uitgegeven door Microsoft Cloud Deutschland of Office 365-Services zijn geldig tijdens de overgang. | SharePoint-klanten | Inflight SharePoint 2013-werkstromen worden tijdens de migratie verbroken en moeten na de migratie opnieuw worden gepubliceerd. |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Skype voor bedrijven naar teams. | Bestaande Skype voor bedrijven-klanten worden gemigreerd naar Office 365-Services in Europa en worden vervolgens overgezet naar Microsoft teams in de Duitse regio van Office 365-Services. | Skype voor bedrijven-klanten |  PowerShell zal gebruiken voor het beheren van de instellingen en het beleid voor uw Tenant en gebruikers. Wanneer u verbinding maakt met een PowerShell-sessie, voegt u het volgende toe: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>Na de migratie

### <a name="azure-ad"></a>Azure AD

Voor hybride:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Azure AD Connect bijwerken. | Nadat de cut naar Azure AD is voltooid, gebruikt de organisatie Office 365-Services en is niet langer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant ervoor zorgen dat het deltasynchronisatie proces is voltooid en vervolgens de tekenreekswaarde van `AzureInstance` 3 (Microsoft Cloud Deutschland) in 0 in het pad voor het register wijzigen `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Hybride Azure AD-verbonden organisaties | Wijzig de waarde van `AzureInstance` de registersleutel. Er kan niet worden gemigreerd naar objecten die niet worden gesynchroniseerd wanneer de Microsoft Cloud Deutschland-eindpunten niet langer beschikbaar zijn. |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

Voor federatieve verificatie:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijder vertrouwensrelaties van de vertrouwens partij van Microsoft Cloud Deutschland AD FS. | Nadat de cut naar Azure AD is voltooid, gebruikt de organisatie Office 365-Services en is niet langer verbonden met Microsoft Cloud Deutschland. De klant moet nu een vertrouwensrelatie tussen de partijen met de Microsoft Cloud Deutschland-eindpunten verwijderen. Dit kan alleen worden gedaan wanneer een toepassing van de klant Point-eindpunten van Microsoft Cloud Deutschland als een identiteits provider (IdP) wordt benut. | Organisaties voor Federatie verificatie | Zonder. |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Voor Azure AD:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Aanvragen om deel te nemen aan een Azure AD-groep in de afgelopen 30 dagen voordat de migratie opnieuw moet worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd. | Gebruikers van eindgebruikers moeten het toegangsvenster gebruiken om aanvragen te doen om deel te nemen aan een Azure AD-groep, als die aanvragen niet in de afgelopen 30 dagen voor de migratie zijn goedgekeurd. | Eindgebruikers van wie de goedkeuringsaanvragen van Azure AD-groepen niet in de afgelopen 30 dagen voor de migratie zijn goedgekeurd |  Als eindgebruiker: <ol><li>Ga naar [het Access-venster](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Zoek een Azure AD-groep waarvoor de goedkeuring van het lidmaatschap binnen 30 dagen vóór de migratie is voltooid.</li><li>Verzoek om deel te nemen aan de Azure AD-groep.</li></ol> Aanvragen om deel te nemen aan een groep die minder dan 30 dagen actief zijn voordat de migratie kan niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd. |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

Voor DNS:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| On-premises DNS services bijwerken voor Office 365-service-eindpunten. | Door de klant beheerde DNS-vermeldingen die verwijzen naar Office 365 Duitsland, moeten verwijzen naar de eindpunten van Office 365-Services. | Alle Office-klanten | Vereiste actie. Dit kan wel, vanwege storing van de service of van software-clients. |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Voor services van derden voor Office 365-Services:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Update partners en services van derden voor Office 365-Services-eindpunten. | -Services van derden en partners die verwijzen naar Office 365 Duitsland moeten verwijzen naar de eindpunten van Office 365 Services. Voorbeeld: opnieuw registreren, in uitlijning met leveranciers en partners, de versie van de galerie-app van toepassingen, indien beschikbaar. <br><br> -Wijs alle aangepaste toepassingen af waarbij de grafiek-API wordt benut `graph.microsoft.de` `graph.microsoft.com` . Andere Api's met gewijzigde eindpunten moeten ook worden bijgewerkt, indien van gebruik. <br><br> -Alle niet-eerste bedrijfstoepassings toepassingen wijzigen om om te leiden naar de wereldwijde eindpunten.  | Alle Office-klanten | Vereiste actie. Dit kan wel, vanwege storing van de service of van software-clients. |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

Als u een hybride Exchange-configuratie gebruikt:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Voer de wizard hybride configuratie (HCW) uit voor Office 365-Services. | De bestaande HCW configuratie is bedoeld voor de ondersteuning van Microsoft Cloud Deutschland. Bij de migratie van Exchange Services is de on-premises configuratie van Microsoft Cloud Deutschland. | Exchange Online-klanten die een hybride implementatie uitvoeren | -Vereiste actie. Dit kan wel, vanwege storing van de service of van software-clients. Voordat migratie van een Exchange-postvak begint (met 5 of meer dagen), informeren klanten clients dat ze onboarding-of offboarding-verplaatsingen van hun postvakken stoppen en verwijderen.  Als dat niet het geval is, zien ze de fouten in hun verplaatsings verzoeken. <br><br> -Nadat Exchange-postvak migratie is voltooid, moet u klanten informeren dat ze onboarding en offboarding-verplaatsings berichten kunnen hervatten. <br> Het uitvoeren van **test-MigrationServerAvailabiilty**, een PowerShell-cmdlet, tijdens het migreren van Exchange via Microsoft Cloud Deutschland naar Office 365-Services werkt mogelijk niet. Het werkt echter goed na voltooiing van de migratie. <br><br> Als clients problemen ondervinden met referenties of autorisatie nadat de postvakken zijn gemigreerd, kunnen gebruikers hun on-premises beheerdersreferenties in het migratie-eindpunt `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` opnieuw invoeren, of ze ook instellen via het Configuratiescherm van Exchange (ECP).  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

Voor eDiscovery:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
|  Alle locaties van SharePoint Online, OneDrive voor bedrijven en Exchange Online zijn gemigreerd naar beveiligings-en compliance Center (SCC). | Alle eDiscovery-activiteiten moet worden uitgevoerd vanuit de wereldwijde Tenant. De zoekopdracht is nu 100% gelukt.  Eventuele fouten of fouten moeten de normale ondersteuningskanalen volgen. | Alle klanten die eDiscovery gebruiken | Zonder. |
| Beleidsregels voor bewaarbeleid voor de gehele organisatie verwijderen die zijn gemaakt tijdens de voorafgaande migratiestappen | Klanten kunnen het bewaarbeleid voor de organisatie verwijderen dat is gemaakt tijdens de voorafgaande migratie van de klanten. | Alle klanten die een bewaarbeleid hebben toegepast als onderdeel van de voorbereidende migratiestappen. | Zonder. |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Publiceer 2013-werkstromen in SharePoint opnieuw. | Voor de voorafgaande migratie hebben we het aantal werkstromen van SharePoint 2013 verlaagd. De klant kan nu de werkstromen opnieuw publiceren wanneer de migratie is voltooid. | Alle Office-klanten | Dit is een vereiste actie. Dit kan niet, maar kan leiden tot verwarring van de gebruiker en de helpdesk. |
| Items delen via Outlook | Het delen van items via Outlook werkt niet meer na de Tenant cutover. | SharePoint Online en OneDrive voor Bedrijven | -In SharePoint Online en OneDrive voor bedrijven kunt u items delen via Outlook. Nadat u op de knop Outlook hebt geklikt, wordt een deelbare koppeling gemaakt en naar een nieuw bericht in de Outlook Web app geduwd. <br><br> -Na Tenant cutover werkt deze methode van delen niet. Dit kent een bekend probleem. Deze Outlook-functie is echter in het pad van de afschaffing, en het oplossen van het probleem niet is gepland totdat de afschaffing is uitgerold. |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>Volgende stap

[Meer informatie over de acties en effecten voor migratie fasen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Acties en effecten bij migratie fasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
