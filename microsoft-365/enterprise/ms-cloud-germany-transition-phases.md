---
title: Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland)
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
ms.openlocfilehash: 5764b5cedf17487320fbfd05885120de86da3a84
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029060"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland

Tenantmigraties van Microsoft Cloud Deutschland (MCD) naar de regio 'Duitsland' van Microsoft's Globale Office 365-services worden uitgevoerd als een reeks fasen en hun geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de tien fasen van de migratie naar de nieuwe Duitse datacenters.

![De tien fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

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
|Eindpunten uitgeschakeld|30 dagen|Microsoft|30 dagen na de finalisatie van Azure AD stopt de Azure AD-service van Microsoft Cloud Deutschland de toegang tot eindpunten voor de overgefaseeerde organisatie. Eindpuntaanvragen zoals Verificatie mislukken vanaf dit moment ten opzichte van de Microsoft Cloud Deutschland-service. |


De fasen en hun acties zorgen ervoor dat kritieke gegevens en ervaringen worden gemigreerd naar de globale Office 365-services. Nadat uw tenant is toegevoegd aan de migratiewachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de back-endservice. Voor sommige werkbelastingen zijn mogelijk acties van de beheerder (of gebruiker) vereist, of kan de migratie van invloed zijn op het gebruik van de fasen die worden uitgevoerd en besproken in [Hoe wordt de migratie georganiseerd?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen terwijl ze verschillende fasen van de migratie doorlopen. Controleer de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u bereid bent om de stappen in de desbetreffende fasen uit te voeren, indien vereist. Als u de benodigde stappen niet voltooit, kan dit leiden tot een servicestoring en kan de voltooiing van de migratie naar de Office 365-services worden vertraagd.

## <a name="phase-opt-in"></a>Fase: Opt-In

**Is** van toepassing op : Alle klanten met een Office 365-tenant die wordt gehost in de Microsoft Cloud Deutschland (MCD) Microsoft kan Office 365-tenants die worden gehost in de MCD niet migreren zonder toestemming.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
|**Klanttaak:** toestemming verlenen voor migratie| Klant verleent toestemming voor de migratie, zodat Microsoft het recht krijgt om de overgang van gegevens en services naar het exemplaar globale services van Office 365 te migreren en te orden. Er zijn twee manieren <ol><li>De Office 365-tenantbeheerder kiest voor de microsoft-migratie. </li><li> Klanten hebben abonnementen in hun MCD Office 365-tenant verlengd na 1 mei 2020. Microsoft informeert deze klanten elke maand over het migratierecht, wacht 30 dagen om klanten de kans te geven om te annuleren en meld u vervolgens rechtstreeks aan.</li></ol> | <ul><li>Tenant is gemarkeerd als toestemming voor migratie en het beheercentrum geeft bevestiging weer. </li><li>Bevestiging wordt gepost in het Office 365-tenantberichtcentrum. Serviceconfiguratie wordt voortgezet vanuit Microsoft Cloud Deutschland-eindpunten. </li><li> </li></ul>
|**Tenantbeheerder:** Berichten controleren|De tenantbeheerder moet vanaf dit moment het Office 365-berichtencentrum controleren op updates over de status van de migratiefase.|De klant kan de benodigde taken op tijd uitvoeren.
||||

## <a name="phase-1-before-the-migration-starts"></a>Fase 1: Voordat de migratie begint

Zorg ervoor dat u bekend bent met de [migratievoorbereidingsstappen die van toepassing zijn op alle klanten.](ms-cloud-germany-transition-add-pre-work.md)

Als u een DNS CNAME met de naam _msoid_ hebt ingesteld in een of meer DNS-naamruimten die u bezit, moet u de CNAME uiterlijk tot het einde van fase 8 verwijderen. U kunt de _CNAME-msoid op elk_ moment vóór het einde van fase 8 verwijderen. Zie de [prework voor DNS](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains).

Als u één aanmelding voor Office 365 en Azure gebruikt in het exemplaar Microsoft Cloud Deutschland, moet u de migratie van uw Azure-abonnement dienovereenkomstig voorbereiden en plannen. Zorg ervoor dat u de [prework voor Microsoft Azure begrijpt.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD Connect met AD FS-federatie
**Van toepassing op**: Klanten met AD FS-federatie

**Wanneer toegepast**: Voordat fase 2 wordt gestart

Als u Active Directory Federation Services (AD FS) gebruikt, moet u een back-up maken van uw [ADFS-configuratie](ms-cloud-germany-transition-azure-ad.md) voor en na het toevoegen van het vertrouwen van de afhankelijke partij voor de globale Office 365-service  vóór het begin van fase 2.

## <a name="phase-2-azure-ad-migration"></a>Fase 2: Azure AD-migratie
In deze fase wordt azure Active Directory gemigreerd naar de nieuwe datacenterregio en wordt deze actief. De oude Azure AD-eindpunten zijn nog steeds beschikbaar.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online Hybrid - AuthServer on-premises wijzigen
**Van toepassing op:** Alle klanten die een actieve hybride Exchange-configuratie gebruiken met on-premises Exchange-servers

**Wanneer toegepast**: Na het einde van fase 2

De on-premises AuthServer moet worden aanwijzen op de algemene BEVEILIGINGS-tokenservice (STS) voor verificatie nadat de Azure AD-migratie is voltooid.
Dit zorgt ervoor dat verificatieaanvragen voor Beschikbaarheidsaanvragen voor Exchange van gebruikers in de migratietoestand die zich richten op de hybride on-premises omgeving, worden geverifieerd om toegang te krijgen tot de on-premises service. Op dezelfde manier zorgt dit voor verificatie van aanvragen van on-premises naar Office 365 Global Services-eindpunten. Nadat Azure AD-migratie (fase 2) is voltooid, moet de beheerder van de on-premises Exchange-topologie (hybride) een nieuw eindpunt voor verificatieservice toevoegen voor de globale Office 365-services. Met deze opdracht van Exchange PowerShell vervangt u de tenant-id van uw organisatie in de `<TenantID>` Azure-portal in Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

Als u deze taak niet voltooit, kan dit ertoe leiden dat hybride vrije-drukke aanvragen geen informatie verstrekken voor postvakgebruikers die zijn gemigreerd van Microsoft Cloud Deutschland naar Office 365-services.

## <a name="phase-3-subscription-transfer"></a>Fase 3: Abonnementsoverdracht

**Van toepassing op**: Alle klanten met een Office 365-tenant die wordt gehost in de Microsoft Cloud Deutschland (MCD)

Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-services onder de nieuwe Office 365-services tenant van dezelfde partner. Na klantmigratie kan de partner deze klant alleen beheren vanuit de Office 365-services tenant.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Abonnementen worden overgezet| Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende Office 365 Global-services-abonnement. <ul><li>De office 365 Global Services-aanbieding van dat abonnement wordt gedefinieerd door Microsoft (ook wel _offer mapping genoemd)._</li><li> Corresponderende Office 365 Global-services-abonnementen worden gekocht in het exemplaar Van Office 365 Global voor de overgedragen Microsoft Cloud Deutschland-abonnementen.</li><li>Oudere Microsoft Cloud Deutschland-abonnementen worden na voltooiing verwijderd uit de Office 365-servicesten tenant.</li></ul>| <ul><li>Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld geen nieuwe abonnementen of wijzigingen in het aantal stoelen) tijdens deze fase.</li><li>Wijzigingen in licentietoewijzingen worden geblokkeerd.</li><li>Wanneer de migratie van abonnementen is voltooid, zijn zowel Office 365-services als Microsoft Cloud Deutschland-abonnementen zichtbaar in de Office 365-beheerportal, met de status van Microsoft Cloud Deutschland-abonnementen als _gedeprovisioneerd._ </li><li>Alle klantprocessen die afhankelijk zijn van Microsoft Cloud Deutschland-abonnementen of SKU-GUID's, worden verbroken en moeten worden aangepast met de Office 365-services. </li><li>Nieuwe abonnementen in de Office 365-services worden gekocht met de nieuwe termijn (maandelijks/kwartaal/jaar) en de klant ontvangt een prorated refund voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. </li></ul> |
|Licenties worden opnieuw toegewezen|Gebruikers met toegewezen Microsoft Cloud Deutschland-licenties krijgen licenties toegewezen in het globale office 365-exemplaar.|<ul><li>Gebruikers krijgen opnieuw toegewezen licenties die zijn gekoppeld aan de nieuwe Office 365-servicesabonnementen. Gebruikerslicenties van alle gebruikers worden automatisch toegewezen aan de nieuwe functies.</li><li>Het aantal functies (serviceabonnementen) dat wordt aangeboden door Office 365-services kan groter zijn dan in de oorspronkelijke Microsoft Cloud Deutschland-aanbieding. Gebruikerslicenties in Office 365-services worden op dezelfde manier toegewezen aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). </li></ul> 
|**Beheertaak** Functies uitschakelen|De beheerder moet een expliciete actie ondernemen om deze functies uit te schakelen, indien nodig. |<ul><li>Gebruikers zien nieuwe onbekende services in de portal</li><li>Extra functionaliteit is beschikbaar (bijvoorbeeld Microsoft Planner en Microsoft Flow), tenzij uitgeschakeld door tenantbeheerder. Zie Toegang tot [Microsoft 365-services](disable-access-to-services-while-assigning-user-licenses.md)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.</li></ul>
|**Beheertaak**|Alle klantprocessen wijzigen die afhankelijk zijn van Microsoft Cloud Deutschland-abonnementen of SKU-GUID's met de Office 365-services|Klantprocessen blijven werken.
||||

**Van toepassing op**: Microsoft-partners die de Office 365-partnerportal gebruiken

Tussen fase 2 en fase 3 is partnerportal mogelijk niet toegankelijk. Gedurende deze periode heeft Partner mogelijk geen toegang tot de informatie van de tenant op de Partnerportal. Aangezien elke migratie anders is, kan de duur van de in-toegankelijkheid in uren zijn.


## <a name="phase-4-sharepoint-online"></a>Fase 4: SharePoint Online

**Van toepassing op**: Alle klanten die SharePoint Online gebruiken

Als u nog steeds SharePoint 2013-werkstromen gebruikt, beperkt u het gebruik van SharePoint 2013-werkstromen tijdens de SharePoint Online-migratie.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-----|:-------|
| SharePoint en OneDrive worden overge- | SharePoint Online en OneDrive voor Bedrijven worden in deze fase gemigreerd van Microsoft Cloud Deutschland naar Globale Office 365-services.<br><ul><li>Bestaande URL's van Microsoft Cloud Deutschland blijven behouden `contoso.sharepoint.de` (bijvoorbeeld).</li><li>Bestaande sites blijven behouden.</li><li>Clientverificatietokens die zijn uitgegeven door de Security Token Service (STS) in het exemplaar Microsoft Cloud Deutschland of Office 365 Global Services zijn geldig tijdens de overgang.</li></ul>|<ul><li>Inhoud is gedurende twee korte perioden tijdens de migratie alleen-lezen. Verwacht gedurende deze periode een banner 'u kunt inhoud niet bewerken' in SharePoint.</li><li>De zoekindex blijft niet behouden en het kan tien dagen duren voordat de zoekindex opnieuw wordt opgebouwd.</li><li>Inhoud van SharePoint Online en OneDrive voor Bedrijven is gedurende twee korte perioden tijdens de migratie alleen-lezen. Gebruikers zien in deze periode kort een banner 'u kunt inhoud niet bewerken'.</li><li>Na voltooiing van de SharePoint Online-migratie zijn de zoekresultaten voor SharePoint Online- en OneDrive voor Bedrijven-inhoud mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode geven zoekquery's mogelijk geen volledige resultaten als resultaat. Functies die afhankelijk zijn van zoekindexen, zoals SharePoint Online News, kunnen worden beïnvloed tijdens het opnieuw indexeren.</li><li>SharePoint 2013-werkstromen worden verbroken tijdens de migratie en moeten opnieuw worden gepubliceerd na de migratie.</li></ul>
|**SPO-beheerder:** SharePoint 2013-werkstromen opnieuw publiceren| Een SharePoint Online-beheerder herpubliceert de SharePoint 2013-werkstromen na de migratie.|SharePoint 2013-werkstromen zijn beschikbaar.
|**PowerShell-gebruiker:** Bijwerken naar nieuwe module| Alle gebruikers van de SharePoint Online Powershell-module moeten module/Microsoft.SharePointOnline.CSOM bijwerken naar versie 16.0.20717.12000 of hoger nadat de SharePoint Online-migratie is voltooid. Voltooiing wordt gecommuniceerd in het berichtencentrum.| SharePoint Online via PowerShell of het objectmodel aan de clientzijde mislukt niet meer.
||||

Aanvullende aandachtspunten:

- Als uw organisatie nog steeds SharePoint 2010-werkstromen gebruikt, werken ze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, maar zijn standaard uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Nadat de migratie naar de SharePoint Online-service is voltooid, raden we u aan over te gaan naar Power Automate of andere ondersteunde oplossingen.
 - Klanten van Microsoft Cloud Deutschland waarvan het Exemplaar van SharePoint Online nog niet is gemigreerd, moeten de SharePoint Online PowerShell-module/Microsoft.SharePointOnline.CSOM versie 16.0.20616.12000 of lager gebruiken. Anders mislukt de verbinding met SharePoint Online via PowerShell of het objectmodel aan de clientzijde.
- Tijdens deze fase worden de IP-adressen achter de SharePoint-URL's gewijzigd. Na de overgang naar Globale Office 365-services worden de adressen voor de behouden tenant-URL's (bijvoorbeeld en ) gewijzigd in de URL's en IP-adresbereiken voor Microsoft `contoso.sharepoint.de` `contoso-my.sharepoint.de` [365 Wereldwijd (SharePoint Online en OneDrive voor Bedrijven)](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business).

> [!NOTE]
> Als u eDiscovery gebruikt, moet u op de hoogte zijn van de [eDiscovery-migratie.](ms-cloud-germany-transition-add-scc.md)

## <a name="phase-5-exchange-online"></a>Fase 5: Exchange Online 
Vanaf fase 5 worden Exchange Online-postvakken verplaatst van Microsoft Cloud Deutschland naar Office 365 Global Services.

De regio Globale services van Office 365 is standaard ingesteld, waardoor de interne service voor taakverdeling postvakken kan distribueren naar de juiste standaardregio in Office 365-services. In deze overgang zijn gebruikers aan beide zijden (MCD- of Globale services) in dezelfde organisatie en kunnen ze url-eindpunten gebruiken.

De nieuwe regio 'Duitsland' wordt toegevoegd aan de organisatie-instelling. Exchange Online-configuratie voegt de nieuwe go-locale Duitse regio toe aan de overgangsorganisatie.

- Gebruikers en services overstappen van uw oudere MCD-URL's `https://outlook.office.de` () naar nieuwe URL's voor Office 365-services ( `https://outlook.office365.com` ).
-  De Exchange Online-services (Outlook Web Access en Exchange-beheercentrum) voor het nieuwe Duitse datacentergebied zijn vanaf deze fase beschikbaar, ze zijn niet eerder beschikbaar.
- Gebruikers kunnen de service blijven gebruiken via oudere MCD-URL's tijdens de migratie, maar ze moeten stoppen met het gebruik van de oudere URL's na voltooiing van de migratie.
- Gebruikers moeten overstappen op het gebruik van de wereldwijde Office-portal voor Office Online-functies (Agenda, E-mail, Personen). Navigatie naar services die nog niet zijn gemigreerd naar Office 365-services, werkt pas wanneer ze zijn gemigreerd. 
- Deze beperking geldt ook voor achtergrondservices zoals 'Mijn account'. Mijn account voor globale services wordt beschikbaar na voltooiing van fase 9. Tot deze tijd moeten gebruikers de MCD-portal gebruiken om hun accountinstellingen te beheren.
- De Outlook Web App biedt niet de ervaring met openbare mappen tijdens de migratie.

Zie [Exchange Online PowerShell](#exchange-online-powershell)- Set-UserPhoto tijdens fase 5 als u gebruikersfoto's wilt wijzigen.

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>DNS-record voor autodiscover in Exchange Online
**Van toepassing op:** Klanten die Exchange Online gebruiken met een aangepast domein

Door klanten beheerde DNS-instellingen voor Autodiscover die momenteel verwijzen naar Microsoft Cloud Deutschland, moeten worden bijgewerkt om te verwijzen naar het globale eindpunt van Office 365 na voltooiing van de Exchange Online-fase (fase 5). <br> Bestaande DNS-vermeldingen met CNAME die naar autodiscover-outlook.office.de moeten worden bijgewerkt om te wijzen **naar autodiscover.outlook.com.**

Klanten die deze DNS-updates niet uitvoeren na voltooiing van de **migratiefase 9,** kunnen serviceproblemen krijgen wanneer de migratie is voltooid.

> [!NOTE]
> Validatiefouten in het beheercentrum voor aangepaste domeinen voor de autodiscover-invoer kunnen worden genegeerd. Services werken alleen goed wanneer de CNAME-record is gewijzigd in autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**Van toepassing op:** Exchange Online-beheerders met Exchange Online PowerShell

Tijdens de migratiefase kan het gebruik van de PowerShell-cmdlets **New-MigrationEndpoint,** **Set-MigrationEndpoint** en **Test-MigrationsServerAvailability** resulteren in fouten (fout bij proxy). Dit gebeurt wanneer het arbitragepostvak is gemigreerd naar de hele wereld, maar het postvak van de beheerder niet of omgekeerd. Als u dit wilt oplossen, gebruikt u tijdens het maken van de tenant PowerShell-sessie het arbitragepostvak als routeringstip in **de ConnectionUri.** Bijvoorbeeld:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
Als u de PowerShell-cmdlet **Set-UserPhoto** gebruikt, wordt een fout weergegeven als een gebruikerspostvak is gemigreerd, maar een beheerderspostvak niet is gemigreerd of omgekeerd. In dit geval moet een beheerder de e-mail-id doorgeven van de gebruiker van wie de foto moet worden gewijzigd tijdens het maken van de `ConnectionUri` tenant PowerShell-sessie: 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 waar `<user_email>` is de tijdelijke aanduiding voor de e-mail-id van het postvak van de gebruiker. 

Aanvullende aandachtspunten:
- Gebruikers van Outlook Web App die toegang hebben tot een gedeeld postvak in de andere omgeving (bijvoorbeeld een gebruiker in de MCD-omgeving heeft toegang tot een gedeeld postvak in de globale omgeving), worden gevraagd een tweede keer te verifiëren. De gebruiker moet eerst zijn of haar postvak verifiëren en openen in `outlook.office.de` en vervolgens het gedeelde postvak openen dat zich in `outlook.office365.com` . Ze moeten zich een tweede keer verifiëren wanneer ze toegang hebben tot de gedeelde resources die worden gehost in de andere service.
- Voor bestaande Klanten van Microsoft Cloud Deutschland of klanten die in een overgangsfase werken, kan het mislukken wanneer een gedeeld postvak wordt toegevoegd aan Outlook met bestand **> Info > Account** toevoegen. Het weergeven van agendamachtigingen kan mislukken (de Outlook-client probeert de Rest API te `https://outlook.office.de/api/v2.0/Me/Calendars` gebruiken). Klanten die een account willen toevoegen om agendamachtigingen weer te geven, kunnen de registersleutel toevoegen zoals beschreven in Gebruikerservaringswijzigingen voor het delen van een agenda [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie zal slagen. Deze registersleutel kan voor de hele organisatie worden geïmplementeerd met behulp van groepsbeleid.
- Alle klanten die een actieve hybride Exchange-configuratie gebruiken, kunnen postvakken niet verplaatsen van on-premises Exchange Server naar Exchange Online, noch naar Microsoft Cloud Deutschland, noch naar de nieuwe datacenterregio in Duitsland. Klanten moeten ervoor zorgen dat de lopende postvakbewegingen zijn voltooid vóór fase 5 en na voltooiing van deze fase worden hervat.
- Zorg ervoor dat alle gebruikers die oudere protocollen (POP3/IMAP4/SMTP) voor hun apparaten gebruiken, bereid zijn om de eindpunten in hun client te wijzigen nadat hun [Exchange-postvak](ms-cloud-germany-transition-add-pre-work.md#exchange-online)is verplaatst naar het nieuwe Duitse datacentergebied, zoals beschreven in de stappen vóór de migratie voor Exchange Online.
- Skype voor Bedrijven-vergaderingen plannen in Outlook Web App is niet meer beschikbaar nadat het postvak is gemigreerd. Zo nodig moeten gebruikers Outlook gebruiken.

Als u meer wilt weten over de verschillen voor organisaties in migratie en nadat Exchange Online-resources zijn gemigreerd, bekijkt u de informatie in Customer experience tijdens de migratie naar [Office 365-services in](ms-cloud-germany-transition-experience.md)de nieuwe Duitse datacenterregio's.

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>Fase 6: Exchange Online Protection /Security and Compliance

**Van toepassing op:** Alle klanten die Exchange Online gebruiken<br>

Back-end EOP-functies (Exchange Online Protection) worden gekopieerd naar de nieuwe regio 'Duitsland'. Exchange Online maakt routering van externe hosts naar Office 365 mogelijk en historische tenantdetails worden gemigreerd, waaronder ook back-endservices voor beveiligings- en compliancefuncties.

Klanten die alleen exchange Online-mogelijkheden (niet-hybride) gebruiken, hoeven in dit stadium niet op te letten.

### <a name="exchange-online-hybrid-deployments"></a>Hybride implementaties van Exchange Online
**Van toepassing op:** Alle klanten die een actieve hybride Exchange-configuratie gebruiken met on-premises Exchange-servers

Zorg ervoor dat [de Exchange-prework](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) is toegepast **voordat de migratiestap fase 5 begint.** Hybride exchange Online-klanten moeten de nieuwste versie van de wizard Hybride configuratie van Exchange (HCW) uitvoeren in de modus 'Office 365 Germany' om de on-premises configuratie voor te bereiden voor de migratie naar globale Office 365-services.

**Beheeracties:**
- Tussen het begin van de migratiefase 6 en de voltooiing van de migratiefase 9 (wanneer de berichtmelding van het Berichtencentrum wordt gepubliceerd), moet u de HCW opnieuw uitvoeren met office 365 Worldwide-instellingen om uw on-premises systemen naar de Globale Office 365-services te wijzen. Als u deze taak niet voltooit vóór fase 9 [Migratie voltooid] kan dit leiden tot NDR's voor e-mail die wordt gerouteerd tussen uw on-premises Exchange-implementatie en Office 365.
- Stop of verwijder alle onboarding- of offboarding-postvakken, namelijk geen postvakken verplaatsen tussen Exchange on-premises en Exchange Online.  Dit zorgt ervoor dat de aanvragen voor het verplaatsen van postvakken niet mislukken met een fout. Als u dit niet doet, kan dit leiden tot een fout van de service- of Office-clients.
- Extra Send-Connectors die zijn gemaakt naast de verbindingslijn die is gemaakt door de HCW en die zijn gericht op Exchange Online, moeten in deze fase worden bijgewerkt direct nadat de HCW-run is uitgevoerd, anders werken ze niet meer. Het TLS-domein moet worden bijgewerkt voor deze verzendconnectors. <br> Als u het TLS-domein wilt bijwerken, gebruikt u de volgende PowerShell-opdracht in uw Exchange Server-omgeving:
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online"></a>Fase 7: Skype voor Bedrijven Online

**Van toepassing op:** Alle klanten die Skype voor Bedrijven Online gebruiken

Bekijk de [stappen vóór de migratie van Skype voor Bedrijven Online](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) en controleer of u alle stappen hebt voltooid.
In deze fase wordt Skype voor Bedrijven gemigreerd naar Microsoft Teams. Bestaande Klanten van Skype voor Bedrijven worden gemigreerd naar globale office 365-services in Europa en vervolgens overge stappen naar Microsoft Teams in de regio 'Duitsland' van Office 365-services.

- Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven op de migratiedatum. Tien dagen vóór de migratie ontvangt de klant een bericht in het beheercentrum waarin wordt aangekondigd wanneer de migratie zal plaatsvinden en opnieuw wanneer de migratie begint.
- Beleidsconfiguratie wordt gemigreerd.
- Gebruikers worden gemigreerd naar Teams en hebben na de migratie geen toegang meer tot Skype voor Bedrijven.
- Gebruikers moeten de bureaubladclient van Microsoft Teams hebben geïnstalleerd. De installatie vindt gedurende de tien dagen via beleid op de Skype voor Bedrijven-infrastructuur, maar als dit mislukt, moeten gebruikers de client nog steeds downloaden of verbinding maken met een ondersteunde browser.
- Contactpersonen en vergaderingen worden gemigreerd naar Microsoft Teams.
- Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven tussen tijdserviceovergangen naar Office 365-services en niet totdat dns-items van klanten zijn voltooid.
- Contactpersonen en bestaande vergaderingen blijven fungeren als Skype voor Bedrijven-vergaderingen.
- De webbrowserversie van Microsoft Teams werkt pas als fase 9 is voltooid.

Als u verbinding moet maken met Skype voor Bedrijven Online met PowerShell nadat migratiefase 9 is voltooid, gebruikt u de volgende PowerShell-code om verbinding te maken:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>Fase 8: Dynamics 365

**Van toepassing op:** Alle klanten die Microsoft Dynamics 365 gebruiken

Zorg ervoor dat u bekend bent met het [prework voor uw Installatieprocedure voor Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics365)

Klanten met Dynamics 365 hebben extra betrokkenheid nodig om de Dynamics-organisaties van de organisatie onafhankelijk te migreren.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Microsoft Dynamics-resources | Klanten met Microsoft Dynamics worden door Microsoft Engineering of Microsoft FastTrack ingeschakeld om Microsoft Dynamics 365 over te brengen naar het exemplaar globale services van Office 365.* |<ul><li>Na de migratie valideert de beheerder de organisatie. <</li><li>De beheerder wijzigt werkstromen zo nodig. </li><li>De beheerder clears AdminOnly mode as appropriate.</li><li>De beheerder wijzigt het organisatietype in _Sandbox_, naar eigen goed</li><li>Eindgebruikers op de hoogte stellen van de nieuwe URL om toegang te krijgen tot het exemplaar (org).</li><li>Werk binnenkomende verbindingen bij met de url van het nieuwe eindpunt. </li><li>De Dynamics-service is niet beschikbaar voor gebruikers tijdens de overgang. </li><li>Gebruikers moeten de status en functies van de organisatie valideren na de migratie van elke organisatie.</li></ul>|
||||

\* (i) Klanten met Microsoft Dynamics 365 moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege de inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="phase-8-power-bi"></a>Fase 8: Power BI

**Van toepassing op:** Alle klanten die Microsoft Power BI (PBI) gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Migratie van Power BI-resources | Klanten met Microsoft Power BI (PBI) worden ingeschakeld door Microsoft Engineering of Microsoft FastTrack nadat ze handmatig een bestaand PBI-migratiehulpmiddel hebben ingeschakeld om Power BI over te brengen naar het exemplaar globale services van Office 365.\*\* |<ul><li>De volgende Power BI-items worden _niet_ overgemaakt en ze moeten opnieuw worden gemaakt: <</li><li>Realtime-gegevenssets (bijvoorbeeld streaming- of pushsets). </li><li>Power BI on-premises gegevensgatewayconfiguratie en gegevensbron. </li><li>Rapporten die bovenop de realtimesets zijn gebouwd, zijn niet beschikbaar na de migratie en moeten opnieuw worden gemaakt. </li><li>Power BI-services zijn niet beschikbaar voor gebruikers tijdens de overgang. De beschikbaarheid van de service mag niet langer dan 24 uur duren.</li><li>Gebruikers moeten gegevensbronnen en hun on-premises gegevensgateways opnieuw configureren met de Power BI-service na de migratie.  Totdat ze dit doen, kunnen gebruikers deze gegevensbronnen niet gebruiken om geplande vernieuwings- en/of directe query's uit te voeren op basis van deze gegevensbronnen. </li><li>Capaciteit en premiumwerkruimten kunnen niet worden gemigreerd. Klanten moeten alle capaciteit vóór de migratie verwijderen en deze opnieuw maken na de migratie. Verplaats werkruimten naar wens terug naar de gewenste capaciteit.</li></ul>  |
||||

\*\* (i) Klanten met Microsoft Power BI moeten actie ondernemen in dit migratiescenario, zoals gedefinieerd in het opgegeven migratieproces. (ii) Als de klant geen actie onderneemt, kan Microsoft de migratie niet voltooien. (iii) Wanneer Microsoft de migratie niet kan voltooien vanwege de inactiviteit van de klant, verloopt het abonnement van de klant op 29 oktober 2021.

## <a name="phase-9-office-apps"></a>Fase 9: Office-apps

**Van toepassing op:** Alle klanten die Office-bureaubladtoepassingen gebruiken (Word, Excel, PowerPoint, Outlook, ...)

Office 365-tenants die overstappen op de regio 'Duitsland' vereisen dat alle gebruikers zich moeten sluiten, zich moeten aanmelden bij Office 365 en zich opnieuw moeten aanmelden voor alle Office-bureaubladtoepassingen (Word, Excel, PowerPoint, Outlook, enzovoort) en OneDrive voor Bedrijven-client nadat de tenantmigratie fase 9 heeft bereikt. Door u af te melden en aan te melden, kunnen de Office-services nieuwe verificatietokens verkrijgen bij de globale Azure AD-service.

De beste gebruikerservaring kan worden gegarandeerd met behulp van de meest recente Office-toepassingen. Ondernemingen moeten overwegen het Monthly Enterprise-kanaal te gebruiken.

Zorg ervoor dat u het [prework voor](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) mobiele apparaten hebt voltooid.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Clients, Office Online tijdens office-client cutover, Azure AD rondt het tenantbereik af om te wijzen naar de Office 365-services. | Met deze configuratiewijziging kunnen Office-clients de eindpunten van office 365-services bijwerken en erop wijzen. | <ul><li>Laat gebruikers weten dat ze _alle_ Office-apps moeten sluiten en zich vervolgens opnieuw moeten aanmelden (of klanten moeten dwingen opnieuw te starten en gebruikers zich moeten aanmelden) zodat Office-clients de wijziging kunnen oppikken. </li><li>Laat gebruikers en helpdeskmedewerkers  weten dat gebruikers mogelijk een Office-banner zien die hen vraagt om Office-apps binnen 72 uur na de cutover opnieuw te activeren. </li><li>Alle Office-toepassingen op persoonlijke machines moeten worden gesloten en gebruikers moeten zich aanmelden en zich opnieuw aanmelden. Meld u op de activeringsbalk Geel aan om opnieuw te activeren voor Office 365-services.</li><li>Gedeelde machines vereisen acties die lijken op persoonlijke machines en waarvoor geen speciale procedure is vereist. </li><li>Op mobiele apparaten moeten gebruikers zich aanmelden bij apps, sluiten en zich opnieuw aanmelden.</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>Fase 9: line-of-business-apps

**Van toepassing op:** Alle klanten die gebruikmaken van line-of-business-apps die zijn verbonden met Office 365

Als u line-of-business-apps hebt, moet u ervoor zorgen dat u de prework voor de procedure voor [line-of-business-apps hebt](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) voltooid.

## <a name="phase-9--10-azure-ad-finalization"></a>Fase 9 & 10: Azure AD Finalization

**Van toepassing op:** Alle klanten

Wanneer de Office 365-tenant de laatste stap van de migratie voltooit (Azure AD Finalization (Fase 9)) worden alle services overgegaan naar de hele wereld. Geen enkele toepassing of gebruiker mag toegang krijgen tot bronnen voor de tenant tegen een van de Microsoft Cloud Deutschland-eindpunten. De Microsoft Cloud Deutschland Azure AD-service stopt automatisch, 30 dagen nadat de laatste fase is voltooid, de eindpunttoegang voor de overgefaseeerde tenant. Eindpuntaanvragen zoals Verificatie mislukken vanaf dit moment ten opzichte van de Microsoft Cloud Deutschland-service. 

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Gebruikers-eindpunten bijwerken | Zorg ervoor dat alle gebruikers toegang hebben tot de service met de juiste Microsoft-eindpunten voor de hele wereld |30 dagen nadat de migratie is afgelopen, worden de Microsoft Cloud Deutschland-eindpunten gestopt met het honoreren van aanvragen. client- of toepassingsverkeer mislukt.  |
| Eindpunten van Azure AD-toepassingen bijwerken | U moet verificatie, Azure Active Directory (Azure AD) Graph en MS Graph-eindpunten voor uw toepassingen bijwerken naar die van de Microsoft Worldwide-service. | 30 dagen nadat de migratie is afgelopen, worden de Microsoft Cloud Deutschland-eindpunten gestopt met het honoreren van aanvragen. client- of toepassingsverkeer mislukt. |
||||

### <a name="azure-ad-connect"></a>Azure AD Connect
**Van toepassing op:** Alle klanten die identiteiten synchroniseren met Azure AD Connect

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk Azure AD Connect bij. | Nadat de cut over naar Azure AD is voltooid, maakt de organisatie volledig gebruik van Office 365-services en is ze niet meer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant ervoor zorgen dat het deltasynchronisatieproces is afgerond en daarna de tekenreekswaarde van `AzureInstance` 3 (Microsoft Cloud Deutschland) wijzigen in 0 in het `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registerpad. | Wijzig de waarde van `AzureInstance` de registersleutel. Als u dit niet doet, worden objecten niet gesynchroniseerd nadat de Microsoft Cloud Deutschland-eindpunten niet meer beschikbaar zijn. |
|||||

## <a name="post-migration"></a>Migratie na de migratie

Zorg ervoor dat u het [artikel postmigratieactiviteiten leest](ms-cloud-germany-transition-add-experience.md) en deze uitvoert.
