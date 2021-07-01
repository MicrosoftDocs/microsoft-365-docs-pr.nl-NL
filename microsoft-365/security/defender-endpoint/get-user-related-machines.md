---
title: API voor gebruikersgerelateerde machines krijgen
description: Lees hoe u de API Voor gebruikersgerelateerde machines ophalen kunt gebruiken om een verzameling apparaten op te halen die betrekking hebben op een gebruikers-id in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, gebruiker, gebruikersgerelateerde waarschuwingen
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229453"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="55d1a-104">API voor gebruikersgerelateerde machines krijgen</span><span class="sxs-lookup"><span data-stu-id="55d1a-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55d1a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="55d1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="55d1a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="55d1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55d1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55d1a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="55d1a-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="55d1a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55d1a-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="55d1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="55d1a-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="55d1a-110">API description</span></span>
<span data-ttu-id="55d1a-111">Hiermee wordt een verzameling apparaten opgehaald die betrekking hebben op een bepaalde gebruikers-id.</span><span class="sxs-lookup"><span data-stu-id="55d1a-111">Retrieves a collection of devices related to a given user ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="55d1a-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="55d1a-112">Limitations</span></span>

<span data-ttu-id="55d1a-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="55d1a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="55d1a-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="55d1a-114">Permissions</span></span>

<span data-ttu-id="55d1a-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="55d1a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="55d1a-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="55d1a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="55d1a-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="55d1a-117">Permission type</span></span> |<span data-ttu-id="55d1a-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="55d1a-118">Permission</span></span>|<span data-ttu-id="55d1a-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="55d1a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="55d1a-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="55d1a-120">Application</span></span> |<span data-ttu-id="55d1a-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="55d1a-121">Machine.Read.All</span></span>|<span data-ttu-id="55d1a-122">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="55d1a-122">'Read all machine profiles'</span></span>
<span data-ttu-id="55d1a-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="55d1a-123">Application</span></span> |<span data-ttu-id="55d1a-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="55d1a-124">Machine.ReadWrite.All</span></span> |<span data-ttu-id="55d1a-125">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="55d1a-125">'Read and write all machine information'</span></span>
<span data-ttu-id="55d1a-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="55d1a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="55d1a-127">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="55d1a-127">Machine.Read</span></span> | <span data-ttu-id="55d1a-128">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="55d1a-128">'Read machine information'</span></span>
<span data-ttu-id="55d1a-129">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="55d1a-129">Delegated (work or school account)</span></span> | <span data-ttu-id="55d1a-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="55d1a-130">Machine.ReadWrite</span></span> | <span data-ttu-id="55d1a-131">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="55d1a-131">'Read and write machine information'</span></span>

> [!NOTE]
> <span data-ttu-id="55d1a-132">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="55d1a-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="55d1a-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'.</span><span class="sxs-lookup"><span data-stu-id="55d1a-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="55d1a-134">Zie Rollen maken [en beheren voor meer informatie](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="55d1a-134">For more information, see [Create and manage roles](user-roles.md))</span></span>
> - <span data-ttu-id="55d1a-135">Antwoord bevat alleen apparaten die de gebruiker kan openen, op basis van de instellingen van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="55d1a-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="55d1a-136">Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="55d1a-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="55d1a-137">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="55d1a-137">HTTP request</span></span>

```http
GET /api/users/{id}/machines
```

<span data-ttu-id="55d1a-138">**De id is niet de volledige UPN, maar alleen de gebruikersnaam. (bijvoorbeeld om machines op te halen voor user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="55d1a-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="55d1a-139">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="55d1a-139">Request headers</span></span>

<span data-ttu-id="55d1a-140">Naam</span><span class="sxs-lookup"><span data-stu-id="55d1a-140">Name</span></span> | <span data-ttu-id="55d1a-141">Type</span><span class="sxs-lookup"><span data-stu-id="55d1a-141">Type</span></span> | <span data-ttu-id="55d1a-142">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="55d1a-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="55d1a-143">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="55d1a-143">Authorization</span></span> | <span data-ttu-id="55d1a-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="55d1a-144">String</span></span> | <span data-ttu-id="55d1a-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="55d1a-145">Bearer {token}.</span></span> <span data-ttu-id="55d1a-146">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="55d1a-146">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="55d1a-147">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="55d1a-147">Request body</span></span>

<span data-ttu-id="55d1a-148">Leeg</span><span class="sxs-lookup"><span data-stu-id="55d1a-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="55d1a-149">Antwoord</span><span class="sxs-lookup"><span data-stu-id="55d1a-149">Response</span></span>

<span data-ttu-id="55d1a-150">Als dit is gelukt en de gebruiker bestaat- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="55d1a-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="55d1a-151">Als gebruiker niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="55d1a-151">If user does not exist - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="55d1a-152">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="55d1a-152">Example</span></span>

### <a name="request"></a><span data-ttu-id="55d1a-153">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="55d1a-153">Request</span></span>

<span data-ttu-id="55d1a-154">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="55d1a-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
