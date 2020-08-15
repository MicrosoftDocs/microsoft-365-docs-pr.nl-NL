---
title: SharePoint-opslag quota's in meerdere geografische omgevingen
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
description: Meer informatie over SharePoint-opslagquota in omgevingen met meerdere geografische omgevingen en de manier waarop quota's kunnen worden beheerd door de SharePoint Online-beheerder.
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689570"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="b462c-103">SharePoint-opslag quota's in meerdere geografische omgevingen</span><span class="sxs-lookup"><span data-stu-id="b462c-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="b462c-104">Standaard delen alle geografische locaties van een multi-geografische omgeving het beschikbare opslagquotum voor de Tenant.</span><span class="sxs-lookup"><span data-stu-id="b462c-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="b462c-105">Met de instelling SharePoint geo Storage target kunt u de opslagquota voor elke geografische locatie beheren.</span><span class="sxs-lookup"><span data-stu-id="b462c-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="b462c-106">Wanneer u een opslagquotum voor een geografische locatie toewijst, wordt dit de maximale hoeveelheid opslagruimte voor die geografische locatie en wordt de beschikbare opslagquota van de Tenant afgetrokken.</span><span class="sxs-lookup"><span data-stu-id="b462c-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="b462c-107">De resterende beschikbare opslagquota voor de Tenant wordt vervolgens gedeeld via de geconfigureerde geo-locaties waarvoor geen specifiek opslagquotum is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b462c-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="b462c-108">De SharePoint Online-beheerder kan het SharePoint-opslagquotum voor een Geo Location toewijzen door verbinding te maken met de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="b462c-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="b462c-109">Geo-beheerders voor satelliet locaties kunnen de opslagquota bekijken maar deze niet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="b462c-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="b462c-110">Een opslagquotum configureren voor een geografische locatie</span><span class="sxs-lookup"><span data-stu-id="b462c-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="b462c-111">Gebruik de [module Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588 ) en maak verbinding met de centrale locatie om het opslagquotum voor een geografische locatie toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b462c-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588 ) and connect to the central location to allocate the storage quota for a geo location.</span></span> 

<span data-ttu-id="b462c-112">Voer cmdlet uit om het opslagquotum voor een locatie toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="b462c-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

<span data-ttu-id="b462c-113">Voer het volgende uit om de opslag quota voor de huidige geografische locatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b462c-113">To view Storage Quota for the current geo location, run:</span></span>

`Get-SPOGeoStorageQuota`

![Schermafbeelding van het PowerShell-venster met de cmdlet Get-SPOGeoStorageQuota](../media/multi-geo-storage-quota.png)

<span data-ttu-id="b462c-115">Voer het volgende uit om het opslagquotum voor alle geografische locaties weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b462c-115">To view Storage Quota for all geo locations, run:</span></span>

`Get-SPOGeoStorageQuota -AllLocations`

<span data-ttu-id="b462c-116">Als u het toegewezen opslagquotum voor een geografische locatie wilt verwijderen, stelt u het `StorageQuota value = 0` volgende in:</span><span class="sxs-lookup"><span data-stu-id="b462c-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
