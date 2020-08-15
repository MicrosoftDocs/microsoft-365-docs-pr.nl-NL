---
title: Microsoft 365-isolatie besturingselementen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Meer informatie over de manier waarop de isolatie besturingselementen werken binnen Microsoft 365, zodat services onder de juiste plaats kunnen blijven.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689283"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365-isolatie besturingselementen 

Microsoft werkt continu, zodat de architectuur met meerdere tenants van Microsoft 365 ondersteuning biedt voor beveiliging, vertrouwelijkheid, privacy, integriteit, lokale, internationale en beschikbaarheids [normen](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons). De schaal en het servicebereik van Microsoft maken het moeilijk en niet-rendabel om Microsoft 365 te beheren met aanzienlijke menselijke interactie. Microsoft 365-services worden geleverd via meerdere algemeen gedistribueerde gegevenscentra, elk met een geautomatiseerd aantal bewerkingen waarbij een menselijk aanraak niveau of toegang tot de inhoud van de klant is vereist. Onze medewerkers ondersteunen deze services en datacenters met behulp van geautomatiseerde hulpprogramma's en zeer veilige externe toegang. 

Microsoft 365 is samengesteld uit meerdere services die belangrijke bedrijfsfunctionaliteit bieden en bijdragen aan de volledige Microsoft 365-ervaring. Deze services zijn zelf en ontworpen voor integratie met elkaar.

Microsoft 365 is ontworpen met de volgende beginselen:

 - ** [Service gerichte architectuur](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** het ontwerpen en ontwikkelen van software in de vorm van interoperabele diensten die goed gedefinieerde bedrijfsfunctionaliteit bieden.
 - **[Operationele beveiligings zekerheid](https://www.microsoft.com/download/details.aspx?id=40872):** een kader dat de kennis vormt van diverse mogelijkheden die uniek zijn voor Microsoft, waaronder de Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), het [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)en de grondige bewustmaking van de Cyber Security-Threat liggend.

Microsoft 365-services die onderling samenwerken, maar zijn ontworpen en geïmplementeerd, zodat ze kunnen worden geïmplementeerd en geëxploiteerd als autonome Services, ongeacht elkaar. Microsoft scheidt bevoegdheden en verantwoordelijkheidsgebieden voor Microsoft 365 om de verkoopkansen te verminderen voor ongeoorloofde of onbedoelde wijzigingen of misbruik van de assets van de organisatie. Microsoft 365 teams heeft rollen gedefinieerd als onderdeel van een uitgebreid toegangsbeheer mechanisme op basis van rollen.

## <a name="customer-content-isolation"></a>Inhouds isolatie van klanten

Alle inhoud van de klant in een Tenant is geïsoleerd van andere tenants en van operations-en systeemgegevens die worden gebruikt in het beheer van Microsoft 365. Er worden meerdere vormen van bescherming geïmplementeerd in Microsoft 365, zodat u het risico voor compromissen met een Microsoft 365-service of-toepassing beperkt. Meerdere vormen van bescherming verhinderen ook onbevoegde toegang tot de gegevens van tenants of het Microsoft 365-systeem zelf.

Zie [Tenant isolatie in Microsoft 365](microsoft-365-tenant-isolation-overview.md)voor informatie over hoe Microsoft logische isolatie van Tenant gegevens implementeert in microsoft 365.
