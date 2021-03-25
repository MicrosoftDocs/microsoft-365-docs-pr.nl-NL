---
title: Softwaremethoden en -eigenschappen
description: Hiermee worden de meest recente waarschuwingen opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187102"
---
# <a name="software-resource-type"></a>Type softwareresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Retourtype |Beschrijving
:---|:---|:---
[Lijstsoftware](get-software.md) | Softwareverzameling | Vermeld de inventaris van de organisatiesoftware.
[Software downloaden op id](get-software-by-id.md) | Software | Een specifieke software downloaden op de software-id.
[Distributie van softwareversies van lijst](get-software-ver-distribution.md)| Distributieverzameling | Lijst met softwareversiedistributie per software-id.
[Machines per softwarelijst maken](get-machines-by-software.md)| MachineRef-verzameling | Een lijst met apparaten ophalen die zijn gekoppeld aan de software-id.
[Beveiligingslekken door software op een lijst zetten](get-vuln-by-software.md) | [Kwetsbaarheidsverzameling](vulnerability.md) | Een lijst met beveiligingslekken ophalen die zijn gekoppeld aan de software-id.
[Ontbrekende KBs krijgen](get-missing-kbs-software.md) | KB-verzameling | Een lijst met ontbrekende KBs downloaden die zijn gekoppeld aan de software-id

## <a name="properties"></a>Eigenschappen

Eigenschap |   Type   |   Beschrijving
:---|:---|:---
id | Tekenreeks | Software-id
Naam | Tekenreeks | Softwarenaam
Leverancier | Tekenreeks | Naam softwareleverancier
Zwakke punten | Lang | Aantal gevonden beveiligingslekken
publicExploit | Booleaanse waarde | Openbare exploit bestaat voor een aantal van de beveiligingslekken
activeAlert | Booleaanse waarde | Actieve waarschuwing is gekoppeld aan deze software
exposedMachines | Lang | Aantal blootgestelde apparaten
impactScore | Dubbel | Impact van blootstellingsscore van deze software
