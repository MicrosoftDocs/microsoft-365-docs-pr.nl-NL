---
title: Geavanceerde API voor opsporing
ms.reviewer: ''
description: Meer informatie over het gebruik van de geavanceerde api voor jagen om geavanceerde query's uit te voeren op Microsoft Defender voor Eindpunt. Lees meer over beperkingen en zie een voorbeeld.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772399"
---
# <a name="advanced-hunting-api"></a>Geavanceerde api voor jagen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Beperkingen

1. U kunt alleen een query uitvoeren op gegevens van de afgelopen 30 dagen.

2. De resultaten bevatten maximaal 100.000 rijen.

3. Het aantal uitvoeringen is beperkt per tenant:
   - API-oproepen: maximaal 45 oproepen per minuut, maximaal 1500 oproepen per uur.
   - Uitvoeringstijd: 10 minuten speeltijd per uur en 3 uur werktijd per dag.

4. De maximale uitvoeringstijd van één aanvraag is 10 minuten.

5. 429-antwoord vertegenwoordigt het bereiken van de quotumlimiet, hetzij per aantal aanvragen of per CPU. Lees de antwoord body om te begrijpen welke limiet is bereikt. 

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   AdvancedQuery.Read.All |    'Geavanceerde query's uitvoeren'
Gedelegeerd (werk- of schoolaccount) | AdvancedQuery.Read | 'Geavanceerde query's uitvoeren'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ad-rol 'Gegevens weergeven' hebben
>- De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Kopteksten aanvragen

Koptekst | Waarde 
:---|:---
Autorisatie | Bearer {token}. **Vereist**.
Inhoudstype    | toepassing/json

## <a name="request-body"></a>Body aanvragen

In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter | Type    | Beschrijving
:---|:---|:---
Query | Tekst |  De query die u wilt uitvoeren. **Vereist**.

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK en _QueryResponse-object_ in de antwoord body.


## <a name="example"></a>Voorbeeld

##### <a name="request"></a>Aanvraag

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a>Antwoord

Hier is een voorbeeld van het antwoord.

>[!NOTE]
>Het antwoordobject dat hier wordt weergegeven, kan worden afgekapt voor beknoptheid. Alle eigenschappen worden geretourneerd uit een echt gesprek.

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender for Endpoint API's introduction](apis-intro.md)
- [Advanced Hunting from Portal](advanced-hunting-query-language.md)
- [Geavanceerde opsporing met behulp van PowerShell](run-advanced-query-sample-powershell.md)
