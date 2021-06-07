---
title: Advanced Hunting with Python API Guide
ms.reviewer: ''
description: Meer informatie over het uitvoeren van query's met behulp van de Microsoft Defender for Endpoint API, met behulp van Python, met voorbeelden.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771439"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="0ce0a-104">Geavanceerde opsporing met behulp van Python</span><span class="sxs-lookup"><span data-stu-id="0ce0a-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ce0a-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0ce0a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0ce0a-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0ce0a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ce0a-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0ce0a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="0ce0a-108">Voer geavanceerde query's uit met Python, zie [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="0ce0a-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="0ce0a-109">In deze sectie delen we Python-voorbeelden om een token op te halen en te gebruiken om een query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0ce0a-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="0ce0a-110">**Vereiste:** u moet eerst [een app maken.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0ce0a-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="0ce0a-111">Token krijgen</span><span class="sxs-lookup"><span data-stu-id="0ce0a-111">Get token</span></span>

- <span data-ttu-id="0ce0a-112">Voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="0ce0a-113">waar</span><span class="sxs-lookup"><span data-stu-id="0ce0a-113">where</span></span>
- <span data-ttu-id="0ce0a-114">tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)</span><span class="sxs-lookup"><span data-stu-id="0ce0a-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="0ce0a-115">appId: id van uw Azure AD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Microsoft Defender voor Eindpunt)</span><span class="sxs-lookup"><span data-stu-id="0ce0a-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="0ce0a-116">appSecret: Geheim van uw Azure AD-app</span><span class="sxs-lookup"><span data-stu-id="0ce0a-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="0ce0a-117">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="0ce0a-117">Run query</span></span>

 <span data-ttu-id="0ce0a-118">Voer de volgende query uit:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="0ce0a-119">schema bevat het schema van de resultaten van de query</span><span class="sxs-lookup"><span data-stu-id="0ce0a-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="0ce0a-120">resultaten bevatten de resultaten van uw query</span><span class="sxs-lookup"><span data-stu-id="0ce0a-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="0ce0a-121">Complexe query's</span><span class="sxs-lookup"><span data-stu-id="0ce0a-121">Complex queries</span></span>

<span data-ttu-id="0ce0a-122">Als u complexe query's (of query's met meerdere lijnen) wilt uitvoeren, kunt u de query opslaan in een bestand en in plaats van de eerste regel in het bovenstaande voorbeeld de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="0ce0a-123">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="0ce0a-123">Work with query results</span></span>

<span data-ttu-id="0ce0a-124">U kunt nu de queryresultaten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0ce0a-124">You can now use the query results.</span></span>

<span data-ttu-id="0ce0a-125">Als u de resultaten wilt itereren, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="0ce0a-126">Ga als file1.csv als u de resultaten van de query wilt uitvoeren in de CSV-indeling:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="0ce0a-127">Ga als file1.jsals u de resultaten van de query wilt uitvoeren in de JSON-indeling:</span><span class="sxs-lookup"><span data-stu-id="0ce0a-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="0ce0a-128">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="0ce0a-128">Related topic</span></span>
- [<span data-ttu-id="0ce0a-129">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="0ce0a-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="0ce0a-130">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="0ce0a-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="0ce0a-131">Geavanceerde opsporing met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ce0a-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
