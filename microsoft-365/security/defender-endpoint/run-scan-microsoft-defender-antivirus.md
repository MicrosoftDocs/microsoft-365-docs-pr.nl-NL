---
title: On-demand scans uitvoeren en aanpassen in Microsoft Defender Antivirus
description: On-demand scans uitvoeren en configureren met behulp van PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows-beveiliging app
keywords: scannen, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878800"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b5722-104">Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b5722-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="b5722-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b5722-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5722-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b5722-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b5722-107">U kunt een scan op aanvraag uitvoeren op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b5722-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="b5722-108">Deze scans worden direct uitgevoerd en u kunt parameters voor de scan definiëren, zoals de locatie of het type.</span><span class="sxs-lookup"><span data-stu-id="b5722-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="b5722-109">Wanneer u een scan uit te voeren, kunt u kiezen uit drie typen: Snelle scan, volledige scan en aangepaste scan.</span><span class="sxs-lookup"><span data-stu-id="b5722-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="b5722-110">Gebruik in de meeste gevallen een snelle scan.</span><span class="sxs-lookup"><span data-stu-id="b5722-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="b5722-111">Een snelle scan bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen.</span><span class="sxs-lookup"><span data-stu-id="b5722-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="b5722-112">Gecombineerd met altijd-aan, realtime beveiliging, die bestanden controleert wanneer ze worden geopend en gesloten, en wanneer een gebruiker naar een map navigeert, biedt een snelle scan een sterke bescherming tegen malware die begint met malware op systeem- en kernelniveau.</span><span class="sxs-lookup"><span data-stu-id="b5722-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="b5722-113">In de meeste gevallen is een snelle scan voldoende en is dit de aanbevolen optie voor geplande of on-demand scans.</span><span class="sxs-lookup"><span data-stu-id="b5722-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="b5722-114">[Meer informatie over scantypen.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="b5722-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5722-115">Microsoft Defender Antivirus wordt uitgevoerd in de context van het [LocalSystem-account](/windows/win32/services/localsystem-account) bij het uitvoeren van een lokale scan.</span><span class="sxs-lookup"><span data-stu-id="b5722-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="b5722-116">Voor netwerkscans wordt de context van het apparaataccount gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b5722-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="b5722-117">Als het domeinapparaataccount niet over de juiste machtigingen voor toegang tot het delen heeft, werkt de scan niet.</span><span class="sxs-lookup"><span data-stu-id="b5722-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="b5722-118">Controleer of het apparaat machtigingen heeft voor het delen van het access-netwerk.</span><span class="sxs-lookup"><span data-stu-id="b5722-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="b5722-119">Een Microsoft Endpoint Manager gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="b5722-120">Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="b5722-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="b5722-121">Kies **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b5722-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="b5722-122">Selecteer in de lijst met tabbladen **Windows 10 niet-ongezonde eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="b5722-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="b5722-123">Selecteer quick **scan** (aanbevolen) of Volledig **scannen** in de lijst met acties.</span><span class="sxs-lookup"><span data-stu-id="b5722-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="b5722-124">[![AFBEELDING ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b5722-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="b5722-125">Zie [Antimalware-](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)en firewalltaken voor meer informatie over het Microsoft Endpoint Manager voor het uitvoeren van een scan: Een scan op aanvraag uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b5722-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="b5722-126">Het hulpprogramma mpcmdrun.exe opdrachtregel gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="b5722-127">Gebruik de volgende `-scan` parameter:</span><span class="sxs-lookup"><span data-stu-id="b5722-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="b5722-128">Zie Het opdrachtlijnhulpmiddel mpcmdrun.exe gebruiken voor het configureren en beheren van Microsoft Defender Antivirus voor meer informatie over het gebruik van het hulpprogramma en aanvullende parameters, zoals het starten van een volledige scan of het definiëren van [paden.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b5722-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="b5722-129">Een Microsoft Intune gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="b5722-130">Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="b5722-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="b5722-131">Selecteer in de zijbalk **Apparaten**  >  **alle apparaten en** kies het apparaat dat u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="b5722-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="b5722-132">Selecteer **... Meer**.</span><span class="sxs-lookup"><span data-stu-id="b5722-132">Select **...More**.</span></span> <span data-ttu-id="b5722-133">Selecteer in de opties **Snel scannen** (aanbevolen) of **Volledig scannen.**</span><span class="sxs-lookup"><span data-stu-id="b5722-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="b5722-134">De app Windows-beveiliging gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="b5722-135">Zie [Een scan uitvoeren in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md) voor instructies voor het uitvoeren van een scan op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b5722-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="b5722-136">PowerShell-cmdlets gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="b5722-137">Gebruik de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5722-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="b5722-138">Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b5722-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="b5722-139">Gebruik Windows Management Instruction (WMI) om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b5722-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="b5722-140">Gebruik de [ **beginmethode** van](/previous-versions/windows/desktop/defender/start-msft-mpscan) de **MSFT_MpScan** klas.</span><span class="sxs-lookup"><span data-stu-id="b5722-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="b5722-141">Zie voor meer informatie over welke parameters zijn toegestaan Windows Defender [WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b5722-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

