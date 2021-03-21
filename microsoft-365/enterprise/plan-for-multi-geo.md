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
ms.openlocfilehash: 9625d55015cc0f18801d59e82fc8ca7090b3b721
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927530"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Plannen voor Microsoft 365 Multi-Geo

Deze richtlijnen zijn bedoeld voor beheerders van multinationale bedrijven (MNCs) die hun Microsoft 365-tenant voorbereiden om uit te breiden naar extra geografische gebieden op basis van de aanwezigheid van het bedrijf om te voldoen aan de vereisten voor gegevensverkendheid.

In een multi-geoconfiguratie bestaat uw Microsoft 365-tenant uit een centrale locatie en een of meer satellietlocaties. Dit is één tenant die zich over meerdere geografische locaties bespant. Uw tenantgegevens, inclusief geografische locaties, worden beheerst in Azure Active Directory (Azure AD).

Hier vindt u enkele belangrijke multi-geotermen om u te helpen de basisbegrippen van de configuratie te begrijpen:

-   **Tenant:** de vertegenwoordiging van een organisatie in Microsoft 365, waarbij meestal een of meer domeinen aan de tenant zijn gekoppeld (bijvoorbeeld https://contoso.sharepoint.com) . 

-   **Geografische locaties:** de geografische locaties die beschikbaar zijn voor het hosten van gegevens in een Microsoft 365-tenant.

-   **Satellietlocaties:** de extra geografische locaties die u hebt geconfigureerd voor het hosten van gegevens in uw Microsoft 365-tenant. Multi-geotententen hebben meerdere geografische locaties, bijvoorbeeld Noord-Amerika en Europa.

-   **Voorkeurslocatie voor gegevens (PDL)** : de geografische locatie waar de Exchange- en OneDrive-gegevens van een afzonderlijke gebruiker worden opgeslagen. Dit kan door de beheerder worden ingesteld op een van de geografische locaties die zijn geconfigureerd voor de tenant. Als u de PDL wijzigt voor een gebruiker die al een OneDrive-site heeft, worden de OneDrive-gegevens niet automatisch verplaatst naar de nieuwe geografische locatie. Zie [Een OneDrive-bibliotheek verplaatsen naar een andere geografische locatie](move-onedrive-between-geo-locations.md) voor meer informatie. Als ze een Exchange-postvak hebben, wordt het postvak automatisch verplaatst naar de nieuwe voorkeurslocatie voor gegevens.

Voor het inschakelen van Multi-Geo zijn vier belangrijke stappen vereist:

1.  Werk samen met uw accountteam om de _multi-geomogelijkheden toe te voegen in het Microsoft 365-serviceplan._

2.  Kies de gewenste satellietlocatie(s) en voeg deze toe aan uw tenant.

3.  Stel de gewenste gegevenslocatie van uw gebruikers in op de gewenste satellietlocatie. Wanneer een nieuwe OneDrive-site of Exchange-postvak is ingericht voor een gebruiker, is dit ingericht op de PDL.

4.  Migreert de bestaande OneDrive-sites van uw gebruikers zo nodig van de centrale locatie naar de gewenste gegevenslocatie. (Exchange-postvakken worden automatisch gemigreerd wanneer u het PDL van een gebruiker in stelt.)

Zie [Microsoft 365 Multi-Geo configureren](multi-geo-tenant-configuration.md) voor meer informatie over elk van deze stappen.

> [!IMPORTANT]
> Microsoft 365 Multi-Geo is niet ontworpen voor prestatieoptimalisatie, maar is ontworpen om te voldoen aan de vereisten voor gegevenslocatie. Zie Netwerkplanning en prestatieafstemming voor Microsoft 365 of neem contact op met uw ondersteuningsgroep voor informatie over prestatieoptimalisatie voor [Microsoft 365.](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)

U kunt een van de volgende locaties configureren als satellietlocaties waar u OneDrive- en SharePoint-sites en Exchange-postvakken kunt hosten. Terwijl u van plan bent voor multi-geo, maakt u een lijst met de locaties die u wilt toevoegen aan uw Microsoft 365-tenant. Het is raadzaam om te beginnen met een of twee satellietlocaties en zo nodig geleidelijk uit te breiden naar meer geografische locaties.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Wanneer u multi-geo configureert, kunt u van de gelegenheid gebruik maken om uw on-premises infrastructuur te consolideren terwijl u migreert naar Microsoft 365. Als u bijvoorbeeld on-premises farms hebt in Singapore en Maleisië, kunt u deze samenvoegen naar de APC-satellietlocatie, mits u dit kunt doen met vereisten voor gegevensverplaatsing.

## <a name="best-practices"></a>Aanbevolen procedures

Het is raadzaam om een testgebruiker te maken in Microsoft 365 om enkele eerste tests uit te voeren. We zullen enkele test- en verificatiestappen met deze gebruiker doorlopen voordat u overgaat tot het onboarden van productiegebruikers in Microsoft 365 Multi-Geo.

Nadat u het testen met de testgebruiker hebt voltooid, selecteert u een testgroep ( misschien van uw IT-afdeling ) om als eerste OneDrive en Exchange op een nieuwe geografische locatie te gebruiken. Selecteer voor deze eerste groep gebruikers die nog geen OneDrive hebben. We raden u aan niet meer dan vijf personen in deze eerste groep uit te breiden volgens een batched rollout-benadering.

Elke gebruiker moet een *voorkeurslocatie* (PDL) hebben, zodat Microsoft 365 kan bepalen op welke geografische locatie de OneDrive moet worden ingericht. De gewenste gegevenslocatie van de gebruiker moet overeenkomen met een van de gekozen satellietlocaties of de centrale locatie. Hoewel het PDL-veld niet verplicht is, raden we aan een PDL in te stellen voor alle gebruikers. Werkbelastingen van een gebruiker zonder PDL worden ingericht op de centrale locatie.

Maak een lijst met uw gebruikers en neem de naam van de gebruikersnaam (UPN) en de locatiecode op voor de gewenste gegevenslocatie. Neem de testgebruiker en de eerste testgroep op om mee te beginnen. U hebt deze lijst nodig voor de configuratieprocedures.

Als uw gebruikers worden gesynchroniseerd van een on-premises Active Directory-systeem naar Azure Active Directory, moet u de gewenste gegevenslocatie instellen als een Active Directory-kenmerk en deze synchroniseren met Azure Active Directory Connect. U kunt de gewenste gegevenslocatie niet rechtstreeks configureren voor gesynchroniseerde gebruikers met Azure AD PowerShell. De stappen voor het instellen van PDL in Active Directory en Synchroniseren worden behandeld in De synchronisatie van Azure Active Directory Connect: De gewenste gegevenslocatie configureren [voor Microsoft 365-resources.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)

Het beheer van een multi-geo tenant kan verschillen van een niet-multi-geo tenant, omdat veel van de Instellingen en services van SharePoint en OneDrive multi-geo-aware zijn. U wordt aangeraden een [multi-geo-omgeving](administering-a-multi-geo-environment.md) te beheren voordat u verder gaat met de configuratie.

Lees [Gebruikerservaring in een multi-geo-omgeving](multi-geo-user-experience.md) voor meer informatie over de ervaring van uw eindgebruikers in een multi-geo-omgeving.

Zie Teams experience [in a Microsoft 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy (Teams experience in a Microsoft 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy](/microsoftteams/teams-experience-o365odb-spo-multi-geo)) voor meer informatie over de Teams-ervaring in een Microsoft 365 Multi-Geo-tenancy.

Zie [Microsoft 365 Multi-Geo configureren](multi-geo-tenant-configuration.md)om aan de slag te gaan met het configureren van Microsoft 365 Multi-Geo.

Wanneer u de configuratie hebt voltooid, moet u de [OneDrive-bibliotheken](move-onedrive-between-geo-locations.md) van uw gebruikers zo nodig migreren om uw gebruikers te laten werken vanaf hun favoriete gegevenslocaties.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 Multi-Geo eDiscovery-configuratie](./multi-geo-ediscovery-configuration.md)