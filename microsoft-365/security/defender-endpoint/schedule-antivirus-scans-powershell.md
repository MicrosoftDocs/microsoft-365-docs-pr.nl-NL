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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="92a9a-104">Antivirusscans plannen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="92a9a-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="92a9a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="92a9a-105">**Applies to:**</span></span>

- [<span data-ttu-id="92a9a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="92a9a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="92a9a-107">In dit artikel wordt beschreven hoe u geplande scans configureert met behulp van PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="92a9a-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="92a9a-108">Zie Geplande snelle of volledige Microsoft Defender Antivirus configureren voor meer informatie over planningsscans [en scantypen.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="92a9a-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="92a9a-109">PowerShell-cmdlets gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="92a9a-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="92a9a-110">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="92a9a-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="92a9a-111">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="92a9a-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="92a9a-112">PowerShell-cmdlets voor planningsscans wanneer een eindpunt niet wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="92a9a-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="92a9a-113">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="92a9a-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="92a9a-114">Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en uit te voeren](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="92a9a-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="92a9a-115">Wanneer u scans inplant voor tijden waarin eindpunten niet worden gebruikt, wordt de configuratie voor het beperken van cpu's niet door scans uitgevoerd en wordt optimaal gebruik gemaakt van de bronnen die beschikbaar zijn om de scan zo snel mogelijk te voltooien.</span><span class="sxs-lookup"><span data-stu-id="92a9a-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="92a9a-116">PowerShell-cmdlets voor planningsscans om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="92a9a-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="92a9a-117">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="92a9a-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="92a9a-118">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="92a9a-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="92a9a-119">PowerShell-cmdlets voor het plannen van dagelijkse scans</span><span class="sxs-lookup"><span data-stu-id="92a9a-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="92a9a-120">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="92a9a-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="92a9a-121">Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [en Defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="92a9a-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


