---
title: On-demand scans uitvoeren en aanpassen in Microsoft Defender AV
description: On-demand scans uitvoeren en configureren met PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows Security-app
keywords: scannen, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690541"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b51d1-104">On-demand Microsoft Defender Antivirus scans configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b51d1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b51d1-105">**Applies to:**</span></span>

- [<span data-ttu-id="b51d1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b51d1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b51d1-107">U kunt een scan op aanvraag uitvoeren op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b51d1-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="b51d1-108">Deze scans worden direct uitgevoerd en u kunt parameters voor de scan definiëren, zoals de locatie of het type.</span><span class="sxs-lookup"><span data-stu-id="b51d1-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="b51d1-109">Snelle scan versus volledige scan</span><span class="sxs-lookup"><span data-stu-id="b51d1-109">Quick scan versus full scan</span></span>

<span data-ttu-id="b51d1-110">Snel scannen bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende opstartmappen van Windows.</span><span class="sxs-lookup"><span data-stu-id="b51d1-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b51d1-111">Microsoft Defender Antivirus wordt uitgevoerd in de context van het [LocalSystem-account](/windows/win32/services/localsystem-account) bij het uitvoeren van een lokale scan.</span><span class="sxs-lookup"><span data-stu-id="b51d1-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="b51d1-112">Voor netwerkscans wordt de context van het apparaataccount gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b51d1-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="b51d1-113">Als het domeinapparaataccount niet over de juiste machtigingen voor toegang tot het delen heeft, werkt de scan niet.</span><span class="sxs-lookup"><span data-stu-id="b51d1-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="b51d1-114">Controleer of het apparaat machtigingen heeft voor het delen van het access-netwerk.</span><span class="sxs-lookup"><span data-stu-id="b51d1-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="b51d1-115">In combinatie met de [altijd-on-realtimebeveiligingsfunctie](configure-real-time-protection-microsoft-defender-antivirus.md)(die bestanden controleert wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert) biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau.</span><span class="sxs-lookup"><span data-stu-id="b51d1-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="b51d1-116">In de meeste gevallen is een snelle scan voldoende om malware te vinden die niet is opgehaald door realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="b51d1-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="b51d1-117">Een volledige scan kan handig zijn voor eindpunten die een malware-bedreiging hebben gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="b51d1-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="b51d1-118">De scan kan bepalen of er inactieve onderdelen zijn die een grondigere opruiming vereisen.</span><span class="sxs-lookup"><span data-stu-id="b51d1-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="b51d1-119">Dit is ideaal als uw organisatie scans op aanvraag maakt.</span><span class="sxs-lookup"><span data-stu-id="b51d1-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="b51d1-120">Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.</span><span class="sxs-lookup"><span data-stu-id="b51d1-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="b51d1-121">Microsoft Endpoint Manager gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="b51d1-122">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="b51d1-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="b51d1-123">Kies **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b51d1-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="b51d1-124">Selecteer in de lijst met tabbladen **windows 10 ongezonde eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="b51d1-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="b51d1-125">Selecteer snel scannen of  Volledig scannen in de lijst met **acties.**</span><span class="sxs-lookup"><span data-stu-id="b51d1-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="b51d1-126">[![AFBEELDING ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b51d1-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="b51d1-127">Zie Antimalware- en firewalltaken voor meer informatie over het gebruik van Microsoft Endpoint Manager voor het uitvoeren van een scan: Een [on-demand scan uitvoeren.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="b51d1-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="b51d1-128">Het hulpprogramma mpcmdrun.exe opdrachtregel gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="b51d1-129">Gebruik de volgende `-scan` parameter:</span><span class="sxs-lookup"><span data-stu-id="b51d1-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="b51d1-130">Zie Het [hulpprogramma mpcmdrun.exe commandline gebruiken](command-line-arguments-microsoft-defender-antivirus.md)voor het configureren en beheren van Microsoft Defender Antivirus voor meer informatie over het gebruik van het hulpprogramma en aanvullende parameters, zoals het starten van een volledige scan of het definiëren van paden.</span><span class="sxs-lookup"><span data-stu-id="b51d1-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="b51d1-131">Microsoft Intune gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="b51d1-132">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="b51d1-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="b51d1-133">Selecteer in de zijbalk **Apparaten > Alle apparaten** en kies het apparaat dat u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="b51d1-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="b51d1-134">Selecteer **... Meer**.</span><span class="sxs-lookup"><span data-stu-id="b51d1-134">Select **...More**.</span></span> <span data-ttu-id="b51d1-135">Selecteer in de opties **Snel scannen** of **Volledig scannen.**</span><span class="sxs-lookup"><span data-stu-id="b51d1-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="b51d1-136">De Windows Security-app gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="b51d1-137">Zie [Een scan uitvoeren in de Windows Security-app](microsoft-defender-security-center-antivirus.md) voor instructies voor het uitvoeren van een scan op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b51d1-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="b51d1-138">PowerShell-cmdlets gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="b51d1-139">Gebruik de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b51d1-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="b51d1-140">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/)te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b51d1-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="b51d1-141">Windows Management Instruction (WMI) gebruiken om een scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b51d1-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="b51d1-142">Gebruik de [ **beginmethode** van](/previous-versions/windows/desktop/defender/start-msft-mpscan) de **MSFT_MpScan** klas.</span><span class="sxs-lookup"><span data-stu-id="b51d1-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="b51d1-143">Zie [WINDOWS Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) voor meer informatie over welke parameters zijn toegestaan.</span><span class="sxs-lookup"><span data-stu-id="b51d1-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="b51d1-144">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b51d1-144">Related articles</span></span>

- [<span data-ttu-id="b51d1-145">Scanopties voor Microsoft Defender Antivirus configureren</span><span class="sxs-lookup"><span data-stu-id="b51d1-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b51d1-146">Geplande Microsoft Defender Antivirus-scans configureren</span><span class="sxs-lookup"><span data-stu-id="b51d1-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b51d1-147">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b51d1-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)