---
title: Scoringsmethoden en -eigenschappen
description: Haalt de blootstellingsscore van uw organisatie, de veilige apparaatscore en de blootstellingsscore per apparaatgroep op
keywords: api's, graph api, ondersteunde api's, score, blootstellingsscore, veilige apparaatscore, blootstellingsscore per apparaatgroep
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
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500945"
---
# <a name="score-resource-type"></a>Scoreresourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Retourtype |Omschrijving
:---|:---|:---
[Blootstellingsscore ophalen](get-exposure-score.md) | [Score](score.md) | De score voor de blootstelling van de organisatie krijgen.
[Secure Score voor apparaten ophalen](get-device-secure-score.md) | [Score](score.md) | Haal de secure score van het organisatieapparaat.
[Lijstblootstellingsscore per apparaatgroep](get-machine-group-exposure-score.md)| [Score](score.md) | Lijstscores per apparaatgroep.

## <a name="properties"></a>Eigenschappen

Eigenschap |  Type    |   Omschrijving
:---|:---|:---
Score | Dubbel | De huidige score.
Tijd | DateTime | De datum en tijd waarin de oproep voor deze API is gedaan.
RbacGroupName | Tekenreeks | De naam van de apparaatgroep.
