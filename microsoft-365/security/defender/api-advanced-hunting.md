---
title: Microsoft 365 Defender advanced hunting API
description: Meer informatie over het uitvoeren van geavanceerde zoekquery's met behulp van de geavanceerde api van Microsoft 365 Defender
keywords: Advanced Hunting, API's, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932891"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

[Geavanceerd zoeken](advanced-hunting-overview.md) is een hulpprogramma [](advanced-hunting-query-language.md) voor het zoeken naar bedreigingen dat speciaal samengestelde query's gebruikt om de afgelopen 30 dagen met gebeurtenisgegevens in Microsoft 365 Defender te bekijken. U kunt geavanceerde zoekquery's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs te reageren op aanvallen. Met de geavanceerde api voor jagen kunt u gebeurtenisgegevens programmeren.

## <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

De volgende voorwaarden hebben betrekking op alle query's.

1. Query's verkennen en retourneren gegevens uit de afgelopen 30 dagen.
2. Resultaten kunnen maximaal 100.000 rijen opleveren.
3. U kunt maximaal 15 oproepen per minuut per tenant voeren.
4. U hebt 10 minuten speeltijd per uur per tenant.
5. U hebt in totaal vier uur aan gebruikstijden per dag per tenant.
6. Als één aanvraag langer dan 10 minuten wordt uitgevoerd, wordt er een time-out uitgevoerd en wordt er een foutbericht weergegeven.
7. Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op het aantal verzonden aanvragen, hetzij door de toegewezen `429` gebruikstijd. Lees de antwoord body voor meer informatie over de limiet die u hebt bereikt. 

> [!NOTE]
> Alle quota die hierboven worden vermeld (bijvoorbeeld 15 oproepen per min) zijn per tenantgrootte. Deze quota's zijn het minimum.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om de geavanceerde api voor jagen te bellen. Zie [Access the Microsoft 365 Defender Protection API's (Access the Microsoft 365 Defender Protection](api-access.md) API's) voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam machtiging
-|-|-
Toepassing | AdvancedHunting.Read.All | Geavanceerde query's uitvoeren
Gedelegeerd (werk- of schoolaccount) | AdvancedHunting.Read | Geavanceerde query's uitvoeren

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>
>- De gebruiker moet de AD-rol 'Gegevens weergeven' hebben
>- De gebruiker moet toegang hebben tot het apparaat op basis van de instellingen van de apparaatgroep.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Kopteksten aanvragen

Koptekst | Waarde
-|-
Autorisatie | Bearer {token} **Opmerking: vereist**
Inhoudstype | toepassing/json

## <a name="request-body"></a>Body aanvragen

In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter | Type | Beschrijving
-|-|-
Query | Tekst | De query die u wilt uitvoeren. **Opmerking: vereist**

## <a name="response"></a>Antwoord

Als dit is gelukt, worden deze methode `200 OK` en een _object QueryResponse_ in de reactie-body als return gegeven.

Het antwoordobject bevat drie eigenschappen op het hoogste niveau:

1. Statistieken: een woordenlijst met prestatiestatistieken voor query's.
2. Schema- Het schema van het antwoord, een lijst met Name-Type paren voor elke kolom.
3. Resultaten: een lijst met geavanceerde gebeurtenissen in de jacht.

## <a name="example"></a>Voorbeeld

In het volgende voorbeeld verzendt een gebruiker de query hieronder en ontvangt een API-antwoordobject met `Stats` `Schema` , en `Results` .

### <a name="query"></a>Query

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Antwoordobject

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

## <a name="related-articles"></a>Verwante artikelen

- [De Microsoft 365 Defender-API's openen](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
