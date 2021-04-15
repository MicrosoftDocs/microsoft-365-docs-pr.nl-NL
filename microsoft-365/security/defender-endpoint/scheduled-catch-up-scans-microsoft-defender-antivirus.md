---
title: Regelmatige snelle en volledige scans plannen met Microsoft Defender Antivirus
description: Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
keywords: quick scan, full scan, quick vs full, schedule scan, daily, weekly, time, scheduled, recurring, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bfa616423fc0c097b9909df8abf5b9c414490383
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764085"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="04b29-104">Geplande snelle of volledige Microsoft Defender Antivirus-scans configureren</span><span class="sxs-lookup"><span data-stu-id="04b29-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="04b29-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="04b29-105">**Applies to:**</span></span>

- [<span data-ttu-id="04b29-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="04b29-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="04b29-107">Standaard wordt in Microsoft Defender Antivirus 15 minuten vóór de tijd van geplande scans gecontroleerd op een update.</span><span class="sxs-lookup"><span data-stu-id="04b29-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="04b29-108">U kunt [de planning beheren voor wanneer beveiligingsupdates moeten worden gedownload](manage-protection-update-schedule-microsoft-defender-antivirus.md) en toegepast om deze standaard te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="04b29-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="04b29-109">Naast realtime-beveiliging en scans op [](run-scan-microsoft-defender-antivirus.md) aanvraag kunt u ook regelmatige, geplande scans instellen.</span><span class="sxs-lookup"><span data-stu-id="04b29-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="04b29-110">U kunt het type scan configureren, wanneer de scan moet [](manage-protection-updates-microsoft-defender-antivirus.md) plaatsvinden en of de scan moet plaatsvinden na een beveiligingsupdate of als het eindpunt wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="04b29-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="04b29-111">U kunt ook opgeven wanneer speciale scans moeten worden uitgevoerd om herstel te voltooien.</span><span class="sxs-lookup"><span data-stu-id="04b29-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="04b29-112">In dit artikel wordt beschreven hoe u geplande scans configureert met groepsbeleid, PowerShell-cmdlets en WMI.</span><span class="sxs-lookup"><span data-stu-id="04b29-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="04b29-113">U kunt ook planningsscans configureren met [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) of Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="04b29-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="04b29-114">De instellingen voor groepsbeleid configureren die in dit artikel worden beschreven</span><span class="sxs-lookup"><span data-stu-id="04b29-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="04b29-115">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="04b29-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="04b29-116">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="04b29-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="04b29-117">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="04b29-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="04b29-118">Vouw de structuur uit **naar Windows-onderdelen > Microsoft Defender Antivirus** en vervolgens de locatie die is opgegeven in de onderstaande tabel. </span><span class="sxs-lookup"><span data-stu-id="04b29-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="04b29-119">Dubbelklik op de **beleidsinstelling** zoals aangegeven in de onderstaande tabel en stel de optie in op de gewenste configuratie.</span><span class="sxs-lookup"><span data-stu-id="04b29-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="04b29-120">Klik **op OK** en herhaal dit voor andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="04b29-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="04b29-121">Zie ook de [onderwerpen Beheren wanneer beveiligingsupdates](manage-protection-update-schedule-microsoft-defender-antivirus.md) moeten worden gedownload en toegepast en Voorkomen of [toestaan](configure-local-policy-overrides-microsoft-defender-antivirus.md) dat gebruikers beleidsinstellingen lokaal kunnen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="04b29-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="04b29-122">Snelle scan versus volledige scan en aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="04b29-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="04b29-123">Wanneer u geplande scans in stelt, kunt u instellen of de scan een volledige scan of een snelle scan moet zijn.</span><span class="sxs-lookup"><span data-stu-id="04b29-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="04b29-124">Snelle scans bekijken alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende opstartmappen van Windows.</span><span class="sxs-lookup"><span data-stu-id="04b29-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="04b29-125">In combinatie met de [altijd-on-realtimebeveiligingsfunctie](configure-real-time-protection-microsoft-defender-antivirus.md) , die bestanden controleert wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert, biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau.</span><span class="sxs-lookup"><span data-stu-id="04b29-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="04b29-126">In de meeste gevallen betekent dit dat een snelle scan voldoende is om malware te vinden die niet is opgehaald door realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="04b29-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="04b29-127">Een volledige scan kan handig zijn voor eindpunten die een malware-bedreiging hebben ondervonden om te bepalen of er inactieve onderdelen zijn die een grondigere opruiming vereisen.</span><span class="sxs-lookup"><span data-stu-id="04b29-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="04b29-128">In dit geval wilt u mogelijk een volledige scan gebruiken bij het uitvoeren van een [on-demand scan.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="04b29-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="04b29-129">Met een aangepaste scan kunt u de bestanden en mappen opgeven die u wilt scannen, zoals een USB-station.</span><span class="sxs-lookup"><span data-stu-id="04b29-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="04b29-130">Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.</span><span class="sxs-lookup"><span data-stu-id="04b29-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="04b29-131">Geplande scans instellen</span><span class="sxs-lookup"><span data-stu-id="04b29-131">Set up scheduled scans</span></span>

<span data-ttu-id="04b29-132">Geplande scans worden uitgevoerd op de dag en tijd die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="04b29-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="04b29-133">U kunt Groepsbeleid, PowerShell en WMI gebruiken om geplande scans te configureren.</span><span class="sxs-lookup"><span data-stu-id="04b29-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="04b29-134">Als een computer is losgekoppeld en tijdens een geplande volledige scan op de batterij werkt, stopt de geplande scan met gebeurtenis 1002, waarin staat dat de scan is gestopt vóór voltooiing.</span><span class="sxs-lookup"><span data-stu-id="04b29-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="04b29-135">Microsoft Defender Antivirus zal een volledige scan uitvoeren op de volgende geplande tijd.</span><span class="sxs-lookup"><span data-stu-id="04b29-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="04b29-136">Groepsbeleid gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="04b29-137">Locatie</span><span class="sxs-lookup"><span data-stu-id="04b29-137">Location</span></span> | <span data-ttu-id="04b29-138">Instelling</span><span class="sxs-lookup"><span data-stu-id="04b29-138">Setting</span></span> | <span data-ttu-id="04b29-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04b29-139">Description</span></span> | <span data-ttu-id="04b29-140">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="04b29-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04b29-141">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-141">Scan</span></span> | <span data-ttu-id="04b29-142">Het scantype opgeven dat moet worden gebruikt voor een geplande scan</span><span class="sxs-lookup"><span data-stu-id="04b29-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="04b29-143">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="04b29-143">Quick scan</span></span> |
|<span data-ttu-id="04b29-144">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-144">Scan</span></span> | <span data-ttu-id="04b29-145">De dag van de week opgeven om een geplande scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="04b29-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="04b29-146">Geef de dag (of nooit) op om een scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="04b29-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="04b29-147">Nooit</span><span class="sxs-lookup"><span data-stu-id="04b29-147">Never</span></span> |
|<span data-ttu-id="04b29-148">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-148">Scan</span></span> | <span data-ttu-id="04b29-149">De tijd van de dag opgeven om een geplande scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="04b29-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="04b29-150">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur).</span><span class="sxs-lookup"><span data-stu-id="04b29-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="04b29-151">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="04b29-151">2 a.m.</span></span> |
|<span data-ttu-id="04b29-152">Hoofdmap</span><span class="sxs-lookup"><span data-stu-id="04b29-152">Root</span></span> | <span data-ttu-id="04b29-153">Geplande taaktijden willekeurig maken</span><span class="sxs-lookup"><span data-stu-id="04b29-153">Randomize scheduled task times</span></span> |<span data-ttu-id="04b29-154">In Microsoft Defender Antivirus: De begintijd van de scan willekeurig instellen op een interval van 0 tot 4 uur.</span><span class="sxs-lookup"><span data-stu-id="04b29-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="04b29-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="04b29-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="04b29-156">Dit kan handig zijn in VM- of VDI-implementaties.</span><span class="sxs-lookup"><span data-stu-id="04b29-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="04b29-157">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="04b29-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="04b29-158">PowerShell-cmdlets gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="04b29-159">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="04b29-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="04b29-160">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="04b29-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="04b29-161">Windows Management Instruction (WMI) gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="04b29-162">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="04b29-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="04b29-163">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="04b29-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="04b29-164">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="04b29-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="04b29-165">Geplande scans alleen starten als het eindpunt niet wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="04b29-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="04b29-166">U kunt instellen dat de geplande scan alleen wordt uitgevoerd wanneer het eindpunt is ingeschakeld, maar niet wordt gebruikt met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="04b29-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="04b29-167">Met deze scans wordt de configuratie voor het beperken van cpu's niet in ere gehouden en wordt optimaal gebruik gemaakt van de beschikbare bronnen om de scan zo snel mogelijk te voltooien.</span><span class="sxs-lookup"><span data-stu-id="04b29-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="04b29-168">Groepsbeleid gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="04b29-169">Locatie</span><span class="sxs-lookup"><span data-stu-id="04b29-169">Location</span></span> | <span data-ttu-id="04b29-170">Instelling</span><span class="sxs-lookup"><span data-stu-id="04b29-170">Setting</span></span> | <span data-ttu-id="04b29-171">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04b29-171">Description</span></span> | <span data-ttu-id="04b29-172">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="04b29-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04b29-173">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-173">Scan</span></span> | <span data-ttu-id="04b29-174">De geplande scan alleen starten wanneer de computer is aan, maar niet in gebruik is</span><span class="sxs-lookup"><span data-stu-id="04b29-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="04b29-175">Geplande scans worden niet uitgevoerd, tenzij de computer is aan maar niet in gebruik is</span><span class="sxs-lookup"><span data-stu-id="04b29-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="04b29-176">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="04b29-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="04b29-177">PowerShell-cmdlets gebruiken</span><span class="sxs-lookup"><span data-stu-id="04b29-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="04b29-178">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="04b29-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="04b29-179">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="04b29-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="04b29-180">Windows Management Instruction (WMI) gebruiken</span><span class="sxs-lookup"><span data-stu-id="04b29-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="04b29-181">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="04b29-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="04b29-182">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="04b29-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="04b29-183">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="04b29-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="04b29-184">Configureren wanneer volledige scans moeten worden uitgevoerd om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="04b29-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="04b29-185">Voor sommige bedreigingen is mogelijk een volledige scan vereist om de verwijdering en herstel ervan te voltooien.</span><span class="sxs-lookup"><span data-stu-id="04b29-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="04b29-186">U kunt plannen wanneer deze scans moeten plaatsvinden met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="04b29-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="04b29-187">Groepsbeleid gebruiken om herstel-vereiste scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="04b29-188">Locatie</span><span class="sxs-lookup"><span data-stu-id="04b29-188">Location</span></span> | <span data-ttu-id="04b29-189">Instelling</span><span class="sxs-lookup"><span data-stu-id="04b29-189">Setting</span></span> | <span data-ttu-id="04b29-190">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04b29-190">Description</span></span> | <span data-ttu-id="04b29-191">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="04b29-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="04b29-192">Herstellen</span><span class="sxs-lookup"><span data-stu-id="04b29-192">Remediation</span></span> | <span data-ttu-id="04b29-193">Geef de dag van de week op om een geplande volledige scan uit te voeren om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="04b29-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="04b29-194">Geef de dag (of nooit) op om een scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="04b29-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="04b29-195">Nooit</span><span class="sxs-lookup"><span data-stu-id="04b29-195">Never</span></span> |
|<span data-ttu-id="04b29-196">Herstellen</span><span class="sxs-lookup"><span data-stu-id="04b29-196">Remediation</span></span> | <span data-ttu-id="04b29-197">Geef de tijd van de dag op om een geplande volledige scan uit te voeren om de hersteltijd te voltooien</span><span class="sxs-lookup"><span data-stu-id="04b29-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="04b29-198">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur)</span><span class="sxs-lookup"><span data-stu-id="04b29-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="04b29-199">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="04b29-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="04b29-200">PowerShell-cmdlets gebruiken</span><span class="sxs-lookup"><span data-stu-id="04b29-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="04b29-201">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="04b29-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="04b29-202">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="04b29-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="04b29-203">Windows Management Instruction (WMI) gebruiken</span><span class="sxs-lookup"><span data-stu-id="04b29-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="04b29-204">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="04b29-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="04b29-205">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="04b29-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="04b29-206">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="04b29-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="04b29-207">Dagelijkse snelle scans instellen</span><span class="sxs-lookup"><span data-stu-id="04b29-207">Set up daily quick scans</span></span>

<span data-ttu-id="04b29-208">U kunt een dagelijkse snelle scan inschakelen die kan worden uitgevoerd naast uw andere geplande scans met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="04b29-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="04b29-209">Groepsbeleid gebruiken om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="04b29-210">Locatie</span><span class="sxs-lookup"><span data-stu-id="04b29-210">Location</span></span> | <span data-ttu-id="04b29-211">Instelling</span><span class="sxs-lookup"><span data-stu-id="04b29-211">Setting</span></span> | <span data-ttu-id="04b29-212">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04b29-212">Description</span></span> | <span data-ttu-id="04b29-213">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="04b29-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04b29-214">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-214">Scan</span></span> | <span data-ttu-id="04b29-215">Geef het interval op om snelle scans per dag uit te voeren</span><span class="sxs-lookup"><span data-stu-id="04b29-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="04b29-216">Geef op hoeveel uren moeten worden verstreken vóór de volgende snelle scan.</span><span class="sxs-lookup"><span data-stu-id="04b29-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="04b29-217">Als u bijvoorbeeld elke twee uur wilt uitvoeren, typt u **2**, voor één keer per dag, voert u **24 in.**</span><span class="sxs-lookup"><span data-stu-id="04b29-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="04b29-218">Voer **0 in** om nooit een dagelijkse quick scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="04b29-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="04b29-219">Nooit</span><span class="sxs-lookup"><span data-stu-id="04b29-219">Never</span></span> |
|<span data-ttu-id="04b29-220">Scannen</span><span class="sxs-lookup"><span data-stu-id="04b29-220">Scan</span></span> | <span data-ttu-id="04b29-221">De tijd voor een dagelijkse snelle scan opgeven</span><span class="sxs-lookup"><span data-stu-id="04b29-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="04b29-222">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur)</span><span class="sxs-lookup"><span data-stu-id="04b29-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="04b29-223">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="04b29-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="04b29-224">PowerShell-cmdlets gebruiken om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="04b29-225">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="04b29-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="04b29-226">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="04b29-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="04b29-227">Windows Management Instruction (WMI) gebruiken om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="04b29-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="04b29-228">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="04b29-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="04b29-229">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="04b29-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="04b29-230">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="04b29-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="04b29-231">Scans inschakelen na beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="04b29-231">Enable scans after protection updates</span></span>

<span data-ttu-id="04b29-232">U kunt een scan dwingen [](manage-protection-updates-microsoft-defender-antivirus.md) na elke beveiligingsupdate met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="04b29-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="04b29-233">Groepsbeleid gebruiken om scans te plannen na beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="04b29-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="04b29-234">Locatie</span><span class="sxs-lookup"><span data-stu-id="04b29-234">Location</span></span> | <span data-ttu-id="04b29-235">Instelling</span><span class="sxs-lookup"><span data-stu-id="04b29-235">Setting</span></span> | <span data-ttu-id="04b29-236">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04b29-236">Description</span></span> | <span data-ttu-id="04b29-237">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="04b29-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="04b29-238">Handtekeningupdates</span><span class="sxs-lookup"><span data-stu-id="04b29-238">Signature updates</span></span> | <span data-ttu-id="04b29-239">Scannen in-/uit-/uit-2014 in- en</span><span class="sxs-lookup"><span data-stu-id="04b29-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="04b29-240">Er wordt direct na het downloaden van een nieuwe beveiligingsupdate een scan uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="04b29-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="04b29-241">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="04b29-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="04b29-242">Zie ook</span><span class="sxs-lookup"><span data-stu-id="04b29-242">See also</span></span>
- [<span data-ttu-id="04b29-243">Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen</span><span class="sxs-lookup"><span data-stu-id="04b29-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04b29-244">Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="04b29-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04b29-245">Microsoft Defender Antivirus-scanopties configureren</span><span class="sxs-lookup"><span data-stu-id="04b29-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04b29-246">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="04b29-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04b29-247">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="04b29-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="04b29-248">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="04b29-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)