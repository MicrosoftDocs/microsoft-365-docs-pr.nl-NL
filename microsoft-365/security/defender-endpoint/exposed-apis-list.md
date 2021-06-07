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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63e38d5c9cfe50d1fa4cda1f7ae9c7df55a45083
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788833"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="16b3c-104">Ondersteunde API's voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="16b3c-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16b3c-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="16b3c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="16b3c-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="16b3c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16b3c-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="16b3c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="16b3c-108">Endpoint URI en versieverken</span><span class="sxs-lookup"><span data-stu-id="16b3c-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="16b3c-109">Eindpunt-URI</span><span class="sxs-lookup"><span data-stu-id="16b3c-109">Endpoint URI</span></span>

> <span data-ttu-id="16b3c-110">De servicebasis URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="16b3c-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="16b3c-111">De query's op basis van OData hebben het voorvoegsel '/api'.</span><span class="sxs-lookup"><span data-stu-id="16b3c-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="16b3c-112">Als u bijvoorbeeld waarschuwingen wilt ontvangen, kunt u GET-aanvraag verzenden naar [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="16b3c-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="16b3c-113">Versiering</span><span class="sxs-lookup"><span data-stu-id="16b3c-113">Versioning</span></span>

> <span data-ttu-id="16b3c-114">De API ondersteunt versieversies.</span><span class="sxs-lookup"><span data-stu-id="16b3c-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="16b3c-115">De huidige versie is **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="16b3c-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="16b3c-116">Als u een specifieke versie wilt gebruiken, gebruikt u deze indeling: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="16b3c-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="16b3c-117">Bijvoorbeeld:`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="16b3c-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="16b3c-118">Als u geen versie opgeeft (bijvoorbeeld) gaat u `https://api.securitycenter.microsoft.com/api/alerts` naar de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="16b3c-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="16b3c-119">Meer informatie over de afzonderlijke ondersteunde entiteiten waar u API-oproepen naar kunt uitvoeren en details zoals HTTP-aanvraagwaarden, aanvraagkoppen en verwachte antwoorden.</span><span class="sxs-lookup"><span data-stu-id="16b3c-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="16b3c-120">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="16b3c-120">In this section</span></span>

<span data-ttu-id="16b3c-121">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="16b3c-121">Topic</span></span> | <span data-ttu-id="16b3c-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="16b3c-122">Description</span></span>
:---|:---
[<span data-ttu-id="16b3c-123">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="16b3c-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="16b3c-124">Query's uitvoeren vanuit API.</span><span class="sxs-lookup"><span data-stu-id="16b3c-124">Run queries from API.</span></span>
[<span data-ttu-id="16b3c-125">Waarschuwingsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="16b3c-126">Voer API-oproepen uit, \- zoals waarschuwingen ontvangen, waarschuwing maken, waarschuwing bijwerken en meer.</span><span class="sxs-lookup"><span data-stu-id="16b3c-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="16b3c-127">Beoordelingsmethoden en -eigenschappen per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="16b3c-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="16b3c-128">Voer API-oproepen uit, zoals \- een veilige configuratiebeoordeling exporteren, beoordeling van de softwarevoorraad exporteren en evaluatie van beveiligingsproblemen met software exporteren.</span><span class="sxs-lookup"><span data-stu-id="16b3c-128">Run API calls such as \- export secure configuration assessment, export software inventory assessment,  and export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="16b3c-129">Methoden en eigenschappen voor geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="16b3c-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="16b3c-130">Voer API-oproepen uit, \- zoals ophalen van onderzoek.</span><span class="sxs-lookup"><span data-stu-id="16b3c-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="16b3c-131">Waarschuwingen met betrekking tot domeinen ophalen</span><span class="sxs-lookup"><span data-stu-id="16b3c-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="16b3c-132">Voer API-oproepen uit, \- zoals domeingerelateerde apparaten, domeinstatistieken en meer.</span><span class="sxs-lookup"><span data-stu-id="16b3c-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="16b3c-133">Bestandsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="16b3c-134">Voer API-oproepen uit, \- zoals bestandsgegevens, bestandsgerelateerde waarschuwingen, bestandsgerelateerde apparaten en bestandsstatistieken.</span><span class="sxs-lookup"><span data-stu-id="16b3c-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="16b3c-135">Methoden en eigenschappen van indicatoren</span><span class="sxs-lookup"><span data-stu-id="16b3c-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="16b3c-136">Voer API-oproep uit, \- zoals Indicatoren op halen, Indicator maken en indicatoren verwijderen.</span><span class="sxs-lookup"><span data-stu-id="16b3c-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="16b3c-137">Waarschuwingen met betrekking tot IP ophalen</span><span class="sxs-lookup"><span data-stu-id="16b3c-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="16b3c-138">Voer API-oproepen uit, \- zoals IP-gerelateerde waarschuwingen ontvangen en IP-statistieken krijgen.</span><span class="sxs-lookup"><span data-stu-id="16b3c-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="16b3c-139">Computermethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="16b3c-140">Voer API-oproepen uit, zoals apparaten op te halen, apparaten op te vragen via id, informatie over \- aangemelde gebruikers, tags bewerken en meer.</span><span class="sxs-lookup"><span data-stu-id="16b3c-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="16b3c-141">Actiemethoden en -eigenschappen van computer</span><span class="sxs-lookup"><span data-stu-id="16b3c-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="16b3c-142">Voer API-oproep uit, \- zoals Isolatie, Anti-virusscan uitvoeren en meer.</span><span class="sxs-lookup"><span data-stu-id="16b3c-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="16b3c-143">Aanbevelingsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="16b3c-144">Voer API-oproepen uit, \- zoals een aanbeveling per id.</span><span class="sxs-lookup"><span data-stu-id="16b3c-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="16b3c-145">Methoden en eigenschappen van herstelactiviteiten</span><span class="sxs-lookup"><span data-stu-id="16b3c-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="16b3c-146">Voer API-oproep uit, zoals alle hersteltaken, de hersteltaak voor blootgestelde apparaten krijgen en één \- hersteltaak per id krijgen.</span><span class="sxs-lookup"><span data-stu-id="16b3c-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="16b3c-147">Scoringsmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="16b3c-148">Voer API-oproepen uit, \- zoals blootstellingsscore krijgen of apparaatveilige score krijgen.</span><span class="sxs-lookup"><span data-stu-id="16b3c-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="16b3c-149">Softwaremethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="16b3c-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="16b3c-150">Voer API-oproepen uit, \- zoals lijstproblemen met software.</span><span class="sxs-lookup"><span data-stu-id="16b3c-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="16b3c-151">Gebruikersmethoden</span><span class="sxs-lookup"><span data-stu-id="16b3c-151">User methods</span></span>](user.md) | <span data-ttu-id="16b3c-152">Voer API-oproepen uit, \- zoals waarschuwingen voor gebruikers en apparaten die aan de gebruiker zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="16b3c-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="16b3c-153">Methoden en eigenschappen van beveiligingsproblemen</span><span class="sxs-lookup"><span data-stu-id="16b3c-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="16b3c-154">Voer API-oproepen uit, zoals \- lijstapparaten op kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="16b3c-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="16b3c-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="16b3c-155">See also</span></span>

- [<span data-ttu-id="16b3c-156">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="16b3c-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="16b3c-157">Releasenotities van Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="16b3c-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
