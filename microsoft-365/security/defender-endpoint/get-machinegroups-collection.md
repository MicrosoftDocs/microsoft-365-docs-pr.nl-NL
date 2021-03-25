---
title: Api voor verzamelingen van RBAC-machinegroepen ophalen
description: Lees hoe u de API van de KB-verzameling ophalen kunt gebruiken om een verzameling RBAC-apparaatgroepen op te halen in Microsoft Defender Advanced Threat Protection.
keywords: api's, graph api, ondersteunde api's, get, RBAC, groep
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166649"
---
# <a name="get-kb-collection-api"></a>KB-verzameling-API ophalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Hiermee wordt een verzameling RBAC-apparaatgroepen opgehaald.

## <a name="permissions"></a>Machtigingen
Gebruiker heeft leesmachtigingen nodig.

## <a name="http-request"></a>HTTP-aanvraag
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Kopteksten aanvragen

Koptekst | Value 
:---|:---
Autorisatie | Bearer {token}. **Vereist**.
Inhoudstype | toepassing/json

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt- 200 OK.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Antwoord**

Hier is een voorbeeld van het antwoord.
Veld-id bevat **apparaatgroep-id** en gelijk aan veld **rbacGroupId** in apparatengegevens. Veld **dat niet is gegroepeerd,** geldt slechts voor één groep voor alle apparaten die niet aan een groep zijn toegewezen. Deze groep heeft zoals gewoonlijk de naam 'UnassignedGroup'.

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
