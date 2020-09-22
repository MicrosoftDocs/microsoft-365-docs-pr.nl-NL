---
title: Geavanceerde jacht-Api's
description: Meer informatie over het uitvoeren van geavanceerde query's met een Microsoft Threat Protection-API
keywords: Geavanceerde jacht, Api's, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197807"
---
# <a name="advanced-hunting-apis"></a>Geavanceerde jacht-Api's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

## <a name="limitations"></a>Beperkingen
1. U kunt alleen een query uitvoeren op gegevens van de afgelopen 30 dagen.
2. De resultaten hebben een maximum van 100.000 rijen.
3. Het aantal uitvoeringen is beperkt per Tenant: tot 10 oproepen per minuut, 10 minuten per uur, met een tijdsduur van telkens een dag en 4 uur.
4. De maximale uitvoeringstijd van één aanvraag duurt 10 minuten.
5. 429-antwoord geeft een limiet aan voor het bereiken van de quotumlimiet per aantal aanvragen of door processor. De antwoordtekst van 429 geeft ook de tijd aan waarop de quota worden verlengd. 


## <a name="permissions"></a>Machtigingen
U moet een van de volgende machtigingen hebben om deze API te kunnen bellen. Zie [de Api's Microsoft Threat Protection openen](api-access.md) voor meer informatie, waaronder de manier waarop u machtigingen kiest.

Type machtiging |   Machtigingsset  |   Weergavenaam van de machtiging
:---|:---|:---
Toepassing |   AdvancedHunting. Read. all |  ' Geavanceerde query's uitvoeren '
Gedelegeerd (werk-of schoolaccount) | AdvancedHunting. Read | ' Geavanceerde query's uitvoeren '

>[!Note]
> Bij het verkrijgen van een token met behulp van gebruikersreferenties:
>- De gebruiker moet de rol gegevens weergeven hebben
>- De gebruiker moet toegang hebben tot het apparaat, op basis van de instellingen van de apparaatgroepen.

## <a name="http-request"></a>HTTP-aanvraag
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Kopteksten aanvragen

Factuurkop | Value 
:---|:---
Bevoegdheid | Bearer {token}. **Vereist**.
Inhouds type    | toepassing/JSON

## <a name="request-body"></a>Aanvraagtekst
Geef in de hoofdtekst van de aanvraag een JSON-object op met de volgende parameters:

Tabelwaardeparameter | Type    | Beschrijving
:---|:---|:---
Query | Tekst |  De query wordt uitgevoerd. **Vereist**.

## <a name="response"></a>Na
Als dit is gelukt, retourneert deze methode 200 OK en _QueryResponse_ object in de tekst van het antwoord. <br><br>

Het antwoordobject is onderverdeeld in drie delen (eigenschappen):<br>
1) ```Stats``` -Prestatiestatistieken voor query's.<br>
2) ```Schema``` -Het schema van het antwoord, een lijst met namen van de typen paren voor elke kolom. <br>
3) ```Results``` -Een lijst met geavanceerde bejacht gebeurtenissen.

## <a name="example"></a>Voorbeeld

Webonderdeelverzoek

Hier ziet u een voorbeeld van de aanvraag.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Na

Hier ziet u een voorbeeld van het antwoord.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Verwante onderwerpen
- [Toegang tot de Microsoft Threat Protection-Api's](api-access.md)
