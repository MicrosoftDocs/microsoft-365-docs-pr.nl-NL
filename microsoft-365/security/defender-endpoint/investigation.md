---
title: Onderzoeksresourcetype
description: Microsoft Defender ATP Investigation-entiteit.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, onderzoeken
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187126"
---
# <a name="investigation-resource-type"></a>Onderzoeksresourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Vertegenwoordig een entiteit geautomatiseerd onderzoek in Defender voor Eindpunt.
<br> Zie [Overzicht van geautomatiseerde onderzoeken voor](automated-investigations.md) meer informatie.

## <a name="methods"></a>Methoden
Methode|Retourtype |Beschrijving
:---|:---|:---
[Lijstonderzoeken](get-investigation-collection.md) | Onderzoeksverzameling | Verzameling van onderzoek ophalen
[Eén onderzoek krijgen](get-investigation-object.md) | Onderzoeksentiteit | Krijgt één onderzoeksentiteit.
[Onderzoek starten](initiate-autoir-investigation.md) | Onderzoeksentiteit | Start Onderzoek op een apparaat.


## <a name="properties"></a>Eigenschappen
Eigenschap |  Type    |   Beschrijving
:---|:---|:---
id | Tekenreeks | Identiteit van de onderzoeksentiteit. 
startTime | DateTime Nullable | De datum en tijd waarop het onderzoek is gemaakt. 
endTime | DateTime Nullable | De datum en tijd waarop het onderzoek is voltooid. 
geannuleerdBy | Tekenreeks | De id van de gebruiker/toepassing die dat onderzoek heeft geannuleerd. 
investigationState | Enum | De huidige stand van het onderzoek. Mogelijke waarden zijn: 'Onbekend', 'Beëindigd', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails | Tekenreeks | Aanvullende informatie over de stand van het onderzoek.
machineId | Tekenreeks | De id van het apparaat waarop het onderzoek wordt uitgevoerd.
computerDnsName | Tekenreeks | De naam van het apparaat waarop het onderzoek wordt uitgevoerd.
triggeringAlertId | Tekenreeks | De id van de waarschuwing die het onderzoek heeft geactiveerd.


## <a name="json-representation"></a>Json-representatie

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
