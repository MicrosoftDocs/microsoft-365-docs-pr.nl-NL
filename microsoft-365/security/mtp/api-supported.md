---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
keywords: MTP, API's, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926196"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="c7164-104">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="c7164-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c7164-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c7164-105">**Applies to:**</span></span>
- <span data-ttu-id="c7164-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7164-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7164-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="c7164-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c7164-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="c7164-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="c7164-109">Lijst met beschikbare API's</span><span class="sxs-lookup"><span data-stu-id="c7164-109">List of available APIs</span></span>

<span data-ttu-id="c7164-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="c7164-110">Article</span></span> | <span data-ttu-id="c7164-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c7164-111">Description</span></span>
-|-
[<span data-ttu-id="c7164-112">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="c7164-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="c7164-113">Voer geavanceerde zoekquery's uit.</span><span class="sxs-lookup"><span data-stu-id="c7164-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="c7164-114">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="c7164-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="c7164-115">Vermeld en werk incidenten bij, samen met andere praktische taken.</span><span class="sxs-lookup"><span data-stu-id="c7164-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="c7164-116">URI's voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="c7164-116">Endpoint URIs</span></span>

<span data-ttu-id="c7164-117">De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="c7164-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="c7164-118">Gebruik voor betere prestaties een server dichter bij uw geolocatie:</span><span class="sxs-lookup"><span data-stu-id="c7164-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="c7164-119">Verenigde Staten: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c7164-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="c7164-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c7164-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="c7164-121">Verenigd Koninkrijk: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c7164-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="c7164-122">Tokens kunnen worden verkregen door toegang te krijgen tot https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="c7164-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="c7164-123">Alle API's op `/api` het pad maken gebruik van het [OData-protocol,](https://docs.microsoft.com/odata/overview) https://api.security.microsoft.com/api/incidents bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="c7164-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c7164-124">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c7164-124">Related articles</span></span>

- [<span data-ttu-id="c7164-125">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="c7164-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c7164-126">Toegang tot de Microsoft Threat Protection-API's</span><span class="sxs-lookup"><span data-stu-id="c7164-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="c7164-127">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="c7164-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c7164-128">Meer te weten komen over foutcodes</span><span class="sxs-lookup"><span data-stu-id="c7164-128">Understand error codes</span></span>](api-error-codes.md)
