---
title: Geavanceerd zoeken met Basisbeginselen van PowerShell-API
ms.reviewer: ''
description: Leer de basisbeginselen van het query's uitvoeren van de Microsoft Defender voor Eindpunt-API met PowerShell.
keywords: api's, ondersteunde api's, geavanceerd zoeken, query
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
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198669"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="b441c-104">Geavanceerd zoeken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b441c-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b441c-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b441c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="b441c-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b441c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b441c-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b441c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b441c-108">Voer geavanceerde query's uit met PowerShell, zie [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="b441c-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="b441c-109">In deze sectie delen we PowerShell-voorbeelden om een token op te halen en te gebruiken om een query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b441c-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b441c-110">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b441c-110">Before you begin</span></span>
<span data-ttu-id="b441c-111">U moet eerst een [app maken.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b441c-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="b441c-112">Voorbereidingsinstructies</span><span class="sxs-lookup"><span data-stu-id="b441c-112">Preparation instructions</span></span>

- <span data-ttu-id="b441c-113">Open een PowerShell-venster.</span><span class="sxs-lookup"><span data-stu-id="b441c-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="b441c-114">Als u de PowerShell-opdrachten niet kunt uitvoeren in uw beleid, kunt u de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b441c-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="b441c-115">Zie [PowerShell-documentatie](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="b441c-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="b441c-116">Token krijgen</span><span class="sxs-lookup"><span data-stu-id="b441c-116">Get token</span></span>

- <span data-ttu-id="b441c-117">Voer het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="b441c-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="b441c-118">waar</span><span class="sxs-lookup"><span data-stu-id="b441c-118">where</span></span>
- <span data-ttu-id="b441c-119">$tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)</span><span class="sxs-lookup"><span data-stu-id="b441c-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="b441c-120">$appId: id van uw Azure AD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Defender voor Eindpunt)</span><span class="sxs-lookup"><span data-stu-id="b441c-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="b441c-121">$appSecret: Geheim van uw Azure AD-app</span><span class="sxs-lookup"><span data-stu-id="b441c-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="b441c-122">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b441c-122">Run query</span></span>

<span data-ttu-id="b441c-123">Voer de volgende query uit:</span><span class="sxs-lookup"><span data-stu-id="b441c-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="b441c-124">$results de resultaten van de query bevatten</span><span class="sxs-lookup"><span data-stu-id="b441c-124">$results contain the results of your query</span></span>
- <span data-ttu-id="b441c-125">$schema bevat het schema van de resultaten van de query</span><span class="sxs-lookup"><span data-stu-id="b441c-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="b441c-126">Complexe query's</span><span class="sxs-lookup"><span data-stu-id="b441c-126">Complex queries</span></span>

<span data-ttu-id="b441c-127">Als u complexe query's (of query's met meerdere lijnen) wilt uitvoeren, kunt u de query opslaan in een bestand en in plaats van de eerste regel in het bovenstaande voorbeeld de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b441c-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="b441c-128">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="b441c-128">Work with query results</span></span>

<span data-ttu-id="b441c-129">U kunt nu de queryresultaten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b441c-129">You can now use the query results.</span></span>

<span data-ttu-id="b441c-130">Ga als file1.csv als u de resultaten van de query wilt uitvoeren in de CSV-indeling:</span><span class="sxs-lookup"><span data-stu-id="b441c-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="b441c-131">Ga als file1.jsals u de resultaten van de query wilt uitvoeren in de JSON-indeling:</span><span class="sxs-lookup"><span data-stu-id="b441c-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="b441c-132">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="b441c-132">Related topic</span></span>
- [<span data-ttu-id="b441c-133">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="b441c-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="b441c-134">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="b441c-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="b441c-135">Geavanceerd jagen met Python</span><span class="sxs-lookup"><span data-stu-id="b441c-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
