---
title: Gebruik de opdrachtregel om de Microsoft Defender Antivirus
description: Voer Microsoft Defender Antivirus scans uit en configureer de beveiliging van de volgende generatie met een speciaal opdrachtregelprogramma.
keywords: Windows Defender-scan uitvoeren, antivirusscan uitvoeren vanaf opdrachtregel, Windows Defender-scan uitvoeren vanaf opdrachtregel, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538901"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="4752c-104">Uw Microsoft Defender Antivirus configureren en beheren met mpcmdrun.exe opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="4752c-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="4752c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4752c-105">**Applies to:**</span></span>

- [<span data-ttu-id="4752c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4752c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4752c-107">U kunt verschillende functies Microsoft Defender Antivirus uitvoeren met de speciale **opdrachtregelfunctiempcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="4752c-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="4752c-108">Dit hulpprogramma is handig als u het gebruik van Microsoft Defender Antivirus wilt automatiseren.</span><span class="sxs-lookup"><span data-stu-id="4752c-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="4752c-109">U vindt het hulpprogramma in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="4752c-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="4752c-110">U moet deze uitvoeren vanuit een opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="4752c-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="4752c-111">Mogelijk moet u een versie op beheerdersniveau van de opdrachtprompt openen.</span><span class="sxs-lookup"><span data-stu-id="4752c-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="4752c-112">Wanneer u in het menu **Start naar opdrachtprompt** zoekt, kiest u **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="4752c-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="4752c-113">Als u een bijgewerkte Versie van het Microsoft Defender-platform gebruikt, kunt u vanaf `**MpCmdRun**` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .</span><span class="sxs-lookup"><span data-stu-id="4752c-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="4752c-114">Zie voor meer informatie over het antimalwareplatform [Microsoft Defender Antivirus updates en basislijnen.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4752c-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="4752c-115">Het hulpprogramma MpCmdRun gebruikt de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="4752c-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="4752c-116">Hier volgt een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="4752c-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="4752c-117">Opdracht</span><span class="sxs-lookup"><span data-stu-id="4752c-117">Command</span></span>  | <span data-ttu-id="4752c-118">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4752c-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="4752c-119">`-?`**of**`-h`</span><span class="sxs-lookup"><span data-stu-id="4752c-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="4752c-120">Hiermee worden alle beschikbare opties voor dit hulpprogramma weergegeven</span><span class="sxs-lookup"><span data-stu-id="4752c-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="4752c-121">Scant op schadelijke software.</span><span class="sxs-lookup"><span data-stu-id="4752c-121">Scans for malicious software.</span></span> <span data-ttu-id="4752c-122">Waarden voor **ScanType** zijn:</span><span class="sxs-lookup"><span data-stu-id="4752c-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="4752c-123">**0** Standaard, volgens uw configuratie</span><span class="sxs-lookup"><span data-stu-id="4752c-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="4752c-124">**-1** Snelle scan</span><span class="sxs-lookup"><span data-stu-id="4752c-124">**-1** Quick scan</span></span><p><span data-ttu-id="4752c-125">**-2** Volledige scan</span><span class="sxs-lookup"><span data-stu-id="4752c-125">**-2** Full scan</span></span><p><span data-ttu-id="4752c-126">**-3** Aangepaste bestands- en adreslijstscan.</span><span class="sxs-lookup"><span data-stu-id="4752c-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="4752c-127">CpuThrottling zal de geconfigureerde CPU-beperking van beleid eren</span><span class="sxs-lookup"><span data-stu-id="4752c-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="4752c-128">Diagnostische tracering starten</span><span class="sxs-lookup"><span data-stu-id="4752c-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="4752c-129">Verzamelt ondersteuningsgegevens.</span><span class="sxs-lookup"><span data-stu-id="4752c-129">Collects support information.</span></span> <span data-ttu-id="4752c-130">Zie['diagnostische gegevens verzamelen'](collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="4752c-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="4752c-131">Hetzelfde als `-GetFiles` , maar wordt uitgevoerd naar een tijdelijke DiagTrack-map</span><span class="sxs-lookup"><span data-stu-id="4752c-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="4752c-132">Herstelt de geïnstalleerde beveiligingsinformatie naar een vorige back-upkopie of naar de oorspronkelijke standaardset</span><span class="sxs-lookup"><span data-stu-id="4752c-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="4752c-133">Verwijdert alleen de dynamisch gedownloade beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="4752c-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="4752c-134">Herstelt de vorige geïnstalleerde engine</span><span class="sxs-lookup"><span data-stu-id="4752c-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="4752c-135">Controleert op nieuwe beveiligingsinformatie-updates</span><span class="sxs-lookup"><span data-stu-id="4752c-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="4752c-136">Herstelt of lijsten met in quarantaine geplaatste items(en)</span><span class="sxs-lookup"><span data-stu-id="4752c-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="4752c-137">Dynamische beveiligingsintelligentie laden</span><span class="sxs-lookup"><span data-stu-id="4752c-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="4752c-138">Bevat de geladen dynamische beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="4752c-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="4752c-139">Hiermee verwijdert u dynamische beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="4752c-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="4752c-140">Hiermee wordt gecontroleerd of een pad is uitgesloten</span><span class="sxs-lookup"><span data-stu-id="4752c-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="4752c-141">Controleert of uw netwerk kan communiceren met de Microsoft Defender Antivirus cloudservice.</span><span class="sxs-lookup"><span data-stu-id="4752c-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="4752c-142">Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="4752c-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="4752c-143">Veelvoorkomende fouten bij het uitvoeren van opdrachten via mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="4752c-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="4752c-144">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="4752c-144">Error message</span></span> | <span data-ttu-id="4752c-145">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="4752c-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="4752c-146">De Microsoft Defender Antivirus is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4752c-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="4752c-147">Schakel de service in en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="4752c-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="4752c-148">**Opmerking:**  In Windows 10 1909 of ouder, en Windows Server 2019 of ouder, werd de service de service Windows Defender Antivirus *genoemd.*</span><span class="sxs-lookup"><span data-stu-id="4752c-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="4752c-149">U gebruikt de opdracht vanaf een computer Windows 10 versie 1607 of ouder, of Windows Server 2016 `-ValidateMapsConnection` of ouder.</span><span class="sxs-lookup"><span data-stu-id="4752c-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="4752c-150">Voer de opdracht uit vanaf een computer Windows 10 versie 1703 of hoger, of Windows Server 2019 of hoger.</span><span class="sxs-lookup"><span data-stu-id="4752c-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="4752c-151">Het hulpprogramma moet worden uitgevoerd vanaf een van beide: of (waar kan verschillen `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` omdat `2012.4-0` platformupdates maandelijks zijn, behalve maart)</span><span class="sxs-lookup"><span data-stu-id="4752c-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="4752c-152">Niet genoeg bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="4752c-152">Not enough privileges.</span></span> <span data-ttu-id="4752c-153">Gebruik de opdrachtprompt (cmd.exe) als beheerder.</span><span class="sxs-lookup"><span data-stu-id="4752c-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="4752c-154">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="4752c-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="4752c-155">Mogelijke netwerkgerelateerde problemen, zoals problemen met naamoplossing</span><span class="sxs-lookup"><span data-stu-id="4752c-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="4752c-156">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="4752c-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="4752c-157">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="4752c-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="4752c-158">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="4752c-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4752c-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4752c-159">See also</span></span>

- [<span data-ttu-id="4752c-160">Microsoft Defender Antivirus-functies configureren</span><span class="sxs-lookup"><span data-stu-id="4752c-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="4752c-161">Uw Microsoft Defender Antivirus in uw bedrijf beheren</span><span class="sxs-lookup"><span data-stu-id="4752c-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4752c-162">Referentieonderwerpen voor beheer- en configuratiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="4752c-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4752c-163">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="4752c-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)