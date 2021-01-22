---
title: Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Overzicht: Informatie over de migratie van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 28344f1249e4f51bb9802bf19ca7561182610a7c
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921587"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's

> [!NOTE]
> Dit artikel is alleen van toepassing op in aanmerking komende klanten van Microsoft Cloud Deutschland.

In augustus 2018 heeft Microsoft laten weten dat we de volledige Microsoft-cloud (Azure, Office 365, Dynamics 365 en Power Platform) willen gaan aanbieden vanuit nieuwe cloudregio's in Duitsland om de digitale transformatie van onze klanten beter mogelijk te maken. In augustus 2019 hebben we aangekondigd dat we de nieuwe cloudregio's in Duitsland gaan openen. We hebben nu de beschikbaarheid van Azure, Office 365, Dynamics 365 en Power Platform aangekondigd.

De nieuwe regio's zijn ontworpen om in tespelen op de veranderende behoeften van Duitse klanten met meer flexibiliteit, de nieuwste intelligente cloudservices, volledige connectiviteit met ons Microsoft 365-services cloudnetwerk en opslag van klantgegevens in Duitsland.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Migreren naar de nieuwe Duitse datacentergebieden

Bestaande klanten van Microsoft Cloud Deutschland kunnen nu beginnen met het migreren van hun klanten van Office 365, Dynamics 365 Klantbetrokkenheid en Power Platform. De eerste stap is het gebruik van een migratie onder leiding van [Microsoft](https://aka.ms/office365germanymoveoptin) naar onze nieuwe Duitse datacenterregio's.

Organisaties die zich hebben gekozen voor de benadering op microsoft-gebied, beginnen naar verwachting begin 2021 en zijn voltooid op 29 oktober 2021. Als gevolg van de migratie worden belangrijke klantgegevens en -abonnementen verplaatst naar de nieuwe Duitse regio's.

Dit artikel bevat een overzicht van de op Microsoft gebaseerde benadering voor de migratie, duidelijkheid over de ervaringen voor zowel gebruikers als beheerders tijdens en na de migratie, en acties die mogelijk voor klanten vereist zijn op basis van welke werkbelasting u gebruikt.

De volgende services worden gemigreerd als onderdeel van de op Microsoft gebaseerde aanpak:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive voor Bedrijven

- Skype voor Bedrijven Online\*\*
- Office 365 Groepen
- Dynamics 365 / Power Platform\*\*\*

\*\*Tijdens de migratie van Microsoft Cloud Deutschland naar de Duitse datacenterregio's zullen bestaande klanten van Skype voor Bedrijven Online overstappen op Microsoft Teams. Zie [Aan de slag met uw upgrade naar Microsoft Teams](https://aka.ms/SkypeToTeams-Home) voor meer informatie.

\*\*\*Vereisten en gevolgen van migratie voor deze services worden beschreven in het artikel klantafspraak in [Dynamics 365.](https://aka.ms/d365ceoptin)

Office 365 Video wordt op 1 maart 2021 niet meer gebruikt. Als u ervoor kiest om uw Office 365-tenant te migreren naar de nieuwe Duitse datacentergebieden, wordt Office 365 Video niet ondersteund nadat de SharePoint Online-migratie is voltooid. Zie de tijdlijn in [Microsoft Cloud Deutschland voor meer informatie.](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Hoe wordt de migratie georganiseerd?

In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Deze fasen beginnen wanneer u [zich voor migratie hebt gekozen.](https://aka.ms/office365germanymoveoptin) De meeste migratiefasen worden uitgevoerd als back-endservicebewerkingen met minimale interactie met de klant en worden de ene fase na de andere uitgevoerd. De start van extra taken door de klant en de algemene migratiestatus worden tijdens het migratieproces gecommuniceerd via het berichtencentrum van het Microsoft 365-beheercentrum. Voorbeeld van taken zijn DNS-updates door de klant, de herconfiguratie van hybride configuratie voor hybride exchange-klanten of Azure-migratie.

De migratie start niet direct wanneer de opt-in plaatsvindt. Uw organisatie wordt toegevoegd aan de lijst met tenants die zijn gepland voor een latere migratie. U kunt nu beginnen met de fases vóór het werk, omdat deze essentieel zijn voor een succesvolle migratie en een goed gebruik na voltooiing:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra voorlopig werk](ms-cloud-germany-transition-add-pre-work.md)

Een week vóór het begin van de tenantmigratie ontvangt u in de service Berichtencentrum een laatste waarschuwing dat alle vereisten moeten zijn voltooid.

De migratie wordt van uw Azure AD-tenant verplaatst van de soevereine Azure AD-service van Duitsland naar het Office 365-services-exemplaar van Azure AD in de EU-regio.

De volgende fase is de migratie van uw tenant en&#39;en gebruikerslicenties van Producten in Duitsland naar globale producten.

Nadat alle stappen zijn voltooid, inclusief de Azure-migratie van de klant, wordt uw tenant voltooid in de Office 365-servicesservice en wordt de migratie als voltooid gemarkeerd. U ontvangt nu de definitieve update voor het berichtencentrum. De tenant is nu een volledig wereldwijde Office 365-organisatie.

U wordt op de hoogte gesteld van de voortgang van de migratie met berichten in het berichtencentrum. De berichten vinden plaats bij specifieke mijlpalen en geven richtlijnen bij de voortgang van een stap en belangrijke informatie waar klanten op moeten reageren op basis van de procesvereisten. Meldingen van het berichtencentrum worden weergegeven bij de volgende mijlpalen:

- Begin van de migratie (5 werkdagen voordat de Azure AD-migratie wordt gestart)
- Azure AD-migratie voltooid
- Migratie van abonnementen en licenties voltooid
- SharePoint-migratie voltooid
- Exchange-migratie voltooid
- Skype voor Bedrijven voltooid
- Dynamics complete
- Power BI voltooid
- Uiteindelijke cutover-services is voltooid

## <a name="moving-to-the-new-german-datacenter-regions"></a>Over land verplaatsen naar de nieuwe Regio's in het Duitse datacenter

Bestaande klanten van Microsoft Cloud Deutschland kunnen nu beginnen met het migreren van hun Office 365-, Dynamics 365-klantbetrokkenheid en Power Platform-services. De eerste stap is het gebruik van een migratie onder leiding van [Microsoft](https://aka.ms/office365germanymoveoptin) naar onze nieuwe Duitse datacenterregio's. Wanneer u uw abonnement verlengt, kunt u zich automatisch inschrijven voor een migratie met Microsoft-ondersteuning. Microsoft stelt de tenantbeheerders via e-mail en in het berichtencentrum van het Microsoft 365-beheercentrum op de hoogte wanneer dit is gebeurd. Als u het proces nu wilt starten, kunt u zich vandaag nog rechtstreeks [in](https://aka.ms/office365germanymoveoptin) het Microsoft 365-beheercentrum hebben. Migraties beginnen naar verwachting begin 2021 en zijn voltooid op 29 oktober 2021. 

Als gevolg van de migratie worden belangrijke klantgegevens en -abonnementen verplaatst naar de nieuwe Duitse datacenterregio's.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Voorbereidingen treffen voor de migratie naar Office 365-services in de nieuwe Duitse datacenterregio's

De eerste stap bestaat uit het melden van Microsoft, zodat we toestemming hebben om uw abonnement en gegevens te migreren van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's. Raadpleeg het [opt-inproces voor](https://aka.ms/office365germanymoveoptin) instructies en houd er rekening mee dat:

- Alle migrerende klanten moeten de verbinding met de Office 365 Services [Office 365-URL's](urls-and-ip-address-ranges.md)en IP-adressen controleren, waaronder de nieuwe Duitse datacenterregio's. Actie kan leiden tot een fout in de service en de client.
- Bekijk de lijst met [pre-workactiviteiten](ms-cloud-germany-transition-add-pre-work.md) om ervoor te zorgen dat uw organisatie goed op de hoogte is en voorbereid is op de wijzigingen.
- Lees de beschrijving van de Office 365-platformservice om te weten welke functies en services beschikbaar zijn voor uw organisatie na de migratie naar de Duitse regio.
- Proefabonnementen worden niet gemigreerd en de migratie van alle betaalde abonnementen wordt geblokkeerd. U moet proefabonnementen annuleren of naar betaalde abonnementen converteren voordat de migratie van start gaat.

## <a name="where-do-i-go-from-here"></a>Waar kan ik vanaf hier naartoe gaan?

Bekijk de volgende sectie met veelgestelde vragen.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="is-migration-required"></a>Is migratie vereist?

Microsoft biedt gratis office 365-tenantmigratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacentergebieden. Hoewel we u ten zeerste aanraden om te migreren naar de nieuwe Duitse datacenterregio's, zullen we de benodigde beveiligingsupdates blijven bieden voor de regio Microsoft Cloud Deutschland.

Office 365-services in de nieuwe Duitse datacenterregio's:

- Aanbieding concurrerende prijzen op de markt voor [Azure,](https://azure.microsoft.com/pricing/calculator/) [Office 365,](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) [Dynamics 365-klantbetrokkenheid](https://dynamics.microsoft.com/pricing/)en [Power BI.](https://powerbi.microsoft.com/pricing/)
- Zijn verbonden met het&#39;van Microsoft&#39;en bieden honderden netwerkrandsites, peeringlocaties en uitgangspunten om overal ter wereld een krachtige gebruikerservaring te leveren.
- Help u aan de lokale vereisten voor het opslaan van klantgegevens in Duitsland.
- Onze volledige globale cloudaanbieding met de nieuwste versies van onze services en nieuwe mogelijkheden, waaronder Microsoft Teams en Multi-Geo in Office 365, leveren. Vergelijk producten per regio voor [Azure,](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central) [Office 365](o365-data-locations.md)en [Dynamics 365.](https://docs.microsoft.com/dynamics365/get-started/availability)
- Bieden volledige functionaliteit, beveiliging op bedrijf niveau en uitgebreide functies om klanten te helpen voldoen aan nalevings- en regelgevingsvereisten.
- Zijn toegankelijk via bestaande contracten voor onlineservices.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Wat is de beschikbaarheid van de service tussen de verschillende Office 365-cloudserviceaanbiedingen?
<h2 id="serv-avail"></h2>

De volgende 15 services zijn beschikbaar in de CloudService voor Microsoft Cloud Deutschland. Er worden geen nieuwe services toegevoegd aan Microsoft Cloud Deutschland.

1. Exchange Online
2. Klanten-lockbox (Exchange Online)
3. Groepen (moderne groepen)
4. Delve-profiel
5. Exchange Online Protection
6. Defender voor Office 365
7. Advanced eDiscovery
8. Advance Data Governance
9. SharePoint Online
10. Klanten-lockbox (SharePoint Online)
11. OneDrive voor Bedrijven
12. Skype voor Bedrijven Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Er zijn momenteel 39 services beschikbaar als onderdeel van Office 365-services in de nieuwe Duitse datacenterregio's. Nieuwe functies en services zullen voortdurend consistent beschikbaar zijn met globale Office 365-services.

1. Exchange Online
2. Klanten-lockbox voor Exchange Online
3. Microsoft 365-groepen
4. Delve-profiel
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender voor Office 365
9. Advanced eDiscovery
10. Advanced Security Management
11. Informatiebescherming voor Office 365 
12. Advance Data Governance
13. SharePoint Online
14. Klanten-lockbox voor SharePoint Online
15. OneDrive voor Bedrijven
16. Microsoft Stream
17. Skype voor Bedrijven (wordt tijdens de migratie gemigreerd naar Microsoft Teams)
18. Cloud PBX
19. PSTN Conferencing
20. Bellen via PSTN
21. Microsoft Teams
22. Beheerrapporten/gebruiksrapporten
23. Webversie van Office
24. Planner
25. Sway
26. Microsoft 365-apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune en Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate voor Office 365
32. Virtuele Power-agenten voor Office 365
33. PowerApps voor Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Lijsten

### <a name="when-will-migration-happen"></a>Wanneer vindt de migratie plaatsvinden?

**Azure**

Als u alleen een Azure-klant bent, kunt u vandaag nog beginnen [met het](https://docs.microsoft.com/azure/germany/germany-migration-main) migreren van uw Azure-resources naar een andere regio. 

Als u Azure met Office 365, Dynamics 365 of Power BI hebt, moet u het migratieproces volgen om een succesvolle migratie van AzureAD te garanderen voordat u met de zelfgestuurde Azure-migratie begint. U moet de Azure-migratie voltooien voordat de service wordt afgesloten om uw Azure-werkbelasting te kunnen behouden met uw AzureAD- en Office 365-organisatie.

**Office 365**

[Vandaag kunt u zich hebben](https://aka.ms/office365germanymoveoptin) gekozen voor de migratie op Microsoft-gebaseerde migratie. Wanneer we klaar zijn om de migratie te starten, informeren we u via het berichtencentrum in het Microsoft 365-beheercentrum.

**Dynamics 365 en Power BI**

Nu al kiezen voor microsoft-migratie voor [Dynamics 365-klantbetrokkenheid](https://aka.ms/D365ceOptIn) en [Power BI.](https://aka.ms/PBIOptIn) Wanneer we klaar zijn om de migratie te starten, informeren we u via het berichtencentrum in het Microsoft 365-beheercentrum.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Verandert de prijs voor de Office 365-services die ik gebruik?

Ja. Prijzen in Microsoft&#39;globale cloudregio's (inclusief de nieuwe datacenterregio's) zijn over het algemeen lager.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Welke SKU's en licenties worden tijdens de migratie van het abonnement toegepast op mijn organisatie en gebruikers?

Tijdens de migratie van Microsoft Cloud Deutschland naar de Office 365-services worden de servicespecifieke SKU's van Duitsland vervangen door globale versies van dezelfde of vergelijkbare SKU. In de meeste gevallen is de SKU in Office 365-services hetzelfde, maar er zijn maar weinig vervangingen waar de SKU in Duitsland niet meer beschikbaar is in de Office 365-services. Als u de aan uw organisatie toegewezen SKU wilt bijwerken nadat de migratie is voltooid, neem dan contact op met de verkoper om de toegewezen services toe te voegen of te wijzigen.

| Microsoft Cloud Deutschland - Product SKU (DE) | Microsoft Cloud Global - Product SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Klanten-lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition - Additional Database Storage \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - Additional Database Storage (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - Additional Non-Production Instance \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - Additional Non-Production Instance (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL Services (EOA, EOP, DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (Abonnement 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (Abonnement 1) (EXCHANGESTANDARD) |
| Exchange Online (Abonnement 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (Abonnement 2) (EXCHANGEENTERPRISE) |
| Exchange Online Archiving voor Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving voor Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online Archiving voor Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving voor Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Instance (CRMINSTANCE) |
| Office 365 A1 voor \_ faculteitEN DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 voor onderwijsmedewerkers (STANDARDWOFFPACK \_ VOOR ONDERWIJSMEDEWERKERS) |
| Office 365 A1 voor \_ leerlingen/studenten DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 voor leerlingen en studenten (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance (INFORMATION \_ PROTECTION \_ COMPLIANCE) |
|Microsoft Defender voor Office 365 (Abonnement 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender voor Office 365 (Abonnement 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps voor Bedrijven (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 zonder ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 zonder ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Office 365 Extra Bestandsopslag (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus voor \_ faculteitEN DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus voor faculteiten (OFFICESUBSCRIPTION \_ FACULTEIT) |
| Office 365 ProPlus voor leerlingen en studenten \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus voor leerlingen en studenten (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive voor Bedrijven (Abonnement 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive voor Bedrijven (Abonnement 1) (WACONEDRIVESTANDARD) |
| OneDrive voor Bedrijven (Abonnement 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive voor Bedrijven (Abonnement 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro voor \_ faculteitEN DE (POWER \_ BI PRO FACULTY \_ \_ \_ DE) | Power BI Pro voor onderwijsmedewerkers (POWER \_ BI \_ PRO VOOR \_ ONDERWIJSMEDEWERKERS) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Project Plan 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (Plan 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (Abonnement 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (Plan 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (Abonnement 2) (SHAREPOINTENTERPRISE) |
| Skype voor Bedrijven Online (Abonnement 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype voor Bedrijven Online (Abonnement 1) \_ DE (MCOIMP \_ DE) | Skype voor Bedrijven Online (Abonnement 1) (MCOIMP) |
| Skype voor Bedrijven Online (Abonnement 2) \_ DE (MCOSTANDARD \_ DE) | Skype voor Bedrijven Online (Abonnement 2) (MCOSTANDARD) |
| Skype voor Bedrijven Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype voor Bedrijven Plus CAL (MCOPLUSCAL) |
| Visio Online Abonnement 1 voor \_ faculteitEN DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online Abonnement 1 voor faculteiten (VISIOONLINE \_ ABONNEMENT1 \_ FAC) |
| Visio Online Abonnement 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online Abonnement 1 (VISIOONLINE \_ ABONNEMENT1) |
| Visio Online Abonnement 2 voor \_ faculteiten DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online Abonnement 2 voor faculteiten (VISIOCLIENT \_ FACULTY) |
| Visio Online Abonnement 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online Abonnement 2 (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio-abonnement 1 \_ (VISIOONLINE-ABONNEMENT1) |
| Visio-abonnement 2 \_ DE (VISIOCLIENT \_ DE) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hoe krijg ik hulp van Microsoft om te migreren naar een nieuwe regio of ondersteuningsvragen te beantwoorden?

Als u vragen hebt, kunt u contact met ons opnemen of uw partner:

- Voor Azure kunt u nieuwe [ondersteuningsaanvragen indienen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) in de Azure Portal.
- Voor Office 365 kunt u vragen indienen via de koppeling Hulp &quot; nodig? &quot; van het Microsoft [365-beheercentrum.](https://portal.office.de/)
- Als u dynamics 365 klantbetrokkenheid en Power BI-klant bent en ook Office 365 hebt, kunt u vragen indienen via de koppeling Hulp nodig? van het &quot; &quot; Microsoft [365-beheercentrum.](https://portal.office.de/) Dynamics 365 Customer Engagement Support-opties bevinden zich [hier.](https://docs.microsoft.com/dynamics365/get-started/support/) Ondersteuningsopties voor Power BI bevinden zich [hier.](https://powerbi.microsoft.com/support/)


## <a name="next-step"></a>Volgende stap

[Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

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
