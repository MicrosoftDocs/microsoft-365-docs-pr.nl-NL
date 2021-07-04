---
title: Lijstwaarschuwingen API
description: Lees hoe u de API Lijstwaarschuwingen kunt gebruiken om een verzameling waarschuwingen op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
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
ms.openlocfilehash: dcc8a9214e0a6d0a0ede3b08aa6a019f2f0c4d2c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289845"
---
# <a name="list-alerts-api"></a><span data-ttu-id="20691-104">Lijstwaarschuwingen API</span><span class="sxs-lookup"><span data-stu-id="20691-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20691-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="20691-105">**Applies to:**</span></span>
- [<span data-ttu-id="20691-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="20691-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20691-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20691-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="20691-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="20691-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20691-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="20691-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="20691-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="20691-110">API description</span></span>
<span data-ttu-id="20691-111">Hiermee wordt een verzameling waarschuwingen opgehaald.</span><span class="sxs-lookup"><span data-stu-id="20691-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="20691-112">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="20691-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="20691-113">OData-ondersteunde operatoren:</span><span class="sxs-lookup"><span data-stu-id="20691-113">OData supported operators:</span></span>
<br><span data-ttu-id="20691-114">```$filter``` op: ```alertCreationTime``` ```lastUpdateTime``` , , , , ```incidentId``` en ```InvestigationId``` ```status``` ```severity``` ```category``` eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="20691-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="20691-115">```$top``` met een maximumwaarde van 10.000</span><span class="sxs-lookup"><span data-stu-id="20691-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="20691-116">```$expand``` van ```evidence```</span><span class="sxs-lookup"><span data-stu-id="20691-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="20691-117">Zie voorbeelden bij [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="20691-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="20691-118">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="20691-118">Limitations</span></span>
1. <span data-ttu-id="20691-119">U kunt waarschuwingen ontvangen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="20691-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="20691-120">De maximale paginagrootte is 10.000.</span><span class="sxs-lookup"><span data-stu-id="20691-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="20691-121">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="20691-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="20691-122">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="20691-122">Permissions</span></span>
<span data-ttu-id="20691-123">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="20691-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="20691-124">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="20691-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="20691-125">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="20691-125">Permission type</span></span> | <span data-ttu-id="20691-126">Machtiging</span><span class="sxs-lookup"><span data-stu-id="20691-126">Permission</span></span> | <span data-ttu-id="20691-127">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="20691-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="20691-128">Toepassing</span><span class="sxs-lookup"><span data-stu-id="20691-128">Application</span></span> | <span data-ttu-id="20691-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="20691-129">Alert.Read.All</span></span> | <span data-ttu-id="20691-130">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="20691-130">'Read all alerts'</span></span>
<span data-ttu-id="20691-131">Toepassing</span><span class="sxs-lookup"><span data-stu-id="20691-131">Application</span></span> | <span data-ttu-id="20691-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="20691-132">Alert.ReadWrite.All</span></span> | <span data-ttu-id="20691-133">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="20691-133">'Read and write all alerts'</span></span>
<span data-ttu-id="20691-134">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="20691-134">Delegated (work or school account)</span></span> | <span data-ttu-id="20691-135">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="20691-135">Alert.Read</span></span> | <span data-ttu-id="20691-136">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="20691-136">'Read alerts'</span></span>
<span data-ttu-id="20691-137">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="20691-137">Delegated (work or school account)</span></span> | <span data-ttu-id="20691-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="20691-138">Alert.ReadWrite</span></span> | <span data-ttu-id="20691-139">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="20691-139">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="20691-140">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="20691-140">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="20691-141">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="20691-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="20691-142">Het antwoord bevat alleen waarschuwingen die zijn gekoppeld aan apparaten die de [](machine-groups.md) gebruiker kan openen, op basis van de instellingen van de apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="20691-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="20691-143">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="20691-143">HTTP request</span></span>

```http
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="20691-144">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="20691-144">Request headers</span></span>

<span data-ttu-id="20691-145">Naam</span><span class="sxs-lookup"><span data-stu-id="20691-145">Name</span></span> | <span data-ttu-id="20691-146">Type</span><span class="sxs-lookup"><span data-stu-id="20691-146">Type</span></span> | <span data-ttu-id="20691-147">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="20691-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="20691-148">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="20691-148">Authorization</span></span> | <span data-ttu-id="20691-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="20691-149">String</span></span> | <span data-ttu-id="20691-150">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="20691-150">Bearer {token}.</span></span> <span data-ttu-id="20691-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="20691-151">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="20691-152">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="20691-152">Request body</span></span>

<span data-ttu-id="20691-153">Leeg</span><span class="sxs-lookup"><span data-stu-id="20691-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="20691-154">Antwoord</span><span class="sxs-lookup"><span data-stu-id="20691-154">Response</span></span>

<span data-ttu-id="20691-155">Als dit is gelukt, retourneert deze methode [](alerts.md) 200 OK en een lijst met waarschuwingsobjecten in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="20691-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>

## <a name="example-1---default"></a><span data-ttu-id="20691-156">Voorbeeld 1 - Standaard</span><span class="sxs-lookup"><span data-stu-id="20691-156">Example 1 - Default</span></span>

### <a name="request"></a><span data-ttu-id="20691-157">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="20691-157">Request</span></span>

<span data-ttu-id="20691-158">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="20691-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

### <a name="response"></a><span data-ttu-id="20691-159">Antwoord</span><span class="sxs-lookup"><span data-stu-id="20691-159">Response</span></span>

<span data-ttu-id="20691-160">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="20691-160">Here is an example of the response.</span></span>

> [!NOTE]
> <span data-ttu-id="20691-161">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="20691-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="20691-162">Alle waarschuwingen worden geretourneerd van een echt gesprek.</span><span class="sxs-lookup"><span data-stu-id="20691-162">All alerts will be returned from an actual call.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="20691-163">Voorbeeld 2 : 10 meest recente waarschuwingen met gerelateerd bewijs ontvangen</span><span class="sxs-lookup"><span data-stu-id="20691-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

### <a name="request"></a><span data-ttu-id="20691-164">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="20691-164">Request</span></span>

<span data-ttu-id="20691-165">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="20691-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```

### <a name="response"></a><span data-ttu-id="20691-166">Antwoord</span><span class="sxs-lookup"><span data-stu-id="20691-166">Response</span></span>

<span data-ttu-id="20691-167">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="20691-167">Here is an example of the response.</span></span>

> [!NOTE]
> <span data-ttu-id="20691-168">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="20691-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="20691-169">Alle waarschuwingen worden geretourneerd van een echt gesprek.</span><span class="sxs-lookup"><span data-stu-id="20691-169">All alerts will be returned from an actual call.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="20691-170">Zie ook</span><span class="sxs-lookup"><span data-stu-id="20691-170">See also</span></span>

[<span data-ttu-id="20691-171">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="20691-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
