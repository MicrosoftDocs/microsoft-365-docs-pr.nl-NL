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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789169"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="6915f-104">Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="6915f-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="6915f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6915f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6915f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6915f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6915f-107">U kunt een scan op aanvraag uitvoeren op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="6915f-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="6915f-108">Deze scans worden direct uitgevoerd en u kunt parameters voor de scan definiëren, zoals de locatie of het type.</span><span class="sxs-lookup"><span data-stu-id="6915f-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="6915f-109">Snelle scan versus volledige scan</span><span class="sxs-lookup"><span data-stu-id="6915f-109">Quick scan versus full scan</span></span>

<span data-ttu-id="6915f-110">Snel scannen bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen.</span><span class="sxs-lookup"><span data-stu-id="6915f-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6915f-111">Microsoft Defender Antivirus wordt uitgevoerd in de context van het [LocalSystem-account](/windows/win32/services/localsystem-account) bij het uitvoeren van een lokale scan.</span><span class="sxs-lookup"><span data-stu-id="6915f-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="6915f-112">Voor netwerkscans wordt de context van het apparaataccount gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6915f-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="6915f-113">Als het domeinapparaataccount niet over de juiste machtigingen voor toegang tot het delen heeft, werkt de scan niet.</span><span class="sxs-lookup"><span data-stu-id="6915f-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="6915f-114">Controleer of het apparaat machtigingen heeft voor het delen van het access-netwerk.</span><span class="sxs-lookup"><span data-stu-id="6915f-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="6915f-115">In combinatie [met de altijd-on-realtimebeveiligingsmogelijkheden](configure-real-time-protection-microsoft-defender-antivirus.md)biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau.</span><span class="sxs-lookup"><span data-stu-id="6915f-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="6915f-116">Altijd-aan, realtime beveiliging controleert bestanden wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert.</span><span class="sxs-lookup"><span data-stu-id="6915f-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="6915f-117">Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.</span><span class="sxs-lookup"><span data-stu-id="6915f-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="6915f-118">In de meeste gevallen is een snelle scan voldoende om malware te vinden die niet is opgehaald door realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="6915f-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="6915f-119">Een volledige scan kan handig zijn wanneer een malwaredreiging wordt gerapporteerd op een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6915f-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="6915f-120">Met de scan kan worden bepaald of er inactieve onderdelen zijn die een grondigere opruiming vereisen.</span><span class="sxs-lookup"><span data-stu-id="6915f-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="6915f-121">Microsoft raadt over het algemeen echter aan snelle scans te gebruiken in plaats van volledige scans.</span><span class="sxs-lookup"><span data-stu-id="6915f-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="6915f-122">Een volledige scan kan enkele uren of dagen duren, afhankelijk van de hoeveelheid en het type gegevens dat moet worden gescand.</span><span class="sxs-lookup"><span data-stu-id="6915f-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="6915f-123">Zie Snel scannen versus volledige scan en aangepaste scan voor meer informatie over de verschillen tussen snelle en volledige [scans.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="6915f-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="6915f-124">Een Microsoft Endpoint Manager gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="6915f-125">Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="6915f-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="6915f-126">Kies **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="6915f-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="6915f-127">Selecteer in de lijst met tabbladen **Windows 10 niet-ongezonde eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="6915f-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="6915f-128">Selecteer snel scannen of  Volledig scannen in de lijst met **acties.**</span><span class="sxs-lookup"><span data-stu-id="6915f-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="6915f-129">[![AFBEELDING ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6915f-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="6915f-130">Zie [Antimalware-](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)en firewalltaken voor meer informatie over het Microsoft Endpoint Manager voor het uitvoeren van een scan: Een scan op aanvraag uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6915f-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="6915f-131">Het hulpprogramma mpcmdrun.exe opdrachtregel gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="6915f-132">Gebruik de volgende `-scan` parameter:</span><span class="sxs-lookup"><span data-stu-id="6915f-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="6915f-133">Zie Het opdrachtlijnhulpmiddel mpcmdrun.exe gebruiken voor het configureren en beheren van Microsoft Defender Antivirus voor meer informatie over het gebruik van het hulpprogramma en aanvullende parameters, zoals het starten van een volledige scan of het definiëren van [paden.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6915f-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="6915f-134">Een Microsoft Intune gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="6915f-135">Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="6915f-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="6915f-136">Selecteer in de zijbalk **Apparaten > Alle apparaten** en kies het apparaat dat u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="6915f-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="6915f-137">Selecteer **... Meer**.</span><span class="sxs-lookup"><span data-stu-id="6915f-137">Select **...More**.</span></span> <span data-ttu-id="6915f-138">Selecteer in de opties **Snel scannen** of **Volledig scannen.**</span><span class="sxs-lookup"><span data-stu-id="6915f-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="6915f-139">De app Windows-beveiliging gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="6915f-140">Zie [Een scan uitvoeren in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md) voor instructies voor het uitvoeren van een scan op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="6915f-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="6915f-141">PowerShell-cmdlets gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="6915f-142">Gebruik de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6915f-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="6915f-143">Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="6915f-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="6915f-144">Gebruik Windows Management Instruction (WMI) om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6915f-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="6915f-145">Gebruik de [ **beginmethode** van](/previous-versions/windows/desktop/defender/start-msft-mpscan) de **MSFT_MpScan** klas.</span><span class="sxs-lookup"><span data-stu-id="6915f-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="6915f-146">Zie voor meer informatie over welke parameters zijn toegestaan Windows Defender [WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="6915f-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="6915f-147">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="6915f-147">Related articles</span></span>

- [<span data-ttu-id="6915f-148">Microsoft Defender Antivirus-scanopties configureren</span><span class="sxs-lookup"><span data-stu-id="6915f-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6915f-149">Geplande scans Microsoft Defender Antivirus configureren</span><span class="sxs-lookup"><span data-stu-id="6915f-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6915f-150">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="6915f-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)