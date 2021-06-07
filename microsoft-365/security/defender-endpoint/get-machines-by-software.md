---
title: Apparaten per softwarelijst maken
description: Een lijst met apparaten ophalen waar deze software is geïnstalleerd.
keywords: api's, graph api, ondersteunde api's, get, list devices, devices list, list devices by software, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770551"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="44b2b-104">Apparaten per softwarelijst maken</span><span class="sxs-lookup"><span data-stu-id="44b2b-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44b2b-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="44b2b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="44b2b-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="44b2b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44b2b-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="44b2b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="44b2b-108">Een lijst met apparaatverwijzingen ophalen waar deze software is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="44b2b-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="44b2b-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="44b2b-109">Permissions</span></span>
<span data-ttu-id="44b2b-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="44b2b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="44b2b-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="44b2b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="44b2b-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="44b2b-112">Permission type</span></span> |   <span data-ttu-id="44b2b-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="44b2b-113">Permission</span></span>  |   <span data-ttu-id="44b2b-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="44b2b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="44b2b-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="44b2b-115">Application</span></span> | <span data-ttu-id="44b2b-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="44b2b-116">Software.Read.All</span></span> | <span data-ttu-id="44b2b-117">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="44b2b-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="44b2b-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="44b2b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="44b2b-119">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="44b2b-119">Software.Read</span></span> | <span data-ttu-id="44b2b-120">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="44b2b-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="44b2b-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="44b2b-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="44b2b-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="44b2b-122">Request headers</span></span>

| <span data-ttu-id="44b2b-123">Naam</span><span class="sxs-lookup"><span data-stu-id="44b2b-123">Name</span></span>        | <span data-ttu-id="44b2b-124">Type</span><span class="sxs-lookup"><span data-stu-id="44b2b-124">Type</span></span> | <span data-ttu-id="44b2b-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="44b2b-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="44b2b-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="44b2b-126">Authorization</span></span> | <span data-ttu-id="44b2b-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44b2b-127">String</span></span> | <span data-ttu-id="44b2b-128">Bearer {token}. **Vereist**.</span><span class="sxs-lookup"><span data-stu-id="44b2b-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="44b2b-129">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="44b2b-129">Request body</span></span>
<span data-ttu-id="44b2b-130">Leeg</span><span class="sxs-lookup"><span data-stu-id="44b2b-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="44b2b-131">Antwoord</span><span class="sxs-lookup"><span data-stu-id="44b2b-131">Response</span></span>
<span data-ttu-id="44b2b-132">Als dit is gelukt, retourneert deze methode 200 OK en een lijst met apparaten waarop de software in de body is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="44b2b-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="44b2b-133">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="44b2b-133">Example</span></span>

<span data-ttu-id="44b2b-134">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="44b2b-134">**Request**</span></span>

<span data-ttu-id="44b2b-135">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="44b2b-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="44b2b-136">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="44b2b-136">**Response**</span></span>

<span data-ttu-id="44b2b-137">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="44b2b-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="44b2b-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="44b2b-138">Related topics</span></span>
- [<span data-ttu-id="44b2b-139">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="44b2b-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="44b2b-140">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="44b2b-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
