---
title: Api voor machine-entiteit bijwerken
description: Meer informatie over het bijwerken van machinetags met behulp van deze API. U kunt de tags en apparaatwaardeeigenschappen bijwerken.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985630"
---
# <a name="update-machine"></a><span data-ttu-id="4f764-105">Computer bijwerken</span><span class="sxs-lookup"><span data-stu-id="4f764-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f764-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4f764-106">**Applies to:**</span></span>
- [<span data-ttu-id="4f764-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4f764-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4f764-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f764-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4f764-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4f764-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4f764-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4f764-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4f764-111">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="4f764-111">API description</span></span>
<span data-ttu-id="4f764-112">De eigenschappen van bestaande [machine worden bijgewerkt.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="4f764-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="4f764-113">Updatable properties are: ```machineTags``` and ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="4f764-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="4f764-114">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="4f764-114">Limitations</span></span>
1. <span data-ttu-id="4f764-115">U kunt machines bijwerken die beschikbaar zijn in de API.</span><span class="sxs-lookup"><span data-stu-id="4f764-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="4f764-116">Update machine voegt alleen tags toe aan de tagverzameling.</span><span class="sxs-lookup"><span data-stu-id="4f764-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="4f764-117">Als er tags bestaan, moeten ze worden opgenomen in de tagsverzameling in de body.</span><span class="sxs-lookup"><span data-stu-id="4f764-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="4f764-118">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="4f764-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4f764-119">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="4f764-119">Permissions</span></span>
<span data-ttu-id="4f764-120">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="4f764-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4f764-121">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="4f764-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4f764-122">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="4f764-122">Permission type</span></span> |   <span data-ttu-id="4f764-123">Machtiging</span><span class="sxs-lookup"><span data-stu-id="4f764-123">Permission</span></span>  |   <span data-ttu-id="4f764-124">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="4f764-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4f764-125">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4f764-125">Application</span></span> |   <span data-ttu-id="4f764-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4f764-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="4f764-127">'Machinegegevens lezen en schrijven voor alle machines'</span><span class="sxs-lookup"><span data-stu-id="4f764-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="4f764-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="4f764-128">Delegated (work or school account)</span></span> | <span data-ttu-id="4f764-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4f764-129">Machine.ReadWrite</span></span> | <span data-ttu-id="4f764-130">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="4f764-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="4f764-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="4f764-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4f764-132">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation'.</span><span class="sxs-lookup"><span data-stu-id="4f764-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="4f764-133">Zie Rollen maken [en beheren voor meer informatie.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4f764-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="4f764-134">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van de instellingen van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="4f764-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="4f764-135">Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4f764-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="4f764-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="4f764-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="4f764-137">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="4f764-137">Request headers</span></span>

<span data-ttu-id="4f764-138">Naam</span><span class="sxs-lookup"><span data-stu-id="4f764-138">Name</span></span> | <span data-ttu-id="4f764-139">Type</span><span class="sxs-lookup"><span data-stu-id="4f764-139">Type</span></span> | <span data-ttu-id="4f764-140">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4f764-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="4f764-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4f764-141">Authorization</span></span> | <span data-ttu-id="4f764-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4f764-142">String</span></span> | <span data-ttu-id="4f764-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4f764-143">Bearer {token}.</span></span> <span data-ttu-id="4f764-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4f764-144">**Required**.</span></span>
<span data-ttu-id="4f764-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4f764-145">Content-Type</span></span> | <span data-ttu-id="4f764-146">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4f764-146">String</span></span> | <span data-ttu-id="4f764-147">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="4f764-147">application/json.</span></span> <span data-ttu-id="4f764-148">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4f764-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4f764-149">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="4f764-149">Request body</span></span>
<span data-ttu-id="4f764-150">In de aanvraagt u de waarden voor de relevante velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4f764-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="4f764-151">Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden.</span><span class="sxs-lookup"><span data-stu-id="4f764-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="4f764-152">Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="4f764-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="4f764-153">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="4f764-153">Property</span></span> | <span data-ttu-id="4f764-154">Type</span><span class="sxs-lookup"><span data-stu-id="4f764-154">Type</span></span> | <span data-ttu-id="4f764-155">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4f764-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="4f764-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="4f764-156">machineTags</span></span> | <span data-ttu-id="4f764-157">Tekenreeksverzameling</span><span class="sxs-lookup"><span data-stu-id="4f764-157">String collection</span></span> | <span data-ttu-id="4f764-158">Set [met machinelabels.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="4f764-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="4f764-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="4f764-159">deviceValue</span></span> | <span data-ttu-id="4f764-160">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="4f764-160">Nullable Enum</span></span> | <span data-ttu-id="4f764-161">De [waarde van het apparaat](tvm-assign-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="4f764-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="4f764-162">Mogelijke waarden zijn: 'Normaal', 'Laag' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="4f764-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="4f764-163">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4f764-163">Response</span></span>
<span data-ttu-id="4f764-164">Als dit is gelukt, retourneert deze methode 200 OK en de [machine-entiteit](machine.md) in de antwoordinstelling met de bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="4f764-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="4f764-165">Als de verzameling van machinelabels in de body geen bestaande machinelabels bevat: 400 ongeldige invoer en een bericht met informatie over de ontbrekende tag/s.</span><span class="sxs-lookup"><span data-stu-id="4f764-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="4f764-166">Als de computer met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="4f764-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4f764-167">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4f764-167">Example</span></span>

<span data-ttu-id="4f764-168">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="4f764-168">**Request**</span></span>

<span data-ttu-id="4f764-169">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4f764-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
