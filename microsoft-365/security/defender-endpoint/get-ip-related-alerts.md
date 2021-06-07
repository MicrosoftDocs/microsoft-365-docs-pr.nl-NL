---
title: IP-gerelateerde waarschuwingen-API krijgen
description: Een verzameling waarschuwingen ophalen die betrekking hebben op een bepaald IP-adres met Microsoft Defender voor Eindpunt
keywords: api's, graph api, ondersteunde api's, get, ip, related, alerts
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
ms.openlocfilehash: a12ae502702b7fc9f69b01cd67857003258c20f2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770119"
---
# <a name="get-ip-related-alerts-api"></a><span data-ttu-id="ff243-104">IP-gerelateerde waarschuwingen-API krijgen</span><span class="sxs-lookup"><span data-stu-id="ff243-104">Get IP related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff243-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ff243-105">**Applies to:**</span></span>
- [<span data-ttu-id="ff243-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ff243-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ff243-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff243-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ff243-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ff243-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ff243-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ff243-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ff243-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="ff243-110">API description</span></span>
<span data-ttu-id="ff243-111">Hiermee wordt een verzameling waarschuwingen opgehaald die betrekking hebben op een bepaald IP-adres.</span><span class="sxs-lookup"><span data-stu-id="ff243-111">Retrieves a collection of alerts related to a given IP address.</span></span>


## <a name="limitations"></a><span data-ttu-id="ff243-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="ff243-112">Limitations</span></span>
1. <span data-ttu-id="ff243-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="ff243-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ff243-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ff243-114">Permissions</span></span>
<span data-ttu-id="ff243-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="ff243-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ff243-116">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ff243-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ff243-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="ff243-117">Permission type</span></span> |   <span data-ttu-id="ff243-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="ff243-118">Permission</span></span>  |   <span data-ttu-id="ff243-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="ff243-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ff243-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ff243-120">Application</span></span> |   <span data-ttu-id="ff243-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="ff243-121">Alert.Read.All</span></span> |    <span data-ttu-id="ff243-122">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="ff243-122">'Read all alerts'</span></span>
<span data-ttu-id="ff243-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ff243-123">Application</span></span> |   <span data-ttu-id="ff243-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ff243-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="ff243-125">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="ff243-125">'Read and write all alerts'</span></span>
<span data-ttu-id="ff243-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ff243-126">Delegated (work or school account)</span></span> | <span data-ttu-id="ff243-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="ff243-127">Alert.Read</span></span> | <span data-ttu-id="ff243-128">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="ff243-128">'Read alerts'</span></span>
<span data-ttu-id="ff243-129">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ff243-129">Delegated (work or school account)</span></span> | <span data-ttu-id="ff243-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ff243-130">Alert.ReadWrite</span></span> | <span data-ttu-id="ff243-131">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="ff243-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="ff243-132">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="ff243-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ff243-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ff243-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ff243-134">Antwoord bevat alleen waarschuwingen, gekoppeld aan apparaten, die de gebruiker toegang [](machine-groups.md) heeft, op basis van instellingen voor apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ff243-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ff243-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="ff243-135">HTTP request</span></span>
```
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="ff243-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="ff243-136">Request headers</span></span>

<span data-ttu-id="ff243-137">Naam</span><span class="sxs-lookup"><span data-stu-id="ff243-137">Name</span></span> | <span data-ttu-id="ff243-138">Type</span><span class="sxs-lookup"><span data-stu-id="ff243-138">Type</span></span> | <span data-ttu-id="ff243-139">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="ff243-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="ff243-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="ff243-140">Authorization</span></span> | <span data-ttu-id="ff243-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ff243-141">String</span></span> | <span data-ttu-id="ff243-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ff243-142">Bearer {token}.</span></span> <span data-ttu-id="ff243-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ff243-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ff243-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="ff243-144">Request body</span></span>
<span data-ttu-id="ff243-145">Leeg</span><span class="sxs-lookup"><span data-stu-id="ff243-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ff243-146">Antwoord</span><span class="sxs-lookup"><span data-stu-id="ff243-146">Response</span></span>
<span data-ttu-id="ff243-147">Als dit is gelukt en IP bestaat- [](alerts.md) 200 OK met een lijst met waarschuwingsentiteiten in de body.</span><span class="sxs-lookup"><span data-stu-id="ff243-147">If successful and IP exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="ff243-148">Als IP niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="ff243-148">If IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ff243-149">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ff243-149">Example</span></span>

<span data-ttu-id="ff243-150">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="ff243-150">**Request**</span></span>

<span data-ttu-id="ff243-151">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ff243-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```
