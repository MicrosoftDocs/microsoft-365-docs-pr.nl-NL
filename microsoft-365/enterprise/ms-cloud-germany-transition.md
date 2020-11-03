---
title: Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
description: 'Overzicht: informatie over de migratie van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 23ccc30bab5d1045e4716cd637899e20362fc597
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846938"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden

> [!NOTE]
> Dit artikel geldt alleen voor in aanmerking komende klanten van Microsoft Cloud Deutschland.

In augustus 2018 heeft Microsoft ons bedoeld voor de levering van de volledige Microsoft Cloud – Azure, Office 365, Dynamics 365 en Power platform – van nieuwe Cloud regio's in Duitsland, zodat u de digitale transformatie van onze klanten beter kunt inschakelen. In augustus 2019 hebben we ons nu geaangekondigd de nieuwe Cloud regio's in Duitsland te openen. We hebben nu de beschikbaarheid van Azure, Office 365, Dynamics 365 en Power platform aangekondigd.

De nieuwe regio's zijn ontworpen om de geprojecteerde behoeften van Duitse klanten met meer flexibeler, de nieuwste intelligente cloudservices en volledige connectiviteit met ons Microsoft 365-Service Cloud netwerk en de klantgegevens woonplaats in Duitsland te beantwoorden.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Migreren naar de nieuwe Duitse regio's

Bestaande Microsoft Cloud Deutschland klanten kunnen nu beginnen met het migreren van hun Office 365-, Dynamics 365-klant afspraken en Power platform-klanten. De eerste stap is om u aan te [melden bij een Microsoft-led's-migratie naar de](https://aka.ms/office365germanymoveoptin) nieuwe Duitse datacenter regio's.

Voor organisaties die zich aanmelden bij de door Microsoft gerichte aanpak, worden de migraties verwacht in eerste 2021 en zullen ze vóór 29 oktober 2021 worden voltooid. Als gevolg van de migratie worden de kerngegevens en abonnementen van klanten naar de nieuwe Duitse regio's verplaatst.

Dit artikel bevat een overzicht van de door Microsoft gerichte aanpak voor de migratie, de duidelijkheid over de ervaringen van gebruikers en beheerders tijdens en na de migratie, en acties die mogelijk zijn vereist voor klanten op basis van de werkbelasting die u gebruikt.

De volgende services worden gemigreerd als onderdeel van de door Microsoft gerichte aanpak:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive voor Bedrijven

- Skype voor bedrijven online\*\*
- Office 365 Groepen
- Dynamics 365/Power platform\*\*\*

\*\*Tijdens de migratie van Microsoft Cloud Deutschland naar de Duitse datacenter gebieden, zullen bestaande Skype voor bedrijven online-klanten overstappen op Microsoft teams. Zie [aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home) voor meer informatie.

\*\*\*De vereisten en gevolgen van de migratie voor deze services worden beschreven in het artikel over de [klant afspraken voor Dynamics 365](https://aka.ms/d365ceoptin) .

Office 365-video wordt op 1 maart 2021 verouderd. Als u ervoor kiest om uw Office 365-Tenant te migreren naar de nieuwe Duitse datacenter gebieden, wordt de video van Office 365 niet ondersteund na voltooiing van de SharePoint Online-migratie. Klik [hier](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) voor meer informatie.

## <a name="how-is-the-migration-organized"></a>Hoe wordt de migratie geordend?

Dit cijfer staat voor de verschillende onderdelen van Office 365 en Dynamics 365 in de migratie naar de nieuwe Duitse datacenters.

![Onderdelen van Office 365 en Dynamics 365 in de migratie naar de nieuwe Duitsland-datacenters](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

De migratie wordt uitgevoerd in fasen die allemaal beginnen wanneer u zich [aanmeldt voor migratie](https://aka.ms/office365germanymoveoptin). De meeste migratie fasen worden uitgevoerd als back-end-servicebewerkingen waarbij minimaal een klant interactie vereist is en één fase achter de andere fase wordt uitgevoerd. Het begin voor extra taken met betrekking tot de klant en migratiestatus wordt tijdens het migratieproces via het berichtencentrum van het Microsoft 365-Beheercentrum gecommuniceerd. Voorbeeld van taken zijn mogelijk DNS-updates van klanten die door de klant worden beheerd, opnieuw configureren van hybride configuratie voor Exchange hybride klanten of Azure-migratie.

De migratie begint niet meteen wanneer u zich kunt aanmelden. Uw organisatie wordt toegevoegd aan de lijst met tenants die zijn gepland voor toekomstige migratie. U kunt nu aan de voor-werk fasen beginnen als deze essentieel zijn om na voltooiing van de migratie te zorgen voor optimale migratie.

Een week vóór het begin van de Tenant migratie ontvangt u een melding in de berichtencentrum-service als laatste waarschuwing dat u alle vereisten moet voltooien.

De migratie gaat naar het Office 365-service-exemplaar van Azure AD in de EU-regio van de soevereine Duitsland Azure AD-service.

De volgende fase is de migratie van uw Tenant&#39;s-abonnementen en gebruikerslicenties van Duitsland-specifieke producten.

Wanneer alle stappen zijn voltooid, waaronder de Azure-migratie van de klant, is de Tenant voltooid in de Office 365-service en wordt de migratie als voltooid gemarkeerd. Op dit moment wordt de laatste update naar het berichtencentrum geleverd. De Tenant is nu geen volledig algemene Office 365-organisatie.

U wordt op de hoogte gesteld van de voortgang van de migratie met berichten in het berichtencentrum. De berichten treden op in bepaalde mijlpalen en bieden richtlijnen voor het uitvoeren van een stap en belangrijke informatie voor klanten die op basis van de proces vereisten handelen. Berichten in het berichtencentrum worden de volgende mijlpalen geboden:

- Start van migratie (5 werkdagen voordat Azure AD-migratie begint)
- Azure AD-Migratie voltooid
- Abonnement en licentie migratie is voltooid
- SharePoint-migratie voltooid
- Migratie van Exchange voltooid
- Skype voor bedrijven voltooien
- Dynamics voltooid
- Power BI voltooien
- Laatste cutover van Services is voltooid

## <a name="moving-to-the-new-german-regions"></a>Verplaatsen naar de nieuwe Duitse regio's

Bestaande klanten met Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) kunnen nu beginnen met het migreren van hun Office 365-, Dynamics 365-klant afspraken en Power platform-klanten. De eerste stap is om u aan te [melden bij een Microsoft-led's-migratie naar de](https://aka.ms/office365germanymoveoptin) nieuwe Duitse datacenter regio's. Wanneer u uw abonnement verlengt, wordt u automatisch aangemeld voor een Microsoft-assistieve migratie. Microsoft waarschuwt tenantbeheerders van klanten via e-mail en in het berichtencentrum van het Microsoft 365-Beheercentrum, wanneer dit is gebeurd. Als u het proces nu wilt starten [, kunt u zich op elk](https://aka.ms/office365germanymoveoptin) moment rechtstreeks aanmelden bij het Beheercentrum van microsoft 365. Migraties worden verwacht in eerste 2021 en worden voltooid vóór 29 oktober 2021. 

Als gevolg van de migratie worden de kerngegevens en abonnementen van klanten naar de nieuwe Duitse regio's verplaatst.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Voorbereidingen treffen voor de migratie naar Office 365-Services in de nieuwe Duitse datacenter gebieden

U wordt aangeraden om Microsoft te laten weten dat we uw toestemming hebben voor het migreren van uw abonnement en gegevens van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter regio's. Raadpleeg het [aanmeldingsproces](https://aka.ms/office365germanymoveoptin) voor instructies en Let op:

- Alle migratende klanten moeten de verbinding met de Office [365-url's en IP-adressen](urls-and-ip-address-ranges.md)van Office 365-Services, waaronder de nieuwe Duitse datacenter gebieden, zijn geverifieerd. Inactief kan leiden tot service-en clientfout.
- U moet de servicebeschrijving van het Office 365-platform nakijken om te begrijpen welke functies en services beschikbaar zijn voor uw organisatie na de migratie naar de Duitse regio.
- Proefabonnementen worden niet gemigreerd en zullen de migratie van alle betaalde abonnementen blokkeren. U dient alle proefversies te annuleren of te converteren naar betaalde abonnementen voordat de migratie begint.

## <a name="where-do-i-go-from-here"></a>Waar ga ik van hieruit vinden?

Bekijk de volgende veelgestelde vragen.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="is-migration-required"></a>Is migratie vereist?

Microsoft biedt geen extra kosten voor de Tenant migratie van Office 365 van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden. We raden u ten zeerste aan om u aan te melden voor het nieuwe Duitse datacenter gebied, en de benodigde beveiligingsupdates worden nu weergegeven voor de regio Microsoft Cloud Deutschland.

Office 365-Services in de nieuwe Duitse datacenter gebieden:

- Voor de concurrerende prijzen bieden [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 klant afspraak](https://dynamics.microsoft.com/pricing/)en [Power bi](https://powerbi.microsoft.com/pricing/).
- Is verbonden met het wereldwijde netwerk van Microsoft&#39;s, met honderden netwerk Edge-sites, peering locaties en uitgangspunten, zodat u overal ter wereld een krachtige gebruikerservaring kunt bieden.
- U kunt aan de woonplaats vereisten voor lokale klanten in Duitsland voldoen.
- Laat onze wereldwijde mondiale Cloud aanbieding met de nieuwste versies van onze services en nieuwe mogelijkheden, waaronder Microsoft teams en meerdere geografische functies, in Office 365. Vergelijk producten per regio voor [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)en [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- U kunt alle functies, beveiliging van uw organisatie en uitgebreide functies aanbieden om klanten te helpen aan nalevings-en regelgeving te voldoen.
- Zijn toegankelijk via bestaande contracten voor Online Services.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>De beschikbaarheid van de service voor cloudservice aanbiedingen van Office 365

De volgende 15 Services zijn beschikbaar in de cloudservice van Microsoft Cloud Deutschland. We kunnen geen nieuwe services toevoegen aan Microsoft Cloud Deutschland.

1. Exchange Online
2. Klant-lockbox (Exchange Online)
3. Groepen (moderne groepen)
4. Delve-profiel
5. Exchange Online Protection
6. Defender voor Office 365
7. Advanced eDiscovery
8. Voorschot gegevensbeheer
9. SharePoint Online
10. Klant-lockbox (SharePoint Online)
11. OneDrive voor Bedrijven
12. Skype voor Bedrijven Online
13. Word online, Excel online, PowerPoint, OneNote, Visio online
14. Office 365 Pro Plus
15. Outlook Mobile

Er zijn momenteel 29 services beschikbaar als onderdeel van Office 365-Services in de nieuwe Duitse datacenter regio's. Nieuwe functies en services zijn continu consistent met de wereldwijde Office 365-Services.

1. Exchange Online
2. Customer lockbox voor Exchange Online
3. Microsoft 365-groepen
4. Delve-profiel
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender voor Office 365
9. Advanced eDiscovery
10. Geavanceerd beveiligingsbeheer
11. Information Rights Management
12. Voorschot gegevensbeheer
13. SharePoint Online
14. Klanten-lockbox voor SharePoint Online
15. OneDrive voor Bedrijven
16. Microsoft Stream
17. Skype voor bedrijven (wordt tijdens de migratie naar Microsoft teams gemigreerd)
18. Cloud-PBX
19. Vergaderen via PSTN
20. Bellen via PSTN
21. Microsoft Teams
22. Beheerders rapporten/gebruiksrapporten
23. Word online, Excel online, PowerPoint, OneNote en Visio online
24. Planner
25. Sway
26. Microsoft 365-apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, intune en Rights Management service)
29. Yammer online

### <a name="when-will-migration-happen"></a>Wanneer gebeurt er een migratie?

**Azure**

Als u alleen een Azure-klant bent, kunt u vandaag nog beginnen met het [migreren](https://docs.microsoft.com/azure/germany/germany-migration-main) van uw Azure-bronnen naar een andere regio. Als u over Azure met Office 365, Dynamics 365 of Power BI beschikt, volgt u de onderstaande stappen.

**Office 365**

[Opt-in](https://aka.ms/office365germanymoveoptin) voor de Microsoft-gerichte migratie vandaag. Wanneer u klaar bent om de migratie te starten, wordt u via het berichtencentrum op de hoogte gesteld van het Microsoft 365-Beheercentrum.

**Dynamics 365 en Power BI**

Opt-in voor de door Microsoft gerichte migratie voor [Dynamics 365 klant afspraak](https://aka.ms/D365ceOptIn) en [Power bi](https://aka.ms/PBIOptIn) vandaag. Wanneer u klaar bent om de migratie te starten, wordt u via het berichtencentrum op de hoogte gesteld van het Microsoft 365-Beheercentrum.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Wordt de prijswijziging voor de Office 365-services die ik gebruik?

Ja. Prijzen in Microsoft&#39;s globale Cloud regio's (waaronder de nieuwe datacenter gebieden), is in het algemeen lager.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Welke Sku's en licenties worden tijdens de migratie van een abonnement op mijn organisatie en gebruikers toegepast?

Tijdens de migratie van Microsoft Cloud Deutschland naar Office 365-Services, worden de service-specifieke Sku's van Duitsland vervangen door globale versies van dezelfde of dezelfde SKU. Voor de meeste zaken is de SKU in Office 365-Services hetzelfde, maar er zijn slechts enkele vervangingen waarbij de SKU in Duitsland niet langer beschikbaar is in de Office 365-Services. Als u de SKU die is toegewezen aan uw organisatie wilt bijwerken nadat de migratie is voltooid, kunt u contact opnemen met de verkoper om de toegewezen services toe te voegen of te wijzigen.

| Microsoft Cloud Deutschland-product SKU (nl) | Globale Microsoft Cloud-product SKU (WW) |
| --- | --- |
| Klanten \_ -lockbox de (lockbox \_ -de) | Klanten-lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition-extra database opslag \_ de (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-extra opslagruimte voor database (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-extra niet-productie \_ -exemplaren de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition-extra non-producerend exemplaar (CRMTESTINSTANCE) |
| Dynamics 365 voor klantenservice Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ service \_ ) | Dynamics 365 voor Customer service Enterprise Edition (DYN365 \_ Enterprise \_ Customer \_ Service) |
| Dynamics 365 voor verkoop Enterprise Edition \_ de (DYN365 \_ Enterprise \_ sales verkoop \_ , de) | Dynamics 365 voor verkoop Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 voor team leden, Enterprise Edition \_ de (DYN365 \_ Enterprise \_ team \_ leden \_ de) | Dynamics 365 voor team leden Enterprise Edition (DYN365 \_ Enterprise \_ team \_ -leden) |
| Dynamics 365 abonnement 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 abonnement 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| ECAL diensten (EOA, EOP, DLP) \_ de (ECAL \_ diensten \_ de) | ECAL diensten (EOA, EOP, DLP) (ECAL \_ -Services) |
| Enterprise Mobility + beveiligings E3 \_ de (EMS \_ -nl) | Enterprise Mobility + beveiligings E3 (EMS) |
| Exchange Online (abonnement 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (abonnement 1) (EXCHANGESTANDARD) |
| Exchange Online (abonnement 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (abonnement 2) (EXCHANGEENTERPRISE) |
| Exchange Online Archiving voor Exchange Online \_ de EXCHANGEARCHIVE- \_ invoegtoepassing \_ de | Exchange Online Archiving voor Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online Archiving voor Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Exchange Online Archiving voor Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ S \_ Essentials) |
| Exchange Online kiosk \_ de (EXCHANGEDESKLESS \_ de) | Exchange Online kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ de (EOP \_ Enterprise \_ de) | Exchange Online Protection (EOP \_ Enterprise) |
| Microsoft 365 Business Standard (O365 \_ Business \_ Premium) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Microsoft Dynamics CRM Online-exemplaar \_ de (CRMINSTANCE \_ de) | Microsoft Dynamics CRM Online-exemplaar (CRMINSTANCE) |
| Office 365 a1 voor faculteiten \_ de ( \_ STANDARDWOFFPACK \_ -faculteit de) | Office 365 a1 voor faculteiten (STANDARDWOFFPACK \_ -faculteit) |
| Office 365 a1 voor studenten en \_ de STANDARDWOFFPACK \_ leerling/student \_ de | Office 365 a1 voor studenten (STANDARDWOFFPACK \_ leerling) |
| Office 365 Advanced compliance \_ de (EQUIVIO \_ Analytics \_ de) | Naleving van Microsoft 365 E5 (naleving van informatie \_ bescherming \_ ) |
|Microsoft Defender voor Office 365 (abonnement 1) \_ de (ATP \_ Enterprise \_ de) |Microsoft Defender voor Office 365 (abonnement 1) (ATP \_ Enterprise) |
| Office 365 Business Essentials the \_ (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ Business \_ Essentials) |
| Office 365 Business Premium \_ de (O365 \_ Business \_ Premium \_ -de) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Office 365 Business \_ de (O365 \_ Business \_ de) | Microsoft 365-apps voor bedrijven (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 zonder ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 zonder ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (Enterprise Pack \_ de) | Office 365 E3 (Enterprise Pack) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (Enterprise Pack \_ de) | Office 365 Enterprise E3 (Enterprise Pack) |
| Office 365 extra bestandsopslag \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 extra bestandsopslag (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus voor faculteiten \_ de (OFFICESUBSCRIPTION \_ faculteit \_ de) | Office 365 ProPlus voor faculteiten (OFFICESUBSCRIPTION \_ faculteit) |
| Office 365 ProPlus voor leerlingen en studenten \_ de (OFFICESUBSCRIPTION \_ leerling/student \_ de) | Office 365 ProPlus voor studenten (OFFICESUBSCRIPTION \_ leerling) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive voor bedrijven (abonnement 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive voor bedrijven (abonnement 1) (WACONEDRIVESTANDARD) |
| OneDrive voor bedrijven (abonnement 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive voor bedrijven (abonnement 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro voor \_ de faculteit de ( \_ Power \_ bi \_ Pro \_ -faculteit de) | Power BI Pro voor onderwijs medewerkers (POWER \_ bi Pro voor docenten \_ \_ ) |
| Power BI Pro \_ de (Power \_ bi \_ Pro \_ de) | Power BI Pro (POWER \_ bi \_ Pro) |
| Project online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project online Essentials (PROJECTESSENTIALS) |
| Project online Premium \_ de (PROJECTPREMIUM \_ de) | Project online Premium (PROJECTPREMIUM) |
| Project online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project online Professional (PROJECTPROFESSIONAL) |
| Project abonnement 3 \_ de (PROJECTPROFESSIONAL \_ de) | Project abonnement 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (Enterprise Pack) |
| SharePoint Online (abonnement 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (abonnement 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (abonnement 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (abonnement 2) (SHAREPOINTENTERPRISE) |
| Skype voor bedrijven online (abonnement 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype voor bedrijven online (abonnement 1) \_ de (MCOIMP \_ de) | Skype voor bedrijven online (abonnement 1) (MCOIMP) |
| Skype voor bedrijven online (abonnement 2) \_ de (MCOSTANDARD \_ de) | Skype voor bedrijven online (abonnement 2) (MCOSTANDARD) |
| Skype voor bedrijven plus CAL \_ de (MCOPLUSCAL \_ de) | Skype voor bedrijven plus CAL (MCOPLUSCAL) |
| Visio online abonnement 1 voor faculteiten \_ de (VISIOONLINE \_ PLAN1 \_ fac \_ de) | Visio online abonnement 1 voor faculteiten (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio online abonnement 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio online abonnement 1 (VISIOONLINE \_ PLAN1) |
| Visio online abonnement 2 voor faculteiten \_ de ( \_ VISIOCLIENT \_ -faculteit de) | Visio online (abonnement 2) voor faculteiten (VISIOCLIENT \_ -faculteit) |
| Visio online abonnement 2 \_ de (VISIOCLIENT \_ de) | Visio online abonnement 2 (VISIOCLIENT) |
| Visio abonnement 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio abonnement 1 (VISIOONLINE \_ PLAN1) |
| Visio-abonnement 2 \_ de (VISIOCLIENT \_ de) | Visio abonnement 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hoe kan ik hulp krijgen van Microsoft om naar een nieuw gebied te migreren en vragen over de ondersteuning te beantwoorden?

Als u vragen hebt, kunt u contact opnemen met ons of uw partner:

- Voor Azure kunt u [nieuwe ondersteuningsaanvragen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) indienen in de Azure-Portal.
- Voor Office 365 kunt u vragen indienen via de &quot; koppeling hulp nodig? &quot; in het [Microsoft 365-Beheercentrum](https://portal.office.de/).
- Als 365 u een Office-klant afspraak en Power BI-klant hebt en ook Office 365, kunt u vragen indienen via de &quot; koppeling hulp nodig? &quot; op de koppeling naar het [Microsoft 365-Beheercentrum](https://portal.office.de/). De ondersteuningsopties voor de klant afspraken van Dynamics 365 zijn [hier](https://docs.microsoft.com/dynamics365/get-started/support/)te vinden. De ondersteuningsopties voor Power BI zijn [hier](https://powerbi.microsoft.com/support/)te vinden.

## <a name="more-information"></a>Meer informatie

Aanvullende informatie over het migreren naar de nieuwe Duitse datacenter regio's. Een bladwijzer toevoegen aan een pagina, zodat u deze kunt in-en uitschakelen.

- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [URL's en IP-adresbereiken voor Office 365](https://aka.ms/o365endpoints)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
