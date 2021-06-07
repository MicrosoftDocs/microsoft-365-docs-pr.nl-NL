---
title: Api voor domeinwaarschuwingen ontvangen
description: Lees hoe u de API Voor domeingerelateerde waarschuwingen ophalen gebruikt om waarschuwingen op te halen die betrekking hebben op een bepaald domeinadres in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, domein, gerelateerde, waarschuwingen
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772255"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="18af5-104">Api voor domeinwaarschuwingen ontvangen</span><span class="sxs-lookup"><span data-stu-id="18af5-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="18af5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="18af5-105">**Applies to:**</span></span>
- [<span data-ttu-id="18af5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="18af5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="18af5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18af5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="18af5-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="18af5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="18af5-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="18af5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="18af5-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="18af5-110">API description</span></span>
<span data-ttu-id="18af5-111">Hiermee wordt een verzameling waarschuwingen [opgehaald die](alerts.md) betrekking hebben op een bepaald domeinadres.</span><span class="sxs-lookup"><span data-stu-id="18af5-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="18af5-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="18af5-112">Limitations</span></span>
1. <span data-ttu-id="18af5-113">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="18af5-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="18af5-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="18af5-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="18af5-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="18af5-115">Permissions</span></span>
<span data-ttu-id="18af5-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="18af5-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="18af5-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="18af5-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="18af5-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="18af5-118">Permission type</span></span> |   <span data-ttu-id="18af5-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="18af5-119">Permission</span></span>  |   <span data-ttu-id="18af5-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="18af5-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="18af5-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="18af5-121">Application</span></span> |   <span data-ttu-id="18af5-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="18af5-122">Alert.Read.All</span></span> |    <span data-ttu-id="18af5-123">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="18af5-123">'Read all alerts'</span></span>
<span data-ttu-id="18af5-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="18af5-124">Application</span></span> |   <span data-ttu-id="18af5-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="18af5-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="18af5-126">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="18af5-126">'Read and write all alerts'</span></span>
<span data-ttu-id="18af5-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="18af5-127">Delegated (work or school account)</span></span> | <span data-ttu-id="18af5-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="18af5-128">Alert.Read</span></span> | <span data-ttu-id="18af5-129">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="18af5-129">'Read alerts'</span></span>
<span data-ttu-id="18af5-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="18af5-130">Delegated (work or school account)</span></span> | <span data-ttu-id="18af5-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="18af5-131">Alert.ReadWrite</span></span> | <span data-ttu-id="18af5-132">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="18af5-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="18af5-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="18af5-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="18af5-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="18af5-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="18af5-135">Antwoord bevat alleen waarschuwingen, gekoppeld aan apparaten, die de gebruiker toegang [](machine-groups.md) heeft, op basis van instellingen voor apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="18af5-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="18af5-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="18af5-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="18af5-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="18af5-137">Request headers</span></span>

| <span data-ttu-id="18af5-138">Koptekst</span><span class="sxs-lookup"><span data-stu-id="18af5-138">Header</span></span>        | <span data-ttu-id="18af5-139">Waarde</span><span class="sxs-lookup"><span data-stu-id="18af5-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="18af5-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="18af5-140">Authorization</span></span> | <span data-ttu-id="18af5-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="18af5-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="18af5-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="18af5-142">Request body</span></span>
<span data-ttu-id="18af5-143">Leeg</span><span class="sxs-lookup"><span data-stu-id="18af5-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="18af5-144">Antwoord</span><span class="sxs-lookup"><span data-stu-id="18af5-144">Response</span></span>
<span data-ttu-id="18af5-145">Als dit is gelukt en domein bestaat- [](alerts.md) 200 OK met lijst met waarschuwingsentiteiten.</span><span class="sxs-lookup"><span data-stu-id="18af5-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="18af5-146">Als domein niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="18af5-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="18af5-147">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="18af5-147">Example</span></span>

<span data-ttu-id="18af5-148">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="18af5-148">**Request**</span></span>

<span data-ttu-id="18af5-149">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="18af5-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
