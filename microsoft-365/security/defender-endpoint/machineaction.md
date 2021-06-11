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
ms.openlocfilehash: a3b017a9a05964c15411668787b035f1052c68cf
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878278"
---
# <a name="machineaction-resource-type"></a>MachineAction-resourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Zie Reactieacties voor [meer informatie.](respond-machine-alerts.md) 

| Methode                                                            | Retourtype                        | Omschrijving                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [Lijst MachineActions](get-machineactions-collection.md)           | [Computeractie](machineaction.md) | List [Machine Action-entiteiten.](machineaction.md)           |
| [MachineAction krijgen](get-machineaction-object.md)                  | [Computeractie](machineaction.md) | Eén entiteit [Machineactie](machineaction.md) krijgen.     |
| [Onderzoekspakket verzamelen](collect-investigation-package.md) | [Computeractie](machineaction.md) | Verzamel het onderzoekspakket van een [computer.](machine.md) |
| [Onderzoekspakket SAS URI ophalen](get-package-sas-uri.md)       | [Computeractie](machineaction.md) | Download URI voor het downloaden van het onderzoekspakket.          |
| [Computer isoleren](isolate-machine.md)                             | [Computeractie](machineaction.md) | De [machine isoleren](machine.md) van het netwerk.                 |
| [Computer loslaten uit isolatie](unisolate-machine.md)            | [Computeractie](machineaction.md) | Laat [de machine los](machine.md) uit Isolatie.               |
| [Het uitvoeren van apps beperken](restrict-code-execution.md)              | [Computeractie](machineaction.md) | Toepassingsuitvoering beperken.                             |
| [App-beperking verwijderen](unrestrict-code-execution.md)            | [Computeractie](machineaction.md) | Beperking voor toepassingsuitvoering verwijderen.                   |
| [Antivirusscan uitvoeren](run-av-scan.md)                              | [Computeractie](machineaction.md) | Voer een AV-scan uit Windows Defender (indien van toepassing).    |
| [Computer offboarden](offboard-machine-api.md)                       | [Computeractie](machineaction.md) | Offboard [machine](machine.md) from Microsoft Defender for Endpoint. |
| [Bestand stoppen en in quarantaine plaatsen](stop-and-quarantine-file.md)           | [Computeractie](machineaction.md) | De uitvoering van een bestand op een computer stoppen en verwijderen.        |
| [Livereactie uitvoeren](run-live-response.md)                     | [Computeractie](machineaction.md)  | Voert een reeks opdrachten voor livereacties uit op een apparaat                       |
| [Live-antwoordresultaat ontvangen](get-live-response-result.md) | URL-entiteit      | Hiermee wordt de downloadkoppeling voor de specifieke liveresponsopdracht opgehaald op de index. |
|[Computeractie annuleren](cancel-machine-action.md)                                | [Computeractie](machineaction.md)  | Een actieve machineactie annuleren.                                            |

<br>

## <a name="properties"></a>Eigenschappen

| Eigenschap            | Type           | Omschrijving                                                                                                                                                                                                    |
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
