---
title: De resultaten van AV-scans van Microsoft Defender bekijken
description: Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows-beveiliging app
keywords: scanresultaten, herstel, volledige scan, snelle scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007626"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Controle Microsoft Defender Antivirus scanresultaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Nadat een Microsoft Defender Antivirus scan is voltooid, of het nu een [on-demand](run-scan-microsoft-defender-antivirus.md) of geplande [scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md)is, worden de resultaten opgenomen en kunt u de resultaten bekijken. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuratiebeheer gebruiken om scanresultaten te bekijken

Zie [De status van Endpoint Protection controleren.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell-cmdlets gebruiken om scanresultaten te bekijken

De volgende cmdlet retourneerd elke detectie op het eindpunt. Als er meerdere detecties van dezelfde bedreiging zijn, wordt elke detectie afzonderlijk weergegeven op basis van het tijdstip van elke detectie:

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="schermafbeelding van PowerShell-cmdlets en -uitvoer":::

U kunt opgeven dat u de uitvoer wilt beperken om alleen de `-ThreatID` detecties voor een specifieke bedreiging weer te geven.

Als u bedreigingsdetecties wilt gebruiken, maar detecties van dezelfde bedreiging wilt combineren tot één item, kunt u de volgende cmdlet gebruiken:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell-code":::

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Gebruik Windows Management Instruction (WMI) om scanresultaten te bekijken

Gebruik de [ **methode Get** van de **MSFT_MpThreat** en **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klassen.


## <a name="related-articles"></a>Verwante artikelen

- [De resultaten van scans en herstel van Microsoft Defender Antivirus aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)