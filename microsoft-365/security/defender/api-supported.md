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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056664"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="a73bd-104">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="a73bd-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a73bd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a73bd-105">**Applies to:**</span></span>
- <span data-ttu-id="a73bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a73bd-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a73bd-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="a73bd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a73bd-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="a73bd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="a73bd-109">Lijst met beschikbare API's</span><span class="sxs-lookup"><span data-stu-id="a73bd-109">List of available APIs</span></span>

<span data-ttu-id="a73bd-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="a73bd-110">Article</span></span> | <span data-ttu-id="a73bd-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a73bd-111">Description</span></span>
-|-
[<span data-ttu-id="a73bd-112">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="a73bd-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="a73bd-113">Geavanceerde zoekquery's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a73bd-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="a73bd-114">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="a73bd-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="a73bd-115">Lijst en werk incidenten bij, samen met andere praktische taken.</span><span class="sxs-lookup"><span data-stu-id="a73bd-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="a73bd-116">Eindpunt-URL's</span><span class="sxs-lookup"><span data-stu-id="a73bd-116">Endpoint URIs</span></span>

<span data-ttu-id="a73bd-117">De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="a73bd-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="a73bd-118">Voor betere prestaties gebruikt u een server die dichter bij uw geolocatie staat:</span><span class="sxs-lookup"><span data-stu-id="a73bd-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="a73bd-119">De Verenigde Staten: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a73bd-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="a73bd-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a73bd-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="a73bd-121">Het Verenigd Koninkrijk: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a73bd-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="a73bd-122">Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com tot .</span><span class="sxs-lookup"><span data-stu-id="a73bd-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="a73bd-123">Alle API's langs `/api` het pad gebruiken het [OData-protocol,](/odata/overview) bijvoorbeeld https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="a73bd-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a73bd-124">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a73bd-124">Related articles</span></span>

- [<span data-ttu-id="a73bd-125">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="a73bd-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a73bd-126">Toegang tot de API's voor Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a73bd-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="a73bd-127">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="a73bd-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a73bd-128">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="a73bd-128">Understand error codes</span></span>](api-error-codes.md)