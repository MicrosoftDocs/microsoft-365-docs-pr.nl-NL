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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771379"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="1f07a-104">Indicatorresourcetype</span><span class="sxs-lookup"><span data-stu-id="1f07a-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f07a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1f07a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f07a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1f07a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f07a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f07a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1f07a-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1f07a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1f07a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1f07a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="1f07a-110">Zie de [bijbehorende pagina Indicatoren](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in de portal.</span><span class="sxs-lookup"><span data-stu-id="1f07a-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="1f07a-111">Methode</span><span class="sxs-lookup"><span data-stu-id="1f07a-111">Method</span></span>|<span data-ttu-id="1f07a-112">Retourtype</span><span class="sxs-lookup"><span data-stu-id="1f07a-112">Return Type</span></span> |<span data-ttu-id="1f07a-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1f07a-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1f07a-114">Lijst van indicatoren</span><span class="sxs-lookup"><span data-stu-id="1f07a-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="1f07a-115">[Indicator](ti-indicator.md) Verzameling</span><span class="sxs-lookup"><span data-stu-id="1f07a-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="1f07a-116">Lijstindicatorentiteiten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="1f07a-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="1f07a-117">Indicator verzenden</span><span class="sxs-lookup"><span data-stu-id="1f07a-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="1f07a-118">Indicator</span><span class="sxs-lookup"><span data-stu-id="1f07a-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="1f07a-119">Entiteit Indicator [verzenden of](ti-indicator.md) bijwerken.</span><span class="sxs-lookup"><span data-stu-id="1f07a-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="1f07a-120">Indicatoren importeren</span><span class="sxs-lookup"><span data-stu-id="1f07a-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="1f07a-121">[Indicator](ti-indicator.md) Verzameling</span><span class="sxs-lookup"><span data-stu-id="1f07a-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="1f07a-122">Indicatoren-entiteiten [verzenden of](ti-indicator.md) bijwerken.</span><span class="sxs-lookup"><span data-stu-id="1f07a-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="1f07a-123">Indicator verwijderen</span><span class="sxs-lookup"><span data-stu-id="1f07a-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="1f07a-124">Geen inhoud</span><span class="sxs-lookup"><span data-stu-id="1f07a-124">No Content</span></span> | <span data-ttu-id="1f07a-125">Hiermee verwijdert u [de entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="1f07a-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="1f07a-126">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="1f07a-126">Properties</span></span>
<span data-ttu-id="1f07a-127">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="1f07a-127">Property</span></span> |  <span data-ttu-id="1f07a-128">Type</span><span class="sxs-lookup"><span data-stu-id="1f07a-128">Type</span></span>    |   <span data-ttu-id="1f07a-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1f07a-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="1f07a-130">id</span><span class="sxs-lookup"><span data-stu-id="1f07a-130">id</span></span> | <span data-ttu-id="1f07a-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-131">String</span></span> | <span data-ttu-id="1f07a-132">Identiteit van de [entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="1f07a-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="1f07a-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="1f07a-133">indicatorValue</span></span> | <span data-ttu-id="1f07a-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-134">String</span></span> | <span data-ttu-id="1f07a-135">De waarde van de [indicator](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="1f07a-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="1f07a-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="1f07a-136">indicatorType</span></span> | <span data-ttu-id="1f07a-137">Enum</span><span class="sxs-lookup"><span data-stu-id="1f07a-137">Enum</span></span> | <span data-ttu-id="1f07a-138">Type indicator.</span><span class="sxs-lookup"><span data-stu-id="1f07a-138">Type of the indicator.</span></span> <span data-ttu-id="1f07a-139">Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url".</span><span class="sxs-lookup"><span data-stu-id="1f07a-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="1f07a-140">toepassing</span><span class="sxs-lookup"><span data-stu-id="1f07a-140">application</span></span> | <span data-ttu-id="1f07a-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-141">String</span></span> | <span data-ttu-id="1f07a-142">De toepassing die aan de indicator is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="1f07a-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="1f07a-143">actie</span><span class="sxs-lookup"><span data-stu-id="1f07a-143">action</span></span> | <span data-ttu-id="1f07a-144">Enum</span><span class="sxs-lookup"><span data-stu-id="1f07a-144">Enum</span></span> | <span data-ttu-id="1f07a-145">De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="1f07a-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="1f07a-146">Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'.</span><span class="sxs-lookup"><span data-stu-id="1f07a-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="1f07a-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="1f07a-147">sourceType</span></span> | <span data-ttu-id="1f07a-148">Enum</span><span class="sxs-lookup"><span data-stu-id="1f07a-148">Enum</span></span> | <span data-ttu-id="1f07a-149">'Gebruiker' voor het geval de indicator die is gemaakt door een gebruiker (bijvoorbeeld vanuit de portal), 'AadApp' voor het geval deze wordt verzonden met behulp van geautomatiseerde toepassing via de API.</span><span class="sxs-lookup"><span data-stu-id="1f07a-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="1f07a-150">bron</span><span class="sxs-lookup"><span data-stu-id="1f07a-150">source</span></span> | <span data-ttu-id="1f07a-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-151">string</span></span> | <span data-ttu-id="1f07a-152">De naam van de gebruiker/toepassing die de indicator heeft ingediend.</span><span class="sxs-lookup"><span data-stu-id="1f07a-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="1f07a-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="1f07a-153">createdBy</span></span> | <span data-ttu-id="1f07a-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-154">String</span></span> | <span data-ttu-id="1f07a-155">Unieke identiteit van de gebruiker/toepassing die de indicator heeft ingediend.</span><span class="sxs-lookup"><span data-stu-id="1f07a-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="1f07a-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1f07a-156">lastUpdatedBy</span></span> | <span data-ttu-id="1f07a-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-157">String</span></span> | <span data-ttu-id="1f07a-158">De identiteit van de gebruiker/toepassing die de indicator het laatst heeft bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1f07a-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="1f07a-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="1f07a-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="1f07a-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1f07a-160">DateTimeOffset</span></span> | <span data-ttu-id="1f07a-161">De datum en tijd waarop de indicator is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1f07a-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="1f07a-162">verlooptijd</span><span class="sxs-lookup"><span data-stu-id="1f07a-162">expirationTime</span></span> | <span data-ttu-id="1f07a-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1f07a-163">DateTimeOffset</span></span> | <span data-ttu-id="1f07a-164">De verlooptijd van de indicator.</span><span class="sxs-lookup"><span data-stu-id="1f07a-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="1f07a-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1f07a-165">lastUpdateTime</span></span> | <span data-ttu-id="1f07a-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1f07a-166">DateTimeOffset</span></span> | <span data-ttu-id="1f07a-167">De laatste keer dat de indicator is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1f07a-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="1f07a-168">ernst</span><span class="sxs-lookup"><span data-stu-id="1f07a-168">severity</span></span> | <span data-ttu-id="1f07a-169">Enum</span><span class="sxs-lookup"><span data-stu-id="1f07a-169">Enum</span></span> | <span data-ttu-id="1f07a-170">De ernst van de indicator.</span><span class="sxs-lookup"><span data-stu-id="1f07a-170">The severity of the indicator.</span></span> <span data-ttu-id="1f07a-171">mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="1f07a-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="1f07a-172">titel</span><span class="sxs-lookup"><span data-stu-id="1f07a-172">title</span></span> | <span data-ttu-id="1f07a-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-173">String</span></span> | <span data-ttu-id="1f07a-174">Indicatortitel.</span><span class="sxs-lookup"><span data-stu-id="1f07a-174">Indicator title.</span></span>
<span data-ttu-id="1f07a-175">beschrijving</span><span class="sxs-lookup"><span data-stu-id="1f07a-175">description</span></span> | <span data-ttu-id="1f07a-176">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-176">String</span></span> | <span data-ttu-id="1f07a-177">Beschrijving van de indicator.</span><span class="sxs-lookup"><span data-stu-id="1f07a-177">Description of the indicator.</span></span>
<span data-ttu-id="1f07a-178">aanbevolenActie</span><span class="sxs-lookup"><span data-stu-id="1f07a-178">recommendedActions</span></span> | <span data-ttu-id="1f07a-179">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1f07a-179">String</span></span> | <span data-ttu-id="1f07a-180">Aanbevolen acties voor de indicator.</span><span class="sxs-lookup"><span data-stu-id="1f07a-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="1f07a-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="1f07a-181">rbacGroupNames</span></span> | <span data-ttu-id="1f07a-182">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="1f07a-182">List of strings</span></span> | <span data-ttu-id="1f07a-183">RBAC-apparaatgroepnamen waarbij de indicator wordt blootgesteld en actief is.</span><span class="sxs-lookup"><span data-stu-id="1f07a-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="1f07a-184">Lege lijst voor het geval deze wordt weergegeven op alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="1f07a-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="1f07a-185">Json-representatie</span><span class="sxs-lookup"><span data-stu-id="1f07a-185">Json representation</span></span>

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
