---
title: Geïnstalleerde software ophalen
description: Hiermee wordt een verzameling geïnstalleerde software opgehaald die betrekking heeft op een bepaalde apparaat-id.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935102"
---
# <a name="get-installed-software"></a><span data-ttu-id="e4dbc-104">Geïnstalleerde software ophalen</span><span class="sxs-lookup"><span data-stu-id="e4dbc-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4dbc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4dbc-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4dbc-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e4dbc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e4dbc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4dbc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e4dbc-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e4dbc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4dbc-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e4dbc-110">Hiermee wordt een verzameling geïnstalleerde software opgehaald die betrekking heeft op een bepaalde apparaat-id.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="e4dbc-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e4dbc-111">Permissions</span></span>
<span data-ttu-id="e4dbc-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e4dbc-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e4dbc-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="e4dbc-114">Permission type</span></span> |   <span data-ttu-id="e4dbc-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="e4dbc-115">Permission</span></span>  |   <span data-ttu-id="e4dbc-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="e4dbc-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e4dbc-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e4dbc-117">Application</span></span> |<span data-ttu-id="e4dbc-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="e4dbc-118">Software.Read.All</span></span> |    <span data-ttu-id="e4dbc-119">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="e4dbc-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="e4dbc-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e4dbc-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e4dbc-121">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="e4dbc-121">Software.Read</span></span> |    <span data-ttu-id="e4dbc-122">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="e4dbc-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e4dbc-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="e4dbc-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="e4dbc-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="e4dbc-124">Request headers</span></span>

<span data-ttu-id="e4dbc-125">Naam</span><span class="sxs-lookup"><span data-stu-id="e4dbc-125">Name</span></span> | <span data-ttu-id="e4dbc-126">Type</span><span class="sxs-lookup"><span data-stu-id="e4dbc-126">Type</span></span> | <span data-ttu-id="e4dbc-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e4dbc-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="e4dbc-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="e4dbc-128">Authorization</span></span> | <span data-ttu-id="e4dbc-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e4dbc-129">String</span></span> | <span data-ttu-id="e4dbc-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-130">Bearer {token}.</span></span> <span data-ttu-id="e4dbc-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e4dbc-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="e4dbc-132">Request body</span></span>
<span data-ttu-id="e4dbc-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="e4dbc-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e4dbc-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="e4dbc-134">Response</span></span>
<span data-ttu-id="e4dbc-135">Als dit is gelukt, retourneert deze methode 200 OK met de geïnstalleerde softwaregegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e4dbc-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="e4dbc-136">Example</span></span>

<span data-ttu-id="e4dbc-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="e4dbc-137">**Request**</span></span>

<span data-ttu-id="e4dbc-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="e4dbc-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="e4dbc-139">**Response**</span></span>

<span data-ttu-id="e4dbc-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="e4dbc-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="e4dbc-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e4dbc-141">See also</span></span>

- [<span data-ttu-id="e4dbc-142">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="e4dbc-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e4dbc-143">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="e4dbc-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
