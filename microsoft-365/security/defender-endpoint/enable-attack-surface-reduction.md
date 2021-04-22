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
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939240"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="b9b35-104">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="b9b35-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9b35-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b9b35-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9b35-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b9b35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9b35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9b35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="b9b35-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b9b35-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9b35-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b9b35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b9b35-110">[Asr-regels (Attack Surface Reduction Rules)](attack-surface-reduction.md) helpen voorkomen dat malware vaak misbruik maakt van apparaten en netwerken.</span><span class="sxs-lookup"><span data-stu-id="b9b35-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="b9b35-111">U kunt ASR-regels instellen voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="b9b35-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="b9b35-112">Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="b9b35-113">Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="b9b35-114">Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="b9b35-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b9b35-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="b9b35-116">**Vereisten** U kunt regels voor het verminderen van aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="b9b35-116">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="b9b35-117">Windows 10 Pro, versie 1709 of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-117">Windows 10 Pro, version 1709 or later</span></span>
- <span data-ttu-id="b9b35-118">Windows 10 Enterprise, versie 1709 of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-118">Windows 10 Enterprise, version 1709 or later</span></span>
- <span data-ttu-id="b9b35-119">Windows Server, versie 1803 (halfjaarlijks kanaal) of hoger</span><span class="sxs-lookup"><span data-stu-id="b9b35-119">Windows Server, version 1803 (Semi-Annual Channel) or later</span></span>
- <span data-ttu-id="b9b35-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b9b35-120">Windows Server 2019</span></span>

<span data-ttu-id="b9b35-121">Hoewel voor regels voor het verminderen van aanvallen geen Windows E5-licentie is vereist, krijgt u geavanceerde beheermogelijkheden als u Windows E5 hebt.</span><span class="sxs-lookup"><span data-stu-id="b9b35-121">Although attack surface reduction rules don't require a Windows E5 license, if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="b9b35-122">Deze mogelijkheden zijn alleen beschikbaar in Windows E5: monitoring, analyse en werkstromen die beschikbaar zijn in Defender voor Eindpunt, evenals rapportage- en configuratiemogelijkheden in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="b9b35-122">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="b9b35-123">Deze geavanceerde mogelijkheden zijn niet beschikbaar met een Windows Professional- of Windows E3-licentie. Als u echter wel over deze licenties hebt, kunt u logboeken eventviewer en Microsoft Defender Antivirus gebruiken om de gebeurtenissen van de surface reduction rule van uw aanval te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b9b35-123">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="b9b35-124">Elke ASR-regel bevat een van de vier instellingen:</span><span class="sxs-lookup"><span data-stu-id="b9b35-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="b9b35-125">**Niet geconfigureerd:** de ASR-regel uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b9b35-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="b9b35-126">**Blokkeren:** De ASR-regel inschakelen</span><span class="sxs-lookup"><span data-stu-id="b9b35-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="b9b35-127">**Controleren:** evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="b9b35-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="b9b35-128">**Waarschuwen:** Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen</span><span class="sxs-lookup"><span data-stu-id="b9b35-128">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9b35-129">Momenteel wordt de waarschuwingsmodus niet ondersteund voor drie ASR-regels wanneer u ASR-regels configureert in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="b9b35-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="b9b35-130">Zie Gevallen waarin de [waarschuwingsmodus niet wordt ondersteund](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9b35-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="b9b35-131">Het wordt ten zeerste aanbevolen om ASR-regels te gebruiken met een Windows E5-licentie (of soortgelijke licentie-SKU) om te profiteren van de geavanceerde controle- en rapportagemogelijkheden die beschikbaar zijn in [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Defender voor Eindpunt).</span><span class="sxs-lookup"><span data-stu-id="b9b35-131">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="b9b35-132">Voor andere licenties, zoals Windows Professional of E3 die geen toegang hebben tot geavanceerde monitoring- en rapportagemogelijkheden, kunt u echter uw eigen hulpprogramma's voor monitoring en rapportage ontwikkelen boven op de gebeurtenissen die op elk eindpunt worden gegenereerd wanneer ASR-regels worden geactiveerd (bijvoorbeeld Gebeurtenis doorsturen).</span><span class="sxs-lookup"><span data-stu-id="b9b35-132">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="b9b35-133">Zie Windows [10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) voor meer informatie over Windows-licenties en de [handleiding Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="b9b35-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="b9b35-134">U kunt regels voor het verminderen van de surface van aanvallen inschakelen met behulp van een van deze methoden:</span><span class="sxs-lookup"><span data-stu-id="b9b35-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="b9b35-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9b35-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="b9b35-136">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="b9b35-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="b9b35-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9b35-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="b9b35-138">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b9b35-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="b9b35-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b35-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="b9b35-140">Beheer op ondernemingsniveau, zoals Intune of Microsoft Endpoint Manager, wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="b9b35-141">Ondernemingsbeheer overschrijft alle conflicterende groepsbeleids- of PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="b9b35-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="b9b35-142">Bestanden en mappen uitsluiten van ASR-regels</span><span class="sxs-lookup"><span data-stu-id="b9b35-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="b9b35-143">U kunt voorkomen dat bestanden en mappen worden geëvalueerd door de meeste regels voor het verminderen van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="b9b35-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="b9b35-144">Dit betekent dat zelfs als een ASR-regel bepaalt dat het bestand of de map schadelijk gedrag bevat, het bestand niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b9b35-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="b9b35-145">Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd.</span><span class="sxs-lookup"><span data-stu-id="b9b35-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="b9b35-146">U kunt asr-regels ook uitsluiten van triggering op basis van certificaat- en bestandshashes door opgegeven Defender voor eindpuntbestands- en certificaatindicatoren toe te staan.</span><span class="sxs-lookup"><span data-stu-id="b9b35-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="b9b35-147">(Zie [Indicatoren beheren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="b9b35-147">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9b35-148">Het uitsluiten van bestanden of mappen kan de beveiliging die door ASR-regels wordt geboden, aanzienlijk verminderen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="b9b35-149">Uitgesloten bestanden mogen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="b9b35-150">Als asr-regels bestanden detecteren die volgens u niet moeten worden gedetecteerd, moet u eerst de auditmodus gebruiken om de [regel te testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="b9b35-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="b9b35-151">U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels de uitsluitingen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="b9b35-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="b9b35-152">Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="b9b35-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="b9b35-153">Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="b9b35-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="b9b35-154">ASR-regels ondersteunen omgevingsvariabelen en jokertekens.</span><span class="sxs-lookup"><span data-stu-id="b9b35-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="b9b35-155">Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="b9b35-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="b9b35-156">De volgende procedures voor het inschakelen van ASR-regels bevatten instructies voor het uitsluiten van bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="b9b35-157">Intune</span><span class="sxs-lookup"><span data-stu-id="b9b35-157">Intune</span></span>

1. <span data-ttu-id="b9b35-158">Selecteer **Apparaatconfiguratieprofielen.**  >  </span><span class="sxs-lookup"><span data-stu-id="b9b35-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="b9b35-159">Kies een bestaand eindpuntbeveiligingsprofiel of maak een nieuw profiel.</span><span class="sxs-lookup"><span data-stu-id="b9b35-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="b9b35-160">Als u een nieuw profiel wilt maken, **selecteert u Profiel maken** en voert u informatie voor dit profiel in.</span><span class="sxs-lookup"><span data-stu-id="b9b35-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="b9b35-161">Selecteer **Voor profieltype** de optie **Eindpuntbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="b9b35-162">Als u een bestaand profiel hebt gekozen, **selecteert** u Eigenschappen en selecteert u **vervolgens Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="b9b35-163">Selecteer in **het deelvenster Endpoint** protection **de optie Windows Defender Exploit Guard** en selecteer vervolgens Attack Surface **Reduction**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="b9b35-164">Selecteer de gewenste instelling voor elke ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="b9b35-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="b9b35-165">Voer **onder Attack Surface Reduction uitzonderingen** afzonderlijke bestanden en mappen in.</span><span class="sxs-lookup"><span data-stu-id="b9b35-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="b9b35-166">U kunt ook Importeren **selecteren om** een CSV-bestand te importeren dat bestanden en mappen bevat om uit te sluiten van ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="b9b35-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="b9b35-167">Elke regel in het CSV-bestand moet als volgt worden opgemaakt:</span><span class="sxs-lookup"><span data-stu-id="b9b35-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="b9b35-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="b9b35-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="b9b35-169">Selecteer **OK** in de drie configuratievensters.</span><span class="sxs-lookup"><span data-stu-id="b9b35-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="b9b35-170">Selecteer vervolgens **Maken** als u een nieuw eindpuntbeveiligingsbestand maakt of **Opslaan** als u een bestaand bestand bewerkt.</span><span class="sxs-lookup"><span data-stu-id="b9b35-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="b9b35-171">MDM</span><span class="sxs-lookup"><span data-stu-id="b9b35-171">MDM</span></span>

<span data-ttu-id="b9b35-172">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) om de modus voor elke regel afzonderlijk in te schakelen en in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-172">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="b9b35-173">Hieronder volgt een voorbeeld voor verwijzing, met [GUID-waarden voor ASR-regels.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="b9b35-173">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="b9b35-174">De waarden die u wilt inschakelen (blokkeren), uitschakelen, waarschuwen of inschakelen in de auditmodus zijn:</span><span class="sxs-lookup"><span data-stu-id="b9b35-174">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="b9b35-175">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="b9b35-175">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="b9b35-176">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="b9b35-176">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="b9b35-177">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="b9b35-177">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="b9b35-178">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen).</span><span class="sxs-lookup"><span data-stu-id="b9b35-178">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="b9b35-179">De waarschuwingsmodus is nu beschikbaar voor de meeste ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="b9b35-179">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="b9b35-180">Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="b9b35-180">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="b9b35-181">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b9b35-181">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="b9b35-182">Zorg ervoor dat u OMA-URI-waarden zonder spaties typt.</span><span class="sxs-lookup"><span data-stu-id="b9b35-182">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="b9b35-183">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9b35-183">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="b9b35-184">Ga in Microsoft Endpoint Configuration Manager naar **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-184">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="b9b35-185">Selecteer **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-185">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="b9b35-186">Voer een naam en een beschrijving in, selecteer **Attack Surface Reduction** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-186">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="b9b35-187">Kies welke regels acties blokkeren of controleren en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-187">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="b9b35-188">Controleer de instellingen en selecteer **Volgende om** het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="b9b35-188">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="b9b35-189">Nadat het beleid is gemaakt, **sluit u**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-189">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="b9b35-190">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b9b35-190">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="b9b35-191">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende instellingen voor groepsbeleid bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="b9b35-191">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="b9b35-192">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](https://technet.microsoft.com/library/cc731212.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9b35-192">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="b9b35-193">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-193">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b9b35-194">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Microsoft Defender Exploit  >  **Guard** Attack  >  **surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="b9b35-194">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="b9b35-195">Selecteer **Aanvalsoppervlakbeperkingsregels configureren** en selecteer **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-195">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="b9b35-196">Vervolgens kunt u de afzonderlijke status voor elke regel instellen in de sectie Opties.</span><span class="sxs-lookup"><span data-stu-id="b9b35-196">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="b9b35-197">Selecteer **Toon...** en voer de regel-id in de kolom **Waardenaam** en de door u gekozen status in de **kolom** Waarde als volgt in:</span><span class="sxs-lookup"><span data-stu-id="b9b35-197">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="b9b35-198">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="b9b35-198">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="b9b35-199">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="b9b35-199">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="b9b35-200">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="b9b35-200">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="b9b35-201">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen)</span><span class="sxs-lookup"><span data-stu-id="b9b35-201">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regels in groepsbeleid":::

5. <span data-ttu-id="b9b35-203">Als u bestanden en mappen wilt uitsluiten van ASR-regels, selecteert u de instelling Bestanden en paden uitsluiten van de instelling Surface **Reduction** Attack en stelt u de optie **in op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-203">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b9b35-204">Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in.</span><span class="sxs-lookup"><span data-stu-id="b9b35-204">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="b9b35-205">Voer **0** in de kolom **Waarde** in voor elk item.</span><span class="sxs-lookup"><span data-stu-id="b9b35-205">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="b9b35-206">Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-206">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="b9b35-207">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b35-207">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="b9b35-208">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="b9b35-208">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="b9b35-209">Als u wilt dat gebruikers de waarde kunnen definiëren met PowerShell, gebruikt u de optie 'Gebruiker gedefinieerd' voor de regel in het beheerplatform.</span><span class="sxs-lookup"><span data-stu-id="b9b35-209">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="b9b35-210">Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="b9b35-210">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="b9b35-211">Typ de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9b35-211">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="b9b35-212">Als u ASR-regels wilt inschakelen in de auditmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9b35-212">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="b9b35-213">Als u ASR-regels wilt inschakelen in de waarschuwingsmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9b35-213">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="b9b35-214">Als u ASR-regels wilt uitschakelen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9b35-214">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b9b35-215">U moet de status afzonderlijk opgeven voor elke regel, maar u kunt regels en toestanden combineren in een door komma's gescheiden lijst.</span><span class="sxs-lookup"><span data-stu-id="b9b35-215">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="b9b35-216">In het volgende voorbeeld worden de eerste twee regels ingeschakeld, wordt de derde regel uitgeschakeld en wordt de vierde regel ingeschakeld in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="b9b35-216">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="b9b35-217">U kunt ook het `Add-MpPreference` werkwoord PowerShell gebruiken om nieuwe regels toe te voegen aan de bestaande lijst.</span><span class="sxs-lookup"><span data-stu-id="b9b35-217">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b9b35-218">`Set-MpPreference` wordt altijd de bestaande set regels overschreven.</span><span class="sxs-lookup"><span data-stu-id="b9b35-218">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="b9b35-219">Als u wilt toevoegen aan de bestaande set, gebruikt u deze `Add-MpPreference` in plaats daarvan.</span><span class="sxs-lookup"><span data-stu-id="b9b35-219">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="b9b35-220">U kunt een lijst met regels en de huidige status verkrijgen met behulp `Get-MpPreference` van .</span><span class="sxs-lookup"><span data-stu-id="b9b35-220">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="b9b35-221">Als u bestanden en mappen wilt uitsluiten van ASR-regels, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9b35-221">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="b9b35-222">Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer bestanden en mappen toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="b9b35-222">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9b35-223">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="b9b35-223">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="b9b35-224">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="b9b35-224">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b9b35-225">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b9b35-225">Related articles</span></span>

- [<span data-ttu-id="b9b35-226">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="b9b35-226">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="b9b35-227">De beperking van het oppervlak van de aanval evalueren</span><span class="sxs-lookup"><span data-stu-id="b9b35-227">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="b9b35-228">Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="b9b35-228">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
