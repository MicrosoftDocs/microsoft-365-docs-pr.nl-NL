---
title: Ondersteunde API's voor Microsoft Defender voor Eindpunt
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
ms.openlocfilehash: ab3d3aa9a13b71f65d3d4335646e32a7e4270242
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061047"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="dbb87-104">Ondersteunde API's voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="dbb87-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbb87-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dbb87-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dbb87-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="dbb87-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbb87-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dbb87-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="dbb87-108">Endpoint URI en versieverken</span><span class="sxs-lookup"><span data-stu-id="dbb87-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="dbb87-109">Eindpunt-URI</span><span class="sxs-lookup"><span data-stu-id="dbb87-109">Endpoint URI</span></span>

> <span data-ttu-id="dbb87-110">De servicebasis URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="dbb87-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="dbb87-111">De query's op basis van OData hebben het voorvoegsel '/api'.</span><span class="sxs-lookup"><span data-stu-id="dbb87-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="dbb87-112">Als u bijvoorbeeld waarschuwingen wilt ontvangen, kunt u GET-aanvraag verzenden naar [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="dbb87-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="dbb87-113">Versiering</span><span class="sxs-lookup"><span data-stu-id="dbb87-113">Versioning</span></span>

> <span data-ttu-id="dbb87-114">De API ondersteunt versieversies.</span><span class="sxs-lookup"><span data-stu-id="dbb87-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="dbb87-115">De huidige versie is **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="dbb87-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="dbb87-116">Als u een specifieke versie wilt gebruiken, gebruikt u deze indeling: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="dbb87-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="dbb87-117">Bijvoorbeeld: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="dbb87-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="dbb87-118">Als u geen versie opgeeft (bijvoorbeeld) gaat u `https://api.securitycenter.microsoft.com/api/alerts` naar de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="dbb87-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="dbb87-119">Meer informatie over de afzonderlijke ondersteunde entiteiten waar u API-oproepen naar kunt uitvoeren en details zoals HTTP-aanvraagwaarden, aanvraagkoppen en verwachte antwoorden.</span><span class="sxs-lookup"><span data-stu-id="dbb87-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="dbb87-120">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="dbb87-120">In this section</span></span>

<span data-ttu-id="dbb87-121">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="dbb87-121">Topic</span></span> | <span data-ttu-id="dbb87-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="dbb87-122">Description</span></span>
:---|:---
[<span data-ttu-id="dbb87-123">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="dbb87-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="dbb87-124">Query's uitvoeren vanuit API.</span><span class="sxs-lookup"><span data-stu-id="dbb87-124">Run queries from API.</span></span>
[<span data-ttu-id="dbb87-125">Waarschuwingsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="dbb87-126">Voer API-oproepen uit, \- zoals waarschuwingen ontvangen, waarschuwing maken, waarschuwing bijwerken en meer.</span><span class="sxs-lookup"><span data-stu-id="dbb87-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="dbb87-127">Methoden en eigenschappen voor geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="dbb87-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="dbb87-128">Voer API-oproepen uit, \- zoals ophalen van onderzoek.</span><span class="sxs-lookup"><span data-stu-id="dbb87-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="dbb87-129">Waarschuwingen met betrekking tot domeinen ophalen</span><span class="sxs-lookup"><span data-stu-id="dbb87-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="dbb87-130">Voer API-oproepen uit, \- zoals domeingerelateerde apparaten, domeinstatistieken en meer.</span><span class="sxs-lookup"><span data-stu-id="dbb87-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="dbb87-131">Bestandsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="dbb87-132">Voer API-oproepen uit, \- zoals bestandsgegevens, bestandsgerelateerde waarschuwingen, bestandsgerelateerde apparaten en bestandsstatistieken.</span><span class="sxs-lookup"><span data-stu-id="dbb87-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="dbb87-133">Methoden en eigenschappen van indicatoren</span><span class="sxs-lookup"><span data-stu-id="dbb87-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="dbb87-134">Voer API-oproep uit, \- zoals Indicatoren op halen, Indicator maken en indicatoren verwijderen.</span><span class="sxs-lookup"><span data-stu-id="dbb87-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="dbb87-135">Waarschuwingen met betrekking tot IP ophalen</span><span class="sxs-lookup"><span data-stu-id="dbb87-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="dbb87-136">Voer API-oproepen uit, \- zoals IP-gerelateerde waarschuwingen ontvangen en IP-statistieken krijgen.</span><span class="sxs-lookup"><span data-stu-id="dbb87-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="dbb87-137">Computermethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="dbb87-138">Voer API-oproepen uit, zoals apparaten op te halen, apparaten op te vragen via id, informatie over \- aangemelde gebruikers, tags bewerken en meer.</span><span class="sxs-lookup"><span data-stu-id="dbb87-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="dbb87-139">Actiemethoden en -eigenschappen van computer</span><span class="sxs-lookup"><span data-stu-id="dbb87-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="dbb87-140">Voer API-oproep uit, \- zoals Isolatie, Anti-virusscan uitvoeren en meer.</span><span class="sxs-lookup"><span data-stu-id="dbb87-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="dbb87-141">Aanbevelingsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="dbb87-142">Voer API-oproepen uit, \- zoals een aanbeveling per id.</span><span class="sxs-lookup"><span data-stu-id="dbb87-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="dbb87-143">Methoden en eigenschappen voor herstelactiviteiten</span><span class="sxs-lookup"><span data-stu-id="dbb87-143">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="dbb87-144">Voer API-oproep uit, zoals alle hersteltaken, de hersteltaak voor blootgestelde apparaten krijgen en één \- hersteltaak per id krijgen.</span><span class="sxs-lookup"><span data-stu-id="dbb87-144">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="dbb87-145">Scoringsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-145">Score methods and properties</span></span>](score.md) | <span data-ttu-id="dbb87-146">Voer API-oproepen uit, \- zoals blootstellingsscore krijgen of apparaatveilige score krijgen.</span><span class="sxs-lookup"><span data-stu-id="dbb87-146">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="dbb87-147">Softwaremethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="dbb87-147">Software methods and properties</span></span>](software.md) | <span data-ttu-id="dbb87-148">Voer API-oproepen uit, \- zoals lijstproblemen met software.</span><span class="sxs-lookup"><span data-stu-id="dbb87-148">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="dbb87-149">Gebruikersmethoden</span><span class="sxs-lookup"><span data-stu-id="dbb87-149">User methods</span></span>](user.md) | <span data-ttu-id="dbb87-150">Voer API-oproepen uit, \- zoals waarschuwingen voor gebruikers en apparaten die aan de gebruiker zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="dbb87-150">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="dbb87-151">Methoden en eigenschappen van beveiligingsproblemen</span><span class="sxs-lookup"><span data-stu-id="dbb87-151">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="dbb87-152">Voer API-oproepen uit, zoals \- lijstapparaten op kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="dbb87-152">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb87-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dbb87-153">See also</span></span>

- [<span data-ttu-id="dbb87-154">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="dbb87-154">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="dbb87-155">Releasenotities van Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="dbb87-155">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
