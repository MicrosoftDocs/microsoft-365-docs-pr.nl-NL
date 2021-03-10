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
ms.openlocfilehash: 045e29cba293dd74d3a77beae80d78380eaa4147
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604006"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)

Tenantmigraties van Microsoft Cloud Deutschland (MCD) naar de regio Duitsland van de globale Office 365-services van Microsoft worden uitgevoerd als een reeks fasen en de geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

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

De fasen en hun acties zorgen ervoor dat essentiële gegevens en ervaringen worden gemigreerd naar de globale services van Office 365. Nadat uw tenant is toegevoegd aan de migratiewachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de back-end-service. Voor sommige werkbelastingen zijn mogelijk acties vereist door de beheerder (of gebruiker) of kan de migratie van invloed zijn op het gebruik van de fasen die worden uitgevoerd en besproken in Hoe is de [migratie georganiseerd?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen naarmate ze de verschillende fasen van de migratie doorlopen. Bekijk de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u voorbereid bent om de stappen in de desbetreffende fasen uit te voeren zoals vereist. Het niet voltooien van de benodigde stappen kan leiden tot serviceuitval en kan de voltooiing van de migratie naar de Office 365-services vertragen.

## <a name="opt-in"></a>Opt-In

**Van toepassing** op: Alle klanten met een Office 365-tenant die wordt gehost in Microsoft Cloud Deutschland (MCD)
| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| We kunnen Office 365-tenants die in de MCD worden gehost, niet zonder toestemming migreren. | Microsoft krijgt het recht om op twee manieren te migreren, waardoor Microsoft de overgang van gegevens en services naar het exemplaar van de globale services van Office 365 kan verbeteren. <ol><li>De Office 365-tenantbeheerder kiest voor de migratie op microsoft-gebaseerde. </li><li> Klanten verlengen eventuele abonnementen in hun MCD Office 365-tenant na 1 mei 2020. We stellen deze klanten elke maand op de hoogte van de migratie, wachten 30 dagen om klanten de mogelijkheid te geven te annuleren en zich direct aan te melden.</li></ol> | <ul><li>Tenant is gemarkeerd als toestemming voor migratie en in het beheercentrum wordt een bevestiging weergegeven. </li><li>Bevestiging wordt gepost naar het Office 365-tenantberichtcentrum. Serviceconfiguratie gaat verder vanuit Microsoft Cloud Deutschland-eindpunten. </li><li>De tenantbeheerder moet het Office 365-berichtencentrum controleren op updates over de status van de controlefase. </li></ul>|

## <a name="subscription-phase-3"></a>Abonnement (fase 3)

**Van toepassing** op: Alle klanten met een Office 365-tenant die wordt gehost in Microsoft Cloud Deutschland (MCD)

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Abonnementen worden overgedragen en licenties worden opnieuw toegewezen. | Bijbehorende globale Office 365-services-abonnementen worden aangeschaft in het globale Office 365-exemplaar voor de overgedragen Microsoft Cloud Deutschland-abonnementen. Aan gebruikers met toegewezen Microsoft Cloud Deutschland-licenties worden licenties toegewezen in het globale exemplaar van Office 365. Oude Microsoft Cloud Deutschland-abonnementen worden bij voltooiing verwijderd uit de Office 365-servicesten tenant.| <ul><li>Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld geen nieuwe abonnementen of wijzigingen in het aantal seats) tijdens deze fase.</li><li>Wijzigingen in licentietoewijzingen worden geblokkeerd.</li><li>Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende office 365-abonnement voor globale services. De algemene Office 365-servicesaanbieding voor dat abonnement wordt gedefinieerd door Microsoft (ook wel _aanbiedingstoewijzing genoemd)._</li><li>Het aantal functies (serviceabonnementen) dat wordt aangeboden door Office 365-services kan groter zijn dan in de oorspronkelijke Microsoft Cloud Deutschland-aanbieding. Gebruikerslicenties in Office 365-services worden op dezelfde manier toegewezen aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). Gebruikerslicenties van alle gebruikers worden automatisch toegewezen aan de nieuwe functies. De beheerder moet zo nodig expliciet actie ondernemen om deze licenties uit te schakelen. </li><li>Wanneer de migratie van het abonnement is voltooid, zijn zowel Office 365-services als Microsoft Cloud Deutschland-abonnementen zichtbaar in de Office 365-beheerportal, met de status van Microsoft Cloud Deutschland-abonnementen als _gedeprovisioneerd._ </li><li>Gebruikers krijgen opnieuw toegewezen licenties die zijn gekoppeld aan de nieuwe Office 365-services-abonnementen. Klantprocessen die afhankelijk zijn van MCD-abonnementen of SKU-GUID's worden verbroken en moeten worden aangepast met de Office 365-services. </li><li>Nieuwe abonnementen in de Office 365-services worden aangeschaft met de nieuwe termijn (maandelijks/driemaandelijks/jaarlijks) en de klant ontvangt een pro stitutie voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. </li><li>Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-services onder de nieuwe Office 365-services-tenant van dezelfde partner. Na de migratie van de klant kan de partner deze klant alleen beheren vanuit de Office 365-services-tenant. </li><li>Er is extra functionaliteit beschikbaar (bijvoorbeeld Microsoft Planner en Microsoft Flow), tenzij uitgeschakeld door de tenantbeheerder. Zie Toegang tot [Microsoft 365-services](disable-access-to-services-while-assigning-user-licenses.md)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fase 4)

**Van toepassing op:** alle klanten die SharePoint Online gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| SharePoint en OneDrive zijn overgestappen | SharePoint Online en OneDrive voor Bedrijven worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar de globale office 365-services.<br><ul><li>Bestaande URL's van Microsoft Cloud Deutschland blijven behouden `contoso.sharepoint.de` (bijvoorbeeld).</li><li>Bestaande sites blijven behouden.</li><li>Tokens voor verificatie aan de clientzijde die zijn uitgegeven door de Security Token Service (STS) in het exemplaar van Microsoft Cloud Deutschland of office 365 Global Services zijn tijdens de overgang geldig.</li></ul>|<ul><li>Tijdens de migratie is inhoud gedurende twee korte perioden alleen-lezen. Verwacht tijdens deze periode een banner 'u kunt inhoud niet bewerken' in SharePoint.</li><li>De zoekindex blijft niet behouden en kan tot 10 dagen duren om opnieuw te worden opgebouwd.</li><li>SharePoint Online en OneDrive voor Bedrijven-inhoud zijn gedurende twee korte perioden alleen-lezen tijdens de migratie. Gebruikers zien een banner 'u kunt inhoud niet bewerken' kort gedurende deze periode.</li><li>Na voltooiing van de SharePoint Online-migratie zijn de zoekresultaten voor inhoud van SharePoint Online en OneDrive voor Bedrijven mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode leveren zoekquery's mogelijk geen volledige resultaten op. Functies die afhankelijk zijn van zoekindexen, zoals Nieuws over SharePoint Online, kunnen worden beïnvloed tijdens het opnieuw indexeren van voltooide producten.</li></ul>|
||||

Aanvullende aandachtspunten:

- Als uw organisatie nog steeds werkstromen van SharePoint 2010 gebruikt, werken deze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, hoewel deze standaard zijn uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Nadat de migratie naar de SharePoint Online-service is voltooid, raden we u aan over te gaan op Power Automate of andere ondersteunde oplossingen.

- Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online nog niet is gemigreerd, moeten een SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM versie 16.0.20616.12000 of hoger gebruiken. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

- Klanten van Microsoft Cloud Deutschland waarvan het SharePoint Online-exemplaar is gemigreerd, moeten de SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM bijwerken naar versie 16.0.20717.12000 of hoger. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

## <a name="exchange-online-phase-5"></a>Exchange Online (fase 5)

**Van toepassing op:** Alle klanten die Exchange Online gebruiken

Als u gebruik maakt van een hybride versie van Exchange Online: Exchange Online Hybrid-beheerders moeten de wizard Hybride configuratie  **(HCW)** meerdere keren uitvoeren als onderdeel van deze overgang. Bekijk de [geavanceerde migratiestappen voor Exchange](ms-cloud-germany-transition-add-experience.md#Exchange-Online-before-phase-5)

Zoals wordt beschreven in de [prework](ms-cloud-germany-transition-add-pre-work.md#exchange-online)voor migratie moeten hybride Exchange Online-klanten voordat de migratiestap **5 begint,** de nieuwste versie van de wizard Exchange Hybrid Configruation (HCW) in de modus Office 365 Germany uitvoeren om de on-premises configuratie voor te bereiden voor de migratie naar de globale Office 365-services.

Als de migratiefase **5** is voltooid (wanneer de melding van het berichtencentrum wordt gepubliceerd), moet u de HCW opnieuw uitvoeren met behulp van de instellingen van Office 365 Worldwide om uw on-premises systemen te laten wijzen naar de algemene Office 365-services. Als u aangepaste domeinen gebruikt, zijn er mogelijk extra DNS-updates vereist.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Exchange Online-postvakken worden verplaatst van Microsoft Cloud Deutschland naar algemene Office 365-services.| Exchange Online-configuratie voegt de nieuwe lokale Duitse go-local-regio toe aan de overgangsorganisatie. De regio Globale services van Office 365 is als standaard ingesteld, zodat de interne taakverdelingsservice postvakken kan distribueren naar de juiste standaardregio in Office 365-services. Bij deze overgang maken gebruikers aan beide kanten (MCD of globale services) gebruik van dezelfde organisatie en kunnen ze beide URL-eindpunten gebruiken. |<ul><li>Gebruikers en services overstappen van uw oude MCD-URL's (outlook.office.de) naar nieuwe URL's voor Office 365-services `https://outlook.office365.com` ().</li><li>Tijdens de migratie hebben gebruikers mogelijk nog steeds toegang tot de service via oudere MCD-URL's, maar ze moeten de oudere URL's niet meer gebruiken na voltooiing van de migratie.</li><li>Gebruikers moeten overstappen op het gebruik van de wereldwijde Office-portal voor Office Online-functies (Agenda, E-mail, Personen). Navigatie naar services die nog niet naar Office 365-services zijn gemigreerd, werkt pas wanneer ze zijn gemigreerd. </li><li>Outlook Web App biedt geen ervaring met openbare mappen tijdens de migratie. </li></ul>|
| Aangepaste DNS-instellingen voor AutoDiscover bijwerken| Door de klant beheerde DNS-instellingen voor AutoDiscover die momenteel verwijzen naar Microsoft Cloud Deutschland, moeten worden bijgewerkt om te verwijzen naar het globale eindpunt van Office 365 als de Exchange Online-fase (fase 5) is voltooid. <br> Bestaande DNS-vermeldingen met CNAME die naar autodiscover-outlook.office.de moeten worden bijgewerkt om te wijzen naar autodiscover.outlook.com. |  Beschikbaarheidsaanvragen en servicedetectie-oproepen via AutoDiscover wijzen rechtstreeks naar de Office 365-services. Klanten die deze DNS-updates niet uitvoeren, kunnen problemen met de Automatischdiscover-service ervaren wanneer de migratie is afgerond. |
||||

Aanvullende aandachtspunten:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` werkt alleen na de tenant cutover in fase 9. Tot die tijd worden er foutberichten weergegeven met de tekst 'Er is iets misgegaan'.

- Gebruikers van Outlook Web App die toegang hebben tot een gedeeld postvak in een andere omgeving (een gebruiker in de MCD-omgeving heeft bijvoorbeeld toegang tot een gedeeld postvak in de algemene omgeving), wordt gevraagd een tweede keer te verifiëren. De gebruiker moet eerst zijn of haar postvak verifiëren en openen en vervolgens het gedeelde postvak `outlook.office.de` openen dat zich in `outlook.office365.com` . Ze moeten zich een tweede keer verifiëren wanneer ze toegang krijgen tot de gedeelde resources die worden gehost in de andere service.

- Voor bestaande klanten van Microsoft Cloud Deutschland of klanten met een overgang, wanneer een gedeeld postvak aan Outlook wordt toegevoegd via Bestand **> Info >** Account toevoegen, kan het bekijken van agendamachtigingen mislukken (de Outlook-client probeert de Rest API te gebruiken `https://outlook.office.de/api/v2.0/Me/Calendars` .) Klanten die een account willen toevoegen om agendamachtigingen te bekijken, kunnen de registersleutel toevoegen zoals wordt beschreven in Wijzigingen in gebruikerservaring voor het delen van een agenda [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie slaagt. Deze registersleutel kan voor de hele organisatie worden geïmplementeerd met groepsbeleid.

- Tijdens de migratiefase kan het gebruik van de **PowerShell-cmdlets New-migrationEndpoint,** **Set-MigrationEndpoint** en **Test-MigrationsServerAvailability** resulteren in fouten (fout op proxy). Dit gebeurt wanneer het arbitragepostvak is gemigreerd naar de hele wereld, maar het postvak van de beheerder niet is gemigreerd of omgekeerd. U kunt dit oplossen door tijdens het maken van de Tenant PowerShell-sessie het arbitragepostvak te gebruiken als routeringstip in de **ConnectionUri.** Bijvoorbeeld:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Voor meer informatie over de verschillen voor organisaties in migratie en nadat Exchange Online-bronnen zijn gemigreerd, bekijkt u de informatie in Klantervaring tijdens de migratie naar [Office 365-services in](ms-cloud-germany-transition-experience.md)de nieuwe Duitse datacenterregio's.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/ Beveiliging en naleving (fase 6)

**Van toepassing op:** Alle klanten die Exchange Online gebruiken<br>

Back-end Exchange Online Protection (EOP)-functies worden gekopieerd naar de nieuwe regio Duitsland.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Exchange Online-routering en historische berichtgegevens. | Exchange Online maakt routering van externe hosts naar Office 365 mogelijk. De externe MX-records worden gerouteeerd naar de EOP-service. Tenantconfiguratie en historische gegevens worden gemigreerd. |<ul><li>Door Microsoft beheerde DNS-vermeldingen worden bijgewerkt van Office 365 Germany EOP naar Office 365-services.</li><li>Klanten moeten 30 dagen na de dubbele EOP-schrijftijd wachten op EOP-migratie. Anders kunnen gegevens verloren gaan.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype voor Bedrijven Online (Fase 7)

**Van toepassing op:** Alle klanten die SharePoint Online gebruiken

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Skype voor Bedrijven naar Teams. | Bestaande klanten van Skype voor Bedrijven worden gemigreerd naar de wereldwijde Office 365-services in Europa en vervolgens overstappen op Microsoft Teams in de regio Duitsland van Office 365-services. |<ul><li>Gebruikers kunnen zich op de migratiedatum niet aanmelden bij Skype voor Bedrijven. Tien dagen vóór de migratie plaatsen we een bericht in het beheercentrum om u te laten weten wanneer de migratie wordt gehouden en nogmaals wanneer we met de migratie beginnen.</li><li> Beleidsconfiguratie wordt gemigreerd. </li><li>Gebruikers worden gemigreerd naar Teams en hebben na de migratie geen Skype voor Bedrijven meer. </li><li>Gebruikers moeten de Teams-bureaubladclient hebben geïnstalleerd. Installatie vindt 10 dagen via beleid voor de Skype voor Bedrijven-infrastructuur plaatsvinden, maar als dit mislukt, moeten gebruikers nog steeds de client downloaden of verbinding maken met een ondersteunde browser. </li><li>Contactpersonen en vergaderingen worden gemigreerd naar Teams.</li><li>Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven tussen tijdsserviceovergangen naar Office 365-services en niet totdat de DNS-vermeldingen van klanten zijn voltooid. </li><li>Contactpersonen en bestaande vergaderingen blijven functioneren als Skype voor Bedrijven-vergaderingen. </li><li>PowerShell wordt gebruikt voor het beheren van instellingen en beleid voor uw tenant en gebruikers. Wanneer u verbinding maakt met een PowerShell-sessie, voegt u het volgende toe: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fase 8)

**Van toepassing op:** Alle klanten die Microsoft Dynamics 365 gebruiken

Klanten met Dynamics 365 vereisen extra betrokkenheid om de Dynamics-organisaties van de organisatie onafhankelijk te migreren.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Microsoft Dynamics-bronnen | Klanten met Microsoft Dynamics gaan via Microsoft Engineering of Microsoft FastTrack overstappen op de overstap van Microsoft Dynamics 365 naar het exemplaar van de globale services van Office 365.* |<ul><li>Na de migratie valideert de beheerder de organisatie. <</li><li>De beheerder wijzigt werkstromen zo nodig. </li><li>De beheerder clears AdminOnly mode as appropriate.</li><li>De beheerder wijzigt het organisatietype in _sandbox,_ wat van toepassing is</li><li>Eindgebruikers op de hoogte stellen van de nieuwe URL om toegang te krijgen tot het exemplaar (organisatie).</li><li>Werk alle binnenkomende verbindingen naar de nieuwe eindpunt-URL bij. </li><li>De Dynamics-service is niet beschikbaar voor gebruikers tijdens de overgang. </li><li>Gebruikers moeten na de migratie van elke organisatie de status en functies van de organisatie valideren.</li></ul>|
|||||

\* (i) Klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="power-bi-phase-8-of-9"></a>Power BI (fase 8 van 9)

**Van toepassing op:** Alle klanten die Microsoft Power BI (PBI) gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Power BI-resources | Klanten met Microsoft Power BI (PBI) worden betrokken door Microsoft Engineering of Microsoft FastTrack nadat een bestaand hulpprogramma voor PBI-migratie handmatig is ingeschakeld om Power BI over te brengen naar het exemplaar van de globale services van Office 365.\*\* |<ul><li>De volgende Power BI-items _worden_ niet overgelijnd en moeten opnieuw worden gemaakt: <</li><li>Realtime gegevenssets (bijvoorbeeld streaming- of push-gegevenssets). </li><li>Configuratie en gegevensbron voor de on-premises Data Gateway van Power BI. </li><li>Rapporten die zijn gemaakt boven op de realtime-gegevenssets zijn na de migratie niet beschikbaar en moeten opnieuw worden gemaakt. </li><li>Power BI-services zijn tijdens de overgang niet beschikbaar voor gebruikers. De beschikbaarheid van de service mag niet langer dan 24 uur duren.</li><li>Gebruikers moeten na de migratie gegevensbronnen en hun on-premises gegevensgateways opnieuw configureren met de Power BI-service.  Tot die tijd kunnen gebruikers deze gegevensbronnen niet gebruiken om geplande vernieuwings- en/of directe query's uit te voeren op deze gegevensbronnen. </li><li>Hoedandaningen en premium-werkruimten kunnen niet worden gemigreerd. Klanten moeten alle hoedaningen verwijderen vóór de migratie en ze na de migratie opnieuw maken. Verplaats werkruimten naar wens terug naar hoedandaningen.</li></ul>  |
||||

\*\* (i) Klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege het inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="office-apps"></a>Office-apps

**Van toepassing op:** Alle klanten die Office-bureaubladtoepassingen gebruiken (Word, Excel, PowerPoint, Outlook, ...)

Voor Office 365-tenants die naar de regio Duitsland overstappen, moeten alle gebruikers zich sluiten, zich bij Office 365 en vervolgens opnieuw aanmelden voor alle Office-bureaubladtoepassingen (Word, Excel, PowerPoint, Outlook, enzovoort) en OneDrive voor Bedrijven-client nadat de tenantmigratie fase 9 heeft bereikt. Door u af te melden en aan te melden, kunnen de Office-services nieuwe verificatietokens verkrijgen van de globale Azure AD-service.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Clients, Office Online tijdens de cutover van de Office-client, met Azure AD wordt het tenantbereik zo definitief dat het naar de Office 365-services kan wijzen. | Deze configuratiewijziging zorgt ervoor dat Office-clients kunnen bijwerken en naar de eindpunten van Office 365-services kunnen wijzen. | <ul><li>Laat gebruikers weten dat _ze_ alle Office-apps moeten sluiten en meld u vervolgens weer aan (of forceer clients opnieuw op te starten en gebruikers zich aan te melden) om office-clients in staat te stellen de wijziging op te halen. </li><li>Informeer gebruikers en helpdeskmedewerkers  dat gebruikers mogelijk een Office-banner zien met de vraag of ze Office-apps binnen 72 uur na de cutover opnieuw moeten activeren. </li><li>Alle Office-toepassingen op persoonlijke computers moeten worden gesloten en gebruikers moeten zich eerst weer aanmelden. Meld u op de gele activeringsbalk aan om office 365-services opnieuw te activeren.</li><li>Voor gedeelde machines zijn acties vereist die lijken op persoonlijke machines en is geen speciale procedure vereist. </li><li>Op mobiele apparaten moeten gebruikers zich aanmelden bij apps, ze sluiten en zich opnieuw aanmelden. </li></ul>|
||||

## <a name="office-services"></a>Office Services

De meest recent gebruikte service (MRU) in Office is een cutover van de MCD naar de globale Office 365-services, niet een migratie. Alleen MRU-koppelingen van de kant globale services van Office 365 zijn zichtbaar na de migratie Office.com portal. MRU-koppelingen van de MCD zijn niet zichtbaar als MRU-koppelingen in globale services van Office 365. In de globale services van Office 365 zijn MRU-koppelingen alleen toegankelijk nadat de tenantmigratie fase 9 heeft bereikt.

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
