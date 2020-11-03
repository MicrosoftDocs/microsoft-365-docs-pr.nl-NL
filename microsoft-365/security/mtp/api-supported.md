---
title: Ondersteunde Microsoft 365 Defender-Api's
description: Ondersteunde Microsoft 365 Defender-Api's
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844958"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="a77f1-104">Ondersteunde Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="a77f1-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a77f1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a77f1-105">**Applies to:**</span></span>
- <span data-ttu-id="a77f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a77f1-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="a77f1-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a77f1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a77f1-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="a77f1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="a77f1-109">Uri's van eindpunt:</span><span class="sxs-lookup"><span data-stu-id="a77f1-109">End Point URIs:</span></span>

- <span data-ttu-id="a77f1-110">De basis-URI van de service is: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a77f1-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="a77f1-111">Voor betere prestaties kunt u Server dichter gebruiken voor uw geografische locatie:</span><span class="sxs-lookup"><span data-stu-id="a77f1-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="a77f1-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a77f1-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="a77f1-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a77f1-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="a77f1-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a77f1-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="a77f1-115">De resource voor het verwerving van tokens moet zijn: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a77f1-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="a77f1-116">Alle Api's onder ```/api``` Path zijn OData-api's.</span><span class="sxs-lookup"><span data-stu-id="a77f1-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="a77f1-117">namelijk. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="a77f1-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="a77f1-118">Lijst met beschikbare Api's:</span><span class="sxs-lookup"><span data-stu-id="a77f1-118">List of available APIs:</span></span>

<span data-ttu-id="a77f1-119">Rond</span><span class="sxs-lookup"><span data-stu-id="a77f1-119">Topic</span></span> | <span data-ttu-id="a77f1-120">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a77f1-120">Description</span></span>
:---|:---
[<span data-ttu-id="a77f1-121">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="a77f1-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="a77f1-122">Voer geavanceerde jacht-query's uit via API.</span><span class="sxs-lookup"><span data-stu-id="a77f1-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="a77f1-123">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="a77f1-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="a77f1-124">Incidentele API-oproepen uitvoeren, zoals: incidenten vermelden, incident bijwerken en meer.</span><span class="sxs-lookup"><span data-stu-id="a77f1-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
