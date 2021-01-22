---
title: Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
ms.openlocfilehash: f0c81813522be1f9d759980df98995f1adb261c5
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921620"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Acties en gevolgen van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)

Tenantmigraties van Microsoft Cloud Deutschland naar de Regio Duitsland van De Office 365-services van Microsoft worden uitgevoerd als een set fasen en de geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

De fasen en hun acties zorgen ervoor dat essentiële gegevens en ervaringen worden gemigreerd naar de Office 365-services. Nadat uw tenant is toegevoegd aan de migratiewachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de back-end-service. Voor sommige werkbelastingen zijn mogelijk acties vereist door de beheerder (of gebruiker) of kan de migratie van invloed zijn op het gebruik van de fasen die worden uitgevoerd en besproken in Hoe is de [migratie georganiseerd?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen naarmate ze de verschillende fasen van de migratie doorlopen. Bekijk de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u voorbereid bent om de stappen in de desbetreffende fasen uit te voeren zoals vereist. Het niet voltooien van de benodigde stappen kan leiden tot een servicestoring en kan de voltooiing van de migratie naar de Office 365-services vertragen.

## <a name="exchange-online"></a>Exchange Online

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| De regio Nieuw Duitsland wordt toegevoegd aan de bestaande organisatie-instellingen en postvakken worden verplaatst naar Office 365-services. | Exchange Online-configuratie voegt de nieuwe lokale Duitse go-local-regio toe aan de overgangsorganisatie. Deze regio voor Office 365-services is als standaard ingesteld, zodat de interne taakverdelingsservice postvakken opnieuw kan distribueren naar de juiste standaardregio in Office 365-services. Bij deze overgang maken gebruikers aan beide kanten (Duitsland of Office 365-services) gebruik van dezelfde organisatie en kunnen ze beide URL-eindpunten gebruiken. | Exchange Online | - Overgang van gebruikers en services van URL's in Duitsland naar URL's voor Office 365-services `https://outlook.office365.com` (). <br><br> - Tijdens de migratie hebben gebruikers nog steeds toegang tot de service via oudere Duitsland-URL's. Geen directe actie nodig. <br><br> - Gebruikers moeten beginnen met het gebruik van office.com voor office Online-functies (Agenda, E-mail, Personen). Navigatie naar services die nog niet naar Office 365-services zijn gemigreerd, werkt pas als ze zijn gemigreerd. <br><br> - Outlook Web App biedt geen ervaring met openbare mappen tijdens de migratie. |
|||||

Aanvullende aandachtspunten:

- `myaccount.msft.com` werkt alleen na de cutover van Office 365. Via koppelingen worden tot die tijd foutberichten weergegeven dat er iets mis is gegaan.

- Gebruikers van Outlook Web App die toegang hebben tot een gedeeld postvak in een andere omgeving (een gebruiker in de Duitsland-omgeving heeft bijvoorbeeld toegang tot een gedeeld postvak in de globale omgeving), wordt gevraagd een tweede keer te verifiëren. De gebruiker moet eerst zijn of haar postvak verifiëren en openen en vervolgens het gedeelde postvak openen dat `outlook.office.de` zich in `outlook.office365.com` . Ze moeten zich een tweede keer verifiëren wanneer ze toegang krijgen tot de gedeelde bronnen die worden gehost in de andere service.

- Voor bestaande klanten van Microsoft Cloud Deutschland of klanten met een overgang, wanneer een gedeeld postvak aan Outlook wordt toegevoegd via Bestand **> Info >** Account toevoegen, kan het bekijken van agendamachtigingen mislukken (de Outlook-client probeert de Rest API te `https://outlook.office.de/api/v2.0/Me/Calendars` gebruiken.) Klanten die een account willen toevoegen om agendamachtigingen te bekijken, kunnen de registersleutel toevoegen zoals wordt beschreven in Wijzigingen in gebruikerservaring voor het delen van een agenda [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie zal slagen. Deze registersleutel kan voor de hele organisatie worden geïmplementeerd met groepsbeleid.

- Tijdens de migratiefase kan het gebruik van de **PowerShell-cmdlets New-migrationEndpoint,** **Set-MigrationEndpoint** en **Test-MigrationsServerAvailability** resulteren in fouten (fout op proxy). Dit gebeurt wanneer het arbitragepostvak is gemigreerd naar de hele wereld, maar het postvak van de beheerder niet is gemigreerd of omgekeerd. U kunt dit oplossen door tijdens het maken van de Tenant PowerShell-sessie het arbitragepostvak te gebruiken als routeringstip in de **ConnectionUri.** Bijvoorbeeld: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Als u een hybride versie van Exchange Online gebruikt:

    - U moet de wizard Hybride configuratie (HCW) opnieuw uitvoeren om de on-premises configuratie bij te werken met Microsoft Cloud Deutschland vóór de overgang en de HCW opnieuw uit te starten bij opschoning van de Office 365-services. Als u aangepaste domeinen gebruikt, zijn er mogelijk extra DNS-updates vereist.

Voor meer informatie over de verschillen voor organisaties in migratie en nadat Exchange Online-bronnen zijn gemigreerd, bekijkt u de informatie in Klantervaring tijdens de migratie naar [Office 365-services in](ms-cloud-germany-transition-experience.md)de nieuwe Duitse datacenterregio's.

## <a name="exchange-online-protection"></a>Exchange Online Protection

Back-end Functies van Exchange Online Protection (EOP) worden gekopieerd naar de nieuwe regio Duitsland. 

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Exchange Online-routering en historische berichtgegevens. | Exchange Online maakt routering van externe hosts naar Office 365 mogelijk. De externe MX-records worden gerouteeerd naar de EOP-service. Tenantconfiguratie en historische gegevens worden gemigreerd. | Exchange Online-klanten | - Door Microsoft beheerde DNS-vermeldingen worden bijgewerkt van Office 365 Germany EOP naar Office 365-services. <br><br> - Klanten moeten 30 dagen na de dubbele EOP-schrijftijd wachten op EOP-migratie. Anders kunnen gegevens verloren gaan. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| SharePoint en OneDrive zijn overgestappen. | SharePoint en OneDrive worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar Office 365-services. Bestaande URL's van Microsoft Cloud Deutschland blijven behouden `contoso.sharepoint.de` (bijvoorbeeld). Tokens die zijn uitgegeven door Microsoft Cloud Deutschland- of Office 365-services zijn geldig tijdens de overgang. | SharePoint-klanten | - Inhoud wordt tijdens de migratie gedurende twee korte perioden alleen-lezen. Verwacht tijdens deze periode een banner 'u kunt inhoud niet bewerken' in SharePoint. <br><br> - De zoekindex blijft niet behouden en kan tot 10 dagen duren om opnieuw te worden opgebouwd. <br><br> - SharePoint-/OneDrive-inhoud wordt gedurende twee korte perioden tijdens de migratie alleen-lezen. Gebruikers zien een banner 'u kunt inhoud niet bewerken' kort gedurende deze periode. <br><br> - De zoekindex is mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode leveren zoekquery's mogelijk geen volledige resultaten op. <br><br> - Bestaande sites blijven behouden. |
|||||

Aanvullende aandachtspunten:

- Wanneer de SharePoint Online-migratie naar de Duitse regio is voltooid, worden gegevensindexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen kunnen worden beïnvloed tijdens het opnieuw indexeren van voltooide functies.

- Als uw organisatie nog steeds werkstromen van SharePoint 2010 gebruikt, werken deze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, hoewel deze standaard zijn uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Nadat de migratie naar de SharePoint Online-service is voltooid, raden we u aan over te gaan op Power Automate of andere ondersteunde oplossingen.

- Als de OneDrive-migratie naar de Duitse regio is voltooid, worden gegevensindexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen kunnen worden beïnvloed terwijl het opnieuw indexeren wordt uitgevoerd.

- Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online nog niet is gemigreerd, moeten een SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM versie 16.0.20616.12000 of hoger gebruiken. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

- Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online is gemigreerd, moeten de SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM bijwerken naar versie 16.0.20717.12000 of hoger. Anders mislukken verbindingen met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.


## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Skype voor Bedrijven naar Teams. | Bestaande klanten van Skype voor Bedrijven worden gemigreerd naar Office 365-services in Europa en vervolgens gemigreerd naar Microsoft Teams in de regio Duitsland van Office 365-services. | Klanten van Skype voor Bedrijven | - Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven op de migratiedatum. Tien dagen vóór de migratie plaatsen we een bericht in het beheercentrum om u te laten weten wanneer de migratie wordt gehouden en nogmaals wanneer we met de migratie beginnen. <br><br> - Beleidsconfiguratie is gemigreerd. <br><br> - Gebruikers worden gemigreerd naar Teams en hebben na de migratie geen Skype voor Bedrijven meer. <br><br> - Gebruikers moeten de Teams-bureaubladclient hebben geïnstalleerd. Installatie vindt gedurende de tien dagen via beleid voor de Skype voor Bedrijven-infrastructuur plaatsvinden, maar als dit mislukt, moeten gebruikers nog steeds de client downloaden of verbinding maken met een ondersteunde browser. <br><br> - Contactpersonen en vergaderingen worden gemigreerd naar Teams. <br><br> - Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven tussen tijdserviceovergangen naar Office 365-services en niet totdat de DNS-vermeldingen van klanten zijn voltooid. <br><br> - Contactpersonen en bestaande vergaderingen blijven functioneren als Skype voor Bedrijven-vergaderingen. |
|||||

## <a name="office-services"></a>Office Services

De meest recent gebruikte service (MRU) in Office is een cutover van de Duitsland-service naar Office 365-services, niet een migratie. Alleen MRU-koppelingen van de kant office 365-services zijn zichtbaar na de migratie van Office.com portal. MRU-koppelingen van de Duitsland-service zijn niet zichtbaar als MRU-koppelingen in Office 365-services. In Office 365 zijn MRU-koppelingen alleen toegankelijk nadat de tenantmigratie is voltooid.

## <a name="subscription"></a>Abonnement

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| We kunnen klanten niet zonder toestemming migreren. | Microsoft krijgt het recht om op twee manieren te migreren, waardoor Microsoft de overgang van gegevens en services naar het Office 365-services-exemplaar kan verbeteren. <br> De beheerder kiest voor de migratie op microsoft-gebaseerde. <br> Klanten verlengen eventuele abonnementen in hun Microsoft Cloud Deutschland-tenant na 1 mei 2020. We stellen deze klanten elke maand op de hoogte van de migratie, wachten 30 dagen om klanten de mogelijkheid te geven te annuleren en vervolgens rechtstreeks aan te melden, bij te houden via ICM. | Alle Office-klanten | - Tenant is gemarkeerd als toestemming voor migratie en in het beheercentrum wordt een bevestiging weergegeven. <br><br> - Bevestiging wordt gepost op de Cloud Germany Message Center-tenant. Serviceconfiguratie gaat verder vanuit Microsoft Cloud Deutschland-eindpunten. <br><br> - Berichtencentrum controleren op updates van de status van de migratiefase. |
| Abonnementen worden overgedragen en licenties worden opnieuw toegewezen. | Nadat de tenant is overgezet naar Office 365-services, worden bijbehorende Office 365-servicesabonnementen aangeschaft voor de overgedragen Microsoft Cloud Deutschland-abonnementen. Aan gebruikers met toegewezen Microsoft Cloud Deutschland-licenties worden Office 365-serviceslicenties toegewezen. Oude Microsoft Cloud Deutschland-abonnementen worden bij voltooiing verwijderd uit de Office 365-servicesten tenant. | Alle Office-klanten | - Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld geen nieuwe abonnementen of wijzigingen in het aantal seats) tijdens deze fase. <br><br> - Licentietoewijzingswijzigingen worden geblokkeerd. <br><br> - Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende Office 365-servicesabonnement. De Office 365-servicesaanbieding van dat abonnement wordt gedefinieerd door Microsoft (ook wel _aanbiedingstoewijzing genoemd)._ <br><br> - Het aantal functies (serviceplannen) dat wordt aangeboden door Office 365-services kan groter zijn dan in de oorspronkelijke Microsoft Cloud Deutschland-aanbieding. Gebruikerslicenties in Office 365-services worden op dezelfde manier toegewezen aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). Gebruikerslicenties van alle gebruikers worden automatisch toegewezen aan de nieuwe functies. De beheerder moet zo nodig expliciet actie ondernemen om deze licenties uit te schakelen. <br><br> - Wanneer de migratie van het abonnement is voltooid, zijn zowel Office 365-services als Duitsland-abonnementen zichtbaar in de Office 365-beheerportal, met de status van Duitsland-abonnementen die zijn _gedeprovisioneerd._ <br><br> - Gebruikers krijgen opnieuw toegewezen licenties die zijn gekoppeld aan de nieuwe Office 365-services-abonnementen. Klantprocessen die afhankelijk zijn van Duitsland-abonnementen of SKU-GUID's worden verbroken en moeten worden aangepast met de Office 365-services. <br><br> - Nieuwe abonnementen in de Office 365-services worden aangeschaft met de nieuwe termijn (maandelijks/driemaandelijks/jaarlijks) en de klant ontvangt een pro stitutie voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. <br><br> - Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-services onder de nieuwe Office 365-services-tenant van dezelfde partner. Na de migratie van de klant kan de partner deze klant alleen beheren vanuit de Office 365-services-tenant. <br><br> - Er is extra functionaliteit beschikbaar (bijvoorbeeld Microsoft Planner en Microsoft Flow), tenzij uitgeschakeld door de tenantbeheerder. Zie Toegang tot [Microsoft 365-services](disable-access-to-services-while-assigning-user-licenses.md)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.  |
|||||

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
