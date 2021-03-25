---
title: Api voor onderzoekspakket verzamelen
description: Gebruik deze API om oproepen te maken die betrekking hebben op het verzamelen van een onderzoekspakket vanaf een apparaat.
keywords: api's, graph api, ondersteunde api's, onderzoekspakket verzamelen
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
ms.technology: mde
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166679"
---
# <a name="collect-investigation-package-api"></a>Api voor onderzoekspakket verzamelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Verzamel een onderzoekspakket vanaf een apparaat.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Machine.CollectForensics |  'Forensics verzamelen'
Gedelegeerd (werk- of schoolaccount) |    Machine.CollectForensics |  'Forensics verzamelen'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts Investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)
>- De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen
In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter | Type    | Beschrijving
:---|:---|:---
Opmerking |   Tekenreeks |    Opmerking om te koppelen aan de actie. **Vereist**.

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
