---
title: Opdrachten voor livereacties uitvoeren op een apparaat
description: Meer informatie over het uitvoeren van een reeks opdrachten voor livereacties op een apparaat.
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879668"
---
#  <a name="run-live-response-commands-on-a-device"></a>Opdrachten voor livereacties uitvoeren op een apparaat

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving

Voert een reeks opdrachten voor livereacties uit op een apparaat

## <a name="limitations"></a>Beperkingen

1.  Tariefbeperkingen voor deze API zijn 10 oproepen per minuut (extra aanvragen worden beantwoord met HTTP 429).

2.  25 gelijktijdige sessies (aanvragen die de beperkingslimiet overschrijden, ontvangen een antwoord op '429 - Te veel aanvragen').

3.  Als de computer niet beschikbaar is, wordt de sessie maximaal 3 dagen in de wachtrij geplaatst.

4.  RunScript-opdracht time-outs na 10 minuten.

5.  Wanneer een livereactieopdracht mislukt, worden alle gevolgde acties niet uitgevoerd.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)

| Machtigingstype                    | Machtiging           | Weergavenaam machtiging                   |
|------------------------------------|----------------------|-------------------------------------------|
| Toepassing                        | Machine.LiveResponse | Livereactie uitvoeren op een specifieke computer |
| Gedelegeerd (werk- of schoolaccount) | Machine.LiveResponse | Livereactie uitvoeren op een specifieke computer |

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Kopteksten aanvragen

| Naam      | Type | Omschrijving                 |
|---------------|----------|---------------------------------|
| Autorisatie | Tekenreeks   | Bearer\<token>\. Vereist.   |
| Inhoudstype  | tekenreeks   | toepassing/json. Vereist. |

## <a name="request-body"></a>Body aanvragen

| Parameter | Type | Omschrijving                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Opmerking       | Tekenreeks   | Opmerking om te koppelen aan de actie.                                 |
| Opdrachten      | Matrix    | Opdrachten die u wilt uitvoeren. Toegestane waarden zijn PutFile, RunScript, GetFile. |

Opdrachten:

| Opdrachttype | Parameters                                                                          | Omschrijving                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Sleutel: Bestandsnaam  <br><br>  Waarde: \<file name\>                                                                          | Zet een bestand uit de bibliotheek op het apparaat. Bestanden worden opgeslagen in een werkmap en worden verwijderd wanneer het apparaat standaard opnieuw wordt gestart.
| RunScript    | Sleutel: Scriptnaam<br>Waarde: \<Script from library\> <br><br> Sleutel: Args  <br> Waarde: \<Script arguments\>                          | Voert een script uit vanuit de bibliotheek op een apparaat.    <br><br>  De parameter Args wordt doorgegeven aan het script. <br><br> Time-outs na 10 minuten.     
| GetFile      | Sleutel: Pad <br> Waarde: \<File path\>                                                        | Bestanden verzamelen vanaf een apparaat. OPMERKING: Backslashes in pad moeten worden ontsnapt.                                                                      |

## <a name="response"></a>Antwoord

-   Als dit is gelukt, retourneert deze methode 200, ok.
    Actie-entiteit. Als de computer met de opgegeven id niet is gevonden- 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```HTTP
HTTP/1.1 200 Ok
```

Inhoudstype: toepassing/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Verwante onderwerpen
- [Api voor machineactie krijgen](get-machineaction-object.md)
- [Live-antwoordresultaat ontvangen](get-live-response-result.md)
- [Computeractie annuleren](cancel-machine-action.md)
