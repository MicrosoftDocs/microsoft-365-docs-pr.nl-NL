---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
keywords: MTP, API, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719320"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="5eef8-104">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="5eef8-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5eef8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5eef8-105">**Applies to:**</span></span>
- <span data-ttu-id="5eef8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5eef8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5eef8-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5eef8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5eef8-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="5eef8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="5eef8-109">Lijst met beschikbare Api's</span><span class="sxs-lookup"><span data-stu-id="5eef8-109">List of available APIs</span></span>

<span data-ttu-id="5eef8-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="5eef8-110">Article</span></span> | <span data-ttu-id="5eef8-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5eef8-111">Description</span></span>
-|-
[<span data-ttu-id="5eef8-112">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="5eef8-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="5eef8-113">Voer geavanceerde zoekopdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="5eef8-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="5eef8-114">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="5eef8-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="5eef8-115">U kunt lijsten met behulp van een lijst en update.</span><span class="sxs-lookup"><span data-stu-id="5eef8-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="5eef8-116">Url's van eindpunten</span><span class="sxs-lookup"><span data-stu-id="5eef8-116">Endpoint URIs</span></span>

<span data-ttu-id="5eef8-117">De basis-URI voor beide belangrijkste Api's is: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="5eef8-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="5eef8-118">Voor betere prestaties gebruikt u een server dichter bij uw geolocatie:</span><span class="sxs-lookup"><span data-stu-id="5eef8-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="5eef8-119">De Verenigde Staten: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5eef8-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="5eef8-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5eef8-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="5eef8-121">Het Verenigd Koninkrijk: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5eef8-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="5eef8-122">Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="5eef8-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="5eef8-123">Alle Api's langs het `/api` pad gebruiken het [OData](https://docs.microsoft.com/odata/overview) -protocol, bijvoorbeeld https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="5eef8-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5eef8-124">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5eef8-124">Related articles</span></span>

- [<span data-ttu-id="5eef8-125">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="5eef8-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5eef8-126">Toegang tot de Microsoft Threat Protection-Api's</span><span class="sxs-lookup"><span data-stu-id="5eef8-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="5eef8-127">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="5eef8-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5eef8-128">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="5eef8-128">Understand error codes</span></span>](api-error-codes.md)
