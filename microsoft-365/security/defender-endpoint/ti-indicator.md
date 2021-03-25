---
title: Indicatorresourcetype
description: Geef de entiteitsdetails op en definieer de afloop van de indicator met Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, get, TiIndicator, Indicator, recent
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
ms.technology: mde
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187106"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="e30b0-104">Indicatorresourcetype</span><span class="sxs-lookup"><span data-stu-id="e30b0-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e30b0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e30b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e30b0-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e30b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e30b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e30b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e30b0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e30b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e30b0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e30b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="e30b0-110">Zie de [bijbehorende pagina Indicatoren](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in de portal.</span><span class="sxs-lookup"><span data-stu-id="e30b0-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="e30b0-111">Methode</span><span class="sxs-lookup"><span data-stu-id="e30b0-111">Method</span></span>|<span data-ttu-id="e30b0-112">Retourtype</span><span class="sxs-lookup"><span data-stu-id="e30b0-112">Return Type</span></span> |<span data-ttu-id="e30b0-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e30b0-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="e30b0-114">Lijstindicatoren</span><span class="sxs-lookup"><span data-stu-id="e30b0-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="e30b0-115">[Indicator](ti-indicator.md) Verzameling</span><span class="sxs-lookup"><span data-stu-id="e30b0-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="e30b0-116">Lijstindicatorentiteiten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e30b0-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="e30b0-117">Indicator verzenden</span><span class="sxs-lookup"><span data-stu-id="e30b0-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="e30b0-118">Indicator</span><span class="sxs-lookup"><span data-stu-id="e30b0-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="e30b0-119">Entiteit Indicator [verzenden of](ti-indicator.md) bijwerken.</span><span class="sxs-lookup"><span data-stu-id="e30b0-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="e30b0-120">Indicatoren importeren</span><span class="sxs-lookup"><span data-stu-id="e30b0-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="e30b0-121">[Indicator](ti-indicator.md) Verzameling</span><span class="sxs-lookup"><span data-stu-id="e30b0-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="e30b0-122">Indicatoren-entiteiten [verzenden of](ti-indicator.md) bijwerken.</span><span class="sxs-lookup"><span data-stu-id="e30b0-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="e30b0-123">Indicator verwijderen</span><span class="sxs-lookup"><span data-stu-id="e30b0-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="e30b0-124">Geen inhoud</span><span class="sxs-lookup"><span data-stu-id="e30b0-124">No Content</span></span> | <span data-ttu-id="e30b0-125">Hiermee verwijdert u [de entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e30b0-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="e30b0-126">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="e30b0-126">Properties</span></span>
<span data-ttu-id="e30b0-127">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="e30b0-127">Property</span></span> |  <span data-ttu-id="e30b0-128">Type</span><span class="sxs-lookup"><span data-stu-id="e30b0-128">Type</span></span>    |   <span data-ttu-id="e30b0-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e30b0-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="e30b0-130">id</span><span class="sxs-lookup"><span data-stu-id="e30b0-130">id</span></span> | <span data-ttu-id="e30b0-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-131">String</span></span> | <span data-ttu-id="e30b0-132">Identiteit van de [entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e30b0-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="e30b0-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="e30b0-133">indicatorValue</span></span> | <span data-ttu-id="e30b0-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-134">String</span></span> | <span data-ttu-id="e30b0-135">De waarde van de [indicator](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="e30b0-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="e30b0-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="e30b0-136">indicatorType</span></span> | <span data-ttu-id="e30b0-137">Enum</span><span class="sxs-lookup"><span data-stu-id="e30b0-137">Enum</span></span> | <span data-ttu-id="e30b0-138">Type indicator.</span><span class="sxs-lookup"><span data-stu-id="e30b0-138">Type of the indicator.</span></span> <span data-ttu-id="e30b0-139">Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url".</span><span class="sxs-lookup"><span data-stu-id="e30b0-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="e30b0-140">toepassing</span><span class="sxs-lookup"><span data-stu-id="e30b0-140">application</span></span> | <span data-ttu-id="e30b0-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-141">String</span></span> | <span data-ttu-id="e30b0-142">De toepassing die aan de indicator is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="e30b0-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="e30b0-143">actie</span><span class="sxs-lookup"><span data-stu-id="e30b0-143">action</span></span> | <span data-ttu-id="e30b0-144">Enum</span><span class="sxs-lookup"><span data-stu-id="e30b0-144">Enum</span></span> | <span data-ttu-id="e30b0-145">De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="e30b0-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="e30b0-146">Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'.</span><span class="sxs-lookup"><span data-stu-id="e30b0-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="e30b0-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="e30b0-147">sourceType</span></span> | <span data-ttu-id="e30b0-148">Enum</span><span class="sxs-lookup"><span data-stu-id="e30b0-148">Enum</span></span> | <span data-ttu-id="e30b0-149">'Gebruiker' voor het geval de indicator die is gemaakt door een gebruiker (bijvoorbeeld vanuit de portal), 'AadApp' voor het geval deze wordt verzonden met behulp van geautomatiseerde toepassing via de API.</span><span class="sxs-lookup"><span data-stu-id="e30b0-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="e30b0-150">bron</span><span class="sxs-lookup"><span data-stu-id="e30b0-150">source</span></span> | <span data-ttu-id="e30b0-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-151">string</span></span> | <span data-ttu-id="e30b0-152">De naam van de gebruiker/toepassing die de indicator heeft ingediend.</span><span class="sxs-lookup"><span data-stu-id="e30b0-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="e30b0-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="e30b0-153">createdBy</span></span> | <span data-ttu-id="e30b0-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-154">String</span></span> | <span data-ttu-id="e30b0-155">Unieke identiteit van de gebruiker/toepassing die de indicator heeft ingediend.</span><span class="sxs-lookup"><span data-stu-id="e30b0-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="e30b0-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e30b0-156">lastUpdatedBy</span></span> | <span data-ttu-id="e30b0-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-157">String</span></span> | <span data-ttu-id="e30b0-158">De identiteit van de gebruiker/toepassing die de indicator het laatst heeft bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e30b0-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="e30b0-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="e30b0-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="e30b0-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e30b0-160">DateTimeOffset</span></span> | <span data-ttu-id="e30b0-161">De datum en tijd waarop de indicator is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e30b0-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="e30b0-162">verlooptijd</span><span class="sxs-lookup"><span data-stu-id="e30b0-162">expirationTime</span></span> | <span data-ttu-id="e30b0-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e30b0-163">DateTimeOffset</span></span> | <span data-ttu-id="e30b0-164">De verlooptijd van de indicator.</span><span class="sxs-lookup"><span data-stu-id="e30b0-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="e30b0-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e30b0-165">lastUpdateTime</span></span> | <span data-ttu-id="e30b0-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e30b0-166">DateTimeOffset</span></span> | <span data-ttu-id="e30b0-167">De laatste keer dat de indicator is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e30b0-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="e30b0-168">ernst</span><span class="sxs-lookup"><span data-stu-id="e30b0-168">severity</span></span> | <span data-ttu-id="e30b0-169">Enum</span><span class="sxs-lookup"><span data-stu-id="e30b0-169">Enum</span></span> | <span data-ttu-id="e30b0-170">De ernst van de indicator.</span><span class="sxs-lookup"><span data-stu-id="e30b0-170">The severity of the indicator.</span></span> <span data-ttu-id="e30b0-171">mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="e30b0-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="e30b0-172">titel</span><span class="sxs-lookup"><span data-stu-id="e30b0-172">title</span></span> | <span data-ttu-id="e30b0-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-173">String</span></span> | <span data-ttu-id="e30b0-174">Indicatortitel.</span><span class="sxs-lookup"><span data-stu-id="e30b0-174">Indicator title.</span></span>
<span data-ttu-id="e30b0-175">beschrijving</span><span class="sxs-lookup"><span data-stu-id="e30b0-175">description</span></span> | <span data-ttu-id="e30b0-176">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-176">String</span></span> | <span data-ttu-id="e30b0-177">Beschrijving van de indicator.</span><span class="sxs-lookup"><span data-stu-id="e30b0-177">Description of the indicator.</span></span>
<span data-ttu-id="e30b0-178">aanbevolenActie</span><span class="sxs-lookup"><span data-stu-id="e30b0-178">recommendedActions</span></span> | <span data-ttu-id="e30b0-179">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e30b0-179">String</span></span> | <span data-ttu-id="e30b0-180">Aanbevolen acties voor de indicator.</span><span class="sxs-lookup"><span data-stu-id="e30b0-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="e30b0-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="e30b0-181">rbacGroupNames</span></span> | <span data-ttu-id="e30b0-182">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e30b0-182">List of strings</span></span> | <span data-ttu-id="e30b0-183">RBAC-apparaatgroepnamen waarbij de indicator wordt blootgesteld en actief is.</span><span class="sxs-lookup"><span data-stu-id="e30b0-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="e30b0-184">Lege lijst voor het geval deze wordt weergegeven op alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="e30b0-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="e30b0-185">Json-representatie</span><span class="sxs-lookup"><span data-stu-id="e30b0-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
