---
title: SharePoint opslagquota in multi-geo-omgevingen
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
description: Meer informatie SharePoint opslagquota's in multi-geoomgevingen en hoe quota's kunnen worden beheerd door de SharePoint Online-beheerder.
ms.openlocfilehash: 0843407e7926027e28cdd1f5893c4aafec4e1cd5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230089"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="92e3e-103">SharePoint opslagquota in multi-geo-omgevingen</span><span class="sxs-lookup"><span data-stu-id="92e3e-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="92e3e-104">Standaard delen alle geografische locaties van een multi-geo-omgeving het beschikbare opslagquotum voor tenants.</span><span class="sxs-lookup"><span data-stu-id="92e3e-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="92e3e-105">Met de SharePoint voor geografische opslagquota kunt u het opslagquotum voor elke geografische locatie beheren.</span><span class="sxs-lookup"><span data-stu-id="92e3e-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="92e3e-106">Wanneer u een opslagquotum toewijst voor een geografische locatie, wordt dit de maximale hoeveelheid opslagruimte die beschikbaar is voor die geografische locatie en wordt deze afgetrokken van het beschikbare tenantopslagquotum.</span><span class="sxs-lookup"><span data-stu-id="92e3e-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="92e3e-107">Het resterende beschikbare tenantopslagquotum wordt vervolgens gedeeld over de geconfigureerde geografische locaties waarvoor geen specifiek opslagquotum is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="92e3e-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="92e3e-108">Het SharePoint opslagquotum voor elke geografische locatie kan worden toegewezen door de SharePoint Online-beheerder door verbinding te maken met de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="92e3e-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="92e3e-109">Geobeheerders voor satellietlocaties kunnen het opslagquotum bekijken, maar kunnen het niet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="92e3e-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="92e3e-110">Een opslagquotum configureren voor een geografische locatie</span><span class="sxs-lookup"><span data-stu-id="92e3e-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="92e3e-111">Gebruik de [Microsoft Office SharePoint Online module en](https://www.microsoft.com/download/details.aspx?id=35588) maak verbinding met de centrale locatie om het opslagquotum voor een geografische locatie toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="92e3e-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588) and connect to the central location to allocate the storage quota for a geo location.</span></span>

<span data-ttu-id="92e3e-112">Als u een Storage quota voor een locatie wilt toewijzen, moet u cmdlet uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="92e3e-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

<span data-ttu-id="92e3e-113">Als u Storage quotum voor de huidige geografische locatie wilt weergeven, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="92e3e-113">To view Storage Quota for the current geo location, run:</span></span>

```powershell
Get-SPOGeoStorageQuota
```

![Schermafbeelding van PowerShell-venster met Get-SPOGeoStorageQuota cmdlet](../media/multi-geo-storage-quota.png)

<span data-ttu-id="92e3e-115">Als u de Storage voor alle geografische locaties wilt weergeven, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="92e3e-115">To view Storage Quota for all geo locations, run:</span></span>

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

<span data-ttu-id="92e3e-116">Als u het toegewezen opslagquotum voor een geografische locatie wilt verwijderen, stelt u `StorageQuota value = 0` het volgende in:</span><span class="sxs-lookup"><span data-stu-id="92e3e-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
