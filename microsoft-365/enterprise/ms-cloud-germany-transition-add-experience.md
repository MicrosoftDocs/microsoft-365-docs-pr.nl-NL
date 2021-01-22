---
title: Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (geavanceerd)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Overzicht: Aanvullende klantervaringsinformatie wanneer u overstapt van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 3f9bc40d7551dfcdb65abcf8b150f98b8242d7d2
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921688"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (geavanceerd) 

Tenantmigraties van Microsoft Cloud Deutschland naar de Regio Duitsland van De Office 365-services van Microsoft worden uitgevoerd als een set fasen en de geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

In de volgende secties vindt u aanvullende informatie over de klantervaringen bij het over stappen van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.

## <a name="services"></a>Services

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (fase 2 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Azure AD-tenant in Microsoft Cloud Deutschland gekopieerd naar Office 365-services. | Azure AD kopieert de tenant naar Office 365-services. Tenant- en gebruikers-id's blijven behouden. Azure AD-servicegesprekken worden omgeleid van Microsoft Cloud Deutschland naar Office 365-services en zijn transparant in de services. | Alle Office-klanten | - De Algemene Verordening Gegevensbescherming (AVG) Verzoeken van personen die van toepassing zijn op de gegevens (DSR's) worden uitgevoerd vanuit de Azure Admin Portal voor toekomstige aanvragen. Verouderde of niet-klant diagnostische gegevens die beschikbaar zijn in Microsoft Cloud Deutschland, worden na of na 30 dagen verwijderd. <br><br> - Klanten die federatieverificatie gebruiken met Active Directory Federation Services (AD FS), mogen tijdens de migratie geen wijzigingen aanbrengen in URI's van probleemgevers die worden gebruikt voor alle verificaties met on-premises Active Directory. Het wijzigen van URI's voor probleemgebruikers leidt tot verificatiefouten voor gebruikers in het domein. URI's van probleemgevers kunnen rechtstreeks in AD  FS worden gewijzigd of wanneer een domein wordt geconverteerd van beheerd naar _federatief_ en omgekeerd. Klanten wordt aangeraden een gemigreerd domein dat is gemigreerd in de Azure AD-tenant niet toe te voegen, te verwijderen of te converteren. URI's van probleemgevers kunnen worden gewijzigd nadat de migratie volledig is voltooid. <br><br> - Meervoudige verificatie (Multi-Factor Authentication, MFA) aanvragen die Microsoft Authenticator gebruiken als de gebruikersobject-id (een GUID) terwijl de tenant wordt gekopieerd naar Office 365-services. MFA-aanvragen worden zoals verwacht weergegeven, ondanks dit weergavegedrag.  Microsoft Authenticator-accounts die zijn geactiveerd met behulp van Office 365-services-eindpunten, geven de UPN (User Principal Name) weer.  Accounts die zijn toegevoegd met microsoft Cloud Deutschland-eindpunten, geven de object-id van de gebruiker weer, maar werken met de eindpunten voor zowel Microsoft Cloud Deutschland als Office 365-services.  |
| Stel Een lokale AuthServer in die wijst naar de globale STS-service. | Dit zorgt ervoor dat aanvragen van gebruikers die migreren naar Microsoft Cloud Deutschland voor Exchange-beschikbaarheidsaanvragen die zijn gericht op de hybride on-premises omgeving, worden geverifieerd voor toegang tot de on-premises service. Op dezelfde manier zorgt u ervoor dat aanvragen van on-premises naar Office 365-services-eindpunten worden verificatie. | Exchange Online-klanten met hybride implementaties (on-premises) | Nadat de migratie van Azure AD is voltooid, moet de beheerder van de on-premises Exchange-topologie (hybride) een nieuw eindpunt voor de verificatieservice toevoegen voor de Office 365-services. Met deze opdracht uit Exchange PowerShell vervangt u de tenant-id van uw organisatie `<TenantID>` (gevonden in Azure Portal in **Azure Active Directory).** <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Als u deze taak niet kunt voltooien, kan dit leiden tot niet-drukke hybride aanvragen voor het geven van informatie aan postvakgebruikers die zijn gemigreerd van Microsoft Cloud Deutschland naar Office 365-services.  |
| Migratie van Azure-bronnen. | Klanten die gebruikmaken van Bronnen van Office 365 en Azure (bijvoorbeeld netwerken, berekenen en opslag) voeren de migratie van resources naar het Office 365-services-exemplaar uit. Deze migratie is een verantwoordelijkheid voor klanten. Berichten in het berichtencentrum geven het begin aan. De migratie moet zijn voltooid voordat de Azure AD-organisatie in de Office 365-servicesomgeving wordt voltooid. | Azure-klanten | Voor Azure-migraties, zie de Azure-migratie playbook, [Overview of migration guidance for Azure Germany.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 van 9)

Als u **Set-UserPhoto gebruikt:**

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| De nieuwe regio Duitsland wordt toegevoegd aan een bestaande organisatie-instelling en postvakken worden verplaatst naar Office 365-services. | Exchange Online-configuratie voegt de nieuwe lokale Duitse go-local-regio toe aan de overgangsorganisatie. Deze regio voor Office 365-services is als standaard ingesteld, zodat de interne taakverdelingsservice postvakken opnieuw kan distribueren naar de juiste standaardregio in Office 365-services. Bij deze overgang maken gebruikers aan beide kanten (Duitsland of Office 365-services) gebruik van dezelfde organisatie en kunnen ze beide URL-eindpunten gebruiken. |  Exchange Online | Als een gebruikerspostvak is gemigreerd, maar een beheerderspostvak nog niet is gemigreerd, of omgekeerd, kunnen beheerders **Set-UserPhoto,** een PowerShell-cmdlet, niet uitvoeren. In dit geval moet een beheerder een extra tekenreeks doorgeven tijdens het instellen van de verbinding `ConnectionUri` met behulp van de volgende syntaxis: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> waarbij de tijdelijke aanduiding is voor de e-mail-id van de gebruiker van wie de foto moet worden gewijzigd met `<user_email>` **set-UserPhoto.** |
|||||

Als u een hybride on-premises implementatie gebruikt:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
|Stop of verwijder onboarding- of offboarding-bewegingen van postvakken.  | Op deze manier mislukt de overstapaanvragen niet met een fout. | Exchange Online-klanten met hybride implementaties (on-premises) | Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout in de service of van software-clients. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (fase 8 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-bronnen | Klanten met Microsoft Dynamics gaan via Engineering of FastTrack werken aan de overstap van Dynamics naar het Office 365-services-exemplaar.* | Klanten van Microsoft Dynamics 365 | - Na de migratie valideert de beheerder de organisatie. <br><br> - De beheerder wijzigt werkstromen indien nodig. <br><br> - De beheerder geschikt de AdminOnly-modus uit. <br><br> - De beheerder wijzigt het organisatietype in _sandbox,_ wat van toepassing is <br><br> - Eindgebruikers op de hoogte stellen van de nieuwe URL om toegang te krijgen tot het exemplaar (organisatie). <br><br> - Werk alle binnenkomende verbindingen naar de nieuwe eindpunt-URL bij. <br><br> - De Dynamics-service is niet beschikbaar voor gebruikers tijdens de overgang. <br><br> - Gebruikers moeten na de migratie van elke organisatie de status en functies van de organisatie valideren.  |
|||||

\* (i) Klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Wanneer de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021. 


### <a name="power-bi-phase-8-of-9"></a>Power BI (fase 8 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Power BI-resources | Klanten met Microsoft Power BI worden betrokken door Engineering of FastTrack nadat een bestaand hulpprogramma voor PBI-migratie handmatig is ingeschakeld om Power BI over te brengen naar het Office 365-services-exemplaar.\*\* | Microsoft Power BI-klanten | - De volgende Power BI-items _worden_ niet overgelijnd en moeten opnieuw worden gemaakt: <br><br> - Realtime gegevenssets (bijvoorbeeld streaming- of push-gegevenssets). <br> - On-premises Data Gateway-configuratie en -gegevensbron voor Power BI. <br> - Rapporten die zijn gebaseerd op de realtime-gegevenssets zijn na de migratie niet beschikbaar en moeten opnieuw worden gemaakt. <br><br> - Power BI-services zijn tijdens de overgang niet beschikbaar voor gebruikers. De beschikbaarheid van de service mag niet langer dan 24 uur duren. <br><br> - Gebruikers moeten na de migratie gegevensbronnen en hun on-premises gegevensgateways opnieuw configureren met de Power BI-service.  Tot die tijd kunnen gebruikers deze gegevensbronnen niet gebruiken om geplande vernieuwings- en/of directe query's uit te voeren op deze gegevensbronnen. <br><br> - Hoedandaningen en premium-werkruimten kunnen niet worden gemigreerd. Klanten moeten alle hoedaningen verwijderen vóór de migratie en ze na de migratie opnieuw maken. Verplaats werkruimten naar wens terug naar hoedaningen.  |
|||||

\*\* (i) Klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het migratieproces. (ii) Wanneer de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021. 


### <a name="office-apps-phase-9-of-9"></a>Office-apps (fase 9 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Clients, Office Online tijdens de cutover van de Office-client, met Azure AD wordt het tenantbereik zo definitief dat dit naar de Office 365-services kan wijzen. | Deze configuratiewijziging zorgt ervoor dat Office-clients kunnen bijwerken en naar de eindpunten van Office 365-services kunnen wijzen. | Alle Office-klanten | - Laat gebruikers  weten dat ze alle Office-apps moeten sluiten en meld u vervolgens weer aan (of forceer clients opnieuw op te starten en gebruikers zich aan te melden) om office-clients in staat te stellen de wijziging op te halen. <br><br> - Informeer gebruikers en helpdeskmedewerkers dat gebruikers mogelijk een Office-banner zien met de vraag of ze Office-apps binnen 72 uur na de cutover opnieuw kunnen activeren.  <br><br> - Alle Office-toepassingen op persoonlijke computers moeten worden gesloten en gebruikers moeten zich eerst weer aanmelden. Meld u op de gele activeringsbalk aan om office 365-services opnieuw te activeren. <br><br> - Voor gedeelde machines zijn acties vereist die lijken op persoonlijke machines en is geen speciale procedure vereist. <br><br> - Op mobiele apparaten moeten gebruikers zich aanmelden bij apps, ze sluiten en zich opnieuw aanmelden. |
|||||

## <a name="during-migration"></a>Tijdens de migratie

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| SharePoint en OneDrive zijn overgestappen. | SharePoint en OneDrive worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar Office 365-services. Bestaande URL's van Microsoft Cloud Deutschland blijven behouden ( `contoso.sharepoint.de` ). Tokens uitgegeven door Microsoft Cloud Deutschland of Office 365-services zijn geldig tijdens de overgang. | SharePoint-klanten | Inflight SharePoint 2013-werkstromen worden verbroken tijdens de migratie en moeten opnieuw worden gepubliceerd na de migratie. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 van 9)

Voor eDiscovery:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Tijdens de migratie mislukken eDiscovery-zoekopdrachten of worden 0 resultaten gevonden voor gemigreerde SharePoint Online-, OneDrive voor Bedrijven- en Exchange Online-locaties. | Tijdens de migratie kunnen klanten nog steeds zaken maken, ordenen, zoeken en exporteren in het beveiligings- & [compliancecentrum,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)waaronder [Inhoud zoeken.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Zoekopdrachten op gemigreerde locaties in SharePoint Online, OneDrive voor Bedrijven en Exchange Online leveren echter 0 resultaten of een fout op. Zie de kolom _Impact_ voor herstel. | Alle klanten die eDiscovery gebruiken |  Voor het geval een zoekopdracht 0 resultaten of een fout retourneert tijdens de migratie, moet u de volgende actie ondernemen voor SharePoint Online: <br><br>  Download sites rechtstreeks van de site van SharePoint Online/OneDrive voor Bedrijven door de instructies te volgen in Bestanden en mappen downloaden van [OneDrive of SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Voor deze methode zijn beheerdersmachtigingen of alleen-lezenmachtigingen voor sharePoint Online op de site vereist. <br><br> Als de limieten zijn overschreden, zoals wordt uitgelegd in Bestanden en mappen downloaden van OneDrive of [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kunnen klanten de synchronisatieclient van OneDrive voor Bedrijven gebruiken aan de hand van de richtlijnen in [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)en Teams-bestanden synchroniseren met uw computer. <br><br> - Exchange Online <br><br> - [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype voor Bedrijven Online (fase 7 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Skype voor Bedrijven naar Teams. | Bestaande klanten van Skype voor Bedrijven worden gemigreerd naar Office 365-services in Europa en vervolgens gemigreerd naar Microsoft Teams in de regio Duitsland van Office 365-services. | Klanten van Skype voor Bedrijven |  PowerShell wordt gebruikt voor het beheren van instellingen en beleid voor uw tenant en gebruikers. Wanneer u verbinding maakt met een PowerShell-sessie, voegt u het volgende toe: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Na de migratie

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (fase 9 van 9)

Voor hybride versie:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Werk Azure AD Connect bij. | Nadat de overboeking naar Azure AD is voltooid, maakt de organisatie volledig gebruik van Office 365-services en is ze niet langer verbonden met Microsoft Cloud Deutschland. De klant moet er nu voor zorgen dat het deltasynchronisatieproces is afgerond en daarna de tekenreekswaarde van `AzureInstance` 3 (Microsoft Cloud Deutschland) wijzigen in 0 in het `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registerpad. | Hybride organisaties die verbonden zijn met Azure AD | Wijzig de waarde van `AzureInstance` de registersleutel. Als u dit niet doet, leidt dit tot objecten die niet worden gesynchroniseerd nadat de Eindpunten van Microsoft Cloud Deutschland niet meer beschikbaar zijn. |
|||||

Voor federatieverificatie:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijder afhankelijke vertrouwensdiensten uit Microsoft Cloud Deutschland AD FS. | Nadat de overboeking naar Azure AD is voltooid, maakt de organisatie volledig gebruik van Office 365-services en is ze niet langer verbonden met Microsoft Cloud Deutschland. De klant moet nu het vertrouwen van de vertrouwensrelatie met de Microsoft Cloud Deutschland-eindpunten verwijderen. Dit kan alleen wanneer er geen toepassingen van het klantpunt naar Microsoft Cloud Deutschland-eindpunten worden gebruikt wanneer Azure AD wordt gebruikt als identiteitsprovider (IdP). | Federatieverificatie-organisaties | Geen. |
|||||

Voor Azure AD:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Aanvragen om de afgelopen 30 dagen vóór de migratie deel te nemen aan een Azure AD-groep, moeten opnieuw worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd. | Eindgebruikers moeten het Access-deelvenster gebruiken om opnieuw een aanvraag voor het deelnemen aan een Azure AD-groep in te dienen als deze aanvragen de afgelopen 30 dagen vóór de migratie niet zijn goedgekeurd. | Eindgebruikers van wie goedkeuringsaanvragen voor de Azure AD-groep niet zijn goedgekeurd in de afgelopen 30 dagen vóór de migratie |  Als eindgebruiker: <ol><li>Ga naar [het deelvenster Access.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Zoek een Azure AD-groep waarvoor goedkeuring van het lidmaatschap 30 dagen vóór de migratie in behandeling was.</li><li>Vraag of u opnieuw lid wilt worden van de Azure AD-groep.</li></ol> Aanvragen om deel te nemen aan een groep die minder dan 30 dagen vóór de migratie actief is, kunnen niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd. |
|||||

Voor DNS:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Werk on-premises DNS-services bij voor eindpunten van Office 365-services. | Door de klant beheerde DNS-vermeldingen die naar Office 365 Duitsland wijzen, moeten worden bijgewerkt om te wijzen naar de eindpunten van Office 365-services. | Alle Office-klanten | Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout in de service of van software-clients. |
|||||

Voor externe services voor eindpunten van Office 365-services:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Werk partners en externe services bij voor eindpunten van Office 365-services. | - Externe services en partners die naar Office 365 Duitsland wijzen, moeten worden bijgewerkt zodat ze naar de eindpunten van Office 365-services wijzen. Voorbeeld: Registreer u opnieuw, in overeenstemming met uw leveranciers en partners, de galerie-app-versie van toepassingen, indien beschikbaar. <br><br> - Wijs alle aangepaste toepassingen die gebruikmaken van Graph API `graph.microsoft.de` aan in `graph.microsoft.com` de . Andere API's met gewijzigde eindpunten moeten ook worden bijgewerkt, indien deze worden gebruikt. <br><br> - Alle niet-first-first-enterprise-toepassingen wijzigen om om te leiden naar de wereldwijde eindpunten.  | Alle Office-klanten | Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout in de service of van software-clients. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| SharePoint 2013-werkstromen opnieuw publiceren. | Tijdens de migratie hebben we het aantal SharePoint 2013-werkstromen verminderd. Nu de migratie is voltooid, kan de klant de werkstromen opnieuw publiceren. | Alle Office-klanten | Dit is een vereiste actie. Als u dit niet doet, kan dit leiden tot verwarring en telefoontjes naar de helpdesk. |
| Items delen via Outlook | Items delen via Outlook werkt niet meer na een cutover van de tenant. | SharePoint Online en OneDrive voor Bedrijven | - In SharePoint Online en OneDrive voor Bedrijven kunt u items delen via Outlook. Nadat u op de Outlook-knop hebt gedrukt, wordt er een deelbare koppeling gemaakt en wordt er een nieuw bericht in de Outlook Web App weergegeven. <br><br> - Na een cutover van de tenant werkt deze methode voor delen niet. We herkennen dit een bekend probleem is. Aangezien deze Outlook-functie echter op het moment van afroeping wordt uitgevoerd, is het oplossen van het probleem niet gepland totdat het aftrekken is uitgerold. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 van 9)

Als u een hybride Exchange-configuratie gebruikt:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| De wizard Hybride configuratie (HCW) opnieuw uitvoeren op Office 365-services. | De bestaande HCW-configuratie is bedoeld om Microsoft Cloud Deutschland te ondersteunen. Als de migratie van Exchange-services is voltooid, wordt de on-premises configuratie ontkoppeld van Microsoft Cloud Deutschland. | Exchange Online-klanten die een hybride implementatie uitvoeren | - Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout in de service of van software-clients. Voordat de migratie van Exchange-postvakken begint (met een kennisgeving van vijf of meer dagen), laat u clients weten dat ze moeten stoppen en alle onboarding- of offboarding-bewegingen van hun postvakken moeten verwijderen.  Als dat niet zo is, zien ze fouten in hun overstapaanvragen. <br><br> - Wanneer de migratie van Exchange-postvakken is voltooid, laat u klanten weten dat ze de onboarding- en offboarding-bewegingen kunnen hervatten. <br> Het uitvoeren van **Test-MigrationServerAvailabiilty,** een PowerShell-cmdlet, tijdens de migratie van Exchange van Microsoft Cloud Deutschland naar Office 365-services werkt mogelijk niet. Het werkt echter correct nadat de migratie is voltooid. <br><br> Als clients na het migreren van postvakken problemen krijgen met referenties of autorisatie, kunnen gebruikers hun lokale beheerdersreferenties opnieuw in het migratie-eindpunt ingeven door het migratie-eindpunt uit te voeren, of door hetzelfde in te stellen via het Exchange-configuratiescherm `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` (ECP).  |

Voor eDiscovery:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
|  Alle locaties van SharePoint Online, OneDrive voor Bedrijven en Exchange Online zijn samen met het beveiligings- en compliancecentrum gemigreerd. | Alle eDiscovery-activiteiten moeten worden uitgevoerd vanaf de wereldwijde tenant. Zoekopdrachten zijn nu 100% succesvol.  Fouten of fouten moeten normale ondersteuningskanalen volgen. | Alle klanten die eDiscovery gebruiken | Geen. |
| Bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens de stappen vóór de migratie | Klanten kunnen het bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens het werk aan de klanten vóór de migratie. | Alle klanten die een bewaarbeleid hebben toegepast als onderdeel van de stappen vóór de migratie. | Geen. |
|||||



## <a name="next-step"></a>Volgende stap

[Meer te weten komen over acties en effecten van migratiefasen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Migratieondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [In te 2010](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

De overgang door lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra voorlopig werk](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Informatie over Dynamics 365-migratieprogramma's](https://aka.ms/d365ceoptin)
- [Informatie over Power BI-migratieprogramma's](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
