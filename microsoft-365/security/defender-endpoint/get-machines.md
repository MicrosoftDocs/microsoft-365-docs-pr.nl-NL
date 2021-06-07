---
title: List machines API
description: Meer informatie over het gebruik van de LIST-machines-API om een verzameling machines op te halen die zijn gecommuniceerd met Microsoft Defender voor endpoint-cloud.
keywords: api's, graph api, ondersteunde api's, get, apparaten
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770743"
---
# <a name="list-machines-api"></a>List machines API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling [machines opgehaald die](machine.md) zijn gecommuniceerd met Microsoft Defender voor endpoint-cloud.
<br>Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)
<br>De query van OData `$filter` wordt ondersteund op: `computerDnsName` , , , en `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>Zie voorbeelden bij [OData-query's met Defender voor Eindpunt](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Beperkingen
1. U kunt apparaten voor het laatst zien op basis van de geconfigureerde bewaarperiode.
2. De maximale paginagrootte is 10.000.
3. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur. 


## <a name="permissions"></a>Machtigingen

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Machine.Read.All |  'Alle machineprofielen lezen'
Toepassing |   Machine.ReadWrite.All | 'Alle computergegevens lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Machine.Lezen | 'Machinegegevens lezen'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)
>- Antwoord bevat alleen apparaten, waar de gebruiker toegang toe heeft, op basis van apparaatgroepsinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en er machines bestaan- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body. Als er geen recente machines - 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)
