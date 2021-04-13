---
title: Microsoft Defender Antivirus-updates toepassen na bepaalde gebeurtenissen
description: Beheer hoe Microsoft Defender Antivirus beveiligingsintelligentie-updates van toepassing is na het opstarten of ontvangen van door de cloud geleverde detectierapporten.
keywords: updates, beveiliging, force updates, gebeurtenissen, opstarten, controleren op recentste, meldingen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b9f09878c645d54aadca21fe01749a0e73939c5f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690437"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="05a1a-104">Geforceerd updates op basis van gebeurtenissen beheren</span><span class="sxs-lookup"><span data-stu-id="05a1a-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="05a1a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="05a1a-105">**Applies to:**</span></span>

- [<span data-ttu-id="05a1a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="05a1a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="05a1a-107">Met Microsoft Defender Antivirus kunt u bepalen of updates wel (of niet) moeten plaatsvinden na bepaalde gebeurtenissen, zoals bij het opstarten of na het ontvangen van specifieke rapporten van de door de cloud geleverde beveiligingsservice.</span><span class="sxs-lookup"><span data-stu-id="05a1a-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="05a1a-108">Controleren op beveiligingsupdates voordat u een scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="05a1a-109">U kunt Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets en WMI gebruiken om Microsoft Defender Antivirus te dwingen beveiligingsupdates te controleren en te downloaden voordat u een geplande scan gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="05a1a-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="05a1a-110">Configuration Manager gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="05a1a-111">Open op uw Microsoft Endpoint Manager-console het antimalwarebeleid dat u wilt wijzigen (klik op Activa en naleving **in** het navigatiedeelvenster aan de linkerkant en vouw de structuur vervolgens uit naar Het  >    >  **antimalwarebeleid voor endpointbeveiliging** van overzicht )</span><span class="sxs-lookup"><span data-stu-id="05a1a-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="05a1a-112">Ga naar de **sectie Geplande scans** en stel Controleren op de meest recente **beveiligingsinformatie-updates in voordat u een scan op** Ja gaat **uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="05a1a-113">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-113">Click **OK**.</span></span>

4. <span data-ttu-id="05a1a-114">[Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="05a1a-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="05a1a-115">Groepsbeleid gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="05a1a-116">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="05a1a-117">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="05a1a-118">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="05a1a-119">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="05a1a-120">Dubbelklik op **Controleren op de meest recente virus-** en spywaredefinities voordat u een geplande scan gaat uitvoeren en stel de optie in **op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="05a1a-121">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="05a1a-122">PowerShell-cmdlets gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="05a1a-123">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="05a1a-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="05a1a-124">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/index)te configureren en uit te voeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05a1a-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="05a1a-125">Windows Management Instruction (WMI) gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="05a1a-126">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="05a1a-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="05a1a-127">Zie Windows [Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05a1a-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="05a1a-128">Controleren op beveiligingsupdates bij opstarten</span><span class="sxs-lookup"><span data-stu-id="05a1a-128">Check for protection updates on startup</span></span>

<span data-ttu-id="05a1a-129">U kunt groepsbeleid gebruiken om Microsoft Defender Antivirus te dwingen beveiligingsupdates te controleren en downloaden wanneer de computer wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="05a1a-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="05a1a-130">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="05a1a-131">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="05a1a-132">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="05a1a-133">Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="05a1a-134">Dubbelklik bij het opstarten op Controleren op de meest recente **virus-** en spywaredefinities en stel de optie in **op Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="05a1a-135">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-135">Click **OK**.</span></span>

<span data-ttu-id="05a1a-136">U kunt ook Groepsbeleid, PowerShell of WMI gebruiken om Microsoft Defender Antivirus te configureren om te controleren op updates bij het opstarten, zelfs wanneer het programma niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="05a1a-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="05a1a-137">Groepsbeleid gebruiken om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is</span><span class="sxs-lookup"><span data-stu-id="05a1a-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="05a1a-138">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="05a1a-139">Ga met **de Groepsbeleidsbeheereditor** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="05a1a-140">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="05a1a-141">Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="05a1a-142">Dubbelklik bij **het opstarten op Beveiligingsinformatieupdate starten** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="05a1a-143">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="05a1a-144">PowerShell-cmdlets gebruiken om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is</span><span class="sxs-lookup"><span data-stu-id="05a1a-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="05a1a-145">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="05a1a-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="05a1a-146">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/index) te beheren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="05a1a-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="05a1a-147">Windows Management Instruction (WMI) gebruiken om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is</span><span class="sxs-lookup"><span data-stu-id="05a1a-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="05a1a-148">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="05a1a-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="05a1a-149">Zie Windows [Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05a1a-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="05a1a-150">Ad-hocwijzigingen toestaan voor beveiliging op basis van beveiliging in de cloud</span><span class="sxs-lookup"><span data-stu-id="05a1a-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="05a1a-151">Microsoft Defender AV kan wijzigingen aanbrengen in de beveiliging op basis van beveiliging in de cloud.</span><span class="sxs-lookup"><span data-stu-id="05a1a-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="05a1a-152">Dergelijke wijzigingen kunnen optreden buiten normale of geplande beveiligingsupdates.</span><span class="sxs-lookup"><span data-stu-id="05a1a-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="05a1a-153">Als u beveiliging via de cloud hebt ingeschakeld, stuurt Microsoft Defender AV bestanden die verdacht zijn naar de Windows Defender-cloud.</span><span class="sxs-lookup"><span data-stu-id="05a1a-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="05a1a-154">Als de cloudservice meldt dat het bestand schadelijk is en het bestand wordt gedetecteerd in een recente beveiligingsupdate, kunt u Groepsbeleid gebruiken om Microsoft Defender AV zo te configureren dat deze beveiligingsupdate automatisch wordt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="05a1a-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="05a1a-155">Andere belangrijke beveiligingsupdates kunnen ook worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="05a1a-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="05a1a-156">Groepsbeleid gebruiken om recente updates automatisch te downloaden op basis van beveiliging in de cloud</span><span class="sxs-lookup"><span data-stu-id="05a1a-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="05a1a-157">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="05a1a-158">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="05a1a-159">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="05a1a-160">Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="05a1a-161">Dubbelklik op **Updates voor realtime beveiligingsinformatie toestaan** op basis van rapporten in Microsoft MAPS en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="05a1a-162">Klik daarna op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-162">Then click **OK**.</span></span>

6. <span data-ttu-id="05a1a-163">**Meldingen toestaan om rapporten op basis van definities uit** te schakelen in Microsoft MAPS en de optie in te stellen op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="05a1a-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="05a1a-164">Klik daarna op **OK**.</span><span class="sxs-lookup"><span data-stu-id="05a1a-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05a1a-165">**Als u meldingen toestaat om rapporten op basis van definities** uit te schakelen, kan Microsoft MAPS de definities uitschakelen die bekend staan als fout-positieve rapporten.</span><span class="sxs-lookup"><span data-stu-id="05a1a-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="05a1a-166">U moet uw computer zo configureren dat u deel kunt nemen aan Microsoft MAPS, om deze functie te laten werken.</span><span class="sxs-lookup"><span data-stu-id="05a1a-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="05a1a-167">Zie ook</span><span class="sxs-lookup"><span data-stu-id="05a1a-167">See also</span></span>

- [<span data-ttu-id="05a1a-168">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="05a1a-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="05a1a-169">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="05a1a-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="05a1a-170">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="05a1a-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="05a1a-171">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="05a1a-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="05a1a-172">Updates voor mobiele apparaten en virtuele machines (VM's) beheren</span><span class="sxs-lookup"><span data-stu-id="05a1a-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="05a1a-173">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="05a1a-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)