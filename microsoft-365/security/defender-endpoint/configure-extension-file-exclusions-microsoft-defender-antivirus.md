---
title: Uitsluitingen configureren en valideren op basis van extensie, naam of locatie
description: Bestanden uitsluiten van Microsoft Defender Antivirus scans op basis van de bestandsextensie, bestandsnaam of locatie.
keywords: uitsluitingen, bestanden, extensie, bestandstype, mapnaam, bestandsnaam, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 338dc249bcd4e092f5a2be39e3d045d094ed957a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765213"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="d62bc-104">Uitsluitingen configureren en valideren op basis van bestandsextensie en maplocatie</span><span class="sxs-lookup"><span data-stu-id="d62bc-104">Configure and validate exclusions based on file extension and folder location</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d62bc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d62bc-105">**Applies to:**</span></span>

- [<span data-ttu-id="d62bc-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d62bc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="d62bc-107">Microsoft Defender Antivirus-uitsluitingen zijn niet van toepassing op andere Mogelijkheden van Microsoft Defender voor eindpunten, zoals eindpuntdetectie en -antwoord [(EDR), ASR-regels](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) [(Attack Surface Reduction)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)en gecontroleerde maptoegang [.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="d62bc-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="d62bc-108">Bestanden die u uitsluit met de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR-waarschuwingen en andere detecties activeren.</span><span class="sxs-lookup"><span data-stu-id="d62bc-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="d62bc-109">Als u bestanden breed wilt uitsluiten, voegt u deze toe aan de aangepaste indicatoren van Microsoft Defender [voor Eindpunt.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="d62bc-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="d62bc-110">Uitsluitingslijsten</span><span class="sxs-lookup"><span data-stu-id="d62bc-110">Exclusion lists</span></span>

<span data-ttu-id="d62bc-111">U kunt bepaalde bestanden uitsluiten van Microsoft Defender Antivirus-scans door uitsluitingslijsten te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="d62bc-112">**Over het algemeen hoeft u geen uitsluitingen toe te passen.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="d62bc-113">Microsoft Defender Antivirus bevat veel automatische uitsluitingen op basis van bekende gedragingen van het besturingssysteem en normale beheerbestanden, zoals bestanden die worden gebruikt in ondernemingsbeheer, databasebeheer en andere ondernemingsscenario's en -situaties.</span><span class="sxs-lookup"><span data-stu-id="d62bc-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="d62bc-114">Uitsluitingen zijn ook van toepassing op pua-detecties (Potentially Unwanted Apps).</span><span class="sxs-lookup"><span data-stu-id="d62bc-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="d62bc-115">Automatische uitsluitingen zijn alleen van toepassing op Windows Server 2016 en hoger.</span><span class="sxs-lookup"><span data-stu-id="d62bc-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="d62bc-116">Deze uitsluitingen zijn niet zichtbaar in de Windows Security-app en in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d62bc-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="d62bc-117">In dit artikel wordt beschreven hoe u uitsluitingslijsten configureert voor de bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="d62bc-118">Zie Aanbevelingen voor het definiëren van uitsluitingen voordat u uw [uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) definieert.</span><span class="sxs-lookup"><span data-stu-id="d62bc-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="d62bc-119">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="d62bc-119">Exclusion</span></span> | <span data-ttu-id="d62bc-120">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="d62bc-120">Examples</span></span> | <span data-ttu-id="d62bc-121">Lijst met uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="d62bc-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="d62bc-122">Een bestand met een specifieke extensie</span><span class="sxs-lookup"><span data-stu-id="d62bc-122">Any file with a specific extension</span></span> | <span data-ttu-id="d62bc-123">Alle bestanden met de opgegeven extensie, overal op de computer.</span><span class="sxs-lookup"><span data-stu-id="d62bc-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="d62bc-124">Geldige syntaxis: `.test` en `test`</span><span class="sxs-lookup"><span data-stu-id="d62bc-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="d62bc-125">Uitbreidingsuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="d62bc-125">Extension exclusions</span></span> |
|<span data-ttu-id="d62bc-126">Een bestand onder een specifieke map</span><span class="sxs-lookup"><span data-stu-id="d62bc-126">Any file under a specific folder</span></span> | <span data-ttu-id="d62bc-127">Alle bestanden onder de `c:\test\sample` map</span><span class="sxs-lookup"><span data-stu-id="d62bc-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="d62bc-128">Bestands- en mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="d62bc-128">File and folder exclusions</span></span> |
| <span data-ttu-id="d62bc-129">Een specifiek bestand in een specifieke map</span><span class="sxs-lookup"><span data-stu-id="d62bc-129">A specific file in a specific folder</span></span> | <span data-ttu-id="d62bc-130">Alleen het `c:\sample\sample.test` bestand</span><span class="sxs-lookup"><span data-stu-id="d62bc-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="d62bc-131">Bestands- en mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="d62bc-131">File and folder exclusions</span></span> |
| <span data-ttu-id="d62bc-132">Een specifiek proces</span><span class="sxs-lookup"><span data-stu-id="d62bc-132">A specific process</span></span> | <span data-ttu-id="d62bc-133">Het uitvoerbare bestand `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="d62bc-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="d62bc-134">Bestands- en mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="d62bc-134">File and folder exclusions</span></span> |

<span data-ttu-id="d62bc-135">Uitsluitingslijsten hebben de volgende kenmerken:</span><span class="sxs-lookup"><span data-stu-id="d62bc-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="d62bc-136">Mapuitsluitingen zijn van toepassing op alle bestanden en mappen onder die map, tenzij de submap een herstelpunt is.</span><span class="sxs-lookup"><span data-stu-id="d62bc-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="d62bc-137">Submappen voor reparse-punten moeten afzonderlijk worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="d62bc-138">Bestandsextensies zijn van toepassing op een bestandsnaam met de gedefinieerde extensie als een pad of map niet is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="d62bc-139">Als u jokertekens zoals het sterretje () gebruikt, wordt de interpretatie van \* de uitsluitingsregels gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="d62bc-140">Zie de [sectie Jokertekens gebruiken in](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) de sectie bestandsnaam- en mappad- of extensieuitsluitingslijsten voor belangrijke informatie over hoe jokertekens werken.</span><span class="sxs-lookup"><span data-stu-id="d62bc-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="d62bc-141">U kunt netwerkstations niet uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="d62bc-142">U moet het werkelijke netwerkpad opgeven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="d62bc-143">Mappen die reparse-punten zijn die worden gemaakt nadat de Microsoft Defender Antivirus-service is gestart en die zijn toegevoegd aan de uitsluitingslijst, worden niet opgenomen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="d62bc-144">U moet de service opnieuw starten (door Windows opnieuw te starten) om nieuwe herstelpunten te kunnen herkennen als een geldig uitsluitingsdoel.</span><span class="sxs-lookup"><span data-stu-id="d62bc-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="d62bc-145">Zie Uitsluitingen configureren en valideren voor bestanden die door processen worden geopend als u bestanden wilt uitsluiten die door een specifiek proces [worden geopend.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d62bc-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d62bc-146">De uitsluitingen zijn van [toepassing op geplande scans,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [scans](run-scan-microsoft-defender-antivirus.md)op aanvraag en [real-time beveiliging.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d62bc-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d62bc-147">Wijzigingen in de uitsluitingslijst die met **groepsbeleid** zijn aangebracht, worden weergegeven in de lijsten in de [Windows-beveiligings-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d62bc-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="d62bc-148">Wijzigingen die zijn aangebracht in de Windows Security-app, **worden niet in** de lijsten met groepsbeleidslijsten vermeld.</span><span class="sxs-lookup"><span data-stu-id="d62bc-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="d62bc-149">Lokale wijzigingen die zijn aangebracht in de lijsten (door gebruikers met beheerdersbevoegdheden, inclusief wijzigingen die zijn aangebracht met PowerShell en WMI), worden standaard samengevoegd met de lijsten zoals gedefinieerd (en geïmplementeerd) door Groepsbeleid, Configuratiebeheer of Intune.</span><span class="sxs-lookup"><span data-stu-id="d62bc-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="d62bc-150">De lijsten met groepsbeleid hebben voorrang wanneer er conflicten zijn.</span><span class="sxs-lookup"><span data-stu-id="d62bc-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="d62bc-151">U kunt [configureren hoe lijsten met](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) lokaal en globaal gedefinieerde uitsluitingen worden samengevoegd, zodat lokale wijzigingen de beheerde implementatie-instellingen kunnen overschrijven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="d62bc-152">De lijst met uitsluitingen configureren op basis van mapnaam of bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="d62bc-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-153">Intune gebruiken om uitsluitingen voor bestandsnaam, map of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="d62bc-154">Zie de volgende artikelen:</span><span class="sxs-lookup"><span data-stu-id="d62bc-154">See the following articles:</span></span>
- [<span data-ttu-id="d62bc-155">Instellingen voor apparaatbeperkingen configureren in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d62bc-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="d62bc-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span><span class="sxs-lookup"><span data-stu-id="d62bc-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-157">Configuration Manager gebruiken om uitsluitingen van bestandsnaam, map of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="d62bc-158">Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) maken en implementeren: Uitsluitingsinstellingen voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige branch).</span><span class="sxs-lookup"><span data-stu-id="d62bc-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-159">Groepsbeleid gebruiken om uitsluitingen van mappen of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="d62bc-160">Als u een volledig gekwalificeerd pad naar een bestand opgeeft, wordt alleen dat bestand uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="d62bc-161">Als een map is gedefinieerd in de uitsluiting, worden alle bestanden en subdirectorieën onder die map uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="d62bc-162">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d62bc-163">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d62bc-164">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="d62bc-165">Open de **instelling Paduitsluitingen** voor bewerken en voeg uw uitsluitingen toe.</span><span class="sxs-lookup"><span data-stu-id="d62bc-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="d62bc-166">Stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="d62bc-167">Klik onder **de** sectie Opties op **Tonen.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="d62bc-168">Geef elke map op een eigen regel op onder de **kolom Waardenaam.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="d62bc-169">Als u een bestand opgeeft, moet u een volledig gekwalificeerd pad naar het bestand invoeren, inclusief de stationletter, het mappad, de bestandsnaam en de extensie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="d62bc-170">Voer **0** in de kolom **Waarde** in.</span><span class="sxs-lookup"><span data-stu-id="d62bc-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="d62bc-171">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-171">Choose **OK**.</span></span>

6. <span data-ttu-id="d62bc-172">Open de **instelling Extensieuitsluitingen** voor bewerken en voeg uw uitsluitingen toe.</span><span class="sxs-lookup"><span data-stu-id="d62bc-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="d62bc-173">Stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="d62bc-174">Selecteer onder **de** sectie Opties de optie **Toon**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="d62bc-175">Voer elke bestandsextensie op een eigen regel in onder de **kolom Waardenaam.**</span><span class="sxs-lookup"><span data-stu-id="d62bc-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="d62bc-176">Voer **0** in de kolom **Waarde** in.</span><span class="sxs-lookup"><span data-stu-id="d62bc-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="d62bc-177">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-178">PowerShell-cmdlets gebruiken om uitsluitingen voor bestandsnaam, map of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="d62bc-179">Als u PowerShell gebruikt om uitsluitingen toe te voegen of te verwijderen voor bestanden op basis van de extensie, locatie of bestandsnaam, moet u een combinatie van drie cmdlets en de juiste uitsluitingslijstparameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d62bc-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="d62bc-180">De cmdlets zijn allemaal in de [Defender-module.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="d62bc-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="d62bc-181">De indeling voor de cmdlets is als volgt:</span><span class="sxs-lookup"><span data-stu-id="d62bc-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="d62bc-182">De volgende opties zijn toegestaan `<cmdlet>` als:</span><span class="sxs-lookup"><span data-stu-id="d62bc-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="d62bc-183">Configuratieactie</span><span class="sxs-lookup"><span data-stu-id="d62bc-183">Configuration action</span></span> | <span data-ttu-id="d62bc-184">PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="d62bc-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="d62bc-185">De lijst maken of overschrijven</span><span class="sxs-lookup"><span data-stu-id="d62bc-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="d62bc-186">Toevoegen aan de lijst</span><span class="sxs-lookup"><span data-stu-id="d62bc-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="d62bc-187">Item verwijderen uit de lijst</span><span class="sxs-lookup"><span data-stu-id="d62bc-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="d62bc-188">De volgende opties zijn toegestaan `<exclusion list>` als:</span><span class="sxs-lookup"><span data-stu-id="d62bc-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="d62bc-189">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="d62bc-189">Exclusion type</span></span> | <span data-ttu-id="d62bc-190">PowerShell-parameter</span><span class="sxs-lookup"><span data-stu-id="d62bc-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="d62bc-191">Alle bestanden met een opgegeven bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="d62bc-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="d62bc-192">Alle bestanden onder een map (inclusief bestanden in subdirectorieën) of een specifiek bestand</span><span class="sxs-lookup"><span data-stu-id="d62bc-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="d62bc-193">Als u een lijst hebt gemaakt, met of , wordt de bestaande lijst opnieuw overschreven door de `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdlet te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d62bc-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="d62bc-194">Met het volgende codefragment wordt bijvoorbeeld een bestand met de bestandsextensie uitgesloten door Microsoft Defender `.test` Antivirus-scans:</span><span class="sxs-lookup"><span data-stu-id="d62bc-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="d62bc-195">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/)te configureren en uit te voeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-196">Windows Management Instruction (WMI) gebruiken om uitsluitingen voor bestandsnaam, map of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="d62bc-197">Gebruik de [ **methoden Set,** **Add** en **Remove** van](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) de MSFT_MpPreference voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d62bc-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="d62bc-198">Het gebruik van **Set,** **Add** en **Remove** is vergelijkbaar met hun tegenhangers in PowerShell: `Set-MpPreference` , en `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="d62bc-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="d62bc-199">Zie Windows [Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="d62bc-200">De Windows Security-app gebruiken om uitsluitingen van bestandsnaam, map of bestandsextensie te configureren</span><span class="sxs-lookup"><span data-stu-id="d62bc-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="d62bc-201">Zie [Uitsluitingen toevoegen in de Windows Security-app](microsoft-defender-security-center-antivirus.md) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="d62bc-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="d62bc-202">Jokertekens gebruiken in de uitsluitingslijsten voor bestandsnaam en map of extensie</span><span class="sxs-lookup"><span data-stu-id="d62bc-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="d62bc-203">U kunt het sterretje, vraagteken of omgevingsvariabelen (zoals ) gebruiken als jokertekens bij het definiëren van items in de uitsluitingslijst voor bestandsnaam of `*` `?` `%ALLUSERSPROFILE%` mappad.</span><span class="sxs-lookup"><span data-stu-id="d62bc-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="d62bc-204">De manier waarop deze jokertekens worden geïnterpreteerd, verschilt van het gebruikelijke gebruik in andere apps en talen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="d62bc-205">Lees deze sectie om de specifieke beperkingen te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d62bc-206">Er zijn belangrijke beperkingen en gebruiksscenario's voor deze jokertekens:</span><span class="sxs-lookup"><span data-stu-id="d62bc-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="d62bc-207">Het gebruik van omgevingsvariabelen is beperkt tot machinevariabelen en deze die van toepassing zijn op processen die worden uitgevoerd als NT AUTHORITY\SYSTEM-account.</span><span class="sxs-lookup"><span data-stu-id="d62bc-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="d62bc-208">U kunt geen jokerteken gebruiken in plaats van een stationletter.</span><span class="sxs-lookup"><span data-stu-id="d62bc-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="d62bc-209">Een sterretje `*` in een mapuitsluiting staat op zijn plaats voor één map.</span><span class="sxs-lookup"><span data-stu-id="d62bc-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="d62bc-210">Gebruik meerdere exemplaren van `\*\` om meerdere geneste mappen met niet-gespecificeerde namen aan te geven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="d62bc-211">In de volgende tabel wordt beschreven hoe de jokertekens kunnen worden gebruikt en worden enkele voorbeelden gegeven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="d62bc-212">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="d62bc-212">Wildcard</span></span>  |<span data-ttu-id="d62bc-213">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="d62bc-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="d62bc-214">`*` (sterretje)</span><span class="sxs-lookup"><span data-stu-id="d62bc-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="d62bc-215">In **bestandsnaam- en bestandsextensie-insluitsels** vervangt het sterretje een aantal tekens en is het alleen van toepassing op bestanden in de laatste map die in het argument is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="d62bc-216">In **mapuitsluitingen** vervangt het sterretje één map.</span><span class="sxs-lookup"><span data-stu-id="d62bc-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="d62bc-217">Gebruik meerdere `*` mappen met schuine mappen `\` om meerdere geneste mappen aan te geven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="d62bc-218">Nadat u het aantal mappen met jokerkaarten en benoemde mappen hebt overeenkomen, worden ook alle submappen opgenomen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="d62bc-219">`C:\MyData\*.txt` bevat `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="d62bc-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="d62bc-220">`C:\somepath\*\Data` bevat een bestand in `C:\somepath\Archives\Data` en de submappen en `C:\somepath\Authorized\Data` de submappen</span><span class="sxs-lookup"><span data-stu-id="d62bc-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="d62bc-221">`C:\Serv\*\*\Backup` bevat een bestand in `C:\Serv\Primary\Denied\Backup` en de submappen en `C:\Serv\Secondary\Allowed\Backup` de submappen</span><span class="sxs-lookup"><span data-stu-id="d62bc-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="d62bc-222">`?` (vraagteken)</span><span class="sxs-lookup"><span data-stu-id="d62bc-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="d62bc-223">In **bestandsnaam- en bestandsextensie-insluitsels** vervangt het vraagteken één teken en is het alleen van toepassing op bestanden in de laatste map die in het argument is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="d62bc-224">In **mapuitsluitingen** vervangt het vraagteken één teken in een mapnaam.</span><span class="sxs-lookup"><span data-stu-id="d62bc-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="d62bc-225">Nadat u het aantal mappen met jokerkaarten en benoemde mappen hebt overeenkomen, worden ook alle submappen opgenomen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="d62bc-226">`C:\MyData\my?.zip` bevat `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="d62bc-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="d62bc-227">`C:\somepath\?\Data` bevat een bestand in `C:\somepath\P\Data` en de submappen</span><span class="sxs-lookup"><span data-stu-id="d62bc-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="d62bc-228">`C:\somepath\test0?\Data` alle bestanden in en de `C:\somepath\test01\Data` submappen</span><span class="sxs-lookup"><span data-stu-id="d62bc-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="d62bc-229">Omgevingsvariabelen</span><span class="sxs-lookup"><span data-stu-id="d62bc-229">Environment variables</span></span> <p> <span data-ttu-id="d62bc-230">De gedefinieerde variabele wordt ingevuld als een pad wanneer de uitsluiting wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="d62bc-231">`%ALLUSERSPROFILE%\CustomLogFiles` zou bestaan uit `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="d62bc-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="d62bc-232">Als u een argument voor bestandsuitsluiting combineert met een argument voor mapuitsluiting, worden de regels gestopt bij het argument bestand in de overeenkomende map en worden er in geen submappen naar bestandsmatchen ge zoeken.</span><span class="sxs-lookup"><span data-stu-id="d62bc-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="d62bc-233">U kunt bijvoorbeeld alle bestanden uitsluiten die beginnen met 'datum' in de mappen en met `c:\data\final\marked` behulp van het argument `c:\data\review\marked` `c:\data\*\marked\date*` regel.</span><span class="sxs-lookup"><span data-stu-id="d62bc-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="d62bc-234">Dit argument komt echter niet overeen met bestanden in submappen onder `c:\data\final\marked` of `c:\data\review\marked` .</span><span class="sxs-lookup"><span data-stu-id="d62bc-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="d62bc-235">Systeemomgevingvariabelen</span><span class="sxs-lookup"><span data-stu-id="d62bc-235">System environment variables</span></span>

<span data-ttu-id="d62bc-236">In de volgende tabel worden de variabelen voor de systeemaccountomgeving vermeld en beschreven.</span><span class="sxs-lookup"><span data-stu-id="d62bc-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="d62bc-237">Deze systeemomgevingvariabele...</span><span class="sxs-lookup"><span data-stu-id="d62bc-237">This system environment variable...</span></span> | <span data-ttu-id="d62bc-238">Hierom wordt omgeleid</span><span class="sxs-lookup"><span data-stu-id="d62bc-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="d62bc-239">C:\ProgramData\Menu Start\Programma's</span><span class="sxs-lookup"><span data-stu-id="d62bc-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="d62bc-240">De lijst met uitsluitingen bekijken</span><span class="sxs-lookup"><span data-stu-id="d62bc-240">Review the list of exclusions</span></span>

<span data-ttu-id="d62bc-241">U kunt de items in de uitsluitingslijst op een van de volgende manieren ophalen:</span><span class="sxs-lookup"><span data-stu-id="d62bc-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="d62bc-242">Intune</span><span class="sxs-lookup"><span data-stu-id="d62bc-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="d62bc-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d62bc-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="d62bc-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="d62bc-244">MpCmdRun</span></span>
- <span data-ttu-id="d62bc-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d62bc-245">PowerShell</span></span>
- [<span data-ttu-id="d62bc-246">Windows-beveiligingsapp</span><span class="sxs-lookup"><span data-stu-id="d62bc-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="d62bc-247">Wijzigingen in de uitsluitingslijst die met **groepsbeleid** zijn aangebracht, worden weergegeven in de lijsten in de [Windows-beveiligings-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d62bc-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="d62bc-248">Wijzigingen die zijn aangebracht in de Windows Security-app, **worden niet in** de lijsten met groepsbeleidslijsten vermeld.</span><span class="sxs-lookup"><span data-stu-id="d62bc-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="d62bc-249">Als u PowerShell gebruikt, kunt u de lijst op twee manieren ophalen:</span><span class="sxs-lookup"><span data-stu-id="d62bc-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="d62bc-250">De status van alle Microsoft Defender Antivirusvoorkeuren ophalen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="d62bc-251">Elke lijst wordt weergegeven op afzonderlijke regels, maar de items in elke lijst worden gecombineerd tot dezelfde regel.</span><span class="sxs-lookup"><span data-stu-id="d62bc-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="d62bc-252">Schrijf de status van alle voorkeuren op een variabele en gebruik deze variabele om alleen de specifieke lijst te bellen waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="d62bc-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="d62bc-253">Elk gebruik van `Add-MpPreference` is geschreven naar een nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="d62bc-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="d62bc-254">De uitsluitingslijst valideren met MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="d62bc-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="d62bc-255">Als u uitsluitingen wilt controleren met de speciale [opdrachtregelfunctie mpcmdrun.exe, ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="d62bc-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="d62bc-256">Voor het controleren van uitsluitingen met MpCmdRun is Microsoft Defender Antivirus CAMP versie 4.18.1812.3 (uitgebracht in december 2018) of hoger vereist.</span><span class="sxs-lookup"><span data-stu-id="d62bc-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="d62bc-257">Bekijk de lijst met uitsluitingen naast alle andere Antivirusvoorkeuren van Microsoft Defender met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d62bc-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="d62bc-258">Gebruik de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d62bc-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="d62bc-259">In het volgende voorbeeld zijn de items in de `ExclusionExtension` lijst gemarkeerd:</span><span class="sxs-lookup"><span data-stu-id="d62bc-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![PowerShell-uitvoer voor Get-MpPreference met de uitsluitingslijst naast andere voorkeuren](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="d62bc-261">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/)te configureren en uit te voeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="d62bc-262">Een specifieke lijst met uitsluitingen ophalen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d62bc-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="d62bc-263">Gebruik het volgende codefragment (voer elke regel in als een afzonderlijke opdracht); vervang **WDAVprefs door** het label dat u de variabele wilt noemen:</span><span class="sxs-lookup"><span data-stu-id="d62bc-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="d62bc-264">In het volgende voorbeeld wordt de lijst gesplitst in nieuwe regels voor elk gebruik van de `Add-MpPreference` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d62bc-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![PowerShell-uitvoer met alleen de vermeldingen in de uitsluitingslijst](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="d62bc-266">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/)te configureren en uit te voeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="d62bc-267">Lijsten met uitsluitingen valideren met het EICAR-testbestand</span><span class="sxs-lookup"><span data-stu-id="d62bc-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="d62bc-268">U kunt valideren dat uw uitsluitingslijsten werken met PowerShell met de `Invoke-WebRequest` cmdlet of de klasse .NET WebClient om een testbestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="d62bc-269">Vervang in het volgende PowerShell-fragment *test.txt* bestand dat voldoet aan de uitsluitingsregels.</span><span class="sxs-lookup"><span data-stu-id="d62bc-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="d62bc-270">Als u bijvoorbeeld de extensie hebt uitgesloten, vervangt `.testing` u `test.txt` door `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="d62bc-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="d62bc-271">Als u een pad test, controleert u of u de cmdlet binnen dat pad hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d62bc-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="d62bc-272">Als Microsoft Defender Antivirus malware meldt, werkt de regel niet.</span><span class="sxs-lookup"><span data-stu-id="d62bc-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="d62bc-273">Als er geen malwarerapport is en het gedownloade bestand bestaat, werkt de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="d62bc-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="d62bc-274">U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de website van het [EICAR-testbestand.](http://www.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="d62bc-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="d62bc-275">U kunt ook de volgende PowerShell-code gebruiken, waarmee de klasse .NET WebClient wordt gebeld om het testbestand te downloaden, zoals met de `Invoke-WebRequest` cmdlet; *c:\test.txt* vervangen door een bestand dat voldoet aan de regel die u valideert:</span><span class="sxs-lookup"><span data-stu-id="d62bc-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="d62bc-276">Als u geen internetverbinding hebt, kunt u uw eigen EICAR-testbestand maken door de EICAR-tekenreeks te schrijven naar een nieuw tekstbestand met de volgende PowerShell-opdracht:</span><span class="sxs-lookup"><span data-stu-id="d62bc-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="d62bc-277">U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d62bc-278">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d62bc-278">Related topics</span></span>

- [<span data-ttu-id="d62bc-279">Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans</span><span class="sxs-lookup"><span data-stu-id="d62bc-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d62bc-280">Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen</span><span class="sxs-lookup"><span data-stu-id="d62bc-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d62bc-281">Microsoft Defender Antivirus-uitsluitingen configureren op Windows Server</span><span class="sxs-lookup"><span data-stu-id="d62bc-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d62bc-282">Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="d62bc-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
