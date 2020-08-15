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
ms.openlocfilehash: 83141f824c76ca5531e1b390b91adcdb4f3874de
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689115"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="614f4-103">Microsoft 365 multi-geo eDiscovery-configuratie</span><span class="sxs-lookup"><span data-stu-id="614f4-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="614f4-104">Standaard kan een eDiscovery-beheerder of beheerder van een meervoudige geo-Tenant alleen eDiscovery uitvoeren op de centrale locatie van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="614f4-104">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="614f4-105">Voor de mogelijkheid om eDiscovery voor satelliet locaties te doen, is een nieuwe beveiligings filter parameter genaamd ' regio ' beschikbaar via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="614f4-105">To support the ability to conduct eDiscovery for satellite locations, a new Compliance Security Filter parameter called "Region" is available via PowerShell.</span></span>

<span data-ttu-id="614f4-106">De globale beheerder van Microsoft 365 moet de machtigingen van een eDiscovery-beheerder toewijzen om de gebruikers de mogelijkheid te bieden om eDiscovery uit te voeren en een ' regio '-parameter toe te wijzen aan het toepasselijke beveiligings filter voor de naam van de locatie van de locatie van de satelliet.</span><span class="sxs-lookup"><span data-stu-id="614f4-106">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="614f4-107">Wanneer de rol van eDiscovery-beheerder of beheerder is ingesteld voor een bepaalde locatie van de satelliet, kan de eDiscovery-beheerder of beheerder alleen eDiscovery-zoekacties uitvoeren met de SharePoint-sites en OneDrive-sites op die locatie.</span><span class="sxs-lookup"><span data-stu-id="614f4-107">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location.</span></span> <span data-ttu-id="614f4-108">Als een eDiscovery-Manager of-beheerder probeert te zoeken naar SharePoint-of OneDrive-sites buiten de opgegeven locatie van de satelliet, worden geen resultaten geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="614f4-108">If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned.</span></span> <span data-ttu-id="614f4-109">Ook wanneer de eDiscovery-Manager of-beheerder voor een locatie voor een satelliet een export activeert, worden gegevens geëxporteerd naar het Azure-exemplaar van die regio.</span><span class="sxs-lookup"><span data-stu-id="614f4-109">Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region.</span></span> <span data-ttu-id="614f4-110">Dit helpt organisaties ertoe te zorgen dat de inhoud niet mag worden geëxporteerd met geplaatste randen.</span><span class="sxs-lookup"><span data-stu-id="614f4-110">This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="614f4-111">Als u wilt dat een eDiscovery-Manager op meerdere SharePoint-locaties kan zoeken, moet u een ander gebruikersaccount maken voor de eDiscovery-beheerder waarmee de andere locatie wordt opgegeven waar de OneDrive-of SharePoint-sites zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="614f4-111">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="614f4-112">Het beveiligings filter voor naleving voor een gebied instellen:</span><span class="sxs-lookup"><span data-stu-id="614f4-112">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="614f4-113">PowerShell-beveiliging verbinding maken met Microsoft 365 beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="614f4-113">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

2. <span data-ttu-id="614f4-114">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="614f4-114">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="614f4-115">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="614f4-115">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="614f4-116">Zie het [nieuwe ComplianceSecurityFilter-](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) artikel voor aanvullende parameters en syntaxis.</span><span class="sxs-lookup"><span data-stu-id="614f4-116">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
