---
title: Apparaten zoeken via interne IP-API
description: Apparaten zoeken die worden gezien met het aangevraagde interne IP-adres in het tijdbereik van 15 minuten vóór en na een bepaalde tijdstempel
keywords: api's, graph api, ondersteunde api's, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769435"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="84c8c-104">Apparaten zoeken via interne IP-API</span><span class="sxs-lookup"><span data-stu-id="84c8c-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="84c8c-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="84c8c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="84c8c-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="84c8c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="84c8c-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="84c8c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="84c8c-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="84c8c-108">API description</span></span>
<span data-ttu-id="84c8c-109">Zoek [machines](machine.md) die worden gezien met het aangevraagde interne IP-adres in het tijdbereik van 15 minuten vóór en na een bepaalde tijdstempel.</span><span class="sxs-lookup"><span data-stu-id="84c8c-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="84c8c-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="84c8c-110">Limitations</span></span>
1. <span data-ttu-id="84c8c-111">De opgegeven tijdstempel moet de afgelopen 30 dagen zijn.</span><span class="sxs-lookup"><span data-stu-id="84c8c-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="84c8c-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="84c8c-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="84c8c-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="84c8c-113">Permissions</span></span>
<span data-ttu-id="84c8c-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="84c8c-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="84c8c-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="84c8c-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="84c8c-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="84c8c-116">Permission type</span></span> |   <span data-ttu-id="84c8c-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="84c8c-117">Permission</span></span>  |   <span data-ttu-id="84c8c-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="84c8c-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="84c8c-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="84c8c-119">Application</span></span> |   <span data-ttu-id="84c8c-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="84c8c-120">Machine.Read.All</span></span> |  <span data-ttu-id="84c8c-121">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="84c8c-121">'Read all machine profiles'</span></span>
<span data-ttu-id="84c8c-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="84c8c-122">Application</span></span> |   <span data-ttu-id="84c8c-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="84c8c-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="84c8c-124">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="84c8c-124">'Read and write all machine information'</span></span>
<span data-ttu-id="84c8c-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="84c8c-125">Delegated (work or school account)</span></span> | <span data-ttu-id="84c8c-126">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="84c8c-126">Machine.Read</span></span> | <span data-ttu-id="84c8c-127">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="84c8c-127">'Read machine information'</span></span>
<span data-ttu-id="84c8c-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="84c8c-128">Delegated (work or school account)</span></span> | <span data-ttu-id="84c8c-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="84c8c-129">Machine.ReadWrite</span></span> | <span data-ttu-id="84c8c-130">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="84c8c-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="84c8c-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="84c8c-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="84c8c-132">Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="84c8c-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="84c8c-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="84c8c-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="84c8c-134">Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="84c8c-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="84c8c-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="84c8c-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="84c8c-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="84c8c-136">Request headers</span></span>

<span data-ttu-id="84c8c-137">Naam</span><span class="sxs-lookup"><span data-stu-id="84c8c-137">Name</span></span> | <span data-ttu-id="84c8c-138">Type</span><span class="sxs-lookup"><span data-stu-id="84c8c-138">Type</span></span> | <span data-ttu-id="84c8c-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="84c8c-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="84c8c-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="84c8c-140">Authorization</span></span> | <span data-ttu-id="84c8c-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="84c8c-141">String</span></span> | <span data-ttu-id="84c8c-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="84c8c-142">Bearer {token}.</span></span> <span data-ttu-id="84c8c-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="84c8c-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="84c8c-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="84c8c-144">Request body</span></span>
<span data-ttu-id="84c8c-145">Leeg</span><span class="sxs-lookup"><span data-stu-id="84c8c-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="84c8c-146">Antwoord</span><span class="sxs-lookup"><span data-stu-id="84c8c-146">Response</span></span>
<span data-ttu-id="84c8c-147">Als dit is gelukt- 200 OK met de lijst met de machines in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="84c8c-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="84c8c-148">Als de tijdstempel niet in de afgelopen 30 dagen - 400 Bad Request is.</span><span class="sxs-lookup"><span data-stu-id="84c8c-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="84c8c-149">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="84c8c-149">Example</span></span>

<span data-ttu-id="84c8c-150">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="84c8c-150">**Request**</span></span>

<span data-ttu-id="84c8c-151">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="84c8c-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
