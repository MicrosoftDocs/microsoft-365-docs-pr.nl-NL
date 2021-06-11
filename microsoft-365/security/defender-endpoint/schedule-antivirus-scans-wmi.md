---
title: Antivirusscans plannen met Windows Management Instrumentation
description: Antivirusscans plannen met WMI
keywords: quick scan, full scan, WMI, schedule, antivirus
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879672"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Antivirusscans plannen met Windows Management Instrumentation (WMI)

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u geplande scans configureert met WMI. Zie Geplande snelle of volledige Microsoft Defender Antivirus configureren voor meer informatie over planningsscans [en scantypen.](schedule-antivirus-scans.md) 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Gebruik Windows Management Instruction (WMI) om scans te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI voor planningsscans wanneer een eindpunt niet wordt gebruikt

Gebruik de [methode Set of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) voor de volgende eigenschappen:

```WMI
ScanOnlyIfIdleEnabled
```

Zie voor meer informatie over API's en toegestane parameters [Windows Defender WMIv2-API's.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> Wanneer u scans inplant voor tijden waarin eindpunten niet worden gebruikt, wordt de configuratie voor het beperken van cpu's niet door scans uitgevoerd en wordt optimaal gebruik gemaakt van de bronnen die beschikbaar zijn om de scan zo snel mogelijk te voltooien.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI voor het plannen van scans om herstel te voltooien

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="wmi-for-scheduling-daily-scans"></a>WMI voor het plannen van dagelijkse scans

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanScheduleQuickScanTime
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

