---
title: Api voor gebruikerswaarschuwingen ontvangen
description: Een verzameling waarschuwingen ophalen die betrekking hebben op een bepaalde gebruikers-id met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, user, related, alerts
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769927"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="1c325-104">Api voor gebruikerswaarschuwingen ontvangen</span><span class="sxs-lookup"><span data-stu-id="1c325-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c325-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1c325-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c325-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1c325-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c325-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c325-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1c325-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1c325-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c325-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1c325-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1c325-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="1c325-110">API description</span></span>
<span data-ttu-id="1c325-111">Hiermee wordt een verzameling waarschuwingen opgehaald die betrekking hebben op een bepaalde gebruikers-id.</span><span class="sxs-lookup"><span data-stu-id="1c325-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="1c325-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="1c325-112">Limitations</span></span>
1. <span data-ttu-id="1c325-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="1c325-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1c325-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="1c325-114">Permissions</span></span>
<span data-ttu-id="1c325-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="1c325-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1c325-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="1c325-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1c325-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="1c325-117">Permission type</span></span> |   <span data-ttu-id="1c325-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="1c325-118">Permission</span></span>  |   <span data-ttu-id="1c325-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="1c325-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1c325-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="1c325-120">Application</span></span> |   <span data-ttu-id="1c325-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="1c325-121">Alert.Read.All</span></span> |    <span data-ttu-id="1c325-122">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="1c325-122">'Read all alerts'</span></span>
<span data-ttu-id="1c325-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="1c325-123">Application</span></span> |   <span data-ttu-id="1c325-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1c325-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="1c325-125">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="1c325-125">'Read and write all alerts'</span></span>
<span data-ttu-id="1c325-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="1c325-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1c325-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="1c325-127">Alert.Read</span></span> | <span data-ttu-id="1c325-128">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="1c325-128">'Read alerts'</span></span>
<span data-ttu-id="1c325-129">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="1c325-129">Delegated (work or school account)</span></span> | <span data-ttu-id="1c325-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1c325-130">Alert.ReadWrite</span></span> | <span data-ttu-id="1c325-131">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="1c325-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="1c325-132">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="1c325-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1c325-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'.</span><span class="sxs-lookup"><span data-stu-id="1c325-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="1c325-134">Zie Rollen maken [en beheren voor meer informatie.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1c325-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="1c325-135">Antwoord bevat alleen waarschuwingen, gekoppeld aan apparaten, die de gebruiker toegang [](machine-groups.md) heeft, op basis van instellingen voor apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="1c325-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1c325-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="1c325-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="1c325-137">**De id is niet de volledige UPN, maar alleen de gebruikersnaam. (bijvoorbeeld om waarschuwingen op te halen voor user1@contoso.com /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="1c325-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="1c325-138">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="1c325-138">Request headers</span></span>

<span data-ttu-id="1c325-139">Naam</span><span class="sxs-lookup"><span data-stu-id="1c325-139">Name</span></span> | <span data-ttu-id="1c325-140">Type</span><span class="sxs-lookup"><span data-stu-id="1c325-140">Type</span></span> | <span data-ttu-id="1c325-141">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1c325-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="1c325-142">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="1c325-142">Authorization</span></span> | <span data-ttu-id="1c325-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1c325-143">String</span></span> | <span data-ttu-id="1c325-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1c325-144">Bearer {token}.</span></span> <span data-ttu-id="1c325-145">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="1c325-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1c325-146">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="1c325-146">Request body</span></span>
<span data-ttu-id="1c325-147">Leeg</span><span class="sxs-lookup"><span data-stu-id="1c325-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1c325-148">Antwoord</span><span class="sxs-lookup"><span data-stu-id="1c325-148">Response</span></span>
<span data-ttu-id="1c325-149">Als dit is gelukt en de gebruiker bestaat- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="1c325-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="1c325-150">Als de gebruiker niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="1c325-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="1c325-151">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="1c325-151">Example</span></span>

<span data-ttu-id="1c325-152">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="1c325-152">**Request**</span></span>

<span data-ttu-id="1c325-153">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="1c325-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
