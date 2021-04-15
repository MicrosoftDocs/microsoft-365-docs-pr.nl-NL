---
title: Problemen met Microsoft Defender Antivirus oplossen die optreden tijdens migratie vanuit een externe oplossing
description: Veelvoorkomende fouten oplossen bij het migreren naar Microsoft Defender Antivirus
keywords: gebeurtenis, foutcode, logboekregistratie, probleemoplossing, microsoft defender antivirus, Windows Defender antivirus, migratie
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764589"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="47c3d-104">Problemen met Microsoft Defender Antivirus oplossen die optreden tijdens migratie vanuit een externe oplossing</span><span class="sxs-lookup"><span data-stu-id="47c3d-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47c3d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="47c3d-105">**Applies to:**</span></span>

- [<span data-ttu-id="47c3d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="47c3d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="47c3d-107">U kunt hier hulp vinden als u problemen ondervindt tijdens het migreren van een beveiligingsoplossing van derden naar Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="47c3d-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="47c3d-108">Gebeurtenislogboeken controleren</span><span class="sxs-lookup"><span data-stu-id="47c3d-108">Review event logs</span></span>

<span data-ttu-id="47c3d-109">Open de app Gebeurtenisviewer door het pictogram **Zoeken** op de taakbalk te selecteren en te zoeken naar *gebeurtenisviewer.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="47c3d-110">Informatie over Microsoft Defender Antivirus vindt u onder **Applications and Services Logs**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="47c3d-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="47c3d-111">Selecteer vervolgens **Openen** onder **Operationeel.**</span><span class="sxs-lookup"><span data-stu-id="47c3d-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="47c3d-112">Als u een gebeurtenis selecteert in het detailvenster, ziet u meer  informatie over een gebeurtenis in het onderste deelvenster, onder de tabbladen Algemeen **en** Details.</span><span class="sxs-lookup"><span data-stu-id="47c3d-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="47c3d-113">Microsoft Defender Antivirus start niet</span><span class="sxs-lookup"><span data-stu-id="47c3d-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="47c3d-114">Dit probleem kan zich manifesteert in de vorm van verschillende gebeurtenis-ID's, die allemaal dezelfde onderliggende oorzaak hebben.</span><span class="sxs-lookup"><span data-stu-id="47c3d-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="47c3d-115">Gekoppelde gebeurtenis-IDs</span><span class="sxs-lookup"><span data-stu-id="47c3d-115">Associated event IDs</span></span>

 <span data-ttu-id="47c3d-116">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="47c3d-116">Event ID</span></span> | <span data-ttu-id="47c3d-117">Naam van logboek</span><span class="sxs-lookup"><span data-stu-id="47c3d-117">Log name</span></span> | <span data-ttu-id="47c3d-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="47c3d-118">Description</span></span> | <span data-ttu-id="47c3d-119">Source</span><span class="sxs-lookup"><span data-stu-id="47c3d-119">Source</span></span>
-|-|-|-
<span data-ttu-id="47c3d-120">15</span><span class="sxs-lookup"><span data-stu-id="47c3d-120">15</span></span> | <span data-ttu-id="47c3d-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="47c3d-121">Application</span></span> | <span data-ttu-id="47c3d-122">De Windows Defender-status is bijgewerkt om SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="47c3d-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="47c3d-123">Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="47c3d-123">Security Center</span></span>
<span data-ttu-id="47c3d-124">5007</span><span class="sxs-lookup"><span data-stu-id="47c3d-124">5007</span></span> | <span data-ttu-id="47c3d-125">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="47c3d-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="47c3d-126">Windows Defender Antivirus Configuration is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="47c3d-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="47c3d-127">Als dit een onverwachte gebeurtenis is, moet u de instellingen controleren, omdat dit mogelijk het gevolg is van malware.</span><span class="sxs-lookup"><span data-stu-id="47c3d-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="47c3d-128">**Oude waarde:** Standaard\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="47c3d-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="47c3d-129">**Nieuwe waarde:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="47c3d-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="47c3d-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="47c3d-130">Windows Defender</span></span>
<span data-ttu-id="47c3d-131">5010</span><span class="sxs-lookup"><span data-stu-id="47c3d-131">5010</span></span> | <span data-ttu-id="47c3d-132">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="47c3d-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="47c3d-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span><span class="sxs-lookup"><span data-stu-id="47c3d-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="47c3d-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="47c3d-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="47c3d-135">Hoe kunt u zien of Microsoft Defender Antivirus niet start omdat er een antivirusprogramma van derden is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="47c3d-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="47c3d-136">Als u op een Windows 10-apparaat geen Microsoft Defender voor Eindpunt gebruikt en u een antivirusprogramma van derden hebt geïnstalleerd, wordt Microsoft Defender Antivirus automatisch uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47c3d-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="47c3d-137">Als u Microsoft Defender voor Eindpunt gebruikt met een antivirusprogramma van derden, wordt Microsoft Defender Antivirus in de passieve modus met beperkte functionaliteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="47c3d-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="47c3d-138">Het scenario dat zojuist is beschreven, is alleen van toepassing op Windows 10.</span><span class="sxs-lookup"><span data-stu-id="47c3d-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="47c3d-139">Andere versies van Windows hebben [verschillende antwoorden op](microsoft-defender-antivirus-compatibility.md) Microsoft Defender Antivirus die wordt uitgevoerd naast beveiligingssoftware van derden.</span><span class="sxs-lookup"><span data-stu-id="47c3d-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="47c3d-140">Services-app gebruiken om te controleren of Microsoft Defender Antivirus is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="47c3d-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="47c3d-141">Als u de Services-app wilt openen, **selecteert** u het pictogram Zoeken op de taakbalk en zoekt u naar *services.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="47c3d-142">U kunt de app ook openen vanaf de opdrachtregel door *services.msc te typen.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="47c3d-143">Informatie over Microsoft Defender Antivirus wordt weergegeven in de Services-app onder **Windows Defender**  >  **Operationeel.**</span><span class="sxs-lookup"><span data-stu-id="47c3d-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="47c3d-144">De naam van de antivirusservice is *Windows Defender Antivirus Service.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="47c3d-145">Tijdens het controleren van de app ziet u mogelijk dat *Windows Defender Antivirus Service* is ingesteld op handmatig, maar wanneer u deze service handmatig probeert te starten, krijgt u een waarschuwing met de melding: De Windows Defender Antivirus Service service op lokale computer is gestart en vervolgens *gestopt. Sommige services worden automatisch gestopt als ze niet worden gebruikt door andere services of programma's.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="47c3d-146">Dit geeft aan dat Microsoft Defender Antivirus automatisch is uitgeschakeld om de compatibiliteit met een antivirusprogramma van derden te behouden.</span><span class="sxs-lookup"><span data-stu-id="47c3d-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="47c3d-147">Een gedetailleerd rapport genereren</span><span class="sxs-lookup"><span data-stu-id="47c3d-147">Generate a detailed report</span></span>

<span data-ttu-id="47c3d-148">U kunt een gedetailleerd rapport genereren over momenteel actief groepsbeleid door een opdrachtprompt te openen in de modus Uitvoeren als **beheerder** en vervolgens de volgende opdracht in te voeren:</span><span class="sxs-lookup"><span data-stu-id="47c3d-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="47c3d-149">Hiermee wordt een rapport gegenereerd dat zich op *./gpresult.html bevindt.*</span><span class="sxs-lookup"><span data-stu-id="47c3d-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="47c3d-150">Open dit bestand en u ziet mogelijk de volgende resultaten, afhankelijk van hoe Microsoft Defender Antivirus is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47c3d-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="47c3d-151">Groepsbeleidsresultaten</span><span class="sxs-lookup"><span data-stu-id="47c3d-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="47c3d-152">Als beveiligingsinstellingen worden geïmplementeerd via groepsbeleid (GPO) op het domein of lokaal niveau, of als System Center Configuration Manager (SCCM)</span><span class="sxs-lookup"><span data-stu-id="47c3d-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="47c3d-153">In het rapport GPResults, onder de kop *Windows Components/Windows Defender Antivirus,* ziet u mogelijk iets als de volgende vermelding, waarmee wordt aangegeven dat Microsoft Defender Antivirus is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47c3d-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="47c3d-154">Beleid</span><span class="sxs-lookup"><span data-stu-id="47c3d-154">Policy</span></span> | <span data-ttu-id="47c3d-155">Instelling</span><span class="sxs-lookup"><span data-stu-id="47c3d-155">Setting</span></span> | <span data-ttu-id="47c3d-156">GPO winnen</span><span class="sxs-lookup"><span data-stu-id="47c3d-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="47c3d-157">Windows Defender Antivirus uitschakelen</span><span class="sxs-lookup"><span data-stu-id="47c3d-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="47c3d-158">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="47c3d-158">Enabled</span></span> | <span data-ttu-id="47c3d-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="47c3d-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="47c3d-160">Als beveiligingsinstellingen worden geïmplementeerd via groepsbeleidsvoorkeuren (GPP)</span><span class="sxs-lookup"><span data-stu-id="47c3d-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="47c3d-161">Onder de kop *Registeritem (Sleutelpad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Waardenaam: DisableAntiSpyware)* ziet u mogelijk zoiets als het volgende item, wat aangeeft dat Microsoft Defender Antivirus is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47c3d-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="47c3d-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="47c3d-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="47c3d-163">GPO winnen</span><span class="sxs-lookup"><span data-stu-id="47c3d-163">Winning GPO</span></span> | <span data-ttu-id="47c3d-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="47c3d-164">Win10-Workstations</span></span>
<span data-ttu-id="47c3d-165">Resultaat: Succes</span><span class="sxs-lookup"><span data-stu-id="47c3d-165">Result: Success</span></span> | 
<span data-ttu-id="47c3d-166">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="47c3d-166">**General**</span></span> | 
<span data-ttu-id="47c3d-167">Actie</span><span class="sxs-lookup"><span data-stu-id="47c3d-167">Action</span></span> | <span data-ttu-id="47c3d-168">Update</span><span class="sxs-lookup"><span data-stu-id="47c3d-168">Update</span></span>
<span data-ttu-id="47c3d-169">**Eigenschappen**</span><span class="sxs-lookup"><span data-stu-id="47c3d-169">**Properties**</span></span> | 
<span data-ttu-id="47c3d-170">Bijenkorf</span><span class="sxs-lookup"><span data-stu-id="47c3d-170">Hive</span></span> | <span data-ttu-id="47c3d-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="47c3d-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="47c3d-172">Sleutelpad</span><span class="sxs-lookup"><span data-stu-id="47c3d-172">Key path</span></span> | <span data-ttu-id="47c3d-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="47c3d-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="47c3d-174">Waardenaam</span><span class="sxs-lookup"><span data-stu-id="47c3d-174">Value name</span></span> | <span data-ttu-id="47c3d-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="47c3d-175">DisableAntiSpyware</span></span>
<span data-ttu-id="47c3d-176">Waardetype</span><span class="sxs-lookup"><span data-stu-id="47c3d-176">Value type</span></span> | <span data-ttu-id="47c3d-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="47c3d-177">REG_DWORD</span></span>
<span data-ttu-id="47c3d-178">Waardegegevens</span><span class="sxs-lookup"><span data-stu-id="47c3d-178">Value data</span></span> | <span data-ttu-id="47c3d-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="47c3d-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="47c3d-180">Als beveiligingsinstellingen worden geïmplementeerd via de registersleutel</span><span class="sxs-lookup"><span data-stu-id="47c3d-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="47c3d-181">Het rapport kan de volgende tekst bevatten, waarmee wordt aangegeven dat Microsoft Defender Antivirus is uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="47c3d-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="47c3d-182">Register (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="47c3d-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="47c3d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span><span class="sxs-lookup"><span data-stu-id="47c3d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="47c3d-184">Als beveiligingsinstellingen zijn ingesteld in Windows of uw Windows Server-afbeelding</span><span class="sxs-lookup"><span data-stu-id="47c3d-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="47c3d-185">Uw fanatiek beheerder heeft mogelijk het **[beveiligingsbeleid, DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, lokaal via *GPEdit.exe*, *LGPO.exe* ingesteld of door het register in hun taakvolgorde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="47c3d-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="47c3d-186">U kunt [een vertrouwde afbeeldingsaanduiding configureren](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) voor Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="47c3d-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="47c3d-187">Microsoft Defender Antivirus weer in- en uit-</span><span class="sxs-lookup"><span data-stu-id="47c3d-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="47c3d-188">Microsoft Defender Antivirus wordt automatisch in gebruik als er geen andere antivirusprogramma's actief zijn.</span><span class="sxs-lookup"><span data-stu-id="47c3d-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="47c3d-189">U moet de antivirussoftware van derden volledig uitschakelen om ervoor te zorgen dat Microsoft Defender Antivirus met volledige functionaliteit kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="47c3d-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="47c3d-190">Oplossingen die suggereren dat u de *beginwaarden* van Windows Defender voor *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* en *windefend* in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services bewerkt, worden niet ondersteund en kunnen u dwingen uw systeem opnieuw te imagen.</span><span class="sxs-lookup"><span data-stu-id="47c3d-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="47c3d-191">De passieve modus is beschikbaar als u Microsoft Defender voor Eindpunt en een antivirusprogramma van derden gaat gebruiken samen met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="47c3d-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="47c3d-192">Met de passieve modus kan Microsoft Defender bestanden scannen en zichzelf bijwerken, maar worden bedreigingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47c3d-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="47c3d-193">Daarnaast is gedragscontrole via [realtimebeveiliging](configure-real-time-protection-microsoft-defender-antivirus.md) niet beschikbaar in de passieve modus, tenzij preventie van gegevensverlies in eindpunten [(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) wordt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="47c3d-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="47c3d-194">Een andere functie, ook [wel beperkt periodiek](limited-periodic-scanning-microsoft-defender-antivirus.md)scannen genoemd, is beschikbaar voor eindgebruikers wanneer Microsoft Defender Antivirus is ingesteld om automatisch uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47c3d-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="47c3d-195">Met deze functie kan Microsoft Defender Antivirus regelmatig bestanden scannen samen met een antivirusprogramma van derden, waarbij een beperkt aantal detecties wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="47c3d-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47c3d-196">Beperkt periodiek scannen wordt niet aanbevolen in bedrijfsomgevingen.</span><span class="sxs-lookup"><span data-stu-id="47c3d-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="47c3d-197">De detectie-, beheer- en rapportagemogelijkheden die beschikbaar zijn bij het uitvoeren van Microsoft Defender Antivirus in deze modus, worden verminderd ten opzichte van de actieve modus.</span><span class="sxs-lookup"><span data-stu-id="47c3d-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="47c3d-198">Zie ook</span><span class="sxs-lookup"><span data-stu-id="47c3d-198">See also</span></span>

* [<span data-ttu-id="47c3d-199">Microsoft Defender Antiviruscompatibiliteit</span><span class="sxs-lookup"><span data-stu-id="47c3d-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="47c3d-200">Microsoft Defender Antivirus in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="47c3d-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)