---
title: Waarschuwings-API krijgen
description: Meer informatie over de methoden en eigenschappen van het brontype Waarschuwing in Microsoft Defender voor Eindpunt.
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
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289677"
---
# <a name="alert-resource-type"></a>Type waarschuwingsresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Methoden

Methode |Retourtype |Omschrijving
:---|:---|:---
[Waarschuwing ontvangen](get-alert-info-by-id.md) | [Waarschuwingsweergave](alerts.md) | Eén [waarschuwingsobject](alerts.md) krijgen.
[Lijstwaarschuwingen](get-alerts.md) | [Waarschuwingsverzameling](alerts.md) | [Lijstwaarschuwingsverzameling.](alerts.md)
[Waarschuwing bijwerken](update-alert.md) | [Waarschuwingsweergave](alerts.md) | Specifieke waarschuwing [bijwerken](alerts.md).
[Batchupdatewaarschuwingen](batch-update-alerts.md) | | Een reeks waarschuwingen [bijwerken.](alerts.md)
[Waarschuwing maken](create-alert-by-reference.md)|[Waarschuwingsweergave](alerts.md)|Maak een waarschuwing op basis van gebeurtenisgegevens die zijn verkregen uit [Advanced Hunting.](run-advanced-query-api.md)
[Gerelateerde domeinen lijst](get-alert-related-domain-info.md)|Domeinverzameling| Lijst-URL's die aan de waarschuwing zijn gekoppeld.
[Gerelateerde bestanden lijst](get-alert-related-files-info.md) | [Bestandsverzameling](files.md) |  Vermeld [](files.md) de bestandsentiteiten die aan de [waarschuwing zijn gekoppeld.](alerts.md)
[Lijstgerelateerde IPs](get-alert-related-ip-info.md) | IP-verzameling | Lijst-IPs die zijn gekoppeld aan de waarschuwing.
[Gerelateerde machines krijgen](get-alert-related-machine-info.md) | [Computer](machine.md) | De [computer](machine.md) die is gekoppeld aan de [waarschuwing](alerts.md).
[Verwante gebruikers krijgen](get-alert-related-user-info.md) | [Gebruiker](user.md) | De [gebruiker](user.md) die is gekoppeld aan de [waarschuwing](alerts.md).

## <a name="properties"></a>Eigenschappen

Eigenschap |    Type    |    Omschrijving
:---|:---|:---
id | Tekenreeks | Waarschuwings-id.
titel | Tekenreeks | Waarschuwingstitel.
beschrijving | Tekenreeks | Beschrijving van waarschuwing.
alertCreationTime | Nullable DateTimeOffset | De datum en tijd (in UTC) de waarschuwing is gemaakt.
lastEventTime | Nullable DateTimeOffset | De laatste gebeurtenis die de waarschuwing op hetzelfde apparaat heeft geactiveerd.
firstEventTime | Nullable DateTimeOffset | De eerste gebeurtenis die de waarschuwing op dat apparaat heeft geactiveerd.
lastUpdateTime | Nullable DateTimeOffset | De datum en tijd (in UTC) de waarschuwing is voor het laatst bijgewerkt.
resolvedTime | Nullable DateTimeOffset | De datum en tijd waarin de status van de waarschuwing is gewijzigd in 'Opgelost'.
incidentId | Nullable Long | De [incident-id](view-incidents-queue.md) van de waarschuwing.
investigationId | Nullable Long | De [onderzoeks-id](automated-investigations.md) die is gerelateerd aan de waarschuwing.
investigationState | Nullable Enum | De huidige stand van het [onderzoek](automated-investigations.md). Mogelijke waarden zijn: 'Onbekend', 'Beëindigd', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
toegewezenTo | Tekenreeks | Eigenaar van de waarschuwing.
ernst | Enum | Ernst van de waarschuwing. Mogelijke waarden zijn: 'Niet gespecificeerd', 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.
status | Enum | Hiermee geeft u de huidige status van de waarschuwing op. Mogelijke waarden zijn: 'Onbekend', 'Nieuw', 'InProgress' en 'Opgelost'.
classificatie | Nullable Enum | Specificatie van de waarschuwing. Mogelijke waarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'.
bepaling | Nullable Enum | Hiermee geeft u de bepaling van de waarschuwing op. Mogelijke waarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.
categorie| Tekenreeks | Categorie van de waarschuwing.
detectionSource | Tekenreeks | Detectiebron.
threatFamilyName | Tekenreeks | Familie van bedreigingen.
threatName | Tekenreeks | Bedreigingsnaam.
machineId | Tekenreeks | Id van een [machine-entiteit](machine.md) die is gekoppeld aan de waarschuwing.
computerDnsName | Tekenreeks | [computer](machine.md) volledig gekwalificeerde naam.
aadTenantId | Tekenreeks | De Azure Active Directory id.
melderId | Tekenreeks | De id van de melder die de waarschuwing heeft geactiveerd.
opmerkingen | Lijst met opmerkingen over waarschuwingen | Object Waarschuwingscommentant bevat: tekenreeks, gemaaktEen tekenreeks en createTime date time.
Bewijs | Lijst met aanwijzingen voor waarschuwingen | Bewijs met betrekking tot de waarschuwing. Zie het onderstaande voorbeeld.

### <a name="response-example-for-getting-single-alert"></a>Voorbeeld van antwoord voor het ontvangen van een enkele waarschuwing:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
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
}
```
