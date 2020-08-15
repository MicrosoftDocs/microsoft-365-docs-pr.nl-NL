---
title: Migratie van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in de nieuwe Duitse datacenter regio's
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
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
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689378"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migratie van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in de nieuwe Duitse datacenter regio's


>[!Note]
>Dit artikel geldt alleen voor in aanmerking komende klanten met Microsoft Cloud Duitsland/Deutschland.
>

## <a name="cloud-service-offerings-in-germany"></a>Serviceaanbiedingen van de cloud in Duitsland

In augustus 2018 hebben we ons bedoeld voor de levering van de volledige Microsoft Cloud – Azure, Office 365, Dynamics 365 en Power platform – van nieuwe Cloud regio's in Duitsland, zodat u de digitale transformatie van onze klanten beter kunt inschakelen. In augustus 2019 hebben we ons nu geaangekondigd de nieuwe Cloud regio's in Duitsland te openen. De beschikbaarheid van Azure in augustus en Office 365 is in december bekend.  Dynamics 365 en Power platform worden verwacht om in het eerste kwartaal van 2020 beschikbaar te zijn.  

De nieuwe regio's zijn ontworpen om de geprojecteerde behoeften van Nederlandse klanten te verhelpen, met de grote flexibele cloudservices, en de volledige connectiviteit met het wereldwijde Cloud netwerk, evenals klantgegevens woonplaats in Duitsland.

## <a name="moving-to-the-new-german-regions"></a>Verplaatsen naar de nieuwe Duitse regio's

Bestaande klanten met Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) kunnen nu beginnen met het migreren van hun Office 365-, Dynamics 365-klant afspraken en Power platform BI-klanten.  De eerste stap is om u aan te [melden bij een Microsoft-led's-migratie naar de](https://aka.ms/office365germanymoveoptin) nieuwe Duitse datacenter regio's.

Voor organisaties die zich aanmelden bij de door Microsoft gerichte aanpak, zullen migraties naar verwachting plaatsvinden in 2020. Als gevolg van de migratie worden de kerngegevens en abonnementen van klanten naar de nieuwe Duitse regio's verplaatst. 

De volgende services worden gemigreerd als onderdeel van de door Microsoft gerichte aanpak:

- Microsoft Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive voor Bedrijven
- Skype voor Bedrijven Online

Tijdens de migratie van Microsoft Cloud Duitsland naar de Duitse datacenter gebieden, zullen bestaande Skype voor bedrijven online-klanten overstappen op Microsoft teams. Zie [aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home) voor meer informatie.

- Office 365 Groepen
- Dynamics 365/Power platform

De vereisten en gevolgen van de migratie voor deze services worden beschreven in het artikel over de [klant afspraken voor Dynamics 365](https://aka.ms/d365ceoptin) .

Office 365-video wordt op 1 maart 2021 verouderd. Als u ervoor kiest om uw Office 365-Tenant te migreren naar de nieuwe Duitse datacenter gebieden, wordt de video van Office 365 niet ondersteund na voltooiing van de SharePoint Online-migratie. [Meer informatie](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Voorbereidingen treffen voor de migratie naar Office 365-Services in de nieuwe Duitse datacenter gebieden

U wordt aangeraden om Microsoft te laten weten dat we uw toestemming hebben voor het migreren van uw abonnement en gegevens uit Microsoft Cloud Duitsland/Deutschland naar Office 365-Services in de nieuwe Duitse datacenter regio's.  Neem contact op met het [aanmeldingsproces](ms-cloud-germany-migration-opt-in.md) voor instructies.

- Alle migratie van klanten moeten de verbinding met de wereld [365-url's en IP-adressen van Office](urls-and-ip-address-ranges.md), waaronder de nieuwe Duitse datacenter gebieden, behoren.
- Bekijk de servicebeschrijving van het Office 365-platform om te begrijpen welke functies en services beschikbaar zijn in uw organisatie na de voltooiing van de Duitse regio. 
- Bij de migratie worden betaalde abonnementen overgezet.  We kunnen geen proefabonnementen migreren.

Tenant migraties worden uitgevoerd als een back-end serviceactiviteiten waarbij minimaal een klant interactie is vereist.  Alle extra klantgerichte taken en de algehele migratiestatus worden tijdens het migratieproces via het berichtencentrum gecommuniceerd.  Voorbeeld van taken zijn mogelijk DNS-updates van klanten of de configuratie van hybride installatie voor hybride klanten van Exchange.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Gebruikerservaring tijdens de migratie naar Office 365-Services in de nieuwe Duitse datacenter gebieden

Tenant migraties zijn ontworpen om minimale gevolgen te bieden voor het beëindigen van klanten en beheerders.  Er zijn echter wel enkele aandachtspunten voor elke werkbelasting.  

### <a name="azure-active-directory"></a>Microsoft Azure Active Directory

Office/Dynamics-abonnementen van Microsoft Cloud Duitsland worden overgezet naar het Duitse gebied met de herplaatsings locatie van Azure Active Directory (Azure AD). De organisatie wordt vervolgens bijgewerkt en weerspiegelt nieuwe wereldwijde Serviceabonnementen. Bij een kort proces voor het verzenden van een abonnement worden wijzigingen in abonnementen geblokkeerd.

### <a name="exchange-online"></a>Exchange Online

Exchange Online hybride klanten moeten de wizard hybride configuratie opnieuw uitvoeren om on-premises configuratie bij te werken in Microsoft Cloud Duitsland vóór de overgang en het opnieuw uitvoeren van HCW bij opruimen in de wereldwijde service. Er zijn mogelijk extra DNS-updates vereist voor klanten met aangepaste domeinen.

Postvakken worden gemigreerd als een backend-proces, kunnen gebruikers in uw organisatie in de Cloud of de regio van de Cloud deelnemen aan de overgang en maken deel uit van dezelfde Exchange-organisatie (GAL).

### <a name="exchange-online-protection"></a>Exchange Online Protection

Online beveiligingsfuncties van Exchange Online worden naar de nieuwe Duitse regio gekopieerd.

### <a name="sharepoint-online"></a>SharePoint Online

Na voltooiing van de SharePoint Online-migratie naar de Duitse regio, worden gegevens indexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen, kunnen worden beïnvloed wanneer u de indexering opnieuw uitvoert.

Bestaande Url's van sharepoint.de blijven behouden voor geoverstape organisaties.

### <a name="onedrive-for-business"></a>OneDrive voor Bedrijven

Na voltooiing van de migratie van OneDrive voor bedrijven naar de Duitse regio, worden gegevens indexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen, kunnen worden beïnvloed wanneer u de indexering opnieuw uitvoert.

### <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

Bestaande Skype voor bedrijven online-klanten zullen overstappen op Microsoft teams. Zie [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) voor meer informatie.

### <a name="office-365-video"></a>Office 365 Video
Inhoud van Office 365 video wordt gemigreerd als onderdeel van de SharePoint Online-migratie. De video van Office 365 wordt echter buiten gebruik gesteld en de video van Office 365 wordt niet ondersteund na voltooiing van de SharePoint Online-migratie naar de nieuwe Duitse datacenter regio's. Video's in Office 365 video worden niet afgespeeld in de GEBRUIKERSINTERFACE van Office 365 voor Video's na de migratie van SharePoint.

Microsoft stream wordt niet geïmplementeerd op Microsoft Deutschland, en we hebben momenteel geen tijdlijn voor de implementatie van Microsoft stream in de nieuwe Duitse datacenter regio's. Daarom zijn er geen migratiehulpprogramma's beschikbaar in dit gebied voor Office 365 video op Microsoft stream. Als u de inhoud wilt behouden, moet u de inhoud handmatig downloaden of verplaatsen vóór 1 maart 2021. [Meer informatie](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Belangrijkste verschillen tussen Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) en Office 365-Services in de nieuwe Duitse datacenter regio's


|| Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) | Office 365-Services in de nieuwe Duitse datacenter regio's |
|:-------|:-----|:-----|
| Microsoft 365-services beschikbaar voor abonnementen met maar één Office 365-Tenant | 15 Services (Zie VERW) | 29 Services (Zie VERW) |
| Nieuwe functies | Er zijn geen nieuwe functies beschikbaar. | De nieuwe functies zijn consistent met de algemene Office 365-Services. |
| Gegevensbeheerder | Ja | Nee |
| Samenwerking tussen tenants en wereldwijde Office 365-tenants | Nee | Ja |
| Woonplaats voor klantgegevens | Klantgegevens worden uitsluitend opgeslagen in een Duitse Data Center. | Microsoft zal de volgende klantgegevens binnen Duitsland bewaren, exclusief de inhoud van postvakken van Exchange Online (e-mail tekst, agenda-items en de inhoud van e-mailbijlagen), site-inhoud van SharePoint Online en de bestanden die zijn opgeslagen op deze site en bestanden die zijn geüpload naar OneDrive voor bedrijven. |
| Toepasselijke voorwaarden | [Online Servicevoorwaarden](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) met [aanvulling](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Online Servicevoorwaarden](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="is-migration-required"></a>Is migratie vereist?

Microsoft biedt Office 365-Tenant migratie van Microsoft Cloud Duitsland naar Office 365-Services in de nieuwe Duitse datacenter-regio's zonder extra kosten.  We raden u ten zeerste aan om u aan te melden voor het nieuwe Duitse datacenter gebied, en de benodigde beveiligingsupdates worden nu weergegeven voor de regio's Microsoft Cloud Duitsland.  

Office 365-Services in de nieuwe Duitse datacenter gebieden bieden een extra voordelen:

- Voor de concurrerende prijzen bieden [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 klant afspraak](https://dynamics.microsoft.com/pricing/)en [Power bi](https://powerbi.microsoft.com/pricing/). 
- Is verbonden met het wereldwijde Microsoft-netwerk, met honderden netwerk Edge-sites, peering locaties en uitgangspunten, zodat u overal ter wereld krachtige gebruikerservaring kunt bieden. 
- U kunt aan de woonplaats vereisten voor lokale klanten in Duitsland voldoen. 
- Zorg voor onze volledige algemene Cloud aanbieding, waaronder de nieuwste versie van onze services en nieuwe mogelijkheden, waaronder Microsoft teams en meerdere geografische versies in Office 365. Vergelijk producten per regio voor [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)en [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- U kunt alle functies, beveiliging van uw organisatie en uitgebreide functies aanbieden om klanten te helpen aan nalevings-en regelgeving te voldoen. 
- Zijn toegankelijk via bestaande contracten voor Online Services.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>De beschikbaarheid van de service voor cloudservice aanbiedingen van Office 365

De volgende 15 Services zijn beschikbaar in de cloudservice van Microsoft Cloud Deutschland.  We kunnen geen nieuwe services toevoegen aan Microsoft Cloud Duitsland.

1. Exchange Online
2. Klant-lockbox (Exchange Online)
3. Groepen (moderne groepen)
4. Delve-profiel
5. Exchange Online Protection
6. Advanced Threat Protection (ATP)
7. Advanced eDiscovery
8. Voorschot gegevensbeheer
9. SharePoint Online
10. Klant-lockbox (SharePoint Online)
11. OneDrive voor Bedrijven
12. Skype voor Bedrijven
13. Word online, Excel online, PowerPoint, OneNote, Visio online
14. Office 365 Pro Plus
15. Outlook Mobile

Er zijn momenteel 29 services beschikbaar als onderdeel van Office 365-Services in de nieuwe Duitse datacenter regio's.  Nieuwe functies en services zijn continu consistent met de wereldwijde Office 365-Services.

1. Exchange Online
2. Klant-lockbox (Exchange Online)
3. Groepen (moderne groepen)
4. Delve-profiel
5. MyAnalytics
6. Bewerkings analyses
7. Exchange Online Protection
8. Advanced Threat Protection (ATP)
9. Advanced eDiscovery
10. Geavanceerd beveiligingsbeheer
11. Information Rights Management
12. Voorschot gegevensbeheer
13. SharePoint Online
14. Klant-lockbox (SharePoint Online)
15. OneDrive voor Bedrijven
16. Microsoft Stream
17. Skype voor bedrijven (wordt tijdens de migratie overgezet naar Microsoft teams)
18. Cloud-PBX
19. Vergaderen via PSTN
20. Bellen via PSTN
21. Microsoft Teams
22. Beheerders rapporten/gebruiksrapporten
23. Word online, Excel online, PowerPoint, OneNote en Visio online
24. Planner
25. Sway
26. Office 365 Pro Plus
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + intune + Rights Management-service)
29. Yammer online

### <a name="when-will-migration-happen"></a>Wanneer gebeurt er een migratie?

#### <a name="azure"></a>Azure 

U kunt nu beginnen met het [migreren](https://docs.microsoft.com/azure/germany/germany-migration-main) van uw Azure-bronnen naar een andere regio. Als u Azure met Office 365, Dynamics 365 en/of Power BI hebt, volgt u de onderstaande stappen.

#### <a name="office-365"></a>Office 365

[Opt-in](https://aka.ms/office365germanymoveoptin) voor de Microsoft-gerichte migratie vandaag. Wanneer u klaar bent om de migratie te starten, wordt u via het [berichtencentrum](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) op de hoogte gesteld van het microsoft 365-Beheercentrum.

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 en Power BI

Opt-in voor de door Microsoft gerichte migratie voor [Dynamics 365 klant afspraak](https://aka.ms/D365ceOptIn) en [Power bi vandaag](https://aka.ms/PBIOptIn). Wanneer u klaar bent om de migratie te starten, wordt u via het [berichtencentrum](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) op de hoogte gesteld van het microsoft 365-Beheercentrum.

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>Wordt de prijswijziging voor de Office-services die ik gebruik?

Ja, prijzen in de globale Cloud regio's van Microsoft (waaronder de nieuwe datacenter gebieden), zijn in het algemeen lager.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hoe kan ik hulp krijgen van Microsoft om naar een nieuw gebied te migreren en vragen over de ondersteuning te beantwoorden?

Als u vragen hebt, kunt u als volgt contact opnemen met ons, of via uw partner:

- Voor Azure kunt u [nieuwe ondersteuningsaanvragen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) indienen in de Azure-Portal.
- Voor Office 365 kunt u vragen indienen met behulp van de ' hulp nodig? ' koppeling van het [Microsoft 365-Beheercentrum](https://portal.office.de/).
- Voor Dynamics 365 klant betrokkenheid en Power BI-klant die ook Office 365 heeft, kunt u vragen indienen met behulp van de ' hulp nodig? ' koppeling van het [Microsoft 365-Beheercentrum](https://portal.office.de/). De ondersteuningsopties voor de klant afspraken van Dynamics 365 zijn [hier](https://docs.microsoft.com/dynamics365/get-started/support/)te vinden. De ondersteuningsopties voor Power BI zijn [hier](https://powerbi.microsoft.com/support/)te vinden.

## <a name="more-information"></a>Meer informatie

- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [URL's en IP-adresbereiken voor Office 365](https://aka.ms/o365endpoints)
- [Wizard hybride configuratie van Office 365](https://aka.ms/HybridWizard)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
