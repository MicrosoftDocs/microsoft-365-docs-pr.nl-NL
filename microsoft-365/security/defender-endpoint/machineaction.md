---
title: machineAction resourcetype
description: Meer informatie over de methoden en eigenschappen van het type MachineAction-resource in Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, get, machineaction, recent
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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187383"
---
# <a name="machineaction-resource-type"></a>MachineAction-resourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Zie Reactieacties voor [meer informatie.](respond-machine-alerts.md) 

| Methode                                                            | Retourtype                        | Beschrijving                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [Lijst MachineActions](get-machineactions-collection.md)           | [Machineactie](machineaction.md) | List [Machine Action-entiteiten.](machineaction.md)           |
| [MachineAction krijgen](get-machineaction-object.md)                  | [Machineactie](machineaction.md) | Eén entiteit [Machineactie](machineaction.md) krijgen.     |
| [Onderzoekspakket verzamelen](collect-investigation-package.md) | [Machineactie](machineaction.md) | Verzamel het onderzoekspakket van een [computer.](machine.md) |
| [Onderzoekspakket SAS URI krijgen](get-package-sas-uri.md)       | [Machineactie](machineaction.md) | Download URI voor het downloaden van het onderzoekspakket.          |
| [Machine isoleren](isolate-machine.md)                             | [Machineactie](machineaction.md) | De [machine isoleren](machine.md) van het netwerk.                 |
| [Loszetapparaat uit isolatie](unisolate-machine.md)            | [Machineactie](machineaction.md) | Laat [de machine los](machine.md) uit Isolatie.               |
| [De uitvoering van apps beperken](restrict-code-execution.md)              | [Machineactie](machineaction.md) | Toepassingsuitvoering beperken.                             |
| [App-beperking verwijderen](unrestrict-code-execution.md)            | [Machineactie](machineaction.md) | Beperking voor toepassingsuitvoering verwijderen.                   |
| [Antivirusscan uitvoeren](run-av-scan.md)                              | [Machineactie](machineaction.md) | Voer een AV-scan uit met Windows Defender (indien van toepassing).    |
| [Offboard-machine](offboard-machine-api.md)                       | [Machineactie](machineaction.md) | Offboard [machine](machine.md) from Microsoft Defender for Endpoint. |
| [Bestand stoppen en in quarantaine plaatsen](stop-and-quarantine-file.md)           | [Machineactie](machineaction.md) | De uitvoering van een bestand op een computer stoppen en verwijderen.        |

<br>

## <a name="properties"></a>Eigenschappen

| Eigenschap            | Type           | Beschrijving                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Identiteit van de [entiteit Machineactie.](machineaction.md)                                                                                                                                                     |
| type                | Enum           | Type van de actie. Mogelijke waarden zijn: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" en "UnrestrictCodeExecution" |
| bereik               | tekenreeks         | Bereik van de actie. 'Volledig' of 'Selectief' voor isolatie, 'Snel' of 'Volledig' voor antivirusscan.                                                                                                   |
| requestor           | Tekenreeks         | De identiteit van de persoon die de actie heeft uitgevoerd.                                                                                                                                                               |
| requestorComment    | Tekenreeks         | Opmerking die is geschreven bij de uitgifte van de actie.                                                                                                                                                              |
| status              | Enum           | Huidige status van de opdracht. Mogelijke waarden zijn: 'In behandeling', 'InProgress', 'Geslaagd', 'Mislukt', 'Time-out' en 'Geannuleerd'.                                                                                 |
| machineId           | Tekenreeks         | Id van de [computer](machine.md) waarop de actie is uitgevoerd.                                                                                                                                              |
| machineId           | Tekenreeks         | Naam van de [machine](machine.md) waarop de actie is uitgevoerd.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | De datum en tijd waarop de actie is gemaakt.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | De laatste datum en tijd waarop de actiestatus is bijgewerkt.                                                                                                                                                     |
| relatedFileInfo     | Klas          | Bevat twee eigenschappen. tekenreeks ```fileIdentifier``` , Enum ```fileIdentifierType``` met de mogelijke waarden: 'Sha1', 'Sha256' en 'Md5'.                                                                         |


## <a name="json-representation"></a>Json-representatie

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
