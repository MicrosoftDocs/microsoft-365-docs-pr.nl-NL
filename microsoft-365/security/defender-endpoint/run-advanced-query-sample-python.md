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
ms.openlocfilehash: 7ee431c88430916fcba60266a3a3a5180d830c0d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289257"
---
# <a name="advanced-hunting-using-python"></a>Geavanceerde opsporing met behulp van Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Voer geavanceerde query's uit met Python, zie [Advanced Hunting API](run-advanced-query-api.md).

In deze sectie delen we Python-voorbeelden om een token op te halen en te gebruiken om een query uit te voeren.

> **Vereiste:** u moet eerst [een app maken.](apis-intro.md)

## <a name="get-token"></a>Token krijgen

- Voer de volgende opdrachten uit:

```python
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

waar

- tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)
- appId: id van uw Azure AD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Microsoft Defender voor Eindpunt)
- appSecret: Geheim van uw Azure AD-app

## <a name="run-query"></a>Query uitvoeren

 Voer de volgende query uit:

```python
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

- schema bevat het schema van de resultaten van de query
- resultaten bevatten de resultaten van uw query

### <a name="complex-queries"></a>Complexe query's

Als u complexe query's (of multilinequery's) wilt uitvoeren, kunt u de query opslaan in een bestand en in plaats van de eerste regel in het bovenstaande voorbeeld de onderstaande opdracht uitvoeren:

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Werken met queryresultaten

U kunt nu de queryresultaten gebruiken.

Als u de resultaten wilt itereren, doet u het volgende:

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

Ga als file1.csv als u de resultaten van de query wilt uitvoeren in de CSV-indeling:

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Ga als file1.jsals u de resultaten van de query wilt uitvoeren in de JSON-indeling:

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>Verwant onderwerp

- [Microsoft Defender voor eindpunt-API's](apis-intro.md)
- [API voor geavanceerde opsporing](run-advanced-query-api.md)
- [Geavanceerde opsporing met behulp van PowerShell](run-advanced-query-sample-powershell.md)
