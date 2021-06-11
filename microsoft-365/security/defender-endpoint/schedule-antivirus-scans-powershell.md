---
title: Antivirusscans plannen met PowerShell
description: Antivirusscans plannen met PowerShell
keywords: quick scan, full scan, antivirus, schedule, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879677"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Antivirusscans plannen met PowerShell

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u geplande scans configureert met behulp van PowerShell-cmdlets. Zie Geplande snelle of volledige Microsoft Defender Antivirus configureren voor meer informatie over planningsscans [en scantypen.](schedule-antivirus-scans.md) 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell-cmdlets gebruiken om scans te plannen

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>PowerShell-cmdlets voor planningsscans wanneer een eindpunt niet wordt gebruikt

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en uit te voeren](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/) voor meer informatie.

> [!NOTE]
> Wanneer u scans inplant voor tijden waarin eindpunten niet worden gebruikt, wordt de configuratie voor het beperken van cpu's niet door scans uitgevoerd en wordt optimaal gebruik gemaakt van de bronnen die beschikbaar zijn om de scan zo snel mogelijk te voltooien.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>PowerShell-cmdlets voor planningsscans om herstel te voltooien

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>PowerShell-cmdlets voor het plannen van dagelijkse scans

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [en Defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.


