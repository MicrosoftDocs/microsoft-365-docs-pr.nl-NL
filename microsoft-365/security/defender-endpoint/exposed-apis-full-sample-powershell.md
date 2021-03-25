---
title: Advanced Hunting met PowerShell API Guide
ms.reviewer: ''
description: Gebruik deze codevoorbeelden en bevraag verschillende Api's voor Eindpunten van Microsoft Defender.
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198319"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>Microsoft Defender voor eindpunt-API's met PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Volledig scenario met meerdere API's van Microsoft Defender voor Eindpunt.

In deze sectie delen we PowerShell-voorbeelden met 
- Een token ophalen 
- Token gebruiken om de meest recente waarschuwingen in Microsoft Defender voor Eindpunt op te halen
- Controleer voor elke waarschuwing, als de waarschuwing een gemiddelde of hoge prioriteit heeft en nog steeds wordt uitgevoerd, hoe vaak het apparaat is verbonden met verdachte URL.

**Vereiste:** u moet eerst [een app maken.](apis-intro.md)

## <a name="preparation-instructions"></a>Voorbereidingsinstructies

- Open een PowerShell-venster.
- Als u de PowerShell-opdrachten niet kunt uitvoeren in uw beleid, kunt u de onderstaande opdracht uitvoeren:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Zie [PowerShell-documentatie](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) voor meer informatie

## <a name="get-token"></a>Token krijgen

Voer het volgende uit:

- $tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)
- $appId: id van uw AAD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Defender voor Eindpunt)
- $appSecret: Geheim van uw Azure AD-app

- $suspiciousUrl: De URL


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a>Zie ook
- [Microsoft Defender voor eindpunt-API's](apis-intro.md)
- [Geavanceerde API voor opsporing](run-advanced-query-api.md)
- [Geavanceerd jagen met Python](run-advanced-query-sample-python.md)
