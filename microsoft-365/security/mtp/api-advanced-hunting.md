---
title: Microsoft 365 Defender advanced hunting API
description: Meer informatie over het uitvoeren van geavanceerde zoekquery's met de geavanceerde api van Microsoft 365 Defender voor zoeken
keywords: Advanced Hunting, API's, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932080"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

[Geavanceerd zoeken](advanced-hunting-overview.md) is een hulpprogramma [](advanced-hunting-query-language.md) voor het op zoek naar risico' en maakt gebruik van speciaal gebouwde query's om de gebeurtenisgegevens van de afgelopen 30 dagen in Microsoft 365 Defender te analyseren. U kunt geavanceerde zoekquery's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs om te reageren op aanvallen. Met de geavanceerde api voor zoeken kunt u gebeurtenisgegevens programmatisch opvragen.

## <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

De volgende voorwaarden hebben betrekking op alle query's.

1. Query's verkennen en retourneren gegevens van de afgelopen 30 dagen.
2. Resultaten kunnen maximaal 100.000 rijen retourneren.
3. U kunt maximaal 10 oproepen per minuut per tenant voeren.
4. U hebt 10 minuten aan gebruikstijd per uur per tenant.
5. U hebt in totaal vier werkdagen per tenant.
6. Als één aanvraag langer dan tien minuten wordt uitgevoerd, wordt er een time-out gemaakt en wordt een foutmelding weergegeven.
7. Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij door het aantal verzonden aanvragen of door de toegewezen `429` lopende tijd. De reactie zelf bevat de tijd tot het quotum dat u hebt bereikt, wordt opnieuw ingesteld.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om de geavanceerde api voor zoeken aan te roepen. Zie Access voor meer informatie, waaronder het kiezen van machtigingen, [de Microsoft 365 Defender Protection-API's](api-access.md)

Machtigingstype | Machtiging | Weergavenaam van machtiging
-|-|-
Toepassing | AdvancedHunting.Read.All | Geavanceerde query's uitvoeren
Gedelegeerd (werk- of schoolaccount) | AdvancedHunting.Read | Geavanceerde query's uitvoeren

>[!Note]
> Wanneer u een token verkrijgt met behulp van gebruikersreferenties:
>
>- De gebruiker moet de AD-rol Gegevens weergeven hebben
>- De gebruiker moet toegang hebben tot het apparaat op basis van de instellingen van de apparaatgroep.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Berichtkoppen aanvragen

Koptekst | Value
-|-
Autorisatie | Opmerking voor gewenste {token}: **vereist**
Inhoudstype | toepassing/json

## <a name="request-body"></a>Aanvraag in de eerste instantie

In de aanvraag zelf een JSON-object opgeven met de volgende parameters:

Parameter | Type | Beschrijving
-|-|-
Query | Tekst | De query die moet worden uitgevoerd. **Opmerking: vereist**

## <a name="response"></a>Antwoord

Als dit lukt, wordt met deze methode `200 OK` een _object QueryResponse_ in de antwoord zelf gegeven.

Het antwoordobject bevat drie eigenschappen op het hoogste niveau:

1. Stats: een woordenlijst met prestatiestatistieken voor query's.
2. Schema: het schema van het antwoord, een lijst Name-Type paren voor elke kolom.
3. Results: een lijst met geavanceerde zoekgebeurtenissen.

## <a name="example"></a>Voorbeeld

In het volgende voorbeeld verzendt een gebruiker de onderstaande query en ontvangt deze een API-antwoordobject met `Stats` `Schema` de volgende . `Results`

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

- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer te weten komen over foutcodes](api-error-codes.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
