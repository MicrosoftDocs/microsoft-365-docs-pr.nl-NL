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
ms.openlocfilehash: fc952ceec7d26d853e39cab0a803daace62a4767
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345883"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="4bcd7-104">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4bcd7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-105">**Applies to:**</span></span>

- [<span data-ttu-id="4bcd7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4bcd7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4bcd7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bcd7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="4bcd7-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4bcd7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4bcd7-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4bcd7-110">[Asr-regels (Attack Surface Reduction Rules)](attack-surface-reduction.md) helpen voorkomen dat malware vaak misbruik maakt van apparaten en netwerken.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="4bcd7-111">**Vereisten** U kunt regels voor de beperking van de surface voor aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="4bcd7-112">Windows 10 Pro, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="4bcd7-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="4bcd7-113">Windows 10 Enterprise, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="4bcd7-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="4bcd7-114">Windows Server, [versie 1803 (halfjaarlijks kanaal)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger</span><span class="sxs-lookup"><span data-stu-id="4bcd7-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="4bcd7-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4bcd7-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="4bcd7-116">Hoewel voor de regels voor het verminderen van aanvallen geen [E5-licentie](/windows/deployment/deploy-enterprise-licenses)Windows vereist, krijgt u geavanceerde beheermogelijkheden als u Windows E5 hebt.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="4bcd7-117">Deze mogelijkheden zijn alleen beschikbaar in Windows E5, zoals monitoring, analyse en werkstromen die beschikbaar zijn in [Defender voor](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)Eindpunt, evenals rapportage- en configuratiemogelijkheden in het [Microsoft 365 beveiligingscentrum.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="4bcd7-118">Deze geavanceerde mogelijkheden zijn niet beschikbaar met een Windows Professional- of Windows E3-licentie. Als u echter wel over deze licenties hebt, kunt u Gebeurtenisviewer en logboeken Microsoft Defender Antivirus om de gebeurtenissen in de surface reduction rule van uw aanval te bekijken.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="4bcd7-119">Elke ASR-regel bevat een van de vier instellingen:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="4bcd7-120">**Niet geconfigureerd:** de ASR-regel uitschakelen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="4bcd7-121">**Blokkeren:** De ASR-regel inschakelen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="4bcd7-122">**Controleren:** evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="4bcd7-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="4bcd7-123">**Waarschuwen:** Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bcd7-124">Momenteel wordt de waarschuwingsmodus niet ondersteund voor drie ASR-regels wanneer u ASR-regels configureert in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="4bcd7-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="4bcd7-125">Zie Gevallen waarin de [waarschuwingsmodus niet wordt ondersteund](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="4bcd7-126">Het wordt ten zeerste aanbevolen om ASR-regels te gebruiken met een Windows E5-licentie (of soortgelijke licentie-SKU) om te profiteren van de geavanceerde controle- en rapportagemogelijkheden die beschikbaar zijn in [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) voor Eindpunt (Defender voor Eindpunt).</span><span class="sxs-lookup"><span data-stu-id="4bcd7-126">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="4bcd7-127">Voor andere licenties, zoals Windows Professional of E3 die geen toegang hebben tot geavanceerde controle- en rapportagemogelijkheden, kunt u echter uw eigen hulpprogramma's voor monitoring en rapportage ontwikkelen boven op de gebeurtenissen die op elk eindpunt worden gegenereerd wanneer ASR-regels worden geactiveerd (bijvoorbeeld Gebeurtenis doorsturen).</span><span class="sxs-lookup"><span data-stu-id="4bcd7-127">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="4bcd7-128">Zie Licenties Windows licenties voor meer [Windows 10 Windows](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) en ontvang de handleiding [Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="4bcd7-129">U kunt regels voor het verminderen van de surface van aanvallen inschakelen met behulp van een van deze methoden:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="4bcd7-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4bcd7-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="4bcd7-131">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="4bcd7-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4bcd7-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="4bcd7-133">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="4bcd7-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="4bcd7-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bcd7-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="4bcd7-135">Beheer op ondernemingsniveau, zoals Intune of Microsoft Endpoint Manager wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="4bcd7-136">Ondernemingsbeheer overschrijft alle conflicterende groepsbeleids- of PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="4bcd7-137">Bestanden en mappen uitsluiten van ASR-regels</span><span class="sxs-lookup"><span data-stu-id="4bcd7-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="4bcd7-138">U kunt voorkomen dat bestanden en mappen worden geëvalueerd door de meeste regels voor het verminderen van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="4bcd7-139">Dit betekent dat zelfs als een ASR-regel bepaalt dat het bestand of de map schadelijk gedrag bevat, het bestand niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="4bcd7-140">Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="4bcd7-141">U kunt asr-regels ook uitsluiten van triggering op basis van certificaat- en bestandshashes door opgegeven Defender voor eindpuntbestands- en certificaatindicatoren toe te staan.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="4bcd7-142">(Zie [Indicatoren beheren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-142">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bcd7-143">Het uitsluiten van bestanden of mappen kan de beveiliging die door ASR-regels wordt geboden, aanzienlijk verminderen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="4bcd7-144">Uitgesloten bestanden mogen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="4bcd7-145">Als asr-regels bestanden detecteren die volgens u niet moeten worden gedetecteerd, moet u eerst de auditmodus gebruiken om de [regel te testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="4bcd7-146">U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels de uitsluitingen van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="4bcd7-147">Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="4bcd7-148">Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="4bcd7-149">ASR-regels ondersteunen omgevingsvariabelen en jokertekens.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="4bcd7-150">Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="4bcd7-151">De volgende procedures voor het inschakelen van ASR-regels bevatten instructies voor het uitsluiten van bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="4bcd7-152">Intune</span><span class="sxs-lookup"><span data-stu-id="4bcd7-152">Intune</span></span>

1. <span data-ttu-id="4bcd7-153">Selecteer **Apparaatconfiguratieprofielen.**  >  </span><span class="sxs-lookup"><span data-stu-id="4bcd7-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="4bcd7-154">Kies een bestaand eindpuntbeveiligingsprofiel of maak een nieuw profiel.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="4bcd7-155">Als u een nieuw profiel wilt maken, **selecteert u Profiel maken** en voert u informatie voor dit profiel in.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="4bcd7-156">Selecteer **Voor profieltype** de optie **Eindpuntbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="4bcd7-157">Als u een bestaand profiel hebt gekozen, **selecteert** u Eigenschappen en selecteert u **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="4bcd7-158">Selecteer in **het deelvenster Endpoint-beveiliging** **Windows Defender Exploit Guard** en selecteer vervolgens Attack Surface **Reduction.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="4bcd7-159">Selecteer de gewenste instelling voor elke ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="4bcd7-160">Voer **onder Attack Surface Reduction uitzonderingen** afzonderlijke bestanden en mappen in.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="4bcd7-161">U kunt ook Importeren **selecteren om** een CSV-bestand te importeren dat bestanden en mappen bevat om uit te sluiten van ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="4bcd7-162">Elke regel in het CSV-bestand moet als volgt worden opgemaakt:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="4bcd7-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="4bcd7-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="4bcd7-164">Selecteer **OK** in de drie configuratievensters.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="4bcd7-165">Selecteer vervolgens **Maken** als u een nieuw eindpuntbeveiligingsbestand maakt of **Opslaan** als u een bestaand bestand bewerkt.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="4bcd7-166">MDM</span><span class="sxs-lookup"><span data-stu-id="4bcd7-166">MDM</span></span>

<span data-ttu-id="4bcd7-167">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) om de modus voor elke regel afzonderlijk in te schakelen en in te stellen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="4bcd7-168">Hieronder volgt een voorbeeld voor verwijzing, met [GUID-waarden voor ASR-regels.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-168">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="4bcd7-169">De waarden die u wilt inschakelen (blokkeren), uitschakelen, waarschuwen of inschakelen in de auditmodus zijn:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-169">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="4bcd7-170">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-170">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="4bcd7-171">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-171">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="4bcd7-172">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-172">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="4bcd7-173">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen).</span><span class="sxs-lookup"><span data-stu-id="4bcd7-173">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="4bcd7-174">De waarschuwingsmodus is nu beschikbaar voor de meeste ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-174">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="4bcd7-175">Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-175">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="4bcd7-176">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-176">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="4bcd7-177">Zorg ervoor dat u OMA-URI-waarden zonder spaties typt.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-177">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4bcd7-178">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4bcd7-178">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="4bcd7-179">Ga Microsoft Endpoint Configuration Manager naar Assets **and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-179">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="4bcd7-180">Selecteer **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-180">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="4bcd7-181">Voer een naam en een beschrijving in, selecteer **Attack Surface Reduction** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-181">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="4bcd7-182">Kies welke regels acties blokkeren of controleren en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-182">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="4bcd7-183">Controleer de instellingen en selecteer **Volgende om** het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-183">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="4bcd7-184">Nadat het beleid is gemaakt, **sluit u**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-184">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="4bcd7-185">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="4bcd7-185">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="4bcd7-186">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende instellingen voor groepsbeleid bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-186">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="4bcd7-187">Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](https://technet.microsoft.com/library/cc731212.aspx), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-187">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="4bcd7-188">Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-188">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="4bcd7-189">Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Microsoft Defender Exploit Guard**  >  **Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-189">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="4bcd7-190">Selecteer **Aanvalsoppervlakbeperkingsregels configureren** en selecteer **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-190">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="4bcd7-191">Vervolgens kunt u de afzonderlijke status voor elke regel instellen in de sectie Opties.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-191">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="4bcd7-192">Selecteer **Toon...** en voer de regel-id in de kolom **Waardenaam** en de door u gekozen status in de **kolom** Waarde als volgt in:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-192">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="4bcd7-193">0 : Uitschakelen (de ASR-regel uitschakelen)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-193">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="4bcd7-194">1 : Blokkeren (asr-regel inschakelen)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-194">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="4bcd7-195">2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-195">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="4bcd7-196">6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen)</span><span class="sxs-lookup"><span data-stu-id="4bcd7-196">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regels in groepsbeleid":::

5. <span data-ttu-id="4bcd7-198">Als u bestanden en mappen wilt uitsluiten van ASR-regels, selecteert u de instelling Bestanden en paden uitsluiten van de instelling Surface **Reduction** Attack en stelt u de optie **in op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-198">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4bcd7-199">Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-199">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="4bcd7-200">Voer **0** in de kolom **Waarde** in voor elk item.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-200">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4bcd7-201">Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-201">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="microsoft-endpoint-manager-custom-procedure"></a><span data-ttu-id="4bcd7-202">Microsoft Endpoint Manager aangepaste procedure</span><span class="sxs-lookup"><span data-stu-id="4bcd7-202">Microsoft Endpoint Manager custom procedure</span></span>

<span data-ttu-id="4bcd7-203">U kunt een Microsoft Endpoint Manager (MEM)-beheercentrum gebruiken om aangepaste ASR-regels te configureren.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-203">You can use a Microsoft Endpoint Manager (MEM) admin center to configure custom ASR rules.</span></span>

1. <span data-ttu-id="4bcd7-204">Open het Microsoft Endpoint Manager (MEM)-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-204">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="4bcd7-205">Klik in **het** menu Start op **Apparaten,** selecteer **Configuratieprofiel** en klik vervolgens **op Profiel maken.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-205">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   ![Profiel maken met MEM](images/mem01-create-profile.png)

2. <span data-ttu-id="4bcd7-207">Selecteer **in Een profiel maken** in de volgende twee vervolgkeuzelijsten de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-207">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="4bcd7-208">Selecteer **in Platform** de Windows 10 en **hoger**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-208">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="4bcd7-209">Selecteer **Sjablonen in** **profieltype**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-209">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="4bcd7-210">Selecteer **Aangepast** en klik vervolgens op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-210">Select **Custom**, and then click **Create**.</span></span>

   ![PROFIELKENMERKEN VAN MEM-regels](images/mem02-profile-attributes.png)

3. <span data-ttu-id="4bcd7-212">Het hulpprogramma Aangepaste sjabloon wordt geopend voor stap **1 Basisbeginselen.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-212">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="4bcd7-213">Typ **in 1** Basisbeginselen in **Naam** een naam voor uw sjabloon en in **Beschrijving** kunt u een beschrijving typen (optioneel).</span><span class="sxs-lookup"><span data-stu-id="4bcd7-213">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional ).</span></span>

   ![BASISKENMERKEN VAN MEM](images/mem03-1-basics.png)

4. <span data-ttu-id="4bcd7-215">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-215">Click **Next**.</span></span> <span data-ttu-id="4bcd7-216">Stap **2 Configuratie-instellingen** worden geopend.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-216">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="4bcd7-217">Klik voor OMA-URI-Instellingen op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-217">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="4bcd7-218">Er worden nu twee opties weergegeven: **Toevoegen** en **exporteren.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-218">Two options now appear: **Add** and **Export**.</span></span>

   ![INSTELLINGEN VOOR MEM-configuratie](images/mem04-2-configuration-settings.png)

5. <span data-ttu-id="4bcd7-220">Klik **nogmaals op** Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-220">Click **Add** again.</span></span> <span data-ttu-id="4bcd7-221">De **oma-URI-Instellingen** toevoegen wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-221">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="4bcd7-222">Ga **als volgt te** werk in Rij toevoegen:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-222">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="4bcd7-223">Typ **in Naam** een naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-223">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="4bcd7-224">Typ **in Beschrijving** een korte beschrijving.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-224">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="4bcd7-225">Typ **of plak in OMA-URI** de specifieke OMA-URI-koppeling voor de regel die u toevoegt.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-225">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="4bcd7-226">Selecteer **tekenreeks** in **gegevenstype**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-226">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="4bcd7-227">Typ **of** plak in Waarde de GUID-waarde, het teken en de statuswaarde zonder \= spaties _(GUID=StateValue)._</span><span class="sxs-lookup"><span data-stu-id="4bcd7-227">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="4bcd7-228">Waar: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="4bcd7-228">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   ![MEM OMA URI-configuratie](images/mem05-add-row-oma-uri.png)

6. <span data-ttu-id="4bcd7-230">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-230">Click **Save**.</span></span> <span data-ttu-id="4bcd7-231">**Rij sluiten** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-231">**Add Row** closes.</span></span> <span data-ttu-id="4bcd7-232">Klik **in Aangepast** op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-232">In **Custom**, click **Next**.</span></span> <span data-ttu-id="4bcd7-233">In stap **3 Bereiklabels** zijn bereiklabels optioneel.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-233">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="4bcd7-234">Voer een van de volgende bewerkingen uit:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-234">Do one of the following:</span></span>

   - <span data-ttu-id="4bcd7-235">Klik **op Bereiklabels** selecteren, selecteer de bereiktag (optioneel) en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-235">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="4bcd7-236">Of klik op **Volgende**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-236">Or click **Next**</span></span>

7. <span data-ttu-id="4bcd7-237">Selecteer in stap **4 Toewijzingen** **,** in Opgenomen groepen - voor de groepen die u wilt toepassen op deze regel- een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-237">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="4bcd7-238">**Groepen toevoegen**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-238">**Add groups**</span></span>
   - <span data-ttu-id="4bcd7-239">**Alle gebruikers toevoegen**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-239">**Add all users**</span></span>
   - <span data-ttu-id="4bcd7-240">**Alle apparaten toevoegen**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-240">**Add all devices**</span></span>

   ![MEM-opdrachten](images/mem06-4-assignments.png)

8. <span data-ttu-id="4bcd7-242">Selecteer **in Uitgesloten groepen** alle groepen die u van deze regel wilt uitsluiten en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-242">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="4bcd7-243">Ga als volgt te werk in stap **5** Toepassingsregels voor de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-243">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="4bcd7-244">Selecteer **in** Regel profiel toewijzen **als** of Profiel niet **toewijzen als**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-244">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="4bcd7-245">Selecteer **in Eigenschap** de eigenschap waarop u deze regel wilt toepassen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-245">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="4bcd7-246">Voer **in Waarde** de toepasselijke waarde of het waardebereik in</span><span class="sxs-lookup"><span data-stu-id="4bcd7-246">In **Value**, enter the applicable value or value range</span></span>

   ![Regels voor mem-toepassing](images/mem07-5-applicability-rules.png)

10. <span data-ttu-id="4bcd7-248">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-248">Click **Next**.</span></span> <span data-ttu-id="4bcd7-249">Controleer in **stap 6 Controleren + maken** de instellingen en informatie die u hebt geselecteerd en ingevoerd en klik vervolgens op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-249">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

   ![MEM Controleren en maken](images/mem08-6-review-create.png)

>[!NOTE]
> <span data-ttu-id="4bcd7-251">Regels zijn actief en leven binnen enkele minuten.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-251">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="4bcd7-252">Conflictafhandeling: Als u een apparaat twee verschillende ASR-beleidsregels toewijst, zijn regels die aan verschillende staten zijn toegewezen, er is geen conflictbeheer en is het resultaat een fout.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-252">Conflict handling: If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
> <span data-ttu-id="4bcd7-253">Niet-conflicterende regels leiden niet tot een fout en de regel wordt correct toegepast.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-253">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="4bcd7-254">Het resultaat is dat de eerste regel wordt toegepast en dat de volgende niet-conflicterende regels worden samengevoegd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-254">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="powershell"></a><span data-ttu-id="4bcd7-255">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bcd7-255">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="4bcd7-256">Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende PowerShell-instellingen bij het opstarten.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-256">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="4bcd7-257">Als u wilt dat gebruikers de waarde kunnen definiëren met PowerShell, gebruikt u de optie 'Gebruiker gedefinieerd' voor de regel in het beheerplatform.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-257">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="4bcd7-258">Typ **powershell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="4bcd7-258">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4bcd7-259">Typ de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-259">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="4bcd7-260">Als u ASR-regels wilt inschakelen in de auditmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-260">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="4bcd7-261">Als u ASR-regels wilt inschakelen in de waarschuwingsmodus, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-261">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="4bcd7-262">Gebruik de volgende cmdlet om misbruik van uitgebuite, kwetsbare ondertekende stuurprogramma's in te stellen:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-262">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled"}
   ```

    <span data-ttu-id="4bcd7-263">Als u ASR-regels wilt uitschakelen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-263">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="4bcd7-264">U moet de status afzonderlijk opgeven voor elke regel, maar u kunt regels en toestanden combineren in een door komma's gescheiden lijst.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-264">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="4bcd7-265">In het volgende voorbeeld worden de eerste twee regels ingeschakeld, wordt de derde regel uitgeschakeld en wordt de vierde regel ingeschakeld in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-265">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="4bcd7-266">U kunt ook het `Add-MpPreference` werkwoord PowerShell gebruiken om nieuwe regels toe te voegen aan de bestaande lijst.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-266">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="4bcd7-267">`Set-MpPreference` wordt altijd de bestaande set regels overschreven.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-267">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="4bcd7-268">Als u wilt toevoegen aan de bestaande set, gebruikt u deze `Add-MpPreference` in plaats daarvan.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-268">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="4bcd7-269">U kunt een lijst met regels en de huidige status verkrijgen met behulp `Get-MpPreference` van .</span><span class="sxs-lookup"><span data-stu-id="4bcd7-269">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="4bcd7-270">Als u bestanden en mappen wilt uitsluiten van ASR-regels, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bcd7-270">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="4bcd7-271">Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer bestanden en mappen toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-271">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4bcd7-272">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-272">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="4bcd7-273">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="4bcd7-273">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4bcd7-274">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-274">Related articles</span></span>

- [<span data-ttu-id="4bcd7-275">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="4bcd7-275">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="4bcd7-276">De beperking van het oppervlak van de aanval evalueren</span><span class="sxs-lookup"><span data-stu-id="4bcd7-276">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="4bcd7-277">Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="4bcd7-277">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
