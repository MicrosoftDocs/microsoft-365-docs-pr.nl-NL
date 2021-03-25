---
title: Ondersteunde API's voor Microsoft Defender voor eindpunten
ms.reviewer: ''
description: Meer informatie over de specifieke ondersteunde Microsoft Defender voor eindpunten waar u API-oproepen naar kunt maken.
keywords: api's, ondersteunde api's, actor, waarschuwingen, apparaat, gebruiker, domein, ip, bestand, geavanceerde query's, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198318"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="1b051-104">Ondersteunde API's voor Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="1b051-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1b051-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1b051-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1b051-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1b051-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b051-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1b051-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="1b051-108">Endpoint URI en versieverken</span><span class="sxs-lookup"><span data-stu-id="1b051-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="1b051-109">Eindpunt-URI:</span><span class="sxs-lookup"><span data-stu-id="1b051-109">Endpoint URI:</span></span>

> <span data-ttu-id="1b051-110">De servicebasis URI is: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1b051-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="1b051-111">De query's op basis van OData hebben het voorvoegsel '/api'.</span><span class="sxs-lookup"><span data-stu-id="1b051-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="1b051-112">Als u bijvoorbeeld waarschuwingen wilt ontvangen, kunt u GET-aanvraag verzenden naar https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="1b051-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="1b051-113">Versiering:</span><span class="sxs-lookup"><span data-stu-id="1b051-113">Versioning:</span></span>

> <span data-ttu-id="1b051-114">De API ondersteunt versieversies.</span><span class="sxs-lookup"><span data-stu-id="1b051-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="1b051-115">De huidige versie is **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="1b051-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="1b051-116">Als u een specifieke versie wilt gebruiken, gebruikt u deze indeling: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="1b051-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="1b051-117">Bijvoorbeeld: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="1b051-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="1b051-118">Als u geen versie opgeeft (bijvoorbeeld) gaat u https://api.securitycenter.microsoft.com/api/alerts naar de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="1b051-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="1b051-119">Meer informatie over de afzonderlijke ondersteunde entiteiten waar u API-oproepen naar kunt uitvoeren en details zoals HTTP-aanvraagwaarden, aanvraagkoppen en verwachte antwoorden.</span><span class="sxs-lookup"><span data-stu-id="1b051-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1b051-120">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="1b051-120">In this section</span></span>

<span data-ttu-id="1b051-121">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="1b051-121">Topic</span></span> | <span data-ttu-id="1b051-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1b051-122">Description</span></span>
:---|:---
<span data-ttu-id="1b051-123">Geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="1b051-123">Advanced Hunting</span></span> | <span data-ttu-id="1b051-124">Query's uitvoeren vanuit API.</span><span class="sxs-lookup"><span data-stu-id="1b051-124">Run queries from API.</span></span>
<span data-ttu-id="1b051-125">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1b051-125">Alerts</span></span> | <span data-ttu-id="1b051-126">Voer API-oproepen uit, zoals waarschuwingen ontvangen, waarschuwing maken, waarschuwing bijwerken en meer.</span><span class="sxs-lookup"><span data-stu-id="1b051-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="1b051-127">Domeinen</span><span class="sxs-lookup"><span data-stu-id="1b051-127">Domains</span></span> | <span data-ttu-id="1b051-128">Voer API-oproepen uit, zoals domeingerelateerde apparaten, domeinstatistieken en meer.</span><span class="sxs-lookup"><span data-stu-id="1b051-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="1b051-129">Bestanden</span><span class="sxs-lookup"><span data-stu-id="1b051-129">Files</span></span> | <span data-ttu-id="1b051-130">Voer API-oproepen uit, zoals bestandsgegevens, bestandsgerelateerde waarschuwingen, bestandsgerelateerde apparaten en bestandsstatistieken.</span><span class="sxs-lookup"><span data-stu-id="1b051-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="1b051-131">IPs</span><span class="sxs-lookup"><span data-stu-id="1b051-131">IPs</span></span> | <span data-ttu-id="1b051-132">Voer API-oproepen uit, zoals IP-gerelateerde waarschuwingen ontvangen en IP-statistieken krijgen.</span><span class="sxs-lookup"><span data-stu-id="1b051-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="1b051-133">Machines</span><span class="sxs-lookup"><span data-stu-id="1b051-133">Machines</span></span> | <span data-ttu-id="1b051-134">Voer API-oproepen uit, zoals apparaten op te halen, apparaten op te vragen via id, informatie over aangemelde gebruikers, tags bewerken en meer.</span><span class="sxs-lookup"><span data-stu-id="1b051-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="1b051-135">Machineacties</span><span class="sxs-lookup"><span data-stu-id="1b051-135">Machine Actions</span></span> | <span data-ttu-id="1b051-136">Voer API-oproep uit, zoals Isolatie, Anti-virusscan uitvoeren en meer.</span><span class="sxs-lookup"><span data-stu-id="1b051-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="1b051-137">Indicatoren</span><span class="sxs-lookup"><span data-stu-id="1b051-137">Indicators</span></span> | <span data-ttu-id="1b051-138">Voer API-oproep uit, zoals Indicator maken, Indicatoren op te halen en indicatoren te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1b051-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="1b051-139">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="1b051-139">Users</span></span> | <span data-ttu-id="1b051-140">Voer API-oproepen uit, zoals waarschuwingen voor gebruikers en apparaten die aan de gebruiker zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="1b051-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="1b051-141">Score</span><span class="sxs-lookup"><span data-stu-id="1b051-141">Score</span></span> | <span data-ttu-id="1b051-142">Voer API-oproepen uit, zoals blootstellingsscore krijgen of apparaatveilige score krijgen.</span><span class="sxs-lookup"><span data-stu-id="1b051-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="1b051-143">Software</span><span class="sxs-lookup"><span data-stu-id="1b051-143">Software</span></span> | <span data-ttu-id="1b051-144">Voer API-oproepen uit, zoals lijstproblemen met software.</span><span class="sxs-lookup"><span data-stu-id="1b051-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="1b051-145">Kwetsbaarheid</span><span class="sxs-lookup"><span data-stu-id="1b051-145">Vulnerability</span></span> | <span data-ttu-id="1b051-146">Voer API-oproepen uit, zoals lijstapparaten op kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="1b051-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="1b051-147">Aanbeveling</span><span class="sxs-lookup"><span data-stu-id="1b051-147">Recommendation</span></span> | <span data-ttu-id="1b051-148">Voer API-oproepen uit, zoals Aanbeveling per id ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1b051-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b051-149">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1b051-149">See also</span></span>
- [<span data-ttu-id="1b051-150">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="1b051-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
