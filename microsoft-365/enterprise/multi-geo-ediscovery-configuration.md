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
description: Meer informatie over het gebruik van de parameter Regio om eDiscovery te configureren voor gebruik op satellietlocaties in Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923718"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="ae2a4-103">Microsoft 365 Multi-Geo eDiscovery-configuratie</span><span class="sxs-lookup"><span data-stu-id="ae2a4-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="ae2a4-104">[Advanced eDiscovery mogelijkheden kan](../compliance/overview-ediscovery-20.md) een multi-geo eDiscovery-beheerder alle geografische gegevens doorzoeken zonder dat u een beveiligingsfilter 'Regio' hoeft te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="ae2a4-105">Gegevens worden geëxporteerd naar het Azure-exemplaar van de centrale locatie van de multi-geo tenant.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="ae2a4-106">Zonder geavanceerde eDiscovery-mogelijkheden kan een eDiscovery-manager of beheerder van een multi-geoten tenant eDiscovery alleen uitvoeren op de centrale locatie van die tenant.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="ae2a4-107">Ter ondersteuning van de mogelijkheid om eDiscovery uit te voeren voor satellietlocaties, is een nieuwe parameter voor compliancebeveiligingsfilter 'Regio' beschikbaar via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="ae2a4-108">Deze parameter kan worden gebruikt door tenants waarvan de centrale locatie zich in Noord-Amerika, Europa of Azië en de Stille Oceaan bevindt.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="ae2a4-109">Advanced eDiscovery wordt aanbevolen voor tenants waarvan de centrale locatie zich niet in Noord-Amerika, Europa of Azië/Stille Oceaan bevindt en die eDiscovery moeten uitvoeren op satellietlocatielocaties.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="ae2a4-110">De globale Microsoft 365-beheerder moet eDiscovery Manager-machtigingen toewijzen om anderen toe te staan eDiscovery uit te voeren en een 'Regio'-parameter toe te wijzen in het toepasselijke compliancebeveiligingsfilter om de regio voor het uitvoeren van eDiscovery op te geven als satellietlocatie, anders wordt er geen eDiscovery uitgevoerd voor de satellietlocatie.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="ae2a4-111">Wanneer de rol eDiscovery Manager of Beheerder is ingesteld voor een bepaalde satellietlocatie, kan eDiscovery Manager of Beheerder alleen eDiscovery-zoekacties uitvoeren op de SharePoint-sites en OneDrive-sites op die satellietlocatie.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-111">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location.</span></span> <span data-ttu-id="ae2a4-112">Als een eDiscovery Manager of Beheerder probeert te zoeken naar SharePoint of OneDrive sites buiten de opgegeven satellietlocatie, worden er geen resultaten geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-112">If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned.</span></span> <span data-ttu-id="ae2a4-113">Wanneer de eDiscovery Manager of Beheerder voor een satellietlocatie een export activeert, worden gegevens ook geëxporteerd naar het Azure-exemplaar van die regio.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-113">Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region.</span></span> <span data-ttu-id="ae2a4-114">Dit helpt organisaties om aan de naleving te blijven voldoen door niet toe te staan dat inhoud wordt geëxporteerd over gecontroleerde randen.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-114">This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="ae2a4-115">Als een eDiscovery Manager moet zoeken op meerdere SharePoint-satellietlocaties, moet er een ander gebruikersaccount worden gemaakt voor eDiscovery Manager, dat de alternatieve satellietlocatie aangeeft waar de OneDrive- of SharePoint-sites zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="ae2a4-116">Het beveiligingsfilter voor naleving voor een regio instellen:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="ae2a4-117">Verbinding maken om Microsoft 365 Beveiligings- & Compliance center PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae2a4-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="ae2a4-118">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="ae2a4-119">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="ae2a4-120">Zie het [artikel New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) voor aanvullende parameters en syntaxis.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>