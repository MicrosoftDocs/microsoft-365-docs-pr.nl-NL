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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771396"
---
# <a name="software-resource-type"></a>Type softwareresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Retourtype |Omschrijving
:---|:---|:---
[Lijst van software](get-software.md) | Softwareverzameling | Vermeld de inventaris van de organisatiesoftware.
[Software per id ophalen](get-software-by-id.md) | Software | Een specifieke software downloaden op de software-id.
[Lijst van distributie van softwareversies](get-software-ver-distribution.md)| Distributieverzameling | Lijst met softwareversiedistributie per software-id.
[Lijst van computers per software](get-machines-by-software.md)| MachineRef-verzameling | Een lijst met apparaten ophalen die zijn gekoppeld aan de software-id.
[Lijst van beveiligingsproblemen per software](get-vuln-by-software.md) | [Kwetsbaarheidsverzameling](vulnerability.md) | Een lijst met beveiligingslekken ophalen die zijn gekoppeld aan de software-id.
[Ontbrekende KB's ophalen](get-missing-kbs-software.md) | KB-verzameling | Een lijst met ontbrekende KBs downloaden die zijn gekoppeld aan de software-id

## <a name="properties"></a>Eigenschappen

Eigenschap |   Type   |   Omschrijving
:---|:---|:---
id | Tekenreeks | Software-id
Naam | Tekenreeks | Softwarenaam
Leverancier | Tekenreeks | Naam softwareleverancier
Zwakke punten | Lang | Aantal gevonden beveiligingslekken
publicExploit | Booleaanse waarde | Openbare exploit bestaat voor een aantal van de beveiligingslekken
activeAlert | Booleaanse waarde | Actieve waarschuwing is gekoppeld aan deze software
exposedMachines | Lang | Aantal blootgestelde apparaten
impactScore | Dubbel | Impact van blootstellingsscore van deze software
