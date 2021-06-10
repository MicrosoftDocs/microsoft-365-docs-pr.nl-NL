---
title: Indicatorresourcetype
description: Geef de entiteitsdetails op en definieer de afloop van de indicator met Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771379"
---
# <a name="indicator-resource-type"></a>Indicatorresourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Zie de [bijbehorende pagina Indicatoren](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in de portal. 

Methode|Retourtype |Beschrijving
:---|:---|:---
[Lijst van indicatoren](get-ti-indicators-collection.md) | [Indicator](ti-indicator.md) Verzameling | Lijstindicatorentiteiten. [](ti-indicator.md)
[Indicator verzenden](post-ti-indicator.md) | [Indicator](ti-indicator.md) | Entiteit Indicator [verzenden of](ti-indicator.md) bijwerken.
[Indicatoren importeren](import-ti-indicators.md) | [Indicator](ti-indicator.md) Verzameling | Indicatoren-entiteiten [verzenden of](ti-indicator.md) bijwerken.
[Indicator verwijderen](delete-ti-indicator-by-id.md) | Geen inhoud | Hiermee verwijdert u [de entiteit Indicator.](ti-indicator.md)


## <a name="properties"></a>Eigenschappen
Eigenschap |  Type    |   Beschrijving
:---|:---|:---
id | Tekenreeks | Identiteit van de [entiteit Indicator.](ti-indicator.md)
indicatorValue | Tekenreeks | De waarde van de [indicator](ti-indicator.md).
indicatorType | Enum | Type indicator. Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url".
toepassing | Tekenreeks | De toepassing die aan de indicator is gekoppeld. 
actie | Enum | De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie. Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'.
sourceType | Enum | 'Gebruiker' voor het geval de indicator die is gemaakt door een gebruiker (bijvoorbeeld vanuit de portal), 'AadApp' voor het geval deze wordt verzonden met behulp van geautomatiseerde toepassing via de API.
bron | tekenreeks | De naam van de gebruiker/toepassing die de indicator heeft ingediend.
createdBy | Tekenreeks | Unieke identiteit van de gebruiker/toepassing die de indicator heeft ingediend.
lastUpdatedBy | Tekenreeks | De identiteit van de gebruiker/toepassing die de indicator het laatst heeft bijgewerkt.
creationTimeDateTimeUtc | DateTimeOffset | De datum en tijd waarop de indicator is gemaakt.
verlooptijd | DateTimeOffset | De verlooptijd van de indicator.
lastUpdateTime | DateTimeOffset | De laatste keer dat de indicator is bijgewerkt.
ernst | Enum | De ernst van de indicator. mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.
titel | Tekenreeks | Indicatortitel.
beschrijving | Tekenreeks | Beschrijving van de indicator.
aanbevolenActie | Tekenreeks | Aanbevolen acties voor de indicator.
rbacGroupNames | Lijst met tekenreeksen | RBAC-apparaatgroepnamen waarbij de indicator wordt blootgesteld en actief is. Lege lijst voor het geval deze wordt weergegeven op alle apparaten.


## <a name="json-representation"></a>Json-representatie

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
