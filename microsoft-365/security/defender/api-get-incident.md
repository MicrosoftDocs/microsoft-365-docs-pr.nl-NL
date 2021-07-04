---
title: Incident-API krijgen
description: Meer informatie over het gebruik van de API Voor incidenten krijgen om één incident in Microsoft 365 Defender.
keywords: api's, graph api, ondersteunde api's, downloaden, bestand, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289605"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="681ea-104">Api voor incidentgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="681ea-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="681ea-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="681ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="681ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="681ea-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="681ea-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="681ea-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="681ea-108">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="681ea-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="681ea-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="681ea-109">API description</span></span>

<span data-ttu-id="681ea-110">Haalt een specifiek incident op met de id</span><span class="sxs-lookup"><span data-stu-id="681ea-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="681ea-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="681ea-111">Limitations</span></span>

1. <span data-ttu-id="681ea-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="681ea-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="681ea-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="681ea-113">Permissions</span></span>

<span data-ttu-id="681ea-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="681ea-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="681ea-115">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="681ea-115">Permission type</span></span> | <span data-ttu-id="681ea-116">Machtiging</span><span class="sxs-lookup"><span data-stu-id="681ea-116">Permission</span></span> | <span data-ttu-id="681ea-117">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="681ea-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="681ea-118">Toepassing</span><span class="sxs-lookup"><span data-stu-id="681ea-118">Application</span></span> | <span data-ttu-id="681ea-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="681ea-119">Incident.Read.All</span></span> | <span data-ttu-id="681ea-120">'Alle incidenten lezen'</span><span class="sxs-lookup"><span data-stu-id="681ea-120">'Read all Incidents'</span></span>
<span data-ttu-id="681ea-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="681ea-121">Application</span></span> | <span data-ttu-id="681ea-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="681ea-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="681ea-123">'Alle incidenten lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="681ea-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="681ea-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="681ea-124">Delegated (work or school account)</span></span> | <span data-ttu-id="681ea-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="681ea-125">Incident.Read</span></span> | <span data-ttu-id="681ea-126">'Incidenten lezen'</span><span class="sxs-lookup"><span data-stu-id="681ea-126">'Read Incidents'</span></span>
<span data-ttu-id="681ea-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="681ea-127">Delegated (work or school account)</span></span> | <span data-ttu-id="681ea-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="681ea-128">Incident.ReadWrite</span></span> | <span data-ttu-id="681ea-129">'Incidenten lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="681ea-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="681ea-130">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="681ea-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="681ea-131">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'</span><span class="sxs-lookup"><span data-stu-id="681ea-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="681ea-132">Het antwoord bevat alleen incidenten waar de gebruiker aan wordt blootgesteld</span><span class="sxs-lookup"><span data-stu-id="681ea-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="681ea-133">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="681ea-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="681ea-134">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="681ea-134">Request headers</span></span>

<span data-ttu-id="681ea-135">Naam</span><span class="sxs-lookup"><span data-stu-id="681ea-135">Name</span></span> | <span data-ttu-id="681ea-136">Type</span><span class="sxs-lookup"><span data-stu-id="681ea-136">Type</span></span> | <span data-ttu-id="681ea-137">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="681ea-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="681ea-138">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="681ea-138">Authorization</span></span> | <span data-ttu-id="681ea-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="681ea-139">String</span></span> | <span data-ttu-id="681ea-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="681ea-140">Bearer {token}.</span></span> <span data-ttu-id="681ea-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="681ea-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="681ea-142">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="681ea-142">Request body</span></span>

<span data-ttu-id="681ea-143">Leeg</span><span class="sxs-lookup"><span data-stu-id="681ea-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="681ea-144">Antwoord</span><span class="sxs-lookup"><span data-stu-id="681ea-144">Response</span></span>

<span data-ttu-id="681ea-145">Als dit is gelukt, retourneert deze methode 200 OK en de incident-entiteit in de antwoordlichaam.</span><span class="sxs-lookup"><span data-stu-id="681ea-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="681ea-146">Als een incident met de opgegeven id niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="681ea-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="681ea-147">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="681ea-147">Example</span></span>

<span data-ttu-id="681ea-148">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="681ea-148">**Request**</span></span>

<span data-ttu-id="681ea-149">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="681ea-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
