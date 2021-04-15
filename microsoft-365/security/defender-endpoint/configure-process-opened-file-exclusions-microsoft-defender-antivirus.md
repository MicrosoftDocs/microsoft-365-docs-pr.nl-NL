---
title: Uitsluitingen configureren voor bestanden die door specifieke processen zijn geopend
description: U kunt bestanden uitsluiten van scans als ze zijn geopend door een specifiek proces.
keywords: Microsoft Defender Antivirus, proces, uitsluiting, bestanden, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 94375bc843c6512616d49345bcc9e7f63899a708
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765081"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="3834b-104">Uitsluitingen configureren voor bestanden die door processen zijn geopend</span><span class="sxs-lookup"><span data-stu-id="3834b-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3834b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3834b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3834b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3834b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3834b-107">U kunt bestanden die door specifieke processen zijn geopend, uitsluiten van Microsoft Defender Antivirus-scans.</span><span class="sxs-lookup"><span data-stu-id="3834b-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="3834b-108">Zie Aanbevelingen voor het definiëren van uitsluitingen voordat u uw [uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) definieert.</span><span class="sxs-lookup"><span data-stu-id="3834b-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="3834b-109">In dit artikel wordt beschreven hoe u uitsluitingslijsten configureert.</span><span class="sxs-lookup"><span data-stu-id="3834b-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="3834b-110">Voorbeelden van uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3834b-110">Examples of exclusions</span></span>

|<span data-ttu-id="3834b-111">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="3834b-111">Exclusion</span></span> | <span data-ttu-id="3834b-112">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="3834b-112">Example</span></span> |
|---|---|
|<span data-ttu-id="3834b-113">Elk bestand op de computer dat wordt geopend door een proces met een specifieke bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="3834b-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="3834b-114">Als u `test.exe` opgeeft, worden bestanden die worden geopend, uitgesloten door:</span><span class="sxs-lookup"><span data-stu-id="3834b-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="3834b-115">Een bestand op de computer dat wordt geopend door een proces onder een specifieke map</span><span class="sxs-lookup"><span data-stu-id="3834b-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="3834b-116">Als u `c:\test\sample\*` opgeeft, worden bestanden die worden geopend, uitgesloten door:</span><span class="sxs-lookup"><span data-stu-id="3834b-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="3834b-117">Een bestand op de computer dat wordt geopend door een specifiek proces in een specifieke map</span><span class="sxs-lookup"><span data-stu-id="3834b-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="3834b-118">Als u `c:\test\process.exe` opgeeft, worden bestanden alleen geopend door `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="3834b-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="3834b-119">Wanneer u een proces toevoegt aan de lijst met procesuitsluitingen, scant Microsoft Defender Antivirus geen bestanden die door dat proces worden geopend, ongeacht waar de bestanden zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="3834b-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="3834b-120">Het proces zelf wordt echter gescand, tenzij het ook is toegevoegd aan de lijst met [bestandsuitsluitingen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3834b-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="3834b-121">De uitsluitingen zijn alleen van toepassing op realtime-beveiliging en -monitoring in [realtime.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3834b-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="3834b-122">Ze zijn niet van toepassing op geplande of on-demand scans.</span><span class="sxs-lookup"><span data-stu-id="3834b-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="3834b-123">Wijzigingen die zijn aangebracht met groepsbeleid in de uitsluitingslijsten, worden **in** de lijsten in de [Windows-beveiligingsapp vermeld.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3834b-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="3834b-124">Wijzigingen die zijn aangebracht in de Windows-beveiligings-app, **worden echter niet in** de lijsten met groepsbeleidslijsten vermeld.</span><span class="sxs-lookup"><span data-stu-id="3834b-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="3834b-125">U kunt lijsten toevoegen, verwijderen en controleren op uitsluitingen in groepsbeleid, Microsoft Endpoint Configuration Manager, Microsoft Intune en met de Windows Security-app. U kunt jokertekens gebruiken om de lijsten verder aan te passen.</span><span class="sxs-lookup"><span data-stu-id="3834b-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="3834b-126">U kunt ook PowerShell-cmdlets en WMI gebruiken om de uitsluitingslijsten te configureren, inclusief het controleren van uw lijsten.</span><span class="sxs-lookup"><span data-stu-id="3834b-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="3834b-127">Standaard worden lokale wijzigingen in de lijsten (door gebruikers met beheerdersbevoegdheden; wijzigingen aangebracht met PowerShell en WMI) samengevoegd met de lijsten zoals gedefinieerd (en geïmplementeerd) door Groepsbeleid, Configuratiebeheer of Intune.</span><span class="sxs-lookup"><span data-stu-id="3834b-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="3834b-128">De lijsten met groepsbeleid hebben voorrang bij conflicten.</span><span class="sxs-lookup"><span data-stu-id="3834b-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="3834b-129">U kunt [configureren hoe lijsten met](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) lokaal en globaal gedefinieerde uitsluitingen worden samengevoegd, zodat lokale wijzigingen de beheerde implementatie-instellingen kunnen overschrijven.</span><span class="sxs-lookup"><span data-stu-id="3834b-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="3834b-130">De lijst met uitsluitingen configureren voor bestanden die zijn geopend met opgegeven processen</span><span class="sxs-lookup"><span data-stu-id="3834b-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-131">Microsoft Intune gebruiken om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="3834b-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="3834b-132">Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus apparaatbeperkingen voor [Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3834b-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-133">Microsoft Endpoint Manager gebruiken om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="3834b-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="3834b-134">Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) maken en implementeren: Uitsluitingsinstellingen voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige branch).</span><span class="sxs-lookup"><span data-stu-id="3834b-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-135">Groepsbeleid gebruiken om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="3834b-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="3834b-136">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="3834b-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3834b-137">Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="3834b-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="3834b-138">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Exclusions**.</span><span class="sxs-lookup"><span data-stu-id="3834b-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="3834b-139">Dubbelklik op **Uitsluitingen verwerken** en voeg de uitsluitingen toe:</span><span class="sxs-lookup"><span data-stu-id="3834b-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="3834b-140">Stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="3834b-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="3834b-141">Klik onder **de** sectie Opties op **Toon...**.</span><span class="sxs-lookup"><span data-stu-id="3834b-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="3834b-142">Voer elk proces op een eigen regel in onder de kolom **Waardenaam.**</span><span class="sxs-lookup"><span data-stu-id="3834b-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="3834b-143">Zie de voorbeeldtabel voor de verschillende typen uitsluitingen van processen.</span><span class="sxs-lookup"><span data-stu-id="3834b-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="3834b-144">Voer **0** in de kolom **Waarde** in voor alle processen.</span><span class="sxs-lookup"><span data-stu-id="3834b-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="3834b-145">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="3834b-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-146">PowerShell-cmdlets gebruiken om bestanden die door bepaalde processen zijn geopend, uit te sluiten van scans</span><span class="sxs-lookup"><span data-stu-id="3834b-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="3834b-147">Als u PowerShell gebruikt om uitsluitingen toe te voegen of te verwijderen voor bestanden die door processen zijn geopend, moet u een combinatie van drie cmdlets met de `-ExclusionProcess` parameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3834b-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="3834b-148">De cmdlets zijn allemaal in de [Defender-module.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="3834b-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="3834b-149">De indeling voor de cmdlets is:</span><span class="sxs-lookup"><span data-stu-id="3834b-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="3834b-150">De volgende opties zijn toegestaan \<cmdlet> als:</span><span class="sxs-lookup"><span data-stu-id="3834b-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="3834b-151">Configuratieactie</span><span class="sxs-lookup"><span data-stu-id="3834b-151">Configuration action</span></span> | <span data-ttu-id="3834b-152">PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="3834b-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="3834b-153">De lijst maken of overschrijven</span><span class="sxs-lookup"><span data-stu-id="3834b-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="3834b-154">Toevoegen aan de lijst</span><span class="sxs-lookup"><span data-stu-id="3834b-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="3834b-155">Items uit de lijst verwijderen</span><span class="sxs-lookup"><span data-stu-id="3834b-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="3834b-156">Als u een lijst hebt gemaakt, met of , wordt de bestaande lijst opnieuw overschreven door de `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdlet te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3834b-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="3834b-157">Het volgende codefragment zorgt er bijvoorbeeld voor dat microsoft Defender AV-scans een bestand uitsluiten dat wordt geopend door het opgegeven proces:</span><span class="sxs-lookup"><span data-stu-id="3834b-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="3834b-158">Zie Antivirus beheren met PowerShell-cmdlets en [Microsoft Defender Antivirus-cmdlets](/powershell/module/defender)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3834b-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-159">Windows Management Instruction (WMI) gebruiken om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="3834b-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="3834b-160">Gebruik de [ **methoden Set,** **Add** en **Remove** van](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) de MSFT_MpPreference voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="3834b-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="3834b-161">Het gebruik van **Set,** **Add** en **Remove** is vergelijkbaar met hun tegenhangers in PowerShell: `Set-MpPreference` , en `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="3834b-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="3834b-162">Zie  [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)voor meer informatie en toegestane parameters.</span><span class="sxs-lookup"><span data-stu-id="3834b-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="3834b-163">Gebruik de Windows Security-app om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten</span><span class="sxs-lookup"><span data-stu-id="3834b-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="3834b-164">Zie [Uitsluitingen toevoegen in de Windows Security-app](microsoft-defender-security-center-antivirus.md) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3834b-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="3834b-165">Jokertekens gebruiken in de lijst met procesuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3834b-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="3834b-166">Het gebruik van jokertekens in de lijst met procesuitsluitingen verschilt van het gebruik ervan in andere uitsluitingslijsten.</span><span class="sxs-lookup"><span data-stu-id="3834b-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="3834b-167">U kunt met name het jokerteken vraagteken () niet gebruiken en het `?` sterretje () jokerteken kan alleen worden gebruikt aan het einde `*` van een volledig pad.</span><span class="sxs-lookup"><span data-stu-id="3834b-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="3834b-168">U kunt nog steeds omgevingsvariabelen (zoals ) als jokertekens gebruiken bij het definiëren van `%ALLUSERSPROFILE%` items in de lijst met procesuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="3834b-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="3834b-169">In de volgende tabel wordt beschreven hoe de jokertekens kunnen worden gebruikt in de lijst met uitsluitingen van processen:</span><span class="sxs-lookup"><span data-stu-id="3834b-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="3834b-170">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="3834b-170">Wildcard</span></span> | <span data-ttu-id="3834b-171">Voorbeeldgebruik</span><span class="sxs-lookup"><span data-stu-id="3834b-171">Example use</span></span> | <span data-ttu-id="3834b-172">Voorbeeld van overeenkomsten</span><span class="sxs-lookup"><span data-stu-id="3834b-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="3834b-173">`*` (sterretje)</span><span class="sxs-lookup"><span data-stu-id="3834b-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="3834b-174">Vervangt een aantal tekens</span><span class="sxs-lookup"><span data-stu-id="3834b-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="3834b-175">Een bestand dat wordt geopend door `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="3834b-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="3834b-176">Omgevingsvariabelen</span><span class="sxs-lookup"><span data-stu-id="3834b-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="3834b-177">De gedefinieerde variabele wordt ingevuld als een pad wanneer de uitsluiting wordt geëvalueerd</span><span class="sxs-lookup"><span data-stu-id="3834b-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="3834b-178">Een bestand dat wordt geopend door `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="3834b-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="3834b-179">De lijst met uitsluitingen bekijken</span><span class="sxs-lookup"><span data-stu-id="3834b-179">Review the list of exclusions</span></span>

<span data-ttu-id="3834b-180">U kunt de items in de uitsluitingslijst ophalen met MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)of de [Windows Security-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3834b-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="3834b-181">Als u PowerShell gebruikt, kunt u de lijst op twee manieren ophalen:</span><span class="sxs-lookup"><span data-stu-id="3834b-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="3834b-182">De status van alle Microsoft Defender Antivirusvoorkeuren ophalen.</span><span class="sxs-lookup"><span data-stu-id="3834b-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="3834b-183">Elk van de lijsten wordt weergegeven op afzonderlijke regels, maar de items in elke lijst worden gecombineerd tot dezelfde regel.</span><span class="sxs-lookup"><span data-stu-id="3834b-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="3834b-184">Schrijf de status van alle voorkeuren op een variabele en gebruik deze variabele om alleen de specifieke lijst te bellen waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="3834b-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="3834b-185">Elk gebruik van `Add-MpPreference` is geschreven naar een nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="3834b-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="3834b-186">De uitsluitingslijst valideren met MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="3834b-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="3834b-187">Als u uitsluitingen wilt controleren met de speciale [opdrachtregelfunctie mpcmdrun.exe, ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="3834b-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="3834b-188">Voor het controleren van uitsluitingen met MpCmdRun is Microsoft Defender Antivirus CAMP versie 4.18.1812.3 (uitgebracht in december 2018) of hoger vereist.</span><span class="sxs-lookup"><span data-stu-id="3834b-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="3834b-189">Bekijk de lijst met uitsluitingen naast alle andere Antivirusvoorkeuren van Microsoft Defender met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3834b-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="3834b-190">Gebruik de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3834b-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="3834b-191">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3834b-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="3834b-192">Een specifieke lijst met uitsluitingen ophalen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3834b-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="3834b-193">Gebruik het volgende codefragment (voer elke regel in als een afzonderlijke opdracht); vervang **WDAVprefs door** het label dat u de variabele wilt noemen:</span><span class="sxs-lookup"><span data-stu-id="3834b-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="3834b-194">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3834b-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3834b-195">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3834b-195">Related articles</span></span>

- [<span data-ttu-id="3834b-196">Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans</span><span class="sxs-lookup"><span data-stu-id="3834b-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3834b-197">Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie</span><span class="sxs-lookup"><span data-stu-id="3834b-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3834b-198">Microsoft Defender Antivirus-uitsluitingen configureren op Windows Server</span><span class="sxs-lookup"><span data-stu-id="3834b-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3834b-199">Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="3834b-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3834b-200">De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren</span><span class="sxs-lookup"><span data-stu-id="3834b-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3834b-201">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="3834b-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)