---
title: API voor machinetags toevoegen of verwijderen
description: Lees hoe u de API voor machinelabels toevoegen of verwijderen kunt gebruiken om een tag voor een computer toe te voegen of te verwijderen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, tags, machinetags
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769819"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="4d049-104">API voor machinetags toevoegen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="4d049-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="4d049-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4d049-105">**Applies to:**</span></span>

- [<span data-ttu-id="4d049-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4d049-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="4d049-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4d049-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d049-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4d049-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4d049-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="4d049-109">API description</span></span>

<span data-ttu-id="4d049-110">Hiermee voegt u tag toe aan een specifieke computer of verwijdert [u deze.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="4d049-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="4d049-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="4d049-111">Limitations</span></span>

1. <span data-ttu-id="4d049-112">U kunt posten op machines die het laatst zijn gezien op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="4d049-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="4d049-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="4d049-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4d049-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="4d049-114">Permissions</span></span>

<span data-ttu-id="4d049-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="4d049-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4d049-116">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="4d049-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4d049-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="4d049-117">Permission type</span></span> |    <span data-ttu-id="4d049-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="4d049-118">Permission</span></span>    |    <span data-ttu-id="4d049-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="4d049-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4d049-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4d049-120">Application</span></span> |    <span data-ttu-id="4d049-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4d049-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="4d049-122">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="4d049-122">'Read and write all machine information'</span></span>
<span data-ttu-id="4d049-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="4d049-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4d049-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4d049-124">Machine.ReadWrite</span></span> | <span data-ttu-id="4d049-125">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="4d049-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="4d049-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="4d049-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="4d049-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Beveiligingsinstelling beheren'.</span><span class="sxs-lookup"><span data-stu-id="4d049-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="4d049-128">Voor meer informatie (Zie [Rollen maken en beheren](user-roles.md) voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="4d049-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4d049-129">Gebruiker moet toegang hebben tot de computer, op basis van instellingen voor de machinegroep (Zie [Machinegroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="4d049-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4d049-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="4d049-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="4d049-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="4d049-131">Request headers</span></span>

<span data-ttu-id="4d049-132">Naam</span><span class="sxs-lookup"><span data-stu-id="4d049-132">Name</span></span> | <span data-ttu-id="4d049-133">Type</span><span class="sxs-lookup"><span data-stu-id="4d049-133">Type</span></span> | <span data-ttu-id="4d049-134">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4d049-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4d049-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4d049-135">Authorization</span></span> | <span data-ttu-id="4d049-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4d049-136">String</span></span> | <span data-ttu-id="4d049-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4d049-137">Bearer {token}.</span></span> <span data-ttu-id="4d049-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4d049-138">**Required**.</span></span>
<span data-ttu-id="4d049-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="4d049-139">Content-Type</span></span> | <span data-ttu-id="4d049-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4d049-140">string</span></span> | <span data-ttu-id="4d049-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="4d049-141">application/json.</span></span> <span data-ttu-id="4d049-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4d049-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4d049-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="4d049-143">Request body</span></span>

<span data-ttu-id="4d049-144">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="4d049-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4d049-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d049-145">Parameter</span></span> |    <span data-ttu-id="4d049-146">Type</span><span class="sxs-lookup"><span data-stu-id="4d049-146">Type</span></span>    | <span data-ttu-id="4d049-147">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4d049-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="4d049-148">Waarde</span><span class="sxs-lookup"><span data-stu-id="4d049-148">Value</span></span> |    <span data-ttu-id="4d049-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4d049-149">String</span></span> |    <span data-ttu-id="4d049-150">De naam van de tag.</span><span class="sxs-lookup"><span data-stu-id="4d049-150">The tag name.</span></span> <span data-ttu-id="4d049-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4d049-151">**Required**.</span></span>
<span data-ttu-id="4d049-152">Actie</span><span class="sxs-lookup"><span data-stu-id="4d049-152">Action</span></span>    | <span data-ttu-id="4d049-153">Enum</span><span class="sxs-lookup"><span data-stu-id="4d049-153">Enum</span></span> |    <span data-ttu-id="4d049-154">Toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4d049-154">Add or Remove.</span></span> <span data-ttu-id="4d049-155">Toegestane waarden zijn: 'Toevoegen' of 'Verwijderen'.</span><span class="sxs-lookup"><span data-stu-id="4d049-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="4d049-156">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4d049-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="4d049-157">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4d049-157">Response</span></span>

<span data-ttu-id="4d049-158">Als dit is gelukt, retourneert deze methode 200 - Ok-antwoordcode en de bijgewerkte machine in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="4d049-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="4d049-159">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4d049-159">Example</span></span>

<span data-ttu-id="4d049-160">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="4d049-160">**Request**</span></span>

<span data-ttu-id="4d049-161">Hier is een voorbeeld van een aanvraag die een machinelabel toevoegt.</span><span class="sxs-lookup"><span data-stu-id="4d049-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="4d049-162">Als u de machinetag wilt verwijderen, stelt u de actie in op 'Verwijderen' in plaats van 'Toevoegen' in de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4d049-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
