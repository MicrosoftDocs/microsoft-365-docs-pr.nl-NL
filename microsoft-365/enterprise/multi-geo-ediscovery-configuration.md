---
title: Microsoft 365 multi-geo eDiscovery configureren
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Meer informatie over het gebruik van de regio parameter voor het configureren van eDiscovery voor gebruik in de locaties van de satellieten in Microsoft 365 multi-geo.
ms.openlocfilehash: 216012791473776395d27821293e8fc565568c2c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547948"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 multi-geo eDiscovery-configuratie

Standaard kan een eDiscovery-beheerder of beheerder van een meervoudige geo-Tenant alleen eDiscovery uitvoeren op de centrale locatie van de Tenant. Voor de mogelijkheid om eDiscovery voor satelliet locaties te doen, is een nieuwe beveiligings filter parameter genaamd ' regio ' beschikbaar via PowerShell.

De globale beheerder van Microsoft 365 moet de machtigingen van een eDiscovery-beheerder toewijzen om de gebruikers de mogelijkheid te bieden om eDiscovery uit te voeren en een ' regio '-parameter toe te wijzen aan het toepasselijke beveiligings filter voor de naam van de locatie van de locatie van de satelliet.

Wanneer de rol van eDiscovery-beheerder of beheerder is ingesteld voor een bepaalde locatie van de satelliet, kan de eDiscovery-beheerder of beheerder alleen eDiscovery-zoekacties uitvoeren met de SharePoint-sites en OneDrive-sites op die locatie. Als een eDiscovery-Manager of-beheerder probeert te zoeken naar SharePoint-of OneDrive-sites buiten de opgegeven locatie van de satelliet, worden geen resultaten geretourneerd. Ook wanneer de eDiscovery-Manager of-beheerder voor een locatie voor een satelliet een export activeert, worden gegevens geëxporteerd naar het Azure-exemplaar van die regio. Dit helpt organisaties ertoe te zorgen dat de inhoud niet mag worden geëxporteerd met geplaatste randen.

> [!NOTE]
> Als u wilt dat een eDiscovery-Manager op meerdere SharePoint-locaties kan zoeken, moet u een ander gebruikersaccount maken voor de eDiscovery-beheerder waarmee de andere locatie wordt opgegeven waar de OneDrive-of SharePoint-sites zich bevinden.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Het beveiligings filter voor naleving voor een gebied instellen:

1. [PowerShell-beveiliging verbinding maken met Microsoft 365 beveiligings & nalevings centrum](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Gebruik de volgende syntaxis:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Bijvoorbeeld:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Zie het [nieuwe ComplianceSecurityFilter-](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) artikel voor aanvullende parameters en syntaxis.
