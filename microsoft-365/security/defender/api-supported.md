---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
keywords: Microsoft 365 Defender, API's, api
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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985082"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="f953a-104">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="f953a-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f953a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f953a-105">**Applies to:**</span></span>
- <span data-ttu-id="f953a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f953a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f953a-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="f953a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f953a-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="f953a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="f953a-109">Lijst met beschikbare API's</span><span class="sxs-lookup"><span data-stu-id="f953a-109">List of available APIs</span></span>

<span data-ttu-id="f953a-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="f953a-110">Article</span></span> | <span data-ttu-id="f953a-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f953a-111">Description</span></span>
-|-
[<span data-ttu-id="f953a-112">API voor geavanceerde opsporing</span><span class="sxs-lookup"><span data-stu-id="f953a-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="f953a-113">Geavanceerde zoekquery's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f953a-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="f953a-114">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="f953a-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="f953a-115">Lijst en werk incidenten bij, samen met andere praktische taken.</span><span class="sxs-lookup"><span data-stu-id="f953a-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="f953a-116">[Streaming API](streaming-api.md) (preview)</span><span class="sxs-lookup"><span data-stu-id="f953a-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="f953a-117">Verzend realtime gebeurtenissen en waarschuwingen als ze in één gegevensstroom voorkomen.</span><span class="sxs-lookup"><span data-stu-id="f953a-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="f953a-118">Eindpunt-URL's</span><span class="sxs-lookup"><span data-stu-id="f953a-118">Endpoint URIs</span></span>

<span data-ttu-id="f953a-119">De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="f953a-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="f953a-120">Voor betere prestaties gebruikt u een server die dichter bij uw geolocatie staat:</span><span class="sxs-lookup"><span data-stu-id="f953a-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="f953a-121">De Verenigde Staten: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f953a-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="f953a-122">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f953a-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="f953a-123">Het Verenigd Koninkrijk: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f953a-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="f953a-124">Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com tot .</span><span class="sxs-lookup"><span data-stu-id="f953a-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="f953a-125">Alle API's langs `/api` het pad gebruiken het [OData-protocol,](/odata/overview) bijvoorbeeld https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="f953a-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f953a-126">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f953a-126">Related articles</span></span>

- [<span data-ttu-id="f953a-127">Microsoft 365 Defender OVERZICHT VAN API's</span><span class="sxs-lookup"><span data-stu-id="f953a-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f953a-128">Toegang tot de Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="f953a-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f953a-129">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="f953a-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="f953a-130">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="f953a-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="f953a-131">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="f953a-131">Understand error codes</span></span>](api-error-codes.md)
