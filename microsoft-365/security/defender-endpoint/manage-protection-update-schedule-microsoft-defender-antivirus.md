---
title: Microsoft Defender Antivirus protection updates plannen
description: Plan de dag, tijd en interval voor wanneer beveiligingsupdates moeten worden gedownload
keywords: updates, beveiligingslijnlijnen, planningsupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 327974c4db4166301820cf148811aceda1700513
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765345"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="b6463-104">Het schema beheren voor wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="b6463-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b6463-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b6463-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6463-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b6463-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b6463-107">Met Microsoft Defender Antivirus kunt u bepalen wanneer u updates moet zoeken en downloaden.</span><span class="sxs-lookup"><span data-stu-id="b6463-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="b6463-108">U kunt updates voor uw eindpunten plannen door:</span><span class="sxs-lookup"><span data-stu-id="b6463-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="b6463-109">De dag van de week opgeven om te controleren op beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="b6463-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="b6463-110">Het interval opgeven om te controleren op beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="b6463-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="b6463-111">De tijd opgeven om te controleren op beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="b6463-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="b6463-112">U kunt ook willekeurig de tijden kiezen waarop elk eindpunt beveiligingsupdates controleert en downloadt.</span><span class="sxs-lookup"><span data-stu-id="b6463-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="b6463-113">Zie het [onderwerp Planning scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6463-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="b6463-114">Configuration Manager gebruiken om beveiligingsupdates te plannen</span><span class="sxs-lookup"><span data-stu-id="b6463-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="b6463-115">Open op uw Microsoft Endpoint Manager-console het antimalwarebeleid dat u wilt wijzigen (klik op Activa en naleving **in** het navigatiedeelvenster aan de linkerkant en vouw de structuur vervolgens uit naar Het  >    >  **antimalwarebeleid voor endpointbeveiliging** van overzicht )</span><span class="sxs-lookup"><span data-stu-id="b6463-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="b6463-116">Ga naar de **sectie Beveiligingsinformatie-updates.**</span><span class="sxs-lookup"><span data-stu-id="b6463-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="b6463-117">Updates op een bepaald moment controleren en downloaden:</span><span class="sxs-lookup"><span data-stu-id="b6463-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="b6463-118">Stel **Controleren op beveiligingsintelligentie-updates** voor eindpunten in met een specifiek interval... op **0**.</span><span class="sxs-lookup"><span data-stu-id="b6463-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="b6463-119">Stel **Dagelijks controleren op beveiligingsintelligentieupdates** voor Eindpuntbeveiliging in op... op het moment waarop updates moeten worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="b6463-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="b6463-120">3</span><span class="sxs-lookup"><span data-stu-id="b6463-120">3</span></span>
4. <span data-ttu-id="b6463-121">Als u updates met een doorlopend interval wilt controleren en downloaden, stelt u Controleren op beveiligingsinformatie-updates voor eindpuntbeveiliging in met een specifiek **interval...** op het aantal uren dat moet plaatsvinden tussen updates.</span><span class="sxs-lookup"><span data-stu-id="b6463-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="b6463-122">[Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="b6463-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="b6463-123">Groepsbeleid gebruiken om beveiligingsupdates te plannen</span><span class="sxs-lookup"><span data-stu-id="b6463-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6463-124">Standaard controleert Microsoft Defender Antivirus 15 minuten vóór het tijdstip van geplande scans op een update.</span><span class="sxs-lookup"><span data-stu-id="b6463-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="b6463-125">Als u deze instellingen inschakelen, wordt deze standaard overgenomen.</span><span class="sxs-lookup"><span data-stu-id="b6463-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="b6463-126">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="b6463-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="b6463-127">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="b6463-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="b6463-128">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="b6463-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="b6463-129">Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Signature Intelligence  >  **Updates** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b6463-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="b6463-130">Dubbelklik op de instelling Geef de dag van de week op om te controleren **of beveiligingsinformatieupdates** zijn ingesteld en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b6463-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b6463-131">Voer de dag van de week in om te controleren op updates.</span><span class="sxs-lookup"><span data-stu-id="b6463-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="b6463-132">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6463-132">Click **OK**.</span></span>
    2. <span data-ttu-id="b6463-133">Dubbelklik op de instelling Geef het interval op om te controleren op de instelling **beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b6463-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b6463-134">Voer het aantal uren tussen updates in.</span><span class="sxs-lookup"><span data-stu-id="b6463-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="b6463-135">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6463-135">Click **OK**.</span></span>
    3. <span data-ttu-id="b6463-136">Dubbelklik op **de instelling Tijd opgeven om te controleren op beveiligingsinformatie-updates** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b6463-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b6463-137">Voer de tijd in waarop updates moeten worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="b6463-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="b6463-138">De tijd is gebaseerd op de lokale tijd van het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6463-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="b6463-139">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6463-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="b6463-140">PowerShell-cmdlets gebruiken om beveiligingsupdates te plannen</span><span class="sxs-lookup"><span data-stu-id="b6463-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="b6463-141">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b6463-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="b6463-142">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)  gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b6463-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="b6463-143">Windows Management Instruction (WMI) gebruiken om beveiligingsupdates te plannen</span><span class="sxs-lookup"><span data-stu-id="b6463-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="b6463-144">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="b6463-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="b6463-145">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="b6463-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b6463-146">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="b6463-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="b6463-147">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b6463-147">Related articles</span></span>

- [<span data-ttu-id="b6463-148">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="b6463-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6463-149">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="b6463-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6463-150">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="b6463-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6463-151">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="b6463-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6463-152">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="b6463-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6463-153">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6463-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)