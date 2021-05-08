---
title: Plan regelmatig snelle en volledige scans met Microsoft Defender Antivirus
description: Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
keywords: quick scan, full scan, quick vs full, schedule scan, daily, weekly, time, scheduled, recurring, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274686"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="d3e1a-104">Geplande snelle of volledige Microsoft Defender Antivirus-scans configureren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="d3e1a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d3e1a-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3e1a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d3e1a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="d3e1a-107">Standaard wordt Microsoft Defender Antivirus 15 minuten vóór de tijd van geplande scans gecontroleerd op een update.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="d3e1a-108">U kunt [de planning beheren voor wanneer beveiligingsupdates moeten worden gedownload](manage-protection-update-schedule-microsoft-defender-antivirus.md) en toegepast om deze standaard te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="d3e1a-109">Naast realtime-beveiliging en scans op [](run-scan-microsoft-defender-antivirus.md) aanvraag kunt u ook regelmatige, geplande scans instellen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="d3e1a-110">U kunt het type scan configureren, wanneer de scan moet [](manage-protection-updates-microsoft-defender-antivirus.md) plaatsvinden en of de scan moet plaatsvinden na een beveiligingsupdate of als het eindpunt wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="d3e1a-111">U kunt ook opgeven wanneer speciale scans moeten worden uitgevoerd om herstel te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="d3e1a-112">In dit artikel wordt beschreven hoe u geplande scans configureert met groepsbeleid, PowerShell-cmdlets en WMI.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="d3e1a-113">U kunt ook planningsscans configureren [met Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) of [Microsoft Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="d3e1a-114">De instellingen voor groepsbeleid configureren die in dit artikel worden beschreven</span><span class="sxs-lookup"><span data-stu-id="d3e1a-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="d3e1a-115">Ga op uw groepsbeleidsbeheercomputer in de groepsbeleidseditor naar **Beheersjablonen** voor computerconfiguratie Windows  >    >  **Onderdelen**  >  **Microsoft Defender Antivirus**  >  **scannen.**</span><span class="sxs-lookup"><span data-stu-id="d3e1a-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="d3e1a-116">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d3e1a-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="d3e1a-117">Geef instellingen op voor het groepsbeleidsobject en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="d3e1a-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="d3e1a-118">Herhaal stap 1-4 voor elke instelling die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="d3e1a-119">Implementeer het groepsbeleidsobject zoals u dat normaal doet.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="d3e1a-120">Zie Een groepsbeleidsobject maken als u hulp nodig hebt bij [groepsbeleidsobjecten.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="d3e1a-121">Zie ook de [onderwerpen Beheren wanneer beveiligingsupdates](manage-protection-update-schedule-microsoft-defender-antivirus.md) moeten worden gedownload en toegepast en Voorkomen of [toestaan](configure-local-policy-overrides-microsoft-defender-antivirus.md) dat gebruikers beleidsinstellingen lokaal kunnen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="d3e1a-122">Snelle scan versus volledige scan en aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="d3e1a-123">Wanneer u geplande scans in stelt, kunt u instellen of de scan een volledige scan of een snelle scan moet zijn.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="d3e1a-124">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-124">Quick scan</span></span>  |<span data-ttu-id="d3e1a-125">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-125">Full scan</span></span>  | <span data-ttu-id="d3e1a-126">Aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d3e1a-127">Een snelle scan bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="d3e1a-128">In de meeste gevallen is een snelle scan voldoende en wordt aanbevolen voor geplande scans.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="d3e1a-129">Een volledige scan begint met een snelle scan en gaat vervolgens verder met een sequentiële bestandsscan van alle vaste schijven en verwisselbare/netwerkstations (als de volledige scan is geconfigureerd om dit te doen).</span><span class="sxs-lookup"><span data-stu-id="d3e1a-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="d3e1a-130">Een volledige scan kan enkele uren of dagen duren, afhankelijk van de hoeveelheid en het type gegevens dat moet worden gescand.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="d3e1a-131">Wanneer de volledige scan is voltooid, is er nieuwe beveiligingsinformatie beschikbaar en is een nieuwe scan vereist om ervoor te zorgen dat er geen andere bedreigingen worden gedetecteerd met de nieuwe beveiligingsintelligentie.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="d3e1a-132">Een aangepaste scan is een snelle scan die wordt uitgevoerd op de bestanden en mappen die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="d3e1a-133">U kunt er bijvoorbeeld voor kiezen om een USB-station of een specifieke map op het lokale station van uw apparaat te scannen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="d3e1a-134">Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="d3e1a-135">Hoe weet ik welk scantype ik moet kiezen?</span><span class="sxs-lookup"><span data-stu-id="d3e1a-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="d3e1a-136">Gebruik de volgende tabel om een scantype te kiezen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="d3e1a-137">Scenario</span><span class="sxs-lookup"><span data-stu-id="d3e1a-137">Scenario</span></span>  |<span data-ttu-id="d3e1a-138">Aanbevolen scantype</span><span class="sxs-lookup"><span data-stu-id="d3e1a-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="d3e1a-139">U wilt normale, geplande scans instellen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="d3e1a-140">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-140">Quick scan</span></span> <p><span data-ttu-id="d3e1a-141">Met een snelle scan worden de processen, het geheugen, de profielen en bepaalde locaties op het apparaat gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="d3e1a-142">In combinatie [met realtime-beveiliging](configure-real-time-protection-microsoft-defender-antivirus.md)die altijd wordt gebruikt, biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="d3e1a-143">Realtime beveiliging controleert bestanden wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="d3e1a-144">Bedreigingen, zoals malware, worden gedetecteerd op een apparaat</span><span class="sxs-lookup"><span data-stu-id="d3e1a-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="d3e1a-145">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-145">Full scan</span></span> <p><span data-ttu-id="d3e1a-146">Een volledige scan kan helpen bepalen of er inactieve onderdelen zijn die een grondigere opruiming vereisen.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="d3e1a-147">U wilt een [scan op aanvraag uitvoeren](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="d3e1a-148">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-148">Full scan</span></span>  <p><span data-ttu-id="d3e1a-149">Een volledige scan bekijkt alle bestanden op de apparaatschijf, inclusief bestanden die verouderd, gearchiveerd en niet dagelijks worden geopend.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="d3e1a-150">U wilt ervoor zorgen dat een draagbaar apparaat, zoals een USB-station, geen malware bevat</span><span class="sxs-lookup"><span data-stu-id="d3e1a-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="d3e1a-151">Aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-151">Custom scan</span></span> <p><span data-ttu-id="d3e1a-152">Met een aangepaste scan kunt u specifieke locaties, mappen of bestanden selecteren en een snelle scan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="d3e1a-153">Wat moet ik nog meer weten over snelle en volledige scans?</span><span class="sxs-lookup"><span data-stu-id="d3e1a-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="d3e1a-154">Schadelijke bestanden kunnen worden opgeslagen op locaties die niet zijn opgenomen in een snelle scan.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="d3e1a-155">In realtime-beveiliging worden echter alle bestanden die worden geopend en gesloten, en alle bestanden in mappen die door een gebruiker worden geopend, gereviewd.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="d3e1a-156">De combinatie van realtimebeveiliging en een snelle scan biedt een sterke bescherming tegen malware.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="d3e1a-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) help ensure that all the files accessed on the system are being scand with the latest security intelligence and cloud machine learning models.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="d3e1a-158">Wanneer realtimebeveiliging malware detecteert en de omvang van de getroffen bestanden in eerste instantie niet wordt bepaald, wordt Microsoft Defender Antivirus een volledige scan gestart als onderdeel van het herstelproces.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="d3e1a-159">Met een volledige scan kunnen schadelijke bestanden worden gedetecteerd die niet zijn gedetecteerd door andere scans, zoals een snelle scan.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="d3e1a-160">Een volledige scan kan echter even duren en kostbare systeembronnen gebruiken om deze te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="d3e1a-161">Als een apparaat langere tijd offline is, kan het langer duren om een volledige scan te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="d3e1a-162">Geplande scans instellen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-162">Set up scheduled scans</span></span>

<span data-ttu-id="d3e1a-163">Geplande scans worden uitgevoerd op de dag en tijd die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="d3e1a-164">U kunt Groepsbeleid, PowerShell en WMI gebruiken om geplande scans te configureren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="d3e1a-165">Als een apparaat wordt losgekoppeld en op de batterij wordt uitgevoerd tijdens een geplande volledige scan, stopt de geplande scan met gebeurtenis 1002, waarin staat dat de scan is gestopt vóór voltooiing.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="d3e1a-166">Microsoft Defender Antivirus wordt op de volgende geplande tijd een volledige scan uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="d3e1a-167">Groepsbeleid gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="d3e1a-168">Locatie</span><span class="sxs-lookup"><span data-stu-id="d3e1a-168">Location</span></span> | <span data-ttu-id="d3e1a-169">Instelling</span><span class="sxs-lookup"><span data-stu-id="d3e1a-169">Setting</span></span> | <span data-ttu-id="d3e1a-170">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d3e1a-170">Description</span></span> | <span data-ttu-id="d3e1a-171">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d3e1a-172">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-172">Scan</span></span> | <span data-ttu-id="d3e1a-173">Het scantype opgeven dat moet worden gebruikt voor een geplande scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="d3e1a-174">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="d3e1a-174">Quick scan</span></span> |
|<span data-ttu-id="d3e1a-175">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-175">Scan</span></span> | <span data-ttu-id="d3e1a-176">De dag van de week opgeven om een geplande scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="d3e1a-177">Geef de dag (of nooit) op om een scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="d3e1a-178">Nooit</span><span class="sxs-lookup"><span data-stu-id="d3e1a-178">Never</span></span> |
|<span data-ttu-id="d3e1a-179">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-179">Scan</span></span> | <span data-ttu-id="d3e1a-180">De tijd van de dag opgeven om een geplande scan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="d3e1a-181">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur).</span><span class="sxs-lookup"><span data-stu-id="d3e1a-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="d3e1a-182">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="d3e1a-182">2 a.m.</span></span> |
|<span data-ttu-id="d3e1a-183">Hoofdmap</span><span class="sxs-lookup"><span data-stu-id="d3e1a-183">Root</span></span> | <span data-ttu-id="d3e1a-184">Geplande taaktijden willekeurig maken</span><span class="sxs-lookup"><span data-stu-id="d3e1a-184">Randomize scheduled task times</span></span> |<span data-ttu-id="d3e1a-185">In Microsoft Defender Antivirus de begintijd van de scan willekeurig instellen op een interval van 0 tot 4 uur.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="d3e1a-186">In [SCEP](/mem/intune/protect/certificates-scep-configure)kunt u een willekeurige scan instellen op een interval plus of min 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="d3e1a-187">Dit kan handig zijn in virtuele machines of VDI-implementaties.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="d3e1a-188">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d3e1a-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="d3e1a-189">PowerShell-cmdlets gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="d3e1a-190">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="d3e1a-191">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="d3e1a-192">Gebruik Windows Management Instruction (WMI) om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="d3e1a-193">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="d3e1a-194">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="d3e1a-195">Geplande scans alleen starten als het eindpunt niet wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="d3e1a-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="d3e1a-196">U kunt instellen dat de geplande scan alleen wordt uitgevoerd wanneer het eindpunt is ingeschakeld, maar niet wordt gebruikt met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="d3e1a-197">Met deze scans wordt de configuratie voor het beperken van cpu's niet in ere gehouden en wordt optimaal gebruik gemaakt van de beschikbare bronnen om de scan zo snel mogelijk te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="d3e1a-198">Groepsbeleid gebruiken om scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="d3e1a-199">Locatie</span><span class="sxs-lookup"><span data-stu-id="d3e1a-199">Location</span></span> | <span data-ttu-id="d3e1a-200">Instelling</span><span class="sxs-lookup"><span data-stu-id="d3e1a-200">Setting</span></span> | <span data-ttu-id="d3e1a-201">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d3e1a-201">Description</span></span> | <span data-ttu-id="d3e1a-202">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d3e1a-203">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-203">Scan</span></span> | <span data-ttu-id="d3e1a-204">De geplande scan alleen starten wanneer de computer is aan, maar niet in gebruik is</span><span class="sxs-lookup"><span data-stu-id="d3e1a-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="d3e1a-205">Geplande scans worden niet uitgevoerd, tenzij de computer is aan maar niet in gebruik is</span><span class="sxs-lookup"><span data-stu-id="d3e1a-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="d3e1a-206">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d3e1a-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="d3e1a-207">PowerShell-cmdlets gebruiken</span><span class="sxs-lookup"><span data-stu-id="d3e1a-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="d3e1a-208">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="d3e1a-209">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken voor het configureren en uitvoeren van Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="d3e1a-210">Gebruik Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="d3e1a-211">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="d3e1a-212">Zie voor meer informatie over API's en toegestane parameters [Windows Defender WMIv2-API's.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="d3e1a-213">Configureren wanneer volledige scans moeten worden uitgevoerd om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="d3e1a-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="d3e1a-214">Voor sommige bedreigingen is mogelijk een volledige scan vereist om de verwijdering en herstel ervan te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="d3e1a-215">U kunt opgeven wanneer deze scans moeten plaatsvinden met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="d3e1a-216">Groepsbeleid gebruiken om herstel-vereiste scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="d3e1a-217">Locatie</span><span class="sxs-lookup"><span data-stu-id="d3e1a-217">Location</span></span> | <span data-ttu-id="d3e1a-218">Instelling</span><span class="sxs-lookup"><span data-stu-id="d3e1a-218">Setting</span></span> | <span data-ttu-id="d3e1a-219">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d3e1a-219">Description</span></span> | <span data-ttu-id="d3e1a-220">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="d3e1a-221">Herstellen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-221">Remediation</span></span> | <span data-ttu-id="d3e1a-222">Geef de dag van de week op om een geplande volledige scan uit te voeren om herstel te voltooien</span><span class="sxs-lookup"><span data-stu-id="d3e1a-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="d3e1a-223">Geef de dag (of nooit) op om een scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="d3e1a-224">Nooit</span><span class="sxs-lookup"><span data-stu-id="d3e1a-224">Never</span></span> |
|<span data-ttu-id="d3e1a-225">Herstellen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-225">Remediation</span></span> | <span data-ttu-id="d3e1a-226">Geef de tijd van de dag op om een geplande volledige scan uit te voeren om de hersteltijd te voltooien</span><span class="sxs-lookup"><span data-stu-id="d3e1a-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="d3e1a-227">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="d3e1a-228">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="d3e1a-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="d3e1a-229">PowerShell-cmdlets gebruiken</span><span class="sxs-lookup"><span data-stu-id="d3e1a-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="d3e1a-230">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="d3e1a-231">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="d3e1a-232">Gebruik Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="d3e1a-233">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="d3e1a-234">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="d3e1a-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="d3e1a-235">Dagelijkse snelle scans instellen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-235">Set up daily quick scans</span></span>

<span data-ttu-id="d3e1a-236">U kunt een dagelijkse snelle scan inschakelen die kan worden uitgevoerd naast uw andere geplande scans met Groepsbeleid, PowerShell of WMI.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="d3e1a-237">Groepsbeleid gebruiken om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="d3e1a-238">Locatie</span><span class="sxs-lookup"><span data-stu-id="d3e1a-238">Location</span></span> | <span data-ttu-id="d3e1a-239">Instelling</span><span class="sxs-lookup"><span data-stu-id="d3e1a-239">Setting</span></span> | <span data-ttu-id="d3e1a-240">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d3e1a-240">Description</span></span> | <span data-ttu-id="d3e1a-241">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d3e1a-242">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-242">Scan</span></span> | <span data-ttu-id="d3e1a-243">Geef het interval op om snelle scans per dag uit te voeren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="d3e1a-244">Geef op hoeveel uren moeten worden verstreken vóór de volgende snelle scan.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="d3e1a-245">Als u bijvoorbeeld elke twee uur wilt uitvoeren, typt u **2**, voor één keer per dag, voert u **24 in.**</span><span class="sxs-lookup"><span data-stu-id="d3e1a-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="d3e1a-246">Voer **0 in** om nooit een dagelijkse quick scan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="d3e1a-247">Nooit</span><span class="sxs-lookup"><span data-stu-id="d3e1a-247">Never</span></span> |
|<span data-ttu-id="d3e1a-248">Scannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-248">Scan</span></span> | <span data-ttu-id="d3e1a-249">De tijd voor een dagelijkse snelle scan opgeven</span><span class="sxs-lookup"><span data-stu-id="d3e1a-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="d3e1a-250">Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="d3e1a-251">02:00 uur</span><span class="sxs-lookup"><span data-stu-id="d3e1a-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="d3e1a-252">PowerShell-cmdlets gebruiken om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="d3e1a-253">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="d3e1a-254">Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [en Defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="d3e1a-255">Gebruik Windows Management Instruction (WMI) om dagelijkse scans te plannen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="d3e1a-256">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d3e1a-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="d3e1a-257">Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="d3e1a-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="d3e1a-258">Scans inschakelen na beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="d3e1a-258">Enable scans after protection updates</span></span>

<span data-ttu-id="d3e1a-259">U kunt een scan dwingen [](manage-protection-updates-microsoft-defender-antivirus.md) na elke beveiligingsupdate met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="d3e1a-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="d3e1a-260">Groepsbeleid gebruiken om scans te plannen na beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="d3e1a-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="d3e1a-261">Locatie</span><span class="sxs-lookup"><span data-stu-id="d3e1a-261">Location</span></span> | <span data-ttu-id="d3e1a-262">Instelling</span><span class="sxs-lookup"><span data-stu-id="d3e1a-262">Setting</span></span> | <span data-ttu-id="d3e1a-263">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d3e1a-263">Description</span></span> | <span data-ttu-id="d3e1a-264">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="d3e1a-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="d3e1a-265">Handtekeningupdates</span><span class="sxs-lookup"><span data-stu-id="d3e1a-265">Signature updates</span></span> | <span data-ttu-id="d3e1a-266">Scannen in-/uit-/uit-2014 in- en</span><span class="sxs-lookup"><span data-stu-id="d3e1a-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="d3e1a-267">Er wordt direct na het downloaden van een nieuwe beveiligingsupdate een scan uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="d3e1a-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="d3e1a-268">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d3e1a-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="d3e1a-269">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d3e1a-269">See also</span></span>

- [<span data-ttu-id="d3e1a-270">Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3e1a-271">Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3e1a-272">Microsoft Defender Antivirus-scanopties configureren</span><span class="sxs-lookup"><span data-stu-id="d3e1a-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3e1a-273">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="d3e1a-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3e1a-274">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="d3e1a-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="d3e1a-275">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="d3e1a-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)