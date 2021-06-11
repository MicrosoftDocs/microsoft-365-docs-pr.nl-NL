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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="f1349-104">Antivirusscans plannen met Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="f1349-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="f1349-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f1349-105">**Applies to:**</span></span>

- [<span data-ttu-id="f1349-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f1349-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f1349-107">In dit artikel wordt beschreven hoe u geplande scans configureert met WMI.</span><span class="sxs-lookup"><span data-stu-id="f1349-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="f1349-108">Zie Geplande snelle of volledige Microsoft Defender Antivirus configureren voor meer informatie over planningsscans [en scantypen.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="f1349-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="f1349-109">Gebruik Windows Management Instruction (WMI) om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="f1349-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="f1349-110">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="f1349-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="f1349-111">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f1349-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="f1349-112">WMI voor planningsscans wanneer een eindpunt niet wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="f1349-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="f1349-113">Gebruik de [methode Set of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="f1349-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="f1349-114">Zie voor meer informatie over API's en toegestane parameters [Windows Defender WMIv2-API's.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f1349-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="f1349-115">Wanneer u scans inplant voor tijden waarin eindpunten niet worden gebruikt, wordt de configuratie voor het beperken van cpu's niet door scans uitgevoerd en wordt optimaal gebruik gemaakt van de bronnen die beschikbaar zijn om de scan zo snel mogelijk te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f1349-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="f1349-116">WMI voor het plannen van scans om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="f1349-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="f1349-117">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="f1349-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="f1349-118">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="f1349-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="f1349-119">WMI voor het plannen van dagelijkse scans</span><span class="sxs-lookup"><span data-stu-id="f1349-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="f1349-120">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="f1349-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="f1349-121">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="f1349-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

