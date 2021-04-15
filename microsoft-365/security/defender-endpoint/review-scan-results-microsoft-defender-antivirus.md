---
title: De resultaten van AV-scans van Microsoft Defender bekijken
description: Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows Security-app
keywords: scanresultaten, herstel, volledige scan, snelle scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764143"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Testresultaten van Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Nadat een Microsoft Defender Antivirus-scan is voltooid, of dit nu een [on-demand](run-scan-microsoft-defender-antivirus.md) of geplande [scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md)is, worden de resultaten opgenomen en kunt u de resultaten bekijken. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuratiebeheer gebruiken om scanresultaten te bekijken

Zie [De status Endpoint Protection bewaken.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell-cmdlets gebruiken om scanresultaten te bekijken

De volgende cmdlet retourneerd elke detectie op het eindpunt. Als er meerdere detecties van dezelfde bedreiging zijn, wordt elke detectie afzonderlijk weergegeven op basis van het tijdstip van elke detectie:

```PowerShell
Get-MpThreatDetection
```

![schermafbeelding van PowerShell-cmdlets en -uitvoer](images/defender/wdav-get-mpthreatdetection.png)

U kunt opgeven dat u de uitvoer wilt beperken om alleen de `-ThreatID` detecties voor een specifieke bedreiging weer te geven.

Als u bedreigingsdetecties wilt gebruiken, maar detecties van dezelfde bedreiging wilt combineren tot één item, kunt u de volgende cmdlet gebruiken:

```PowerShell
Get-MpThreat
```

![schermafbeelding van PowerShell](images/defender/wdav-get-mpthreat.png)

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Windows Management Instruction (WMI) gebruiken om scanresultaten te bekijken

Gebruik de [ **methode Get** van de **MSFT_MpThreat** en **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klassen.


## <a name="related-articles"></a>Verwante artikelen

- [De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)