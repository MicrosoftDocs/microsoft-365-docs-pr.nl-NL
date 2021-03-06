---
title: Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
description: 'Overzicht: Informatie over de acties voor migratiefasen en de gevolgen van de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 310b8abe0597a4d28a5c539e52bf9a0f5f5f83d9
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515174"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)

Tenantmigraties van Microsoft Cloud Deutschland naar de Regio Duitsland van De Office 365-services van Microsoft worden uitgevoerd als een set fasen en de geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters. 

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Het migratieproces zal vele weken duren, afhankelijk van de algehele grootte en complexiteit van de organisatie. Tijdens de migratie kunnen gebruikers en beheerders de services blijven gebruiken met aanzienlijke wijzigingen die in deze documentatie worden beschreven. De afbeelding en tabel definiëren fasen en stappen tijdens de migratie.

|Stap|Duur|Verantwoordelijke partij|Beschrijving|
|:--------|:--------|:--------|:--------|
|Opt-In|Uren|Klant|Kies uw organisatie voor de migratie.|
|Pre-work|Dagen|Klant|Voltooi het werk dat nodig is om gebruikers, werkstations en het netwerk voor te bereiden op migratie.|
|Azure Active Directory (Azure AD)|1-2 dagen|Microsoft|Migreert Azure AD-organisatie naar de hele wereld.|
|Azure|Weken|Klant|Maak nieuwe wereldwijde Azure-abonnementen en overgangen voor Azure-services.|
|Abonnement & licentieovergang|1-2 dagen|Microsoft|Koop wereldwijde abonnementen, annuleer Microsoft Cloud Deutschland-abonnementen en gebruikslicenties voor overgangen.|
|SharePoint en OneDrive|15+ dagen|Microsoft|Inhoud van SharePoint en OneDrive voor Bedrijven migreren en de URL sharepoint.de s blijven bestaan.|
|Exchange Online|15+ dagen|Microsoft|Exchange Online-inhoud migreren en overstappen op wereldwijde URL's.|
|Naleving & beveiliging|1-2 dagen|Microsoft|Overgangsbeveiliging & compliancebeleid en inhoud.|
|Skype voor Bedrijven|1-2 dagen|Microsoft|Stap over van Skype voor Bedrijven naar Microsoft Teams.|
|Power BI & Dynamics 365|15+ dagen|Microsoft|Migreert Power BI- en Dynamics 365-inhoud.|
|Azure AD definitief maken|1-2 dagen|Microsoft|Voltooi de cutover van de tenant naar de hele wereld.|
|Clean-Up|1-2 dagen|Klant|Oude verbindingen met Microsoft Cloud Deutschland, zoals Active Directory Federation Services (AD FS) Relying Party Trust, Azure AD Connect en Office-client, worden opnieuw opgestart.|

De fasen en hun acties zorgen ervoor dat essentiële gegevens en ervaringen worden gemigreerd naar de Office 365-services. Nadat uw tenant is toegevoegd aan de migratiewachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de back-end-service. Voor sommige werkbelastingen zijn mogelijk acties vereist door de beheerder (of gebruiker) of kan de migratie van invloed zijn op het gebruik van de fasen die worden uitgevoerd en besproken in Hoe is de [migratie georganiseerd?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen naarmate ze de verschillende fasen van de migratie doorlopen. Bekijk de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u voorbereid bent om de stappen in de desbetreffende fasen uit te voeren zoals vereist. Het niet voltooien van de benodigde stappen kan leiden tot serviceuitval en kan de voltooiing van de migratie naar de Office 365-services vertragen.

## <a name="opt-in"></a>Opt-In
| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| We kunnen klanten niet zonder toestemming migreren. | Microsoft krijgt het recht om op twee manieren te migreren, waardoor Microsoft de overgang van gegevens en services naar het Office 365-services-exemplaar kan verbeteren. <br> De beheerder kiest voor de migratie op microsoft-gebaseerde. <br> Klanten verlengen eventuele abonnementen in hun Microsoft Cloud Deutschland-tenant na 1 mei 2020. We stellen deze klanten elke maand op de hoogte van de migratie, wachten 30 dagen om klanten de mogelijkheid te geven te annuleren en vervolgens rechtstreeks aan te melden, bij te houden via ICM. | Alle Office-klanten | - Tenant is gemarkeerd als toestemming voor migratie en in het beheercentrum wordt een bevestiging weergegeven. <br><br> - Bevestiging wordt gepost op de Cloud Germany Message Center-tenant. Serviceconfiguratie gaat verder vanuit Microsoft Cloud Deutschland-eindpunten. <br><br> - Berichtencentrum controleren op updates van de status van de migratiefase. |


## <a name="subscription-phase-3"></a>Abonnement (fase 3)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Abonnementen worden overgedragen en licenties worden opnieuw toegewezen. | Nadat de tenant is overgezet naar Office 365-services, worden bijbehorende Office 365-servicesabonnementen aangeschaft voor de overgedragen Microsoft Cloud Deutschland-abonnementen. Aan gebruikers met toegewezen Microsoft Cloud Deutschland-licenties worden Office 365-serviceslicenties toegewezen. Oude Microsoft Cloud Deutschland-abonnementen worden bij voltooiing verwijderd uit de Office 365-servicesten tenant. | Alle Office-klanten | - Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld geen nieuwe abonnementen of wijzigingen in het aantal seats) tijdens deze fase. <br><br> - Licentietoewijzingswijzigingen worden geblokkeerd. <br><br> - Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende Office 365-servicesabonnement. De Office 365-servicesaanbieding van dat abonnement wordt gedefinieerd door Microsoft (ook wel _aanbiedingstoewijzing genoemd)._ <br><br> - Het aantal functies (serviceplannen) dat wordt aangeboden door Office 365-services kan groter zijn dan in de oorspronkelijke Microsoft Cloud Deutschland-aanbieding. Gebruikerslicenties in Office 365-services worden op dezelfde manier toegewezen aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). Gebruikerslicenties van alle gebruikers worden automatisch toegewezen aan de nieuwe functies. De beheerder moet zo nodig expliciet actie ondernemen om deze licenties uit te schakelen. <br><br> - Wanneer de migratie van het abonnement is voltooid, zijn zowel Office 365-services als Duitsland-abonnementen zichtbaar in de Office 365-beheerportal, met de status van Duitsland-abonnementen die zijn _gedeprovisioneerd._ <br><br> - Gebruikers krijgen opnieuw toegewezen licenties die zijn gekoppeld aan de nieuwe Office 365-services-abonnementen. Klantprocessen die afhankelijk zijn van Duitsland-abonnementen of SKU-GUID's worden verbroken en moeten worden aangepast met de Office 365-services. <br><br> - Nieuwe abonnementen in de Office 365-services worden aangeschaft met de nieuwe termijn (maandelijks/driemaandelijks/jaarlijks) en de klant ontvangt een pro stitutie voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. <br><br> - Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-services onder de nieuwe Office 365-services-tenant van dezelfde partner. Na de migratie van de klant kan de partner deze klant alleen beheren vanuit de Office 365-services-tenant. <br><br> - Er is extra functionaliteit beschikbaar (bijvoorbeeld Microsoft Planner en Microsoft Flow), tenzij uitgeschakeld door de tenantbeheerder. Zie Toegang tot [Microsoft 365-services](disable-access-to-services-while-assigning-user-licenses.md)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.  |
|||||


## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fase 4)

**Van toepassing op**: SharePoint Online

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| SharePoint en OneDrive zijn overgestappen | SharePoint Online en OneDrive voor Bedrijven worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar de globale office 365-services.<br><ul><li>Bestaande URL's van Microsoft Cloud Deutschland blijven behouden `contoso.sharepoint.de` (bijvoorbeeld).</li><li>Bestaande sites blijven behouden.</li><li>Tokens voor verificatie aan de clientzijde die zijn uitgegeven door de Security Token Service (STS) in het exemplaar van Microsoft Cloud Deutschland of office 365 Global Services zijn tijdens de overgang geldig.</li></ul>|<ul><li>Tijdens de migratie is inhoud gedurende twee korte perioden alleen-lezen. Verwacht tijdens deze periode een banner 'u kunt inhoud niet bewerken' in SharePoint.</li><li>De zoekindex blijft niet behouden en kan tot 10 dagen duren om opnieuw te worden opgebouwd.</li><li>SharePoint Online en OneDrive voor Bedrijven-inhoud zijn gedurende twee korte perioden alleen-lezen tijdens de migratie. Gebruikers zien een banner 'u kunt inhoud niet bewerken' kort gedurende deze periode.</li><li>Na voltooiing van de SharePoint Online-migratie zijn de zoekresultaten voor inhoud van SharePoint Online en OneDrive voor Bedrijven mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode leveren zoekquery's mogelijk geen volledige resultaten op. Functies die afhankelijk zijn van zoekindexen, zoals Nieuws over SharePoint Online, kunnen worden beïnvloed tijdens het opnieuw indexeren van voltooide producten.</li></ul>|
||||

Aanvullende aandachtspunten:

- Als uw organisatie nog steeds werkstromen van SharePoint 2010 gebruikt, werken deze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, hoewel deze standaard zijn uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Nadat de migratie naar de SharePoint Online-service is voltooid, raden we u aan over te gaan op Power Automate of andere ondersteunde oplossingen.

- Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online nog niet is gemigreerd, moeten een SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM versie 16.0.20616.12000 of hoger gebruiken. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

- Klanten van Microsoft Cloud Deutschland waarvan het SharePoint Online-exemplaar is gemigreerd, moeten de SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM bijwerken naar versie 16.0.20717.12000 of hoger. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

## <a name="exchange-online-phase-5"></a>Exchange Online (fase 5)

**Van toepassing op:**  Exchange Online

Als u gebruik maakt van een hybride versie van Exchange Online: voor hybride Exchange Online-klanten moet de wizard Hybride configuratie (HCW) meerdere keren worden uitgevoerd als onderdeel van deze overgang.

Zoals wordt beschreven in de [prework](ms-cloud-germany-transition-add-pre-work.md#exchange-online)voor migratie, moeten hybride Exchange Online-klanten, voordat de migratiestap **5 begint,** de nieuwste versie van de HCW in Office 365 Duitsland uitvoeren om de on-premises configuratie voor te bereiden voor de migratie naar Office 365 wereldwijd.

Als de migratiefase **5** is voltooid (wanneer de melding van het berichtencentrum wordt gepubliceerd), moet u de HCW opnieuw uitvoeren met behulp van de instellingen van Office 365 Worldwide om uw on-premises systemen te laten wijzen naar de globale Office 365-service. Als u aangepaste domeinen gebruikt, zijn er mogelijk extra DNS-updates vereist.


| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Exchange Online-postvakken worden verplaatst van Microsoft Cloud Deutschland naar algemene Office 365-services.| Exchange Online-configuratie voegt de nieuwe lokale Duitse go-local-regio toe aan de overgangsorganisatie. De regio Globale services van Office 365 is als standaard ingesteld, zodat de interne taakverdelingsservice postvakken kan distribueren naar de juiste standaardregio in Office 365-services. Bij deze overgang maken gebruikers aan beide kanten (Duitsland of globale services) gebruik van dezelfde organisatie en kunnen ze beide URL-eindpunten gebruiken. |<ul><li>U kunt gebruikers en services overstappen van de oudere URL's van Duitsland (outlook.office.de) naar nieuwe URL's voor Office 365-services `https://outlook.office365.com` ().</li><li>Tijdens de migratie hebben gebruikers mogelijk nog steeds toegang tot de service via oudere Duitsland-URL's, maar ze moeten de oudere URL's niet meer gebruiken na voltooiing van de migratie.</li><li>Gebruikers moeten overstappen op het gebruik van de wereldwijde Office-portal voor Office Online-functies (Agenda, E-mail, Personen). Navigatie naar services die nog niet naar Office 365-services zijn gemigreerd, werkt pas wanneer ze zijn gemigreerd. </li><li>Outlook Web App biedt geen ervaring met openbare mappen tijdens de migratie. </li></ul>|
| Aangepaste DNS-instellingen voor AutoDiscover bijwerken| Door de klant beheerde DNS-instellingen voor AutoDiscover die momenteel verwijzen naar Microsoft Cloud Deutschland, moeten worden bijgewerkt om te verwijzen naar het globale eindpunt van Office 365 als de Exchange Online-fase (fase 5) is voltooid. <br> Bestaande DNS-vermeldingen met CNAME die naar autodiscover-outlook.office.de moeten worden bijgewerkt om te wijzen naar autodiscover.outlook.com. |  Beschikbaarheidsaanvragen en servicedetectie-oproepen via AutoDiscover wijzen rechtstreeks naar de Office 365-services. Klanten die deze DNS-updates niet uitvoeren, kunnen problemen met de automatischdiscover-service ervaren wanneer de migratie is afgerond. |
||||

Aanvullende aandachtspunten:

- `myaccount.microsoft.com` werkt alleen na de cutover van Office 365. Tot die tijd worden er foutberichten weergegeven met de tekst 'Er is iets misgegaan'.

- Gebruikers van Outlook Web App die toegang hebben tot een gedeeld postvak in een andere omgeving (een gebruiker in de Duitsland-omgeving heeft bijvoorbeeld toegang tot een gedeeld postvak in de globale omgeving), wordt gevraagd een tweede keer te verifiëren. De gebruiker moet eerst zijn of haar postvak verifiëren en openen en vervolgens het gedeelde postvak `outlook.office.de` openen dat zich in `outlook.office365.com` . Ze moeten zich een tweede keer verifiëren wanneer ze toegang krijgen tot de gedeelde bronnen die worden gehost in de andere service.

- Voor bestaande klanten van Microsoft Cloud Deutschland of klanten met een overgang, wanneer een gedeeld postvak aan Outlook wordt toegevoegd met bestandsgegevens **> Info >** Account toevoegen, kan het weergeven van agendamachtigingen mislukken (de Outlook-client probeert de Rest API te gebruiken `https://outlook.office.de/api/v2.0/Me/Calendars` .) Klanten die een account willen toevoegen om agendamachtigingen te bekijken, kunnen de registersleutel toevoegen zoals wordt beschreven in Wijzigingen in gebruikerservaring voor het delen van een agenda [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie slaagt. Deze registersleutel kan voor de hele organisatie worden geïmplementeerd met groepsbeleid.

- Tijdens de migratiefase kan het gebruik van de **PowerShell-cmdlets New-migrationEndpoint,** **Set-MigrationEndpoint** en **Test-MigrationsServerAvailability** resulteren in fouten (fout op proxy). Dit gebeurt wanneer het arbitragepostvak is gemigreerd naar de hele wereld, maar het postvak van de beheerder niet is gemigreerd of omgekeerd. U kunt dit oplossen door tijdens het maken van de Tenant PowerShell-sessie het arbitragepostvak te gebruiken als routeringstip in de **ConnectionUri.** Bijvoorbeeld: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

Bekijk de informatie in Klantervaring tijdens de migratie naar [Office 365-services in](ms-cloud-germany-transition-experience.md)de nieuwe Duitse datacenterregio's voor meer informatie over de verschillen voor organisaties in migratie en nadat Exchange Online-bronnen zijn gemigreerd.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/ Beveiliging en naleving (fase 6)

Back-end Exchange Online Protection (EOP)-functies worden gekopieerd naar de nieuwe regio Duitsland. 

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Exchange Online-routering en historische berichtgegevens. | Exchange Online maakt routering van externe hosts naar Office 365 mogelijk. De externe MX-records worden gerouteeerd naar de EOP-service. Tenantconfiguratie en historische gegevens worden gemigreerd. | Exchange Online-klanten | - Door Microsoft beheerde DNS-vermeldingen worden bijgewerkt van Office 365 Germany EOP naar Office 365-services. <br><br> - Klanten moeten 30 dagen na de dubbele EOP-schrijftijd wachten op EOP-migratie. Anders kunnen gegevens verloren gaan. |
|||||

## <a name="skype-for-business-online-phase-7"></a>Skype voor Bedrijven Online (Fase 7)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Skype voor Bedrijven naar Teams. | Bestaande klanten van Skype voor Bedrijven worden gemigreerd naar Office 365-services in Europa en vervolgens overstappen op Microsoft Teams in de regio Duitsland van Office 365-services. | Klanten van Skype voor Bedrijven | - Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven op de migratiedatum. Tien dagen vóór de migratie plaatsen we een bericht in het beheercentrum om u te laten weten wanneer de migratie wordt gehouden en nogmaals wanneer we met de migratie beginnen. <br><br> - Beleidsconfiguratie is gemigreerd. <br><br> - Gebruikers worden gemigreerd naar Teams en hebben na de migratie geen Skype voor Bedrijven meer. <br><br> - Gebruikers moeten de Teams-bureaubladclient hebben geïnstalleerd. Installatie vindt 10 dagen via beleid voor de Skype voor Bedrijven-infrastructuur plaatsvinden, maar als dit mislukt, moeten gebruikers nog steeds de client downloaden of verbinding maken met een ondersteunde browser. <br><br> - Contactpersonen en vergaderingen worden gemigreerd naar Teams. <br><br> - Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven tussen tijdserviceovergangen naar Office 365-services en niet totdat de DNS-vermeldingen van klanten zijn voltooid. <br><br> - Contactpersonen en bestaande vergaderingen blijven functioneren als Skype voor Bedrijven-vergaderingen. |
|||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fase 8)
Klanten met Dynamics 365 vereisen extra betrokkenheid om de Dynamics-organisaties van de organisatie onafhankelijk te migreren.
 
| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-bronnen | Klanten met Microsoft Dynamics gaan via Engineering of FastTrack overstappen op Dynamics naar het Office 365-services-exemplaar.* | Klanten van Microsoft Dynamics 365 | - Na de migratie valideert de beheerder de organisatie. <br><br> - De beheerder wijzigt werkstromen indien nodig. <br><br> - De beheerder geschikt de AdminOnly-modus uit. <br><br> - De beheerder wijzigt het organisatietype in _sandbox,_ wat van toepassing is <br><br> - Eindgebruikers op de hoogte stellen van de nieuwe URL om toegang te krijgen tot het exemplaar (organisatie). <br><br> - Werk alle binnenkomende verbindingen naar de nieuwe eindpunt-URL bij. <br><br> - De Dynamics-service is tijdens de overgang niet beschikbaar voor gebruikers. <br><br> - Gebruikers moeten na de migratie van elke organisatie de status en functies van de organisatie valideren.  |
|||||

\* (i) Klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Wanneer de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.


## <a name="power-bi-phase-8-of-9"></a>Power BI (fase 8 van 9)

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Power BI-resources | Klanten met Microsoft Power BI worden betrokken door Engineering of FastTrack nadat een bestaand hulpprogramma voor PBI-migratie handmatig is ingeschakeld om Power BI over te brengen naar het Office 365-services-exemplaar.\*\* | Microsoft Power BI-klanten | - De volgende Power BI-items _worden_ niet overgelijnd en moeten opnieuw worden gemaakt: <br><br> - Realtime-gegevenssets (bijvoorbeeld streaming- of push-gegevenssets). <br> - On-premises Data Gateway-configuratie en -gegevensbron voor Power BI. <br> - Rapporten die zijn gebaseerd op de realtime-gegevenssets zijn na de migratie niet beschikbaar en moeten opnieuw worden gemaakt. <br><br> - Power BI-services zijn tijdens de overgang niet beschikbaar voor gebruikers. De beschikbaarheid van de service mag niet langer dan 24 uur duren. <br><br> - Gebruikers moeten na de migratie gegevensbronnen en hun on-premises gegevensgateways opnieuw configureren met de Power BI-service.  Tot die tijd kunnen gebruikers deze gegevensbronnen niet gebruiken om geplande vernieuwings- en/of directe query's uit te voeren op deze gegevensbronnen. <br><br> - Hoedandaningen en premium-werkruimten kunnen niet worden gemigreerd. Klanten moeten alle hoedaningen verwijderen vóór de migratie en ze na de migratie opnieuw maken. Verplaats werkruimten naar wens terug naar hoedandaningen.  |
|||||

\*\* (i) Klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het migratieproces. (ii) Wanneer de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021. 


## <a name="office-apps"></a>Office-apps

Office-klanten die overstappen naar de regio Duitsland, moeten zich sluiten en weer aanmelden voor alle Office-toepassingen (Word, PowerPoint, Outlook, enzovoort) en OneDrive voor Bedrijven-client nadat de migratie is voltooid. Door u af te melden en aan te melden, kunnen de Office-services nieuwe verificatietokens verkrijgen van de globale Azure AD-service.
 
| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Clients, Office Online tijdens de cutover van de Office-client, met Azure AD wordt het tenantbereik zo definitief dat dit naar de Office 365-services kan wijzen. | Deze configuratiewijziging zorgt ervoor dat Office-clients kunnen bijwerken en naar de eindpunten van Office 365-services kunnen wijzen. | Alle Office-klanten | - Laat gebruikers  weten dat ze alle Office-apps moeten sluiten en meld u vervolgens weer aan (of forceer clients opnieuw op te starten en gebruikers zich aan te melden) om office-clients in staat te stellen de wijziging op te halen. <br><br> - Informeer gebruikers en helpdeskmedewerkers dat gebruikers mogelijk een Office-banner zien met de vraag of ze Office-apps binnen 72 uur na de cutover opnieuw moeten activeren.  <br><br> - Alle Office-toepassingen op persoonlijke computers moeten worden gesloten en gebruikers moeten zich eerst weer aanmelden. Meld u op de gele activeringsbalk aan om office 365-services opnieuw te activeren. <br><br> - Voor gedeelde computers zijn acties vereist die vergelijkbaar zijn met persoonlijke machines en is geen speciale procedure vereist. <br><br> - Op mobiele apparaten moeten gebruikers zich aanmelden bij apps, ze sluiten en zich opnieuw aanmelden. |
|||||

## <a name="office-services"></a>Office Services

De meest recent gebruikte service (MRU) in Office is een cutover van de Duitsland-service naar Office 365-services, niet een migratie. Alleen MRU-koppelingen van de kant office 365-services zijn zichtbaar na de migratie van Office.com portal. MRU-koppelingen van de Duitsland-service zijn niet zichtbaar als MRU-koppelingen in Office 365-services. In Office 365 zijn MRU-koppelingen alleen toegankelijk nadat de tenantmigratie is voltooid.


## <a name="next-step"></a>Volgende stap

[Extra taken uitvoeren](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Migratieondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [In te 2010](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

De overgang door lopen:

- [Extra voorlopig werk](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Informatie over Dynamics 365-migratieprogramma's](https://aka.ms/d365ceoptin)
- [Informatie over Power BI-migratieprogramma's](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
