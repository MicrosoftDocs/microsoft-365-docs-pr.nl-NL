---
title: Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)
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
description: 'Samenvatting: Inzicht in de migratiefasen en de gevolgen van de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 53a8c9470093db9d57d8dc18f4242d1a596c6efd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165631"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (algemeen)

Tenantmigraties van Microsoft Cloud Deutschland (MCD) naar de regio 'Duitsland' van Microsoft's Globale Office 365-services worden uitgevoerd als een reeks fasen en hun geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Het migratieproces wordt gedurende vele weken voltooid, afhankelijk van de totale grootte en complexiteit van de organisatie. Terwijl de migratie aan de gang is, kunnen gebruikers en beheerders de services blijven gebruiken met belangrijke wijzigingen die in deze documentatie worden beschreven. De afbeelding en tabel definiëren fasen en stappen tijdens de migratie.

|Stap|Duur|Verantwoordelijke partij|Beschrijving|
|:--------|:--------|:--------|:--------|
|Opt-In|Uren|Klant|Kies uw organisatie voor de migratie.|
|Pre-Work|Dagen|Klant|Voltooi het werk dat nodig is om gebruikers, werkstations en netwerken voor te bereiden op migratie.|
|Azure Active Directory (Azure AD)|1-2 dagen|Microsoft|Azure AD-organisatie migreren naar de hele wereld.|
|Azure|Weken|Klant|Nieuwe azure-abonnementen voor de hele wereld maken en Azure-services overstappen.|
|Abonnement & licentieovergang|1-2 dagen|Microsoft|Koop wereldwijde abonnementen, annuleer Microsoft Cloud Deutschland-abonnementen en gebruikslicenties overstappen.|
|SharePoint en OneDrive|15+ dagen|Microsoft|SharePoint- en OneDrive voor Bedrijven-inhoud migreren, met sharepoint.de URL's.|
|Exchange Online|15+ dagen|Microsoft|Exchange Online-inhoud en de overgang migreren naar URL's over de hele wereld.|
|Beveiligings- & compliance|1-2 dagen|Microsoft|Overgangsbeveiliging & compliancebeleid en -inhoud.|
|Skype voor Bedrijven|1-2 dagen|Microsoft|Overstappen van Skype voor Bedrijven naar Microsoft Teams.|
|Power BI & Dynamics 365|15+ dagen|Microsoft|Power BI- en Dynamics 365-inhoud migreren.|
|Azure AD definitief maken|1-2 dagen|Microsoft|Complete tenant cutover to worldwide.|
|Clean-Up|1-2 dagen|Klant|Oude verbindingen met Microsoft Cloud Deutschland, zoals Active Directory Federation Services (AD FS) Relying Party Trust, Azure AD Connect en Office-client, worden opnieuw opgestart.|

De fasen en hun acties zorgen ervoor dat kritieke gegevens en ervaringen worden gemigreerd naar de globale Office 365-services. Nadat uw tenant is toegevoegd aan de migratiewachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de back-endservice. Voor sommige werkbelastingen zijn mogelijk acties van de beheerder (of gebruiker) vereist, of kan de migratie van invloed zijn op het gebruik van de fasen die worden uitgevoerd en besproken in [Hoe wordt de migratie georganiseerd?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen terwijl ze verschillende fasen van de migratie doorlopen. Controleer de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u bereid bent om de stappen in de desbetreffende fasen uit te voeren, indien vereist. Als u de benodigde stappen niet voltooit, kan dit leiden tot een servicestoring en kan de voltooiing van de migratie naar de Office 365-services worden vertraagd.

## <a name="opt-in"></a>Opt-In

**Van toepassing op**: Alle klanten met een Office 365-tenant die wordt gehost in de Microsoft Cloud Deutschland (MCD)

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| We kunnen Office 365-tenants die worden gehost in de MCD niet zonder toestemming migreren. | Microsoft krijgt het recht om op twee manieren te migreren, waardoor Microsoft de overgang van gegevens en services naar het exemplaar globale services van Office 365 kan doorvertalen. <ol><li>De Office 365-tenantbeheerder kiest voor de microsoft-migratie. </li><li> Klanten verlengen abonnementen in hun MCD Office 365-tenant na 1 mei 2020. We zullen deze klanten elke maand op de hoogte stellen van de migratie, 30 dagen wachten om klanten de kans te geven om te annuleren en zich direct aan te melden.</li></ol> | <ul><li>Tenant is gemarkeerd als toestemming voor migratie en het beheercentrum geeft bevestiging weer. </li><li>Bevestiging wordt gepost in het Office 365-tenantberichtcentrum. Serviceconfiguratie wordt voortgezet vanuit Microsoft Cloud Deutschland-eindpunten. </li><li>De tenantbeheerder moet het Office 365-berichtencentrum controleren op updates over de status van de migratiefase. </li></ul>|

## <a name="before-the-migration-starts"></a>Voordat de migratie begint

Zorg ervoor dat u bekend bent met de [migratievoorbereidingsstappen die van toepassing zijn op alle klanten.](ms-cloud-germany-transition-add-pre-work.md)

Als u een DNS CNAME met de naam _msoid_ hebt ingesteld in een of meer DNS-naamruimten die u bezit, moet u de CNAME uiterlijk tot het einde van fase 8 verwijderen. U kunt de _CNAME-msoid op elk_ moment vóór het einde van fase 8 verwijderen. Zie de [prework voor DNS](ms-cloud-germany-transition-add-pre-work.md#dns).

Als u één aanmelding voor Office 365 en Azure gebruikt in het exemplaar Microsoft Cloud Deutschland, moet u de migratie van uw Azure-abonnement dienovereenkomstig voorbereiden en plannen. Zorg ervoor dat u de [prework voor Microsoft Azure begrijpt.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

## <a name="before-phase-2-starts"></a>Voordat fase 2 wordt gestart

Als u ADFS gebruikt, moet u een back-up maken van uw [ADFS-configuratie](ms-cloud-germany-transition-azure-ad.md) voor en na het toevoegen van het vertrouwen van de afhankelijke partij voor de Globale Office 365-service.

## <a name="subscription-transfer-phase-3"></a>Abonnementsoverdracht (fase 3)

**Van toepassing op**: Alle klanten met een Office 365-tenant die wordt gehost in de Microsoft Cloud Deutschland (MCD)

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Abonnementen worden overgedragen en licenties worden opnieuw toegewezen. | Corresponderende Office 365 Global-services-abonnementen worden gekocht in het exemplaar Van Office 365 Global voor de overgedragen Microsoft Cloud Deutschland-abonnementen. Gebruikers met toegewezen Microsoft Cloud Deutschland-licenties krijgen licenties toegewezen in het globale office 365-exemplaar. Oudere Microsoft Cloud Deutschland-abonnementen worden na voltooiing verwijderd uit de Office 365-servicesten tenant.| <ul><li>Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld geen nieuwe abonnementen of wijzigingen in het aantal stoelen) tijdens deze fase.</li><li>Wijzigingen in licentietoewijzingen worden geblokkeerd.</li><li>Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende Office 365 Global-services-abonnement. De office 365 Global Services-aanbieding van dat abonnement wordt gedefinieerd door Microsoft (ook wel _offer mapping genoemd)._</li><li>Het aantal functies (serviceabonnementen) dat wordt aangeboden door Office 365-services kan groter zijn dan in de oorspronkelijke Microsoft Cloud Deutschland-aanbieding. Gebruikerslicenties in Office 365-services worden op dezelfde manier toegewezen aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). Gebruikerslicenties van alle gebruikers worden automatisch toegewezen aan de nieuwe functies. De beheerder moet zo nodig een expliciete actie ondernemen om deze licenties uit te schakelen. </li><li>Wanneer de migratie van abonnementen is voltooid, zijn zowel Office 365-services als Microsoft Cloud Deutschland-abonnementen zichtbaar in de Office 365-beheerportal, met de status van Microsoft Cloud Deutschland-abonnementen als _gedeprovisioneerd._ </li><li>Gebruikers krijgen opnieuw toegewezen licenties die zijn gekoppeld aan de nieuwe Office 365-servicesabonnementen. Alle klantprocessen die afhankelijk zijn van Microsoft Cloud Deutschland-abonnementen of SKU-GUID's, worden verbroken en moeten worden aangepast met de Office 365-services. </li><li>Nieuwe abonnementen in de Office 365-services worden gekocht met de nieuwe termijn (maandelijks/kwartaal/jaar) en de klant ontvangt een prorated refund voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. </li><li>Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-services onder de nieuwe Office 365-services tenant van dezelfde partner. Na klantmigratie kan de partner deze klant alleen beheren vanuit de Office 365-services tenant. </li><li>Extra functionaliteit is beschikbaar (bijvoorbeeld Microsoft Planner en Microsoft Flow), tenzij uitgeschakeld door tenantbeheerder. Zie Toegang tot [Microsoft 365-services](disable-access-to-services-while-assigning-user-licenses.md)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fase 4)

**Van toepassing op**: Alle klanten die SharePoint Online gebruiken

Als u nog steeds SharePoint 2013-werkstromen gebruikt, beperkt u het gebruik van SharePoint 2013-werkstromen tijdens de SharePoint Online-migratie.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| SharePoint en OneDrive worden overge- | SharePoint Online en OneDrive voor Bedrijven worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar Globale Office 365-services.<br><ul><li>Bestaande URL's van Microsoft Cloud Deutschland blijven behouden `contoso.sharepoint.de` (bijvoorbeeld).</li><li>Bestaande sites blijven behouden.</li><li>Clientverificatietokens die zijn uitgegeven door de Security Token Service (STS) in het exemplaar Microsoft Cloud Deutschland of Office 365 Global Services zijn geldig tijdens de overgang.</li></ul>|<ul><li>Inhoud is gedurende twee korte perioden tijdens de migratie alleen-lezen. Verwacht gedurende deze periode een banner 'u kunt inhoud niet bewerken' in SharePoint.</li><li>De zoekindex blijft niet behouden en het kan tien dagen duren voordat de zoekindex opnieuw wordt opgebouwd.</li><li>Inhoud van SharePoint Online en OneDrive voor Bedrijven is gedurende twee korte perioden tijdens de migratie alleen-lezen. Gebruikers zien in deze periode kort een banner 'u kunt inhoud niet bewerken'.</li><li>Na voltooiing van de SharePoint Online-migratie zijn de zoekresultaten voor SharePoint Online- en OneDrive voor Bedrijven-inhoud mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode geven zoekquery's mogelijk geen volledige resultaten als resultaat. Functies die afhankelijk zijn van zoekindexen, zoals SharePoint Online News, kunnen worden beïnvloed tijdens het opnieuw indexeren.</li><li>SharePoint 2013-werkstromen worden verbroken tijdens de migratie en moeten opnieuw worden gepubliceerd na de migratie.</li></ul>|
||||

Aanvullende aandachtspunten:

- Als uw organisatie nog steeds SharePoint 2010-werkstromen gebruikt, werken ze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, maar zijn standaard uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Nadat de migratie naar de SharePoint Online-service is voltooid, raden we u aan over te gaan naar Power Automate of andere ondersteunde oplossingen.

- Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online nog niet is gemigreerd, moeten de SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM versie 16.0.20616.12000 of lager gebruiken. Anders mislukt de verbinding met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

- Klanten van Microsoft Cloud Deutschland waarvan het SharePoint Online-exemplaar is gemigreerd, moeten de PowerShell-module van SharePoint Online/Microsoft.SharePointOnline.CSOM bijwerken naar versie 16.0.20717.12000 of hoger. Anders mislukt de verbinding met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.

> [!NOTE]
> Als u eDiscovery gebruikt, moet u op de hoogte zijn van de [eDiscovery-migratie.](ms-cloud-germany-transition-add-experience.md#ediscovery-phase-4-to-the-end-of-phase-9)

## <a name="exchange-online-phase-5"></a>Exchange Online (fase 5)

**Van toepassing op:** Alle klanten die Exchange Online gebruiken

Als u hybride Exchange Online gebruikt: Hybride beheerders van Exchange Online moeten de wizard Hybride configuratie  **(HCW)** meerdere keren uitvoeren als onderdeel van deze overgang. Pas het [Exchange-voorwerk toe voordat](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-configuration) **de migratiestap fase 5 begint.** Hybride exchange Online-klanten moeten de nieuwste versie van de wizard Hybride configuratie van Exchange (HCW) uitvoeren in de modus 'Office 365 Germany' om de on-premises configuratie voor te bereiden voor de migratie naar globale Office 365-services.

Nadat de migratiefase **9** is voltooid (wanneer de berichtmelding van het Berichtencentrum wordt gepubliceerd), moet u de HCW opnieuw uitvoeren met office 365 Worldwide-instellingen om uw on-premises systemen aan te wijzen op de globale Office 365-services.

Zie Exchange Online-Set-UserPhoto tijdens fase 5 als u [gebruikersfoto's](ms-cloud-germany-transition-add-experience.md#exchange-online-set-userphoto-during-phase-5) wilt wijzigen

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
|Stop of verwijder alle onboarding- of offboarding-postvakken, namelijk geen postvakken verplaatsen tussen Exchange on-premises en Exchange Online.  | Dit zorgt ervoor dat de aanvragen voor het verplaatsen van postvakken niet mislukken met een fout. | Als u dit niet doet, kan dit leiden tot een fout van de service- of Office-clients. |
| Exchange Online-postvakken worden verplaatst van Microsoft Cloud Deutschland naar Office 365 Global Services.| Exchange Online-configuratie voegt de nieuwe go-locale Duitse regio toe aan de overgangsorganisatie. De regio Globale services van Office 365 is standaard ingesteld, waardoor de interne service voor taakverdeling postvakken kan distribueren naar de juiste standaardregio in Office 365-services. In deze overgang zijn gebruikers aan beide zijden (MCD- of Globale services) in dezelfde organisatie en kunnen ze url-eindpunten gebruiken. |<ul><li>Gebruikers en services overstappen van uw oudere MCD-URL's (outlook.office.de) naar nieuwe URL's voor Office 365-services ( `https://outlook.office365.com` ).</li><li>Gebruikers kunnen de service blijven gebruiken via oudere MCD-URL's tijdens de migratie, maar ze moeten stoppen met het gebruik van de oudere URL's na voltooiing van de migratie.</li><li>Gebruikers moeten overstappen op het gebruik van de wereldwijde Office-portal voor Office Online-functies (Agenda, E-mail, Personen). Navigatie naar services die nog niet zijn gemigreerd naar Office 365-services, werkt pas wanneer ze zijn gemigreerd. </li><li>De Outlook Web App biedt niet de ervaring met openbare mappen tijdens de migratie. </li></ul>|
| Aangepaste DNS-instellingen bijwerken voor AutoDiscover| Door klanten beheerde DNS-instellingen voor AutoDiscover die momenteel verwijzen naar Microsoft Cloud Deutschland, moeten worden bijgewerkt om te verwijzen naar het globale eindpunt van Office 365 na voltooiing van de Exchange Online-fase (fase 5). <br> Bestaande DNS-vermeldingen met CNAME die naar autodiscover-outlook.office.de moeten worden bijgewerkt om naar de autodiscover.outlook.com. |  Beschikbaarheidsaanvragen en servicedetectiegesprekken via AutoDiscover wijzen rechtstreeks naar de Office 365-services. Klanten die deze DNS-updates niet uitvoeren, kunnen problemen met de Autodiscover-service ervaren wanneer de migratie is afgerond. |
||||

Aanvullende aandachtspunten:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` werkt alleen na de tenant cutover in fase 9. Koppelingen geven tot die tijd foutberichten 'er is iets misgegaan'.

- Gebruikers van Outlook Web App die toegang hebben tot een gedeeld postvak in de andere omgeving (bijvoorbeeld een gebruiker in de MCD-omgeving heeft toegang tot een gedeeld postvak in de globale omgeving), worden gevraagd een tweede keer te verifiëren. De gebruiker moet eerst zijn of haar postvak verifiëren en openen in `outlook.office.de` en vervolgens het gedeelde postvak openen dat zich in `outlook.office365.com` . Ze moeten zich een tweede keer verifiëren wanneer ze toegang hebben tot de gedeelde resources die worden gehost in de andere service.

- Voor bestaande Klanten van Microsoft Cloud Deutschland of klanten die in een overgangsfase werken, kan het mislukken wanneer een gedeeld postvak wordt toegevoegd aan Outlook met bestand **> Info > Account** toevoegen. Het weergeven van agendamachtigingen kan mislukken (de Outlook-client probeert de Rest API te `https://outlook.office.de/api/v2.0/Me/Calendars` gebruiken). Klanten die een account willen toevoegen om agendamachtigingen weer te geven, kunnen de registersleutel toevoegen zoals beschreven in Gebruikerservaringswijzigingen voor het delen van een agenda [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie zal slagen. Deze registersleutel kan voor de hele organisatie worden geïmplementeerd met behulp van groepsbeleid.

- Tijdens de migratiefase kan het gebruik van de PowerShell-cmdlets **New-migrationEndpoint,** **Set-MigrationEndpoint** en **Test-MigrationsServerAvailability** resulteren in fouten (fout bij proxy). Dit gebeurt wanneer het arbitragepostvak is gemigreerd naar de hele wereld, maar het postvak van de beheerder niet of omgekeerd. Als u dit wilt oplossen, gebruikt u tijdens het maken van de tenant PowerShell-sessie het arbitragepostvak als routeringstip in **de ConnectionUri.** Bijvoorbeeld:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Als u meer wilt weten over de verschillen voor organisaties in migratie en nadat Exchange Online-resources zijn gemigreerd, bekijkt u de informatie in Customer experience tijdens de migratie naar [Office 365-services in](ms-cloud-germany-transition-experience.md)de nieuwe Duitse datacenterregio's.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection /Security and Compliance (fase 6)

**Van toepassing op:** Alle klanten die Exchange Online gebruiken<br>

Back-end EOP-functies (Exchange Online Protection) worden gekopieerd naar de nieuwe regio 'Duitsland'.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Exchange Online-routering en historische berichtdetails. | Exchange Online maakt routering van externe hosts naar Office 365 mogelijk. De externe MX-records worden overgerouteerd naar de EOP-service. Tenantconfiguratie en historische details worden gemigreerd. |<ul><li>Microsoft-beheerde DNS-vermeldingen worden bijgewerkt van Office 365 Germany EOP naar Office 365-services.</li><li>Klanten moeten 30 dagen wachten nadat EOP dual write heeft geschreven voor EOP-migratie. Anders kan er gegevensverlies zijn.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype voor Bedrijven Online (fase 7)

**Van toepassing op:** Alle klanten die Skype voor Bedrijven Online gebruiken

Zorg ervoor dat u bekend bent met het [voorwerk voor uw Skype voor Bedrijven Online-migratieprocedure.](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online)

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Skype voor Bedrijven naar Teams. | Bestaande Klanten van Skype voor Bedrijven worden gemigreerd naar globale office 365-services in Europa en vervolgens overge stappen naar Microsoft Teams in de regio 'Duitsland' van Office 365-services. |<ul><li>Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven op de migratiedatum. Tien dagen vóór de migratie, posten we naar het beheercentrum om u te laten weten wanneer de migratie zal plaatsvinden, en opnieuw wanneer we beginnen met de migratie.</li><li> Beleidsconfiguratie wordt gemigreerd. </li><li>Gebruikers worden gemigreerd naar Teams en hebben na de migratie geen Skype voor Bedrijven meer. </li><li>Gebruikers moeten de bureaubladclient van Teams hebben geïnstalleerd. De installatie vindt gedurende de tien dagen via beleid op de Skype voor Bedrijven-infrastructuur, maar als dit mislukt, moeten gebruikers de client nog steeds downloaden of verbinding maken met een ondersteunde browser. </li><li>Contactpersonen en vergaderingen worden gemigreerd naar Teams.</li><li>Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven tussen tijdserviceovergangen naar Office 365-services en niet totdat dns-items van klanten zijn voltooid. </li><li>Contactpersonen en bestaande vergaderingen blijven fungeren als Skype voor Bedrijven-vergaderingen. </li></ul>|
||||

Als u verbinding moet maken met Skype voor Bedrijven Online met PowerShell nadat migratiefase 9 is voltooid, gebruikt u de volgende code om verbinding te maken:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fase 8)

**Van toepassing op:** Alle klanten die Microsoft Dynamics 365 gebruiken

Zorg ervoor dat u bekend bent met het [prework voor uw Installatieprocedure voor Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics365)

Klanten met Dynamics 365 hebben extra betrokkenheid nodig om de Dynamics-organisaties van de organisatie onafhankelijk te migreren.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Microsoft Dynamics-resources | Klanten met Microsoft Dynamics worden door Microsoft Engineering of Microsoft FastTrack ingeschakeld om Microsoft Dynamics 365 over te brengen naar het exemplaar globale services van Office 365.* |<ul><li>Na de migratie valideert de beheerder de organisatie. <</li><li>De beheerder wijzigt werkstromen zo nodig. </li><li>De beheerder clears AdminOnly mode as appropriate.</li><li>De beheerder wijzigt het organisatietype in _Sandbox_, naar eigen goed</li><li>Eindgebruikers op de hoogte stellen van de nieuwe URL om toegang te krijgen tot het exemplaar (org).</li><li>Werk binnenkomende verbindingen bij met de url van het nieuwe eindpunt. </li><li>De Dynamics-service is niet beschikbaar voor gebruikers tijdens de overgang. </li><li>Gebruikers moeten de status en functies van de organisatie valideren na de migratie van elke organisatie.</li></ul>|
||||

\* (i) Klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege de inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="power-bi-phase-8"></a>Power BI (fase 8)

**Van toepassing op:** Alle klanten die Microsoft Power BI (PBI) gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Power BI-resources | Klanten met Microsoft Power BI (PBI) worden ingeschakeld door Microsoft Engineering of Microsoft FastTrack nadat ze handmatig een bestaand PBI-migratiehulpmiddel hebben ingeschakeld om Power BI over te brengen naar het exemplaar globale services van Office 365.\*\* |<ul><li>De volgende Power BI-items worden _niet_ overgemaakt en ze moeten opnieuw worden gemaakt: <</li><li>Realtime-gegevenssets (bijvoorbeeld streaming- of pushsets). </li><li>Power BI on-premises gegevensgatewayconfiguratie en gegevensbron. </li><li>Rapporten die bovenop de realtimesets zijn gebouwd, zijn niet beschikbaar na de migratie en moeten opnieuw worden gemaakt. </li><li>Power BI-services zijn niet beschikbaar voor gebruikers tijdens de overgang. De beschikbaarheid van de service mag niet langer dan 24 uur duren.</li><li>Gebruikers moeten gegevensbronnen en hun on-premises gegevensgateways opnieuw configureren met de Power BI-service na de migratie.  Totdat ze dit doen, kunnen gebruikers deze gegevensbronnen niet gebruiken om geplande vernieuwings- en/of directe query's uit te voeren op basis van deze gegevensbronnen. </li><li>Capaciteit en premiumwerkruimten kunnen niet worden gemigreerd. Klanten moeten alle capaciteit vóór de migratie verwijderen en deze opnieuw maken na de migratie. Verplaats werkruimten naar wens terug naar de gewenste capaciteit.</li></ul>  |
||||

\*\* (i) Klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege de inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="office-apps"></a>Office-apps

**Van toepassing op:** Alle klanten die Office-bureaubladtoepassingen gebruiken (Word, Excel, PowerPoint, Outlook, ...)

Office 365-tenants die overstappen op de regio 'Duitsland' vereisen dat alle gebruikers zich moeten sluiten, zich moeten aanmelden bij Office 365 en zich opnieuw moeten aanmelden voor alle Office-bureaubladtoepassingen (Word, Excel, PowerPoint, Outlook, enzovoort) en OneDrive voor Bedrijven-client nadat de tenantmigratie fase 9 heeft bereikt. Door u af te melden en aan te melden, kunnen de Office-services nieuwe verificatietokens verkrijgen bij de globale Azure AD-service.

Zorg ervoor dat u het [prework voor](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) mobiele apparaten hebt voltooid.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Clients, Office Online tijdens office-client cutover, Azure AD rondt het tenantbereik af om te wijzen naar de Office 365-services. | Met deze configuratiewijziging kunnen Office-clients de eindpunten van office 365-services bijwerken en erop wijzen. | <ul><li>Laat gebruikers weten dat ze _alle_ Office-apps moeten sluiten en zich vervolgens opnieuw moeten aanmelden (of klanten moeten dwingen opnieuw te starten en gebruikers zich moeten aanmelden) zodat Office-clients de wijziging kunnen oppikken. </li><li>Laat gebruikers en helpdeskmedewerkers  weten dat gebruikers mogelijk een Office-banner zien die hen vraagt om Office-apps binnen 72 uur na de cutover opnieuw te activeren. </li><li>Alle Office-toepassingen op persoonlijke machines moeten worden gesloten en gebruikers moeten zich aanmelden en zich opnieuw aanmelden. Meld u op de activeringsbalk Geel aan om opnieuw te activeren voor Office 365-services.</li><li>Gedeelde machines vereisen acties die lijken op persoonlijke machines en waarvoor geen speciale procedure is vereist. </li><li>Op mobiele apparaten moeten gebruikers zich aanmelden bij apps, sluiten en zich opnieuw aanmelden.</li></ul>|
||||

## <a name="line-of-business-apps"></a>Line-of-business-apps

Als u line-of-business-apps hebt, moet u ervoor zorgen dat u de prework voor de procedure voor [line-of-business-apps hebt](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) voltooid.

## <a name="office-services"></a>Office Services

De meest recent gebruikte (MRU) service in Office is een cutover van de Microsoft Cloud Deutschland naar Office 365 Global Services, niet een migratie. Alleen MRU-koppelingen van de kant globale services van Office 365 zijn zichtbaar na de migratie vanuit de Office.com portal. MRU-koppelingen vanuit de Microsoft Cloud Deutschland zijn niet zichtbaar als MRU-koppelingen in Office 365 Global Services. In Globale Office 365-services zijn MRU-koppelingen alleen toegankelijk nadat de tenantmigratie fase 9 heeft bereikt.

## <a name="post-migration"></a>Migratie na de migratie

Zorg ervoor dat u het [artikel postmigratieactiviteiten leest](ms-cloud-germany-transition-add-experience.md#post-migration) en deze uitvoert.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Informatie over power bi-migratieprogramma's](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams-upgrade](/microsoftteams/upgrade-start-here)
