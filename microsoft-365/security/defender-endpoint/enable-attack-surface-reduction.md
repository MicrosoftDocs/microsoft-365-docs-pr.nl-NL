---
title: Regels voor het verminderen van aanvalsoppervlakken inschakelen
description: Schakel ASR-regels (Attack Surface Reduction) in om uw apparaten te beschermen tegen aanvallen met macro's, scripts en veelgebruikte technieken voor insinjectie.
keywords: Surface Reduction attack, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689163"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="33802-104">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="33802-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33802-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="33802-105">**Applies to:**</span></span>
- [<span data-ttu-id="33802-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="33802-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="33802-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33802-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="33802-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="33802-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33802-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="33802-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="33802-110">[Asr-regels (Attack Surface Reduction Rules)](attack-surface-reduction.md) helpen voorkomen dat malware vaak misbruik maakt van apparaten en netwerken.</span><span class="sxs-lookup"><span data-stu-id="33802-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="33802-111">U kunt ASR-regels instellen voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="33802-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="33802-112">Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="33802-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="33802-113">Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="33802-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="33802-114">Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger</span><span class="sxs-lookup"><span data-stu-id="33802-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="33802-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="33802-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="33802-116">Elke ASR-regel bevat een van de vier instellingen:</span><span class="sxs-lookup"><span data-stu-id="33802-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="33802-117">**Niet geconfigureerd:** de ASR-regel uitschakelen</span><span class="sxs-lookup"><span data-stu-id="33802-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="33802-118">**Blokkeren:** De ASR-regel inschakelen</span><span class="sxs-lookup"><span data-stu-id="33802-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="33802-119">**Controleren:** evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="33802-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="33802-120">**Waarschuwen:** Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen</span><span class="sxs-lookup"><span data-stu-id="33802-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33802-121">Momenteel wordt de waarschuwingsmodus niet ondersteund voor drie ASR-regels wanneer u ASR-regels configureert in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="33802-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="33802-122">Zie Gevallen waarin de [waarschuwingsmodus niet wordt ondersteund](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="33802-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="33802-123">Het wordt ten zeerste aanbevolen om ASR-regels te gebruiken met een Windows E5-licentie (of soortgelijke licentie-SKU) om te profiteren van de geavanceerde controle- en rapportagemogelijkheden die beschikbaar zijn in [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Defender voor Eindpunt).</span><span class="sxs-lookup"><span data-stu-id="33802-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="33802-124">Voor andere licenties, zoals Windows Professional of E3 die geen toegang hebben tot geavanceerde monitoring- en rapportagemogelijkheden, kunt u echter uw eigen hulpprogramma's voor monitoring en rapportage ontwikkelen boven op de gebeurtenissen die op elk eindpunt worden gegenereerd wanneer ASR-regels worden geactiveerd (bijvoorbeeld Gebeurtenis doorsturen).</span><span class="sxs-lookup"><span data-stu-id="33802-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="33802-125">Zie Windows [10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) voor meer informatie over Windows-licenties en de [handleiding Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="33802-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="33802-126">U kunt regels voor het verminderen van de surface van aanvallen inschakelen met behulp van een van deze methoden:</span><span class="sxs-lookup"><span data-stu-id="33802-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="33802-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="33802-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="33802-128">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="33802-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="33802-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33802-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="33802-130">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="33802-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="33802-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="33802-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="33802-132">Beheer op ondernemingsniveau, zoals Intune of Microsoft Endpoint Manager, wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="33802-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="33802-133">Ondernemingsbeheer overschrijft alle conflicterende groepsbeleids- of PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="33802-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="33802-134">Bestanden en mappen uitsluiten van ASR-regels</span><span class="sxs-lookup"><span data-stu-id="33802-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="33802-135">U kunt voorkomen dat bestanden en mappen worden geëvalueerd door de meeste regels voor het verminderen van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="33802-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="33802-136">Dit betekent dat zelfs als een ASR-regel bepaalt dat het bestand of de map schadelijk gedrag bevat, het bestand niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="33802-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="33802-137">Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd.</span><span class="sxs-lookup"><span data-stu-id="33802-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="33802-138">U kunt asr-regels ook uitsluiten van triggering op basis van certificaat- en bestandshashes door opgegeven Defender voor eindpuntbestands- en certificaatindicatoren toe te staan.</span><span class="sxs-lookup"><span data-stu-id="33802-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="33802-139">(Zie [Indicatoren beheren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="33802-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33802-140">Het uitsluiten van bestanden of mappen kan de beveiliging die door ASR-regels wordt geboden, aanzienlijk verminderen.</span><span class="sxs-lookup"><span data-stu-id="33802-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="33802-141">Uitgesloten bestanden mogen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.</span><span class="sxs-lookup"><span data-stu-id="33802-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="33802-142">Als asr-regels bestanden detecteren die volgens u niet moeten worden gedetecteerd, moet u eerst de auditmodus gebruiken om de [regel te testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="33802-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="33802-143">U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels de uitsluitingen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="33802-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="33802-144">Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="33802-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="33802-145">Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="33802-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="33802-146">ASR-regels ondersteunen omgevingsvariabelen en jokertekens.</span><span class="sxs-lookup"><span data-stu-id="33802-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="33802-147">Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="33802-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="33802-148">De volgende procedures voor het inschakelen van ASR-regels bevatten instructies voor het uitsluiten van bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="33802-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="33802-149">Intune</span><span class="sxs-lookup"><span data-stu-id="33802-149">Intune</span></span>

1. <span data-ttu-id="33802-150">Selecteer **Apparaatconfiguratieprofielen.**  >  </span><span class="sxs-lookup"><span data-stu-id="33802-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="33802-151">Kies een bestaand eindpuntbeveiligingsprofiel of maak een nieuw profiel.</span><span class="sxs-lookup"><span data-stu-id="33802-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="33802-152">Als u een nieuw profiel wilt maken, **selecteert u Profiel maken** en voert u informatie voor dit profiel in.</span><span class="sxs-lookup"><span data-stu-id="33802-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="33802-153">Selecteer **Voor profieltype** de optie **Eindpuntbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="33802-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="33802-154">Als u een bestaand profiel hebt gekozen, **selecteert** u Eigenschappen en selecteert u **vervolgens Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="33802-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="33802-155">Selecteer in **het deelvenster Endpoint** protection **de optie Windows Defender Exploit Guard** en selecteer vervolgens Attack Surface **Reduction**.</span><span class="sxs-lookup"><span data-stu-id="33802-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="33802-156">Selecteer de gewenste instelling voor elke ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="33802-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="33802-157">Voer **onder Attack Surface Reduction uitzonderingen** afzonderlijke bestanden en mappen in.</span><span class="sxs-lookup"><span data-stu-id="33802-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="33802-158">U kunt ook Importeren **selecteren om** een CSV-bestand te importeren dat bestanden en mappen bevat om uit te sluiten van ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="33802-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="33802-159">Elke regel in het CSV-bestand moet als volgt worden opgemaakt:</span><span class="sxs-lookup"><span data-stu-id="33802-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="33802-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="33802-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="33802-161">Selecteer **OK** in de drie configuratievensters.</span><span class="sxs-lookup"><span data-stu-id="33802-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="33802-162">Selecteer vervolgens **Maken** als u een nieuw eindpuntbeveiligingsbestand maakt of **Opslaan** als u een bestaand bestand bewerkt.</span><span class="sxs-lookup"><span data-stu-id="33802-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="33802-163">MDM</span><span class="sxs-lookup"><span data-stu-id="33802-163">MDM</span></span>

<span data-ttu-id="33802-164">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) om de modus voor elke regel afzonderlijk in te schakelen en in te stellen.</span><span class="sxs-lookup"><span data-stu-id="33802-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="33802-165">Hieronder volgt een voorbeeld voor verwijzing, met [GUID-waarden voor ASR-regels.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="33802-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="33802-166">De waarden die u wilt inschakelen (blokkeren), uitschakelen, waarschuwen of inschakelen in de auditmodus zijn:</span><span class="sxs-lookup"><span data-stu-id="33802-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="33802-167">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="33802-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="33802-168">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="33802-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="33802-169">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="33802-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="33802-170">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen)</span><span class="sxs-lookup"><span data-stu-id="33802-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="33802-171">Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="33802-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="33802-172">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="33802-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="33802-173">Zorg ervoor dat u OMA-URI-waarden zonder spaties typt.</span><span class="sxs-lookup"><span data-stu-id="33802-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="33802-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33802-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="33802-175">Ga in Microsoft Endpoint Configuration Manager naar **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="33802-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="33802-176">Selecteer **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="33802-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="33802-177">Voer een naam en een beschrijving in, selecteer **Attack Surface Reduction** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="33802-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="33802-178">Kies welke regels acties blokkeren of controleren en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="33802-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="33802-179">Controleer de instellingen en selecteer **Volgende om** het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="33802-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="33802-180">Nadat het beleid is gemaakt, **sluit u**.</span><span class="sxs-lookup"><span data-stu-id="33802-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="33802-181">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="33802-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="33802-182">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende instellingen voor groepsbeleid bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="33802-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="33802-183">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](https://technet.microsoft.com/library/cc731212.aspx)</span><span class="sxs-lookup"><span data-stu-id="33802-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="33802-184">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="33802-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="33802-185">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Microsoft Defender Exploit  >  **Guard** Attack  >  **surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="33802-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="33802-186">Selecteer **Aanvalsoppervlakbeperkingsregels configureren** en selecteer **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="33802-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="33802-187">Vervolgens kunt u de afzonderlijke status voor elke regel instellen in de sectie Opties.</span><span class="sxs-lookup"><span data-stu-id="33802-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="33802-188">Selecteer **Toon...** en voer de regel-id in de kolom **Waardenaam** en de door u gekozen status in de **kolom** Waarde als volgt in:</span><span class="sxs-lookup"><span data-stu-id="33802-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="33802-189">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="33802-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="33802-190">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="33802-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="33802-191">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="33802-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="33802-192">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen)</span><span class="sxs-lookup"><span data-stu-id="33802-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regels in groepsbeleid":::

5. <span data-ttu-id="33802-194">Als u bestanden en mappen wilt uitsluiten van ASR-regels, selecteert u de instelling Bestanden en paden uitsluiten van de instelling Surface **Reduction** Attack en stelt u de optie **in op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="33802-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="33802-195">Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in.</span><span class="sxs-lookup"><span data-stu-id="33802-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="33802-196">Voer **0** in de kolom **Waarde** in voor elk item.</span><span class="sxs-lookup"><span data-stu-id="33802-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="33802-197">Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**</span><span class="sxs-lookup"><span data-stu-id="33802-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="33802-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="33802-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="33802-199">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="33802-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="33802-200">Als u wilt dat gebruikers de waarde kunnen definiëren met PowerShell, gebruikt u de optie 'Gebruiker gedefinieerd' voor de regel in het beheerplatform.</span><span class="sxs-lookup"><span data-stu-id="33802-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="33802-201">Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="33802-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="33802-202">Typ de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33802-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="33802-203">Als u ASR-regels wilt inschakelen in de auditmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33802-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="33802-204">Als u ASR-regels wilt inschakelen in de waarschuwingsmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33802-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="33802-205">Als u ASR-regels wilt uitschakelen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33802-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="33802-206">U moet de status afzonderlijk opgeven voor elke regel, maar u kunt regels en toestanden combineren in een door komma's gescheiden lijst.</span><span class="sxs-lookup"><span data-stu-id="33802-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="33802-207">In het volgende voorbeeld worden de eerste twee regels ingeschakeld, wordt de derde regel uitgeschakeld en wordt de vierde regel ingeschakeld in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="33802-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="33802-208">U kunt ook het `Add-MpPreference` werkwoord PowerShell gebruiken om nieuwe regels toe te voegen aan de bestaande lijst.</span><span class="sxs-lookup"><span data-stu-id="33802-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="33802-209">`Set-MpPreference` wordt altijd de bestaande set regels overschreven.</span><span class="sxs-lookup"><span data-stu-id="33802-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="33802-210">Als u wilt toevoegen aan de bestaande set, gebruikt u deze `Add-MpPreference` in plaats daarvan.</span><span class="sxs-lookup"><span data-stu-id="33802-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="33802-211">U kunt een lijst met regels en de huidige status verkrijgen met behulp `Get-MpPreference` van .</span><span class="sxs-lookup"><span data-stu-id="33802-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="33802-212">Als u bestanden en mappen wilt uitsluiten van ASR-regels, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33802-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="33802-213">Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer bestanden en mappen toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="33802-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="33802-214">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="33802-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="33802-215">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="33802-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="33802-216">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="33802-216">Related articles</span></span>

- [<span data-ttu-id="33802-217">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="33802-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="33802-218">De beperking van het oppervlak van de aanval evalueren</span><span class="sxs-lookup"><span data-stu-id="33802-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="33802-219">Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="33802-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
