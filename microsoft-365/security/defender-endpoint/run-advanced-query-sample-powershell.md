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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844884"
---
# <a name="advanced-hunting-using-powershell"></a>Geavanceerde opsporing met behulp van PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Voer geavanceerde query's uit met PowerShell, zie [Advanced Hunting API](run-advanced-query-api.md).

In deze sectie delen we PowerShell-voorbeelden om een token op te halen en te gebruiken om een query uit te voeren.

## <a name="before-you-begin"></a>Voordat u begint
U moet eerst een [app maken.](apis-intro.md)

## <a name="preparation-instructions"></a>Voorbereidingsinstructies

- Open een PowerShell-venster.
- Als u de PowerShell-opdrachten niet kunt uitvoeren in uw beleid, kunt u de onderstaande opdracht uitvoeren:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Zie [PowerShell-documentatie](/powershell/module/microsoft.powershell.security/set-executionpolicy) voor meer informatie

## <a name="get-token"></a>Token krijgen

- Voer het volgende uit:

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

waar
- $tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)
- $appId: id van uw Azure AD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Defender voor Eindpunt)
- $appSecret: Geheim van uw Azure AD-app

## <a name="run-query"></a>Query uitvoeren

Voer de volgende query uit:

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

- $results de resultaten van de query bevatten
- $schema bevat het schema van de resultaten van de query

### <a name="complex-queries"></a>Complexe query's

Als u complexe query's (of query's met meerdere lijnen) wilt uitvoeren, kunt u de query opslaan in een bestand en in plaats van de eerste regel in het bovenstaande voorbeeld de onderstaande opdracht uitvoeren:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Werken met queryresultaten

U kunt nu de queryresultaten gebruiken.

Ga als file1.csv als u de resultaten van de query wilt uitvoeren in de CSV-indeling:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Ga als file1.jsals u de resultaten van de query wilt uitvoeren in de JSON-indeling:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Verwant onderwerp
- [Microsoft Defender voor eindpunt-API's](apis-intro.md)
- [Geavanceerde API voor opsporing](run-advanced-query-api.md)
- [Geavanceerde opsporing met behulp van Python](run-advanced-query-sample-python.md)
