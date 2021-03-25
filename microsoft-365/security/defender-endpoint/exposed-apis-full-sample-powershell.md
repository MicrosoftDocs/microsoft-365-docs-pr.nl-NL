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
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="f8175-104">Microsoft Defender voor eindpunt-API's met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8175-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8175-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f8175-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f8175-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f8175-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8175-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f8175-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="f8175-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f8175-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8175-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f8175-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="f8175-110">Volledig scenario met meerdere API's van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f8175-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="f8175-111">In deze sectie delen we PowerShell-voorbeelden met</span><span class="sxs-lookup"><span data-stu-id="f8175-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="f8175-112">Een token ophalen</span><span class="sxs-lookup"><span data-stu-id="f8175-112">Retrieve a token</span></span> 
- <span data-ttu-id="f8175-113">Token gebruiken om de meest recente waarschuwingen in Microsoft Defender voor Eindpunt op te halen</span><span class="sxs-lookup"><span data-stu-id="f8175-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f8175-114">Controleer voor elke waarschuwing, als de waarschuwing een gemiddelde of hoge prioriteit heeft en nog steeds wordt uitgevoerd, hoe vaak het apparaat is verbonden met verdachte URL.</span><span class="sxs-lookup"><span data-stu-id="f8175-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="f8175-115">**Vereiste:** u moet eerst [een app maken.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8175-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="f8175-116">Voorbereidingsinstructies</span><span class="sxs-lookup"><span data-stu-id="f8175-116">Preparation instructions</span></span>

- <span data-ttu-id="f8175-117">Open een PowerShell-venster.</span><span class="sxs-lookup"><span data-stu-id="f8175-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="f8175-118">Als u de PowerShell-opdrachten niet kunt uitvoeren in uw beleid, kunt u de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="f8175-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="f8175-119">Zie [PowerShell-documentatie](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="f8175-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="f8175-120">Token krijgen</span><span class="sxs-lookup"><span data-stu-id="f8175-120">Get token</span></span>

<span data-ttu-id="f8175-121">Voer het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="f8175-121">Run the below:</span></span>

- <span data-ttu-id="f8175-122">$tenantId: id van de tenant namens wie u de query wilt uitvoeren (dat wil zeggen dat de query wordt uitgevoerd op de gegevens van deze tenant)</span><span class="sxs-lookup"><span data-stu-id="f8175-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="f8175-123">$appId: id van uw AAD-app (de app moet de machtiging Geavanceerde query's uitvoeren hebben voor Defender voor Eindpunt)</span><span class="sxs-lookup"><span data-stu-id="f8175-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="f8175-124">$appSecret: Geheim van uw Azure AD-app</span><span class="sxs-lookup"><span data-stu-id="f8175-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="f8175-125">$suspiciousUrl: De URL</span><span class="sxs-lookup"><span data-stu-id="f8175-125">$suspiciousUrl: The URL</span></span>


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


## <a name="see-also"></a><span data-ttu-id="f8175-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f8175-126">See also</span></span>
- [<span data-ttu-id="f8175-127">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="f8175-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="f8175-128">Geavanceerde API voor opsporing</span><span class="sxs-lookup"><span data-stu-id="f8175-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="f8175-129">Geavanceerd jagen met Python</span><span class="sxs-lookup"><span data-stu-id="f8175-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
