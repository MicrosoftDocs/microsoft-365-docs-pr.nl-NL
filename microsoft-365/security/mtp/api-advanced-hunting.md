---
title: Microsoft 365 Defender Advanced jacht API
description: Meer informatie over het uitvoeren van geavanceerde jacht-query's met behulp van de geavanceerde Microsoft 365-API
keywords: Geavanceerde jacht, Api's, API, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988114"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced jacht API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

[Geavanceerde jacht](advanced-hunting-overview.md) is een hulpprogramma voor een Threat-jacht waarbij [speciaal samengestelde query's](advanced-hunting-query-language.md) worden gebruikt om de afgelopen 30 dagen van gebeurtenisgegevens te bekijken in Microsoft 365 Defender. U kunt geavanceerde jacht-query's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs tegen aanvallen te reageren. Met de Advanced jacht-API kunt u programmatische gegevens van querygebeurtenissen uitvoeren.

## <a name="quotas-and-resource-allocation"></a>Quota's en resources toewijzen

De volgende voorwaarden hebben betrekking op alle query's.

1. Met query's worden gegevens uit de afgelopen 30 dagen verkend en geretourneerd.
2. Resultaten kunnen resulteren in 100.000 rijen.
3. U kunt maximaal 15 oproepen per Tenant maken.
4. U hebt 10 minuten per uur tijdsperiode per Tenant.
5. U hebt vier totale uren per dag per Tenant.
6. Als één verzoek langer dan 10 minuten wordt uitgevoerd, wordt de time-out weergegeven en wordt een fout geretourneerd.
7. Met een `429` HTTP-antwoordcode wordt aangegeven dat u een quotum hebt bereikt, hetzij op basis van het aantal ingediende aanvragen of over de beschikde periode. Lees de antwoordtekst als u wilt weten wat de limiet is bereikt. 

> [!NOTE]
> Alle hierboven genoemde quota's (bijvoorbeeld 15 oproepen per min) zijn per Tenant grootte. Dit zijn de quota's.

## <a name="permissions"></a>Machtigingen

U hebt een van de volgende machtigingen nodig om de API Advanced jacht te bellen. Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Microsoft 365 Defender-beveiligings-Api's openen](api-access.md)

Type machtiging | Machtigingsset | Weergavenaam van de machtiging
-|-|-
Toepassing | AdvancedHunting. Read. all | Geavanceerde query's uitvoeren
Gedelegeerd (werk-of schoolaccount) | AdvancedHunting. Read | Geavanceerde query's uitvoeren

>[!Note]
> Bij het verkrijgen van een token met behulp van gebruikersreferenties:
>
>- De gebruiker moet de rol gegevens weergeven hebben
>- De gebruiker moet toegang hebben tot het apparaat, op basis van de instellingen van de apparaatgroepen.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Kopteksten aanvragen

Factuurkop | Value
-|-
Bevoegdheid | Bearer {token} **Opmerking: vereist**
Inhouds type | toepassing/JSON

## <a name="request-body"></a>Aanvraagtekst

Geef in de hoofdtekst van de aanvraag een JSON-object op met de volgende parameters:

Tabelwaardeparameter | Type | Beschrijving
-|-|-
Query | Tekst | De query wordt uitgevoerd. **Opmerking: vereist**

## <a name="response"></a>Na

Als dit is gelukt, wordt deze methode geretourneerd `200 OK` en wordt een _QueryResponse_ -object in de tekst van het antwoord weergegeven.

Het antwoordobject bevat drie eigenschappen op het hoogste niveau:

1. Stats: een dictionary met statistieken voor queryprestaties.
2. Schema: het schema van het antwoord, een lijst met Name-Type paren voor elke kolom.
3. Resultaten: een lijst met geavanceerde jacht gebeurtenissen.

## <a name="example"></a>Voorbeeld

In het volgende voorbeeld worden de onderstaande query verzonden en ontvangt hij of zij een API-antwoordobject met de naam `Stats` , `Schema` en `Results` .

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

- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer informatie over foutcodes](api-error-codes.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
