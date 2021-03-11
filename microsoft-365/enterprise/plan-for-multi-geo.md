---
title: Plannen voor Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Meer informatie over Microsoft 365 Multi-Geo, hoe multi-geo werkt en welke geografische locaties beschikbaar zijn voor gegevensopslag.
ms.openlocfilehash: ce8b752cc6a335249f9d8e03289fd16b04756ce9
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712340"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo plannen

Deze richtlijnen zijn bedoeld voor beheerders van multinationale bedrijven (MNCs) die hun Microsoft 365-tenant voorbereiden om te worden uitgebreid naar andere regio's in overeenstemming met de aanwezigheid van het bedrijf om te voldoen aan de vereisten voor gegevensverwooning.

In een configuratie met meerdere geo's bestaat uw Microsoft 365-tenant uit een centrale locatie en een of meer satellietlocaties. Dit is één tenant die zich verspreidt over meerdere geografische locaties. Uw tenantgegevens, inclusief geografische locaties, worden gebruikt in Azure Active Directory (Azure AD).

Hier vindt u enkele belangrijke multi geotermen om de basisconcepten van de configuratie te begrijpen:

-   **Tenant:** de weergave van een organisatie in Microsoft 365, waaraan meestal een of meer domeinen zijn gekoppeld https://contoso.sharepoint.com) (bijvoorbeeld. 

-   **Geografische locaties:** de geografische locaties die beschikbaar zijn voor het hosten van gegevens in een Microsoft 365-tenant.

-   **Satellietlocaties:** de extra geografische locaties die u hebt geconfigureerd voor het hosten van gegevens in uw Microsoft 365-tenant. Meerdere geografische tenants bevinden zich op meer dan één geografische locatie, bijvoorbeeld Noord-Amerika en Europa.

-   **Voorkeursgegevenslocatie (PDL),** de geografische locatie waar de Exchange- en OneDrive-gegevens van een individuele gebruiker worden opgeslagen. Dit kan door de beheerder worden ingesteld op een van de geografische locaties die zijn geconfigureerd voor de tenant. Als u het PDF-gegevensitem wijzigt voor een gebruiker die al een OneDrive-site heeft, worden de OneDrive-gegevens van deze gebruiker niet automatisch verplaatst naar de nieuwe geografische locatie. Zie [Een OneDrive-bibliotheek verplaatsen naar een andere geografische locatie](move-onedrive-between-geo-locations.md) voor meer informatie. Als het postvak een Exchange-postvak heeft, wordt het postvak automatisch verplaatst naar de nieuwe voorkeursgegevenslocatie.

Voor het inschakelen van Multi-Geo zijn vier belangrijke stappen vereist:

1.  Werk samen met uw accountteam om de _Multi-Geo Capabilities toe te voegen in het Microsoft 365-serviceplan._

2.  Kies de gewenste satellietlocatie(s) en voeg deze toe aan uw tenant.

3.  Stel de gewenste locatie voor gegevens van uw gebruikers in op de gewenste satellietlocatie. Wanneer een nieuw OneDrive-site- of Exchange-postvak voor een gebruiker wordt ingericht, wordt dit ingericht in het PDF-systeem van de gebruiker.

4.  Migreert de bestaande OneDrive-sites van uw gebruikers van de centrale locatie naar de gewenste gegevenslocatie. (Exchange-postvakken worden automatisch gemigreerd wanneer u een PDF-gegevens van een gebruiker in stelt.)

Zie [Microsoft 365 Multi-Geo configureren](multi-geo-tenant-configuration.md) voor meer informatie over elk van deze stappen.

> [!IMPORTANT]
> Houd er rekening mee dat Microsoft 365 Multi-Geo niet is ontworpen voor optimalisatie van de prestaties, maar is ontworpen om te voldoen aan vereisten voor het opslaan van gegevens. Zie Netwerkplanning en prestaties optimaliseren voor Microsoft 365 of neem contact op met uw ondersteuningsgroep voor informatie over prestatie-optimalisatie voor [Microsoft 365.](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)

U kunt de volgende locaties instellen als satellietlocaties waar u OneDrive- en SharePoint-sites en Exchange-postvakken kunt hosten. Terwijl u meerdere geografische locaties wilt gaan gebruiken, maakt u een lijst met de locaties die u wilt toevoegen aan uw Microsoft 365-tenant. Het is raadzaam om te beginnen met een of twee satellietlocaties en indien nodig geleidelijk uit te breiden naar meer geografische locaties.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Wanneer u multige geo configureert, kunt u overwegen om uw on-premises infrastructuur samen te staan terwijl u migreert naar Microsoft 365. Als u bijvoorbeeld on-premises farms in Singapore en Maleisië hebt, kunt u ze samenvoegen in de APC-satellietlocatie, mits u de vereisten voor het opslaan van gegevens hebt toegestaan.

## <a name="best-practices"></a>Aanbevolen procedures

Het is raadzaam om in Microsoft 365 een testgebruiker te maken voor de eerste tests. We zullen enkele test- en verificatiestappen met deze gebruiker doorlopen voordat u productiegebruikers in microsoft 365 Multi-Geo overwerkt.

Nadat u klaar bent met het testen met de testgebruiker, selecteert u een testgroep (mogelijk van uw IT-afdeling) om als eerste OneDrive en Exchange op een nieuwe geografische locatie te gebruiken. Selecteer voor deze eerste groep gebruikers die nog geen OneDrive hebben. Het is raadzaam om niet meer dan vijf personen in deze aanvankelijke groep te laten werken en deze geleidelijk uit te breiden volgens een batchuitrol.

Voor elke gebruiker moet een *voorkeursgegevenslocatie* (PDL) zijn ingesteld, zodat Microsoft 365 kan bepalen op welke geografische locatie zijn of haar OneDrive moet worden ingericht. De voorkeursgegevenslocatie van de gebruiker moet overeenkomen met een van de satellietlocaties die u hebt gekozen of uw centrale locatie. Hoewel het PDF-veld niet verplicht is, raden we aan om een PDF-nummer in te stellen voor alle gebruikers. Werkbelasting van een gebruiker zonder PDF-bestanden wordt ingericht op de centrale locatie.

Maak een lijst met uw gebruikers en voeg hun UPN (User Principal Name) en de locatiecode voor de juiste voorkeursgegevenslocatie toe. Neem de testgebruiker en de eerste testgroep op om mee te beginnen. U hebt deze lijst nodig voor de configuratieprocedures.

Als uw gebruikers vanuit een on-premises Active Directory-systeem worden gesynchroniseerd met Azure Active Directory, moet u de gewenste gegevenslocatie instellen als een Active Directory-kenmerk en deze synchroniseren met behulp van Azure Active Directory Connect. U kunt de voorkeursgegevenslocatie niet rechtstreeks configureren voor gesynchroniseerde gebruikers met Azure AD PowerShell. De stappen voor het instellen van PDL in Active Directory en Synchronisatie worden behandeld in Azure Active Directory Connect-synchronisatie: Voorkeursgegevenslocatie configureren [voor Microsoft 365-bronnen.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)

Het beheer van een multige geo-tenant kan verschillen van een niet-multi-geo tenant, omdat veel van de Instellingen en services van SharePoint en OneDrive multige geo-aware zijn. We raden u aan een [multige geo-omgeving te](administering-a-multi-geo-environment.md) beheren voordat u verder gaat met de configuratie.

Lees [de gebruikerservaring in een multige geo-omgeving](multi-geo-user-experience.md) voor meer informatie over de ervaring van uw eindgebruikers in een multige geo-omgeving.

Voor meer informatie over de Teams-ervaring in een Microsoft 365 Multi-Geo tenancy, bekijkt u de [Teams-ervaring in een Microsoft 365 OneDrive en SharePoint Online Multi-Geo-enabled tenancy.](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)

Zie Microsoft 365 Multi-Geo configureren voor meer informatie over het configureren van [Microsoft 365 Multi-Geo.](multi-geo-tenant-configuration.md)

Wanneer u de configuratie hebt voltooid, vergeet dan niet om de [OneDrive-bibliotheken](move-onedrive-between-geo-locations.md) van uw gebruikers zo nodig te migreren om uw gebruikers te laten werken vanaf hun favoriete gegevenslocaties.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 Multi-Geo eDiscovery-configuratie](https://docs.microsoft.com/microsoft-365/enterprise/multi-geo-ediscovery-configuration)
