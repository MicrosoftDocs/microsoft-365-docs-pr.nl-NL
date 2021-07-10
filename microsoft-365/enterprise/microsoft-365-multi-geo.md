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
description: In dit artikel leert u hoe u uw aanwezigheid Microsoft 365 meerdere geografische regio's kunt uitbreiden met Microsoft 365 Multi-Geo.
ms.openlocfilehash: 17fc2645f69a0d91c71c91718f321e5932d31bd2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362760"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Met Microsoft 365 Multi-Geo kan uw organisatie de aanwezigheid van Microsoft 365 uitbreiden naar meerdere geografische regio's en/of landen binnen uw bestaande tenant. Contact op met uw Microsoft-accountteam om uw multi-national company te registreren voor Microsoft 365 Multi-Geo.
  
Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag en tegelijkertijd uw globale implementatie van moderne productiviteitservaringen voor uw werknemers ontgrendelen.

Voor een video-inleiding tot Microsoft 365 Multi-Geo, zie SharePoint Online en OneDrive Multi-Geo om te bepalen waar uw [gegevens zich bevinden.](https://www.youtube.com/watch?v=Do9U3JuROhk)

## <a name="multi-geo-architecture"></a>Architectuur met meerdere geo's

In een Multi-Geo-omgeving bestaat Microsoft 365 tenant uit een centrale locatie (waar uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satellietlocaties. In een multi-geo tenant wordt de informatie over geografische locaties, groepen en gebruikersgegevens beheerst in Azure Active Directory (Azure AD). Omdat uw tenantgegevens centraal worden gemodelleerd en gesynchroniseerd naar elke geografische locatie, bevatten delen en ervaringen met iedereen uit uw bedrijf globale bekendheid.

![Schermafbeelding van multi-geomap vanuit het SharePoint beheercentrum](../media/multi-geo-world-map.png)

Houd er rekening Microsoft 365 Multi-Geo niet is ontworpen voor prestatieoptimalisatie, maar is ontworpen om te voldoen aan de vereisten voor gegevenslocatie. Zie Netwerkplanning en prestatieafstemming voor Microsoft 365 voor meer informatie over prestatieoptimalisatie voor Microsoft 365 [of](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) neem contact op met uw ondersteuningsgroep.

## <a name="terminology"></a>Terminologie

Hier zijn de belangrijkste termen die worden gebruikt bij het beschrijven Microsoft 365 Multi-Geo:

- **Centrale locatie:** de geografische locatie waar de tenant oorspronkelijk is ingericht.
- **Geobeheerder:** een beheerder die een of meer opgegeven satellietlocaties kan beheren.
- **Geocode:** een code met drie letters voor een bepaalde geografische locatie.
- **Geografische locatie:** een geografische locatie die kan worden gebruikt in een multi-geotenator voor het hosten van gegevens, Exchange postvakken en OneDrive en SharePoint sites.
- **Voorkeurslocatie voor gegevens (PDL)** : een eigenschap van de gebruiker die is ingesteld door de beheerder die aangeeft waar de geografische locatie waar de gebruikers Exchange postvak en OneDrive moeten worden ingericht. De PDL bepaalt ook waar SharePoint sites die door de gebruiker zijn gemaakt, zijn ingericht.
- **Satellietlocatie:** de geografische locaties waar de geo-aware Microsoft 365 workloads (SharePoint, OneDrive en Exchange) zijn ingeschakeld in een multi-geoten tenant.
- **Tenant:** de vertegenwoordiging van een organisatie in Microsoft 365 waarbij meestal een of meer domeinen aan de tenant zijn gekoppeld (bijvoorbeeld contoso.com).

## <a name="licensing"></a>Licenties

Microsoft 365 Multi-Geo is beschikbaar als invoegabonnement op de volgende Microsoft 365-abonnementen voor Enterprise Agreement-klanten met minimaal 250 Microsoft 365-seats in hun tenant, en minimaal 5% van deze seats met multi-geo. Gebruikersabonnementslicenties moeten op dezelfde Enterprise Agreement als de Multi-Geo Services-licenties. Neem contact op met uw Microsoft-accountteam voor meer informatie.

- Microsoft 365 F1, F3, E3 of E5
- Office 365 F3, E1, E3 of E5
- Exchange Online Plan 1 of Plan 2
- OneDrive voor Bedrijven Plan 1 of Plan 2
- SharePoint Online abonnement 1 of Abonnement 2

Als een licentie is toegewezen aan een gebruiker en later wordt verwijderd, worden Teams gebruikerschatgegevens in de wachtrij geplaatst om terug te worden verplaatst naar de centrale locatie. SharePoint en Exchange gegevens worden niet verplaatst.

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 Beschikbaarheid van meerdere geo's

Microsoft 365 Multi-Geo wordt momenteel aangeboden in deze regio's en landen:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Aan de slag

Volg de volgende stappen om aan de slag te gaan met multi-geo:

1. Werk samen met uw accountteam om de _Multi-Geo-mogelijkheden toe_ te voegen in Microsoft 365 serviceplan. Ze begeleiden u bij het toevoegen van het benodigde aantal licenties. Multi-Geo-functie is beschikbaar voor EA-klanten met een minimum van 250 Microsoft 365 abonnementen.

   Voordat u kunt beginnen met Microsoft 365 Multi-Geo, moet Microsoft uw Exchange Online configureren voor multi-geo-ondersteuning. Dit eendimensionale configuratieproces wordt geactiveerd nadat u de *Multi-Geo Capabilities hebt* Microsoft 365 serviceplan en de licenties worden in uw tenant. U ontvangt werkbelastingspecifieke meldingen [](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) in het Microsoft 365-berichtencentrum zodra uw tenant het configuratieproces voor elke werkbelasting heeft voltooid en u vervolgens kunt beginnen met het configureren en gebruiken van uw Microsoft 365 Multi-Geo-mogelijkheden. De tijd die nodig is voor het configureren van een tenant voor Multi-Geo-ondersteuning verschilt per tenant, maar de meeste tenants eindigen binnen een maand na ontvangst van de functielicenties. Grotere of complexere tenants hebben mogelijk meer tijd nodig om het configuratieproces te voltooien. Neem contact op met uw accountteam voor meer informatie over uw specifieke tenant indien u dit nodig hebt.

2. Lees [Uw multi-geo-omgeving plannen.](plan-for-multi-geo.md)

3. Meer informatie [over het beheren van een multi-geo-omgeving](administering-a-multi-geo-environment.md) en hoe uw gebruikers de omgeving zullen [ervaren.](multi-geo-user-experience.md)

4. Wanneer u klaar bent om de Microsoft 365 Multi-Geo in te stellen, configureert u [de tenant voor multi-geo.](multi-geo-tenant-configuration.md)

5. [Zoekactie instellen.](configure-search-for-multi-geo.md)

## <a name="see-also"></a>Zie ook

[Multi-Geo in Exchange Online en OneDrive](https://Aka.ms/GoMultiGeo)

[Multi-Geo Capabilities in OneDrive en SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Multi-Geo Capabilities in Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Teams ervaring in een multi-geo-omgeving](/microsoftteams/teams-experience-o365odb-spo-multi-geo)