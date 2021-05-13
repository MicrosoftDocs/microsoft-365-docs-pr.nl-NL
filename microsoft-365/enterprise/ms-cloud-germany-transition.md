---
title: Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Samenvatting: Inzicht in de migratie van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: ad6c81f04b9e8551ad6eeb6521f7562243df53e9
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346302"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's

> [!NOTE]
> Dit artikel is alleen van toepassing op in aanmerking komende Klanten van Microsoft Cloud Deutschland.

In augustus 2018 heeft Microsoft aangekondigd dat we de volledige Microsoft-cloud ( Azure, Office 365, Dynamics 365 en Power Platform) willen leveren vanuit nieuwe cloudregio's in Duitsland om de digitale transformatie van onze klanten beter mogelijk te maken. In augustus 2019 hebben we aangekondigd dat we nu bezig zijn met het openen van de nieuwe cloudregio's in Duitsland. Sindsdien hebben we de beschikbaarheid van Azure, Office 365, Dynamics 365 en Power Platform aangekondigd.

De nieuwe regio's zijn ontworpen om te voldoen aan de veranderende behoeften van Duitse klanten met een grotere flexibiliteit, de nieuwste intelligente cloudservices en volledige connectiviteit met ons cloudnetwerk voor Microsoft 365-services en klantgegevens in Duitsland.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Migreren naar de nieuwe Duitse datacenterregio's

Bestaande Klanten van Microsoft Cloud Deutschland kunnen nu beginnen met het migreren van hun Office 365, Dynamics 365 Customer Engagement en Power Platform-klanten. De eerste stap is om [u aan te sluiten](./ms-cloud-germany-migration-opt-in.md) bij een migratie die door Microsoft wordt geleid naar onze nieuwe Duitse datacenterregio's.

Voor organisaties die zich hebben voor de microsoft-aanpak, wordt verwacht dat de migraties begin 2021 beginnen en op 29 oktober 2021 zijn voltooid. Als gevolg van de migratie worden de belangrijkste klantgegevens en -abonnementen verplaatst naar de nieuwe Duitse regio's.

In dit artikel vindt u een overzicht van de microsoft-aanpak voor de migratie, duidelijkheid over de ervaringen voor zowel gebruikers als beheerders tijdens en na de migratie, en acties die mogelijk vereist zijn voor klanten op basis van de werkbelasting die u gebruikt.

De volgende services worden gemigreerd als onderdeel van de microsoft-aanpak:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive voor Bedrijven
- Skype voor Bedrijven Online\*\*
- Office 365 Groepen
- Dynamics 365 / Power Platform\*\*\*

\*\*Tijdens de migratie van Microsoft Cloud Deutschland naar de Duitse datacenterregio's worden bestaande klanten Skype voor Bedrijven Online overstappen op Microsoft Teams. Zie [Aan de slag met uw Microsoft Teams upgrade](/microsoftteams/upgrade-start-here) voor meer informatie.

\*\*\*Vereisten en gevolgen van migratie voor deze services worden beschreven in het [artikel Klantafspraak dynamics 365.](/dynamics365/get-started/migrate-data-german-region)

Office 365 Video wordt op 1 maart 2021 niet meer gebruikt. Als u ervoor kiest om uw Office 365 te migreren naar de nieuwe Duitse datacenterregio's, wordt Office 365 Video niet ondersteund nadat de SharePoint Online-migratie is voltooid. Zie de tijdlijn van [Microsoft Cloud Deutschland](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)voor meer informatie.

## <a name="how-is-the-migration-organized"></a>Hoe wordt de migratie georganiseerd?

In deze afbeelding ziet u de tien fasen van de migratie naar de nieuwe Duitse datacenters.

![De tien fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Deze fasen beginnen wanneer [u zich aant voor migratie.](./ms-cloud-germany-migration-opt-in.md) De meeste migratiefasen worden uitgevoerd als back-endservicebewerkingen met minimale interactie tussen klanten en worden de ene fase na de andere uitgevoerd. Het begin van extra taken onder leiding van de klant en de algehele migratiestatus worden tijdens het migratieproces gecommuniceerd via het Berichtencentrum van het Microsoft 365 beheercentrum. Voorbeeld van taken: door klanten beheerde DNS-updates, herconfiguratie van hybride configuratie voor Exchange hybride klanten of Azure-migratie.

De migratie begint niet onmiddellijk wanneer de opt-in optreedt. Uw organisatie wordt toegevoegd aan de lijst met tenants die zijn gepland voor latere migratie. U kunt nu beginnen met de fasen vóór het werk, omdat deze essentieel zijn om ervoor te zorgen dat de migratie en het gebruik na voltooiing zijn voltooid:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)

Een week vóór het begin van de tenantmigratie ontvangt u een melding in de service Berichtcentrum als een laatste waarschuwing dat alle vereisten moeten zijn voltooid.

De migratie verplaatst uw Azure AD-tenant van de soevereine Azure AD-service van Duitsland naar het Office 365-services-exemplaar van Azure AD in de EU-regio.

De volgende fase is de migratie van uw tenant-&#39;en gebruikerslicenties van Duitsland-specifieke producten naar globale producten.

Nadat alle stappen zijn voltooid, inclusief de Azure-migratie van klanten, is uw tenant voltooid in de Office 365 servicesservice en is de migratie gemarkeerd als voltooid. Op dit moment wordt de laatste update naar het Berichtencentrum aan u geleverd. De tenant is nu een volledig globale Office 365 organisatie.

U wordt op de hoogte gesteld van de voortgang van de migratie met berichten in het berichtencentrum. De berichten vinden plaats op specifieke mijlpalen en bieden richtlijnen voor de voortgang van een stap en belangrijke informatie voor klanten om op te treden op basis van de procesvereisten. Berichtencentrummeldingen worden op de volgende mijlpalen weergegeven:

- Begin van de migratie (5 werkdagen voordat Azure AD-migratie begint)
- Azure AD-migratie voltooid
- Abonnements- en licentiemigratie voltooid
- SharePoint migratie voltooid
- Exchange migratie voltooid
- Skype voor Bedrijven voltooid
- Dynamics voltooid
- Power BI voltooid
- De laatste cutover van services is voltooid

Na de laatste cutover van Azure AD naar de wereldwijde service, wordt verwacht dat alle clients en toepassingen volledig worden overgeboekt om de juiste eindpunten te gebruiken. Er is een venster van 30 dagen na de laatste cutover waarin het mogelijk is om Azure AD-tokens te blijven verkrijgen bij de Microsoft Cloud Deutschland-service. Wanneer het venster van 30 dagen verloopt, hebben clients en toepassingen geen toegang meer tot de Azure AD-eindpunten van Microsoft Cloud Deutschland. Toepassingen of gebruikerstoegang mislukt vanaf dit punt. U moet ervoor zorgen dat alle gebruikers en toepassingen naar de juiste eindpunten worden gemigreerd voordat dit tijdvenster wordt gesloten. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Naar de nieuwe Duitse datacenterregio's gaan

Bestaande Klanten van Microsoft Cloud Deutschland kunnen nu beginnen met het migreren van hun Office 365, Dynamics 365 Customer Engagement en Power Platform-services. De eerste stap is om [u aan te sluiten](./ms-cloud-germany-migration-opt-in.md) bij een migratie die door Microsoft wordt geleid naar onze nieuwe Duitse datacenterregio's. Wanneer u uw abonnement verlengt, kiest u automatisch voor een door Microsoft ondersteunde migratie. Microsoft informeert tenantbeheerders van klanten via e-mail en in het berichtencentrum van het Microsoft 365-beheercentrum wanneer dit is gebeurd. Als u het proces echter liever nu [](./ms-cloud-germany-migration-opt-in.md) wilt starten, kunt u zich vandaag rechtstreeks in het Microsoft 365-beheercentrum. Migraties beginnen naar verwachting begin 2021 en zijn voltooid op 29 oktober 2021. 

Als gevolg van de migratie worden de belangrijkste klantgegevens en -abonnementen verplaatst naar de nieuwe Duitse datacenterregio's.

> [!NOTE]
> Dit artikel bevat richtlijnen voor de migratie van Office 365 services. Als u extra Azure-werkbelastingen gebruikt in Microsoft Cloud Deutschland, bekijkt u de [migratie-richtlijnen voor Azure Germany.](/azure/germany/germany-migration-main)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Voorbereidingen treffen voor migratie naar Office 365 services in de nieuwe Duitse datacenterregio's

De eerste stap is om Microsoft op de hoogte te stellen, zodat we uw toestemming hebben om uw abonnement en gegevens te migreren van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's. Raadpleeg het [opt-inproces voor](./ms-cloud-germany-migration-opt-in.md) instructies en houd er rekening mee dat:

- Alle migrerende klanten moeten de verbinding met de Office 365 Services [Office 365 URL's](urls-and-ip-address-ranges.md)en IP-adressen controleren, waaronder de nieuwe Duitse datacenterregio's. Inactiviteit kan leiden tot service- en clientfout.
- Bekijk de lijst met [activiteiten vóór](ms-cloud-germany-transition-add-pre-work.md) het werk om ervoor te zorgen dat uw organisatie op de hoogte is en voorbereid op de wijzigingen.
- Bekijk de beschrijving van Office 365 platformservice om te begrijpen welke functies en services beschikbaar komen voor uw organisatie na de migratie naar de Duitse regio.
- Proefabonnementen worden niet gemigreerd en blokkeren de migratie van alle betaalde abonnementen. U moet proefabonnementen annuleren of converteren naar betaalde abonnementen voordat de migratie begint.

## <a name="where-do-i-go-from-here"></a>Waar ga ik vandaan?

Bekijk de volgende sectie Veelgestelde vragen.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="is-migration-required"></a>Is migratie vereist?

Microsoft biedt Office 365 tenantmigratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's zonder extra kosten. Hoewel we u ten zeerste adviseren om te migreren naar de nieuwe Duitse datacenterregio's, blijven we de benodigde beveiligingsupdates leveren voor de Microsoft Cloud Deutschland-regio.

Office 365 services in de nieuwe Duitse datacenterregio's:

- Marktconforme prijzen bieden voor [Azure,](https://azure.microsoft.com/pricing/calculator/) [Office 365,](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)en [Power BI.](https://powerbi.microsoft.com/pricing/)
- Zijn verbonden met&#39;wereldwijde netwerk van Microsoft en bieden honderden netwerkrandsites, peeringlocaties en uitgangspunten om overal ter wereld een krachtige gebruikerservaring te bieden.
- U helpen te voldoen aan lokale vereisten voor klantgegevens in Duitsland.
- Lever ons volledige globale cloudaanbod met de nieuwste versies van onze services en nieuwe mogelijkheden, waaronder Microsoft Teams en Multi-Geo in Office 365. Vergelijk producten per regio voor [Azure,](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central) [Office 365](o365-data-locations.md)en [Dynamics 365.](/dynamics365/get-started/availability)
- Biedt volledige functionaliteit, beveiliging van ondernemingskwaliteit en uitgebreide functies om klanten te helpen voldoen aan de nalevings- en regelgevingsvereisten.
- Zijn toegankelijk via bestaande onlineservicescontracten.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Wat is de beschikbaarheid van de service tussen de verschillende Office 365 cloudserviceaanbiedingen?
<h2 id="serv-avail"></h2>

De volgende 15 services zijn beschikbaar in de cloudservice van Microsoft Cloud Deutschland. We voegen geen nieuwe services toe aan Microsoft Cloud Deutschland.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Groepen (moderne groepen)
4. Delve Profiel
5. Exchange Online Protection
6. Defender voor Office 365
7. Advanced eDiscovery
8. Gegevensbeheer vooraf
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. OneDrive voor Bedrijven
12. Skype voor Bedrijven Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Er zijn momenteel 39 services beschikbaar als onderdeel van Office 365 services in de nieuwe Duitse datacenterregio's. Nieuwe functies en services zijn voortdurend beschikbaar in overeenstemming met Office 365 services.

1. Exchange Online
2. Klanten lockbox voor Exchange Online
3. Microsoft 365-groepen
4. Delve Profiel
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender voor Office 365
9. Advanced eDiscovery
10. Geavanceerd beveiligingsbeheer
11. Informatiebeveiliging voor Office 365 
12. Gegevensbeheer vooraf
13. SharePoint Online
14. Customer Lockbox voor SharePoint Online
15. OneDrive voor Bedrijven
16. Microsoft Stream
17. Skype voor Bedrijven (wordt gemigreerd naar Microsoft Teams tijdens de migratie)
18. Cloud PBX
19. PSTN-conferencing
20. BELLEN via PSTN
21. Microsoft Teams
22. Beheerdersrapporten/gebruiksrapporten
23. Webversie van Office
24. Planner
25. Sway
26. Microsoft 365-apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune en Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate voor Office 365
32. Power Virtual Agents voor Office 365
33. PowerApps voor Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Lijsten

### <a name="when-will-migration-happen"></a>Wanneer wordt de migratie gemaakt?

**Azure**

Als u alleen een Azure-klant [](/azure/germany/germany-migration-main) bent, kunt u vandaag beginnen met het migreren van uw Azure-resources naar een andere regio. 

Als u Azure hebt met Office 365, Dynamics 365 of Power BI, moet u het migratieproces volgen om een succesvolle migratie van AzureAD te garanderen voordat u begint met de self-directed Azure-migratie. U moet de Azure-migratie vóór de sluiting van de service voltooien om uw Azure-werkbelastingen te behouden met uw AzureAD en Office 365 organisatie.

**Office 365**

[Kies vandaag nog voor](./ms-cloud-germany-migration-opt-in.md) de microsoft-migratie. Wanneer we klaar zijn om uw migratie te starten, informeren we u via het Berichtencentrum in het Microsoft 365 beheercentrum.

**Dynamics 365 en Power BI**

Opt-in voor de microsoft-migratie voor [Dynamics 365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) [en Power BI](/power-bi/admin/service-admin-migrate-data-germany) vandaag. Wanneer we klaar zijn om uw migratie te starten, informeren we u via het Berichtencentrum in het Microsoft 365 beheercentrum.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Verandert de prijs voor de Office 365 services die ik gebruik?

Ja. De prijzen in de&#39;globale cloudregio's van Microsoft (inclusief de nieuwe datacenterregio's) zijn over het algemeen lager.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Welke SKU's en licenties worden tijdens de migratie van het abonnement toegepast op mijn organisatie en gebruikers?

Tijdens de migratie van Microsoft Cloud Deutschland naar de Office 365 services, worden de servicespecifieke SKU's in Duitsland vervangen door globale versies van dezelfde of soortgelijke SKU. In de meeste gevallen is de SKU in Office 365-services hetzelfde, maar er zijn weinig vervangingen waarbij de SKU in Duitsland niet meer beschikbaar is in de Office 365 services. Als u de SKU wilt bijwerken die aan uw organisatie is toegewezen nadat de migratie is voltooid, neem dan contact op met de verkoper om de toegewezen services toe te voegen of te wijzigen.

| Microsoft Cloud Deutschland - Product SKU (DE) | Microsoft Cloud Global - Product SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Klanten lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition - Extra database Storage \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - Extra database Storage (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - Additional Non-Production Instance \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - Extra exemplaar niet-productie (CRMTESTINSTANCE) |
| Dynamics 365 voor Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 voor teamleden Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 voor teamleden Enterprise Edition (DYN365 \_ ENTERPRISE \_ \_ TEAMLEDEN) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_ECAL-services (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE) | ECAL-services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| \_Enterprise Mobility + Security E3 DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (Abonnement 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online (Abonnement 1) (EXCHANGESTANDARD) |
| \_Exchange Online (Abonnement 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (Abonnement 2) (EXCHANGEENTERPRISE) |
| \_Exchange Online Archiving voor Exchange Online DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving voor Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| \_Exchange Online Archiving voor Exchange Server DE (EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving voor Exchange Server (EXCHANGEARCHIVEREN) |
| \_Exchange Online Essentials DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| \_Exchange Online Kiosk DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| \_Exchange Online Protection DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Exemplaar (CRMINSTANCE) |
| Office 365 A1 voor faculteit \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 voor faculteiten (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 voor studenten \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 voor studenten (STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced Compliance DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance (NALEVING \_ VAN \_ GEGEVENSBESCHERMING) |
|Microsoft Defender voor Office 365 (Plan 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender voor Office 365 (Plan 1) (ATP \_ ENTERPRISE) |
| \_Office 365 Business Essentials DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| \_Office 365 Business Premium DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| \_Office 365 Business DE (O365 \_ BUSINESS \_ DE) | Microsoft 365-apps voor bedrijven (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 zonder ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 zonder ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| \_Office 365 Extra Bestandsopslag DE (SHAREPOINTSTORAGE \_ DE) | Office 365 Extra Bestandsopslag (SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus voor Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus voor faculteiten (FACULTEIT \_ OFFICESUBSCRIPTION) |
| Office 365 ProPlus voor Studenten \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus voor studenten (OFFICESUBSCRIPTION \_ STUDENT) |
| \_Office 365 ProPlus DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| \_OneDrive voor Bedrijven (Abonnement 1) DE (WACONEDRIVESTANDARD \_ DE) | OneDrive voor Bedrijven (Abonnement 1) (WACONEDRIVESTANDARD) |
| \_OneDrive voor Bedrijven (Abonnement 2) DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive voor Bedrijven (Abonnement 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro voor faculteit \_ DE (POWER \_ BI PRO \_ FACULTY \_ \_ DE) | Power BI Pro voor faculteiten (POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI Pro DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| \_Project Online Essentials DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| \_Project Online Premium DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| \_Project Online Professional DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| \_Project Abonnement 3 DE (PROJECTPROFESSIONAL \_ DE) | Project Abonnement 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (Abonnement 1) DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (Abonnement 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (Abonnement 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (Abonnement 2) (SHAREPOINTENTERPRISE) |
| Skype voor Bedrijven Online (Plan 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype voor Bedrijven Online (Plan 1) \_ DE (MCOIMP \_ DE) | Skype voor Bedrijven Online (Plan 1) (MCOIMP) |
| Skype voor Bedrijven Online (Plan 2) \_ DE (MCOSTANDARD \_ DE) | Skype voor Bedrijven Online (Plan 2) (MCOSTANDARD) |
| Skype voor Bedrijven Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype voor Bedrijven Plus CAL (MCOPLUSCAL) |
| Visio Onlineplan 1 voor faculteit \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Onlineplan 1 voor onderwijsmedewerkers (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online abonnement 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online abonnement 1 (VISIOONLINE \_ PLAN1) |
| Visio Onlineplan 2 voor faculteit \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Onlineplan 2 voor onderwijsmedewerkers (VISIOCLIENT \_ FACULTY) |
| Visio Onlineplan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online abonnement 2 (VISIOCLIENT) |
| \_Visio Abonnement 1 DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Abonnement 1 (VISIOONLINE \_ PLAN1) |
| \_Visio Abonnement 2 DE (VISIOCLIENT \_ DE) | Visio Abonnement 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hoe krijg ik hulp van Microsoft om te migreren naar een nieuwe regio of om ondersteuningsvragen te beantwoorden?

Als u vragen hebt, kunt u contact opnemen met ons of uw partner:

- Voor Azure kunt u nieuwe [ondersteuningsaanvragen indienen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) in de Azure-portal.
- Voor Office 365 kunt u vragen indienen via de koppeling Hulp &quot; nodig? &quot; van het Microsoft 365 [beheercentrum.](https://portal.office.de/)
- Als u Dynamics 365 Customer Engagement en Power BI klant bent en ook Office 365 hebt, kunt u vragen indienen via de koppeling Hulp nodig? van het &quot; &quot; [Microsoft 365-beheercentrum.](https://portal.office.de/) De ondersteuningsopties voor Dynamics 365 Customer Engagement bevinden zich [hier.](/dynamics365/get-started/support/) Power BI ondersteuningsopties bevinden zich [hier.](https://powerbi.microsoft.com/support/)

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Mijn klant heeft al een M365-tenant in de globale Microsoft-cloud, naast een Microsoft Cloud Deutschland-tenant. Kunnen deze twee tenants worden samengevoegd tot één als onderdeel van de migratie?

Nee, er is geen mogelijkheid voor tenant samenvoegen. Tenants blijven afzonderlijk en uniek omdat elke tenant een eigen naamruimte en unieke id heeft. Microsoft migreert desgewenst een Microsoft Cloud Deutschland-tenant naar de globale cloud, anders kan de klant deze annuleren en verlaten.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Welke acties moeten de meeste eindgebruikers uitvoeren als onderdeel van de migratie?
De migratie is ontworpen om minimale gevolgen te hebben voor eindgebruikers/klanten.
- Controleer of Office de meest recente beschikbare versies worden uitgevoerd. 
- Klanten die Skype voor Bedrijven zullen overstappen op Teams als onderdeel van de migratie en moeten mogelijk de Teams op apparaten downloaden [en](/deployoffice/teams-install) installeren.
- Eindgebruikers moeten zich mogelijk afmelden bij de Office en zich opnieuw aanmelden wanneer de migratie is voltooid. 
- Klanten met de OneDrive-synchronisatieclient moeten zich afmelden bij hun werkstation en zich opnieuw aanmelden, zodat OneDrive Sync-client zich kan aanmelden bij de globale Azure Active Directory-service.
- Wees op de hoogte van nieuwe algemene URL's zodra de migratie is voltooid, met name Outlook Web Access (bijvoorbeeld: gebruik outlook.office365.com). SharePoint Online clients blijven met succes verbinding maken met de MCD-naamruimte met behulp van de bestaande URL (bijvoorbeeld: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Welke klanten worden beïnvloed door de Azure Active Directory migratie? 

Alle klanten van Office365 zijn afhankelijk van Azure Active Directory voor het verifiëren en opslaan van essentiële serviceonderdelen die nodig zijn voor de werking van gehoste microsoft-services. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Wat zijn de gevolgen van de Azure Active Directory migratie?

De eerste migratie van Azure Active Directory in de beginfase heeft geen invloed op de klantervaring. Na de laatste migratiefase zijn alle services voor de klant tenant volledig in de globale service. Na deze laatste fase kan Azure Active Directory service in Microsoft Cloud Deutschland geen autorisatieaanvragen meer accepteren of toegangstokens verstrekken voor Office services.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Wat betekent het om ervoor te zorgen dat netwerkconnectiviteit wordt [Office 365 services-URL's en IP-adressen?](./urls-and-ip-address-ranges.md)

In dit artikel worden de benodigde URL's en IP-adressen beschreven die nodig zijn voor de juiste functie van de globale service om een goede klantervaring te garanderen. In relatief zeldzame gevallen proberen sommige klanten de beveiliging van de netwerkperimeter zo te configureren dat verkeersstromen worden geminimaliseerd en de toegang tot services beperkt is tot services die alleen worden gebruikt als onderdeel van het IP-bereik van de Microsoft Cloud Deutschland-service.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Hoe beheer ik de DNS-wijzigingen voor Exchange Online zodat e-mail blijft stromen?

Door Microsoft beheerde IP-bereik en DNS-zones worden tijdens en als onderdeel van de migratie naar de globale service overgestappen. 

Door klanten beheerde DNS-zones, zoals aangepaste domein MX-records, zijn echter de verantwoordelijkheid van de klant om deze migratie te vereenvoudigen. De door de klant beheerde MX-record wijst naar een Office 365-service-eindpunt in de office.de-zone en Microsoft beheert de migratie van dit service-eindpunt automatisch.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Hoe beheer ik de DNS-wijzigingen voor Skype voor Bedrijven? 
 
Alle Skype Voor Bedrijven-klanten in worden over Microsoft Teams. De overgang van Skype DNS-zones is niet vereist in de migratie naar Teams. Klanten kunnen zich direct aanmelden bij Teams met alle functionaliteit na de migratie.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Werken Outlook voor iOS en Android na de migratie? 

Ja. De aanbeveling van Microsoft is dat alle klanten de nieuwste beschikbare versies van Office-clients uitvoeren, Outlook voor iOS- en Android-clients. Nadat de migratie naar de globale Office 365-service is voltooid, moeten alle Office-clients zich afmelden en zich opnieuw aanmelden om een nieuw Azure Active Directory-toegangs token te verkrijgen van de globale service. 



## <a name="next-step"></a>Volgende stap

[Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Power BI migratieprogrammagegevens](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams upgrade](/microsoftteams/upgrade-start-here)
