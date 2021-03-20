---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In dit artikel leert u hoe u uw Microsoft 365-aanwezigheid uitbreidt naar meerdere geografische regio's met Microsoft 365 Multi-Geo.
ms.openlocfilehash: 2805470f1a35bb5978f3d25c30aa07523ad21afb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909548"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Met Microsoft 365 Multi-Geo kan uw organisatie de aanwezigheid van Microsoft 365 uitbreiden naar meerdere geografische regio's en/of landen binnen uw bestaande tenant. Contact op met uw Microsoft-accountteam om uw multi-national company voor Microsoft 365 Multi-Geo te registreren.
  
Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag en tegelijkertijd uw wereldwijde implementatie van moderne productiviteitservaringen voor uw werknemers ontgrendelen.

Zie SharePoint Online en [OneDrive Multi-Geo](https://www.youtube.com/watch?v=Do9U3JuROhk)voor een video-inleiding tot Microsoft 365 Multi-Geo om te bepalen waar uw gegevens zich bevinden.

## <a name="multi-geo-architecture"></a>Architectuur met meerdere geo's

In een Multi-Geo-omgeving bestaat uw Microsoft 365-tenant uit een centrale locatie (waar uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satellietlocaties. In een multi-geo tenant wordt de informatie over geografische locaties, groepen en gebruikersgegevens beheerst in Azure Active Directory (Azure AD). Omdat uw tenantgegevens centraal worden gemodelleerd en gesynchroniseerd naar elke geografische locatie, bevatten delen en ervaringen met iedereen uit uw bedrijf globale bekendheid.

![Schermafbeelding van multi-geomap vanuit het SharePoint-beheercentrum](../media/multi-geo-world-map.png)

Microsoft 365 Multi-Geo is niet ontworpen voor prestatieoptimalisatie, maar is ontworpen om te voldoen aan de vereisten voor gegevenslocatie. Zie Netwerkplanning en prestatieafstemming voor Microsoft 365 of neem contact op met uw ondersteuningsgroep voor informatie over prestatieoptimalisatie voor [Microsoft 365.](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)

## <a name="terminology"></a>Terminologie

Hier zijn de belangrijkste termen die worden gebruikt bij het beschrijven van Microsoft 365 Multi-Geo:

- **Centrale locatie:** de geografische locatie waar de tenant oorspronkelijk is ingericht.
- **Geobeheerder:** een beheerder die een of meer opgegeven satellietlocaties kan beheren.
- **Geocode:** een code met drie letters voor een bepaalde geografische locatie.
- **Geografische locatie:** een geografische locatie die kan worden gebruikt in een multi-geoten tenant om gegevens te hosten, waaronder Exchange-postvakken en OneDrive- en SharePoint-sites.
- **Voorkeurslocatie voor gegevens (PDL)** : een eigenschap van de gebruiker die is ingesteld door de beheerder die aangeeft waar de geografische locatie waar de gebruikers Exchange-postvak en OneDrive moeten worden ingericht. De PDL bepaalt ook waar SharePoint-sites die door de gebruiker zijn gemaakt, zijn ingericht.
- **Satellietlocatie:** de geografische locaties waar de geo-aware Microsoft 365-werkbelastingen (SharePoint, OneDrive en Exchange) zijn ingeschakeld in een multi-geoten tenant.
- **Tenant:** de vertegenwoordiging van een organisatie in Microsoft 365, waarbij meestal een of meer domeinen aan de tenant zijn gekoppeld (bijvoorbeeld contoso.com).

## <a name="licensing"></a>Licenties

Microsoft 365 Multi-Geo is beschikbaar als een add-on voor de volgende Microsoft 365-abonnementsabonnementen voor klanten met een enterprise-overeenkomst met minimaal 250 Microsoft 365-seats in hun tenant en minimaal 5% van deze seats met multi-geo. Gebruikersabonnementslicenties moeten zich op dezelfde Enterprise Agreement als de Multi-Geo Services-licenties hebben. Neem contact op met uw Microsoft-accountteam voor meer informatie.

- Microsoft 365 F1, F3, E3 of E5
- Office 365 F3, E1, E3 of E5
- Exchange Online-abonnement 1 of Abonnement 2
- OneDrive voor Bedrijven-abonnement 1 of Abonnement 2
- SharePoint Online-abonnement 1 of Abonnement 2

## <a name="microsoft-365-multi-geo-availability"></a>Beschikbaarheid van Microsoft 365 Multi-Geo

Microsoft 365 Multi-Geo wordt momenteel aangeboden in deze regio's en landen:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Aan de slag

Volg de volgende stappen om aan de slag te gaan met multi-geo:

1. Werk samen met uw accountteam om de _multi-geomogelijkheden toe te voegen in het Microsoft 365-serviceplan._ Ze begeleiden u bij het toevoegen van het benodigde aantal licenties. Multi-Geo-functie is beschikbaar voor EA-klanten met minimaal 250 Microsoft 365-abonnementen.

   Voordat u Microsoft 365 Multi-Geo kunt gaan gebruiken, moet Microsoft uw Exchange Online-tenant configureren voor multi-geo-ondersteuning. Dit eendaagse configuratieproces wordt geactiveerd nadat u de *multi-geo-mogelijkheden in het Microsoft 365-serviceplan* hebt bestelt en de licenties worden in uw tenant gebruikt. U ontvangt werkbelastingspecifieke meldingen in het [Microsoft 365-berichtencentrum](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) zodra uw tenant het configuratieproces voor elke werkbelasting heeft voltooid. Vervolgens kunt u beginnen met het configureren en gebruiken van uw Microsoft 365 Multi-Geo-mogelijkheden. De tijd die nodig is voor het configureren van een tenant voor Multi-Geo-ondersteuning verschilt per tenant, maar de meeste tenants eindigen binnen een maand na ontvangst van de functielicenties. Grotere of complexere tenants hebben mogelijk meer tijd nodig om het configuratieproces te voltooien. Neem contact op met uw accountteam voor meer informatie over uw specifieke tenant indien u dit nodig hebt.

2. Lees [Uw multi-geo-omgeving plannen.](plan-for-multi-geo.md)

3. Meer informatie [over het beheren van een multi-geo-omgeving](administering-a-multi-geo-environment.md) en hoe uw gebruikers de omgeving zullen [ervaren.](multi-geo-user-experience.md)

4. Wanneer u klaar bent om Microsoft 365 Multi-Geo in te stellen, configureert u [de tenant voor multi-geo.](multi-geo-tenant-configuration.md)

5. [Zoekactie instellen.](configure-search-for-multi-geo.md)

## <a name="see-also"></a>Zie ook

[Multi-Geo in Exchange Online en OneDrive](https://Aka.ms/GoMultiGeo)

[Multi-Geo-mogelijkheden in OneDrive en SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Multi-Geo-mogelijkheden in Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Teams-ervaring in een multi-geo-omgeving](/microsoftteams/teams-experience-o365odb-spo-multi-geo)