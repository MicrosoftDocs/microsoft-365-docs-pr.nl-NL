---
title: Resultaten van livereacties ontvangen
description: Meer informatie over het ophalen van een specifiek resultaat van een livereactieopdracht door de index.
keywords: api's, graph api, ondersteunde api's, uploaden naar bibliotheek
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879687"
---
#  <a name="get-live-response-results"></a>Resultaten van livereacties ontvangen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving

Hiermee wordt een specifiek resultaat van de livereactieopdracht opgehaald op de index.

## <a name="limitations"></a>Beperkingen

1.  Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)

| Machtigingstype                    | Machtiging           | Weergavenaam machtiging                   |
|------------------------------------|----------------------|-------------------------------------------|
| Toepassing                        | Machine.LiveResponse | Livereactie uitvoeren op een specifieke computer |
| Gedelegeerd (werk- of schoolaccount) | Machine.LiveResponse | Livereactie uitvoeren op een specifieke computer |

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Kopteksten aanvragen

| Naam      | Type | Omschrijving               |
|---------------|----------|-------------------------------|
| Autorisatie | Tekenreeks   | Bearer {token}. Vereist. |

## <a name="request-body"></a>Body aanvragen

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met object met de koppeling naar het opdrachtresultaat in de *eigenschap waarde.* Deze koppeling is 30 minuten geldig en moet onmiddellijk worden gebruikt voor het downloaden van het pakket naar een lokale opslag. Een verlopen koppeling kan opnieuw worden gemaakt door een ander gesprek en het is niet nodig om de livereactie opnieuw uit te voeren.

*Eigenschappen van runscripttranscript:*

| Eigenschap  | Omschrijving                       |
|---------------|---------------------------------------|
| naam          | Naam van uitgevoerd script                  |
| exit_code     | Scriptuitgangscode uitgevoerd             |
| script_output | Standaarduitvoer voor uitgevoerd script       |
| script_error  | Standaarduitvoer van uitgevoerd script |

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

HTTP/1.1 200 Ok

Inhoudstype: toepassing/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Bestandsinhoud:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Verwante onderwerpen

- [Api voor machineactie krijgen](get-machineaction-object.md)
- [Computeractie annuleren](cancel-machine-action.md)
- [Livereactie uitvoeren](run-live-response.md) 
