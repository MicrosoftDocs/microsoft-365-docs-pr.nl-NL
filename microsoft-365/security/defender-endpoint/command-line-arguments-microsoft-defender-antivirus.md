---
title: De opdrachtregel gebruiken om Microsoft Defender Antivirus te beheren
description: Voer Microsoft Defender Antivirus-scans uit en configureer beveiliging van de volgende generatie met een speciaal hulpprogramma voor opdrachtregel.
keywords: Windows Defender-scan uitvoeren, antivirusscan uitvoeren vanaf opdrachtregel, Windows Defender-scan uitvoeren vanaf opdrachtregel, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764625"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="a06d9-104">Microsoft Defender Antivirus configureren en beheren met mpcmdrun.exe opdrachtregelprogramma</span><span class="sxs-lookup"><span data-stu-id="a06d9-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a06d9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a06d9-105">**Applies to:**</span></span>

- [<span data-ttu-id="a06d9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a06d9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a06d9-107">U kunt verschillende Microsoft Defender Antivirus-functies uitvoeren met het speciale opdrachtregelprogramma **mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="a06d9-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="a06d9-108">Dit hulpprogramma is handig als u het gebruik van Microsoft Defender Antivirus wilt automatiseren.</span><span class="sxs-lookup"><span data-stu-id="a06d9-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="a06d9-109">U vindt het hulpprogramma in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="a06d9-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="a06d9-110">U moet deze uitvoeren vanuit een opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="a06d9-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="a06d9-111">Mogelijk moet u een versie op beheerdersniveau van de opdrachtprompt openen.</span><span class="sxs-lookup"><span data-stu-id="a06d9-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="a06d9-112">Wanneer u in het menu **Start naar opdrachtprompt** zoekt, kiest u **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="a06d9-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="a06d9-113">Als u een bijgewerkte Versie van het Microsoft Defender-platform gebruikt, kunt u vanaf `**MpCmdRun**` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="a06d9-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="a06d9-114">Het hulpprogramma heeft de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="a06d9-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="a06d9-115">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a06d9-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="a06d9-116">Opdracht</span><span class="sxs-lookup"><span data-stu-id="a06d9-116">Command</span></span>  | <span data-ttu-id="a06d9-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a06d9-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="a06d9-118">`-?`**of**`-h`</span><span class="sxs-lookup"><span data-stu-id="a06d9-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="a06d9-119">Hiermee worden alle beschikbare opties voor dit hulpprogramma weergegeven</span><span class="sxs-lookup"><span data-stu-id="a06d9-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="a06d9-120">Scant op schadelijke software.</span><span class="sxs-lookup"><span data-stu-id="a06d9-120">Scans for malicious software.</span></span> <span data-ttu-id="a06d9-121">Waarden voor **ScanType** zijn: **0** Standaard, volgens uw configuratie, **-1** Snelle scan, **-2** Volledige scan, **-3** Aangepaste scan van bestand en adreslijst.</span><span class="sxs-lookup"><span data-stu-id="a06d9-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="a06d9-122">CpuThrottling zal de geconfigureerde CPU-beperking van beleid eren</span><span class="sxs-lookup"><span data-stu-id="a06d9-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="a06d9-123">Diagnostische tracering starten</span><span class="sxs-lookup"><span data-stu-id="a06d9-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="a06d9-124">Verzamelt ondersteuningsgegevens.</span><span class="sxs-lookup"><span data-stu-id="a06d9-124">Collects support information.</span></span> <span data-ttu-id="a06d9-125">Zie['diagnostische gegevens verzamelen'](collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="a06d9-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="a06d9-126">Hetzelfde als `-GetFiles` , maar wordt uitgevoerd naar een tijdelijke DiagTrack-map</span><span class="sxs-lookup"><span data-stu-id="a06d9-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="a06d9-127">Herstelt de geïnstalleerde beveiligingsinformatie naar een vorige back-upkopie of naar de oorspronkelijke standaardset</span><span class="sxs-lookup"><span data-stu-id="a06d9-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="a06d9-128">Verwijdert alleen de dynamisch gedownloade beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="a06d9-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="a06d9-129">Herstelt de vorige geïnstalleerde engine</span><span class="sxs-lookup"><span data-stu-id="a06d9-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="a06d9-130">Controleert op nieuwe beveiligingsinformatie-updates</span><span class="sxs-lookup"><span data-stu-id="a06d9-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="a06d9-131">Herstelt of lijsten met in quarantaine geplaatste items(en)</span><span class="sxs-lookup"><span data-stu-id="a06d9-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="a06d9-132">Dynamische beveiligingsintelligentie laden</span><span class="sxs-lookup"><span data-stu-id="a06d9-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="a06d9-133">Bevat de geladen dynamische beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="a06d9-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="a06d9-134">Hiermee verwijdert u dynamische beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="a06d9-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="a06d9-135">Hiermee wordt gecontroleerd of een pad is uitgesloten</span><span class="sxs-lookup"><span data-stu-id="a06d9-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="a06d9-136">Controleert of uw netwerk kan communiceren met de Microsoft Defender Antivirus-cloudservice.</span><span class="sxs-lookup"><span data-stu-id="a06d9-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="a06d9-137">Deze opdracht werkt alleen in Windows 10, versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="a06d9-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="a06d9-138">Veelvoorkomende fouten bij het uitvoeren van opdrachten via mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="a06d9-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="a06d9-139">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="a06d9-139">Error message</span></span> | <span data-ttu-id="a06d9-140">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="a06d9-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="a06d9-141">De Microsoft Defender Antivirus-service is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a06d9-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="a06d9-142">Schakel de service in en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="a06d9-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="a06d9-143">**Opmerking:**  In Windows 10 1909 of ouder, en Windows Server 2019 of ouder, heette de service 'Windows Defender Antivirus'-service.</span><span class="sxs-lookup"><span data-stu-id="a06d9-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="a06d9-144">U gebruikt de opdracht vanaf een computer die `-ValidateMapsConnection` Windows 10 versie 1607 of ouder is, of Windows Server 2016 of ouder.</span><span class="sxs-lookup"><span data-stu-id="a06d9-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="a06d9-145">Voer de opdracht uit vanaf een computer die Windows 10 versie 1703 of hoger is, of Windows Server 2019 of hoger.</span><span class="sxs-lookup"><span data-stu-id="a06d9-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="a06d9-146">Het hulpprogramma moet worden uitgevoerd vanaf een van beide: of (waar kan verschillen `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` omdat `2012.4-0` platformupdates maandelijks zijn, behalve maart)</span><span class="sxs-lookup"><span data-stu-id="a06d9-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="a06d9-147">Niet genoeg bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="a06d9-147">Not enough privileges.</span></span> <span data-ttu-id="a06d9-148">Gebruik de opdrachtprompt (cmd.exe) als beheerder.</span><span class="sxs-lookup"><span data-stu-id="a06d9-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="a06d9-149">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="a06d9-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="a06d9-150">Mogelijke netwerkgerelateerde problemen, zoals problemen met naamoplossing</span><span class="sxs-lookup"><span data-stu-id="a06d9-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="a06d9-151">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="a06d9-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="a06d9-152">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="a06d9-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="a06d9-153">De firewall blokkeert de verbinding of voert SSL-inspectie uit.</span><span class="sxs-lookup"><span data-stu-id="a06d9-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a06d9-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a06d9-154">See also</span></span>

- [<span data-ttu-id="a06d9-155">Microsoft Defender Antivirus-functies configureren</span><span class="sxs-lookup"><span data-stu-id="a06d9-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="a06d9-156">Microsoft Defender Antivirus beheren in uw bedrijf</span><span class="sxs-lookup"><span data-stu-id="a06d9-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a06d9-157">Referentieonderwerpen voor beheer- en configuratiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="a06d9-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a06d9-158">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a06d9-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)