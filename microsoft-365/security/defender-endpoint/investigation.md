---
title: Onderzoeksresourcetype
description: Microsoft Defender voor de entiteit Endpoint Investigation.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, onderzoeken
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587681"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="51a6f-104">Onderzoeksresourcetype</span><span class="sxs-lookup"><span data-stu-id="51a6f-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51a6f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="51a6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="51a6f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="51a6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51a6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51a6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="51a6f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="51a6f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51a6f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="51a6f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="51a6f-110">Vertegenwoordig een entiteit geautomatiseerd onderzoek in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51a6f-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="51a6f-111">Zie [Overzicht van geautomatiseerde onderzoeken voor](automated-investigations.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51a6f-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="51a6f-112">Methoden</span><span class="sxs-lookup"><span data-stu-id="51a6f-112">Methods</span></span>
<span data-ttu-id="51a6f-113">Methode</span><span class="sxs-lookup"><span data-stu-id="51a6f-113">Method</span></span>|<span data-ttu-id="51a6f-114">Retourtype</span><span class="sxs-lookup"><span data-stu-id="51a6f-114">Return Type</span></span> |<span data-ttu-id="51a6f-115">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="51a6f-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="51a6f-116">Lijstonderzoeken</span><span class="sxs-lookup"><span data-stu-id="51a6f-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="51a6f-117">Onderzoeksverzameling</span><span class="sxs-lookup"><span data-stu-id="51a6f-117">Investigation collection</span></span> | <span data-ttu-id="51a6f-118">Verzameling van onderzoek ophalen</span><span class="sxs-lookup"><span data-stu-id="51a6f-118">Get collection of Investigation</span></span>
[<span data-ttu-id="51a6f-119">Eén onderzoek krijgen</span><span class="sxs-lookup"><span data-stu-id="51a6f-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="51a6f-120">Onderzoeksentiteit</span><span class="sxs-lookup"><span data-stu-id="51a6f-120">Investigation entity</span></span> | <span data-ttu-id="51a6f-121">Krijgt één onderzoeksentiteit.</span><span class="sxs-lookup"><span data-stu-id="51a6f-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="51a6f-122">Onderzoek starten</span><span class="sxs-lookup"><span data-stu-id="51a6f-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="51a6f-123">Onderzoeksentiteit</span><span class="sxs-lookup"><span data-stu-id="51a6f-123">Investigation entity</span></span> | <span data-ttu-id="51a6f-124">Start Onderzoek op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="51a6f-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="51a6f-125">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="51a6f-125">Properties</span></span>
<span data-ttu-id="51a6f-126">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="51a6f-126">Property</span></span> |  <span data-ttu-id="51a6f-127">Type</span><span class="sxs-lookup"><span data-stu-id="51a6f-127">Type</span></span>    |   <span data-ttu-id="51a6f-128">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="51a6f-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="51a6f-129">id</span><span class="sxs-lookup"><span data-stu-id="51a6f-129">id</span></span> | <span data-ttu-id="51a6f-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-130">String</span></span> | <span data-ttu-id="51a6f-131">Identiteit van de onderzoeksentiteit.</span><span class="sxs-lookup"><span data-stu-id="51a6f-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="51a6f-132">startTime</span><span class="sxs-lookup"><span data-stu-id="51a6f-132">startTime</span></span> | <span data-ttu-id="51a6f-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="51a6f-133">DateTime Nullable</span></span> | <span data-ttu-id="51a6f-134">De datum en tijd waarop het onderzoek is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="51a6f-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="51a6f-135">endTime</span><span class="sxs-lookup"><span data-stu-id="51a6f-135">endTime</span></span> | <span data-ttu-id="51a6f-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="51a6f-136">DateTime Nullable</span></span> | <span data-ttu-id="51a6f-137">De datum en tijd waarop het onderzoek is voltooid.</span><span class="sxs-lookup"><span data-stu-id="51a6f-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="51a6f-138">geannuleerdBy</span><span class="sxs-lookup"><span data-stu-id="51a6f-138">cancelledBy</span></span> | <span data-ttu-id="51a6f-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-139">String</span></span> | <span data-ttu-id="51a6f-140">De id van de gebruiker/toepassing die dat onderzoek heeft geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="51a6f-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="51a6f-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="51a6f-141">investigationState</span></span> | <span data-ttu-id="51a6f-142">Enum</span><span class="sxs-lookup"><span data-stu-id="51a6f-142">Enum</span></span> | <span data-ttu-id="51a6f-143">De huidige stand van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="51a6f-143">The current state of the investigation.</span></span> <span data-ttu-id="51a6f-144">Mogelijke waarden zijn: 'Onbekend', 'Beëindigd', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="51a6f-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="51a6f-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="51a6f-145">statusDetails</span></span> | <span data-ttu-id="51a6f-146">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-146">String</span></span> | <span data-ttu-id="51a6f-147">Aanvullende informatie over de stand van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="51a6f-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="51a6f-148">machineId</span><span class="sxs-lookup"><span data-stu-id="51a6f-148">machineId</span></span> | <span data-ttu-id="51a6f-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-149">String</span></span> | <span data-ttu-id="51a6f-150">De id van het apparaat waarop het onderzoek wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="51a6f-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="51a6f-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="51a6f-151">computerDnsName</span></span> | <span data-ttu-id="51a6f-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-152">String</span></span> | <span data-ttu-id="51a6f-153">De naam van het apparaat waarop het onderzoek wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="51a6f-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="51a6f-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="51a6f-154">triggeringAlertId</span></span> | <span data-ttu-id="51a6f-155">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="51a6f-155">String</span></span> | <span data-ttu-id="51a6f-156">De id van de waarschuwing die het onderzoek heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="51a6f-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="51a6f-157">Json-representatie</span><span class="sxs-lookup"><span data-stu-id="51a6f-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
