---
title: Apparaatwaarde-API instellen
description: Meer informatie over het opgeven van de waarde van een apparaat met een Microsoft Defender voor Eindpunt-API.
keywords: api's, graph api, ondersteunde api's, tags, machinetags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498310"
---
# <a name="set-device-value-api"></a>Apparaatwaarde-API instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving

Stel de apparaatwaarde van een specifieke [computer in.](machine.md)<br>
Zie [Apparaatwaarden toewijzen](tvm-assign-device-value.md) voor meer informatie.

## <a name="limitations"></a>Beperkingen

1. U kunt posten op apparaten die het laatst zijn gezien op basis van de geconfigureerde bewaarperiode.

2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |    Machtiging    |    Weergavenaam machtiging
:---|:---|:---
Toepassing |    Machine.ReadWrite.All |    'Alle computergegevens lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Beveiligingsinstelling beheren'. Voor meer informatie (Zie [Rollen maken en beheren](user-roles.md) voor meer informatie)
>- Gebruiker moet toegang hebben tot de computer, op basis van instellingen voor de machinegroep (Zie [Machinegroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen

In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter |    Type    | Omschrijving
:---|:---|:---
Apparaatwaarde |    Enum |    Apparaatwaarde. Toegestane waarden zijn: 'Normaal', 'Laag' en 'Hoog'. **Vereist**.

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 - Ok-antwoordcode en de bijgewerkte machine in de antwoord body.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van een aanvraag die een machinelabel toevoegt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
