---
title: Regels voor het verminderen van aanvalsoppervlakken evalueren
description: Bekijk hoe aanvalsoppervlakverkorting aanvallen zou blokkeren en voorkomen met het aangepaste demoprogramma.
keywords: Aanvalsoppervlakverminking, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, evaluate, test, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570337"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="c2fbe-104">Regels voor het verminderen van aanvalsoppervlakken evalueren</span><span class="sxs-lookup"><span data-stu-id="c2fbe-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c2fbe-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c2fbe-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2fbe-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c2fbe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c2fbe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2fbe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c2fbe-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c2fbe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c2fbe-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="c2fbe-110">Met de regels voor het verminderen van aanvallen kunt u voorkomen dat acties die gewoonlijk door malware worden gebruikt om apparaten of netwerken te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="c2fbe-111">Stel regels voor het verminderen van aanvallen in voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="c2fbe-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="c2fbe-112">Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="c2fbe-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c2fbe-113">Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="c2fbe-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c2fbe-114">Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger</span><span class="sxs-lookup"><span data-stu-id="c2fbe-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="c2fbe-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c2fbe-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c2fbe-116">Lees hoe u regels voor het verminderen van aanvallen kunt evalueren door de auditmodus in te schakelen om de functie rechtstreeks in uw organisatie te testen.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="c2fbe-117">U kunt ook naar de website voor demoscenario's van Microsoft Defender voor [Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="c2fbe-118">Controlemodus gebruiken om de impact te meten</span><span class="sxs-lookup"><span data-stu-id="c2fbe-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="c2fbe-119">Schakel regels voor het verminderen van aanvallen in de auditmodus in om een record weer te geven van apps die zouden zijn geblokkeerd als de functie volledig was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="c2fbe-120">Test hoe de functie in uw organisatie werkt om ervoor te zorgen dat deze geen invloed heeft op uw line-of-business-apps.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="c2fbe-121">U kunt ook een idee krijgen van hoe vaak de regels worden gebruikt tijdens normaal gebruik.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="c2fbe-122">Gebruik de volgende PowerShell-cmdlet als u een regel voor het verminderen van het oppervlak van een aanval wilt inschakelen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="c2fbe-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="c2fbe-123">Waar `<rule ID>` is een [GUID-waarde van de regel voor de beperking van het aanvalsoppervlak](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="c2fbe-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="c2fbe-124">Gebruik de volgende PowerShell-cmdlet als u alle extra regels voor het verlagen van de surface-aanvallen wilt inschakelen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="c2fbe-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="c2fbe-125">Als u volledig wilt controleren hoe de regels voor het verlagen van de surface voor aanvallen in uw organisatie werken, moet u een beheerhulpmiddel gebruiken om deze instelling te implementeren op apparaten in uw netwerk(en).</span><span class="sxs-lookup"><span data-stu-id="c2fbe-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="c2fbe-126">U kunt ook configuratieserviceproviders (MDM) (Group Policy, Intune) of Mobile Device Management (MDM) gebruiken om de instelling te configureren en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="c2fbe-127">Meer informatie in het [hoofdartikel Van de surface-beperkingsregels van](attack-surface-reduction.md) Attack.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="c2fbe-128">Gebeurtenissen voor het verminderen van aanvallen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="c2fbe-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="c2fbe-129">Als u apps wilt bekijken die zijn geblokkeerd, opent u Gebeurtenisviewer en filtert u op Gebeurtenis-id 1121 in het Microsoft-Windows-Windows Defender/Operationeel logboek.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="c2fbe-130">In de volgende tabel worden alle netwerkbeveiligingsgebeurtenissen vermeld.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="c2fbe-131">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="c2fbe-131">Event ID</span></span> | <span data-ttu-id="c2fbe-132">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c2fbe-132">Description</span></span>
-|-
 <span data-ttu-id="c2fbe-133">5007</span><span class="sxs-lookup"><span data-stu-id="c2fbe-133">5007</span></span> | <span data-ttu-id="c2fbe-134">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="c2fbe-134">Event when settings are changed</span></span>
 <span data-ttu-id="c2fbe-135">1121</span><span class="sxs-lookup"><span data-stu-id="c2fbe-135">1121</span></span> | <span data-ttu-id="c2fbe-136">Gebeurtenis wanneer een regel voor het verminderen van het aanvalsoppervlak wordt gebruikt in de blokmodus</span><span class="sxs-lookup"><span data-stu-id="c2fbe-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="c2fbe-137">1122</span><span class="sxs-lookup"><span data-stu-id="c2fbe-137">1122</span></span> | <span data-ttu-id="c2fbe-138">Gebeurtenis wanneer een regel voor het verminderen van het oppervlak van een aanval wordt uitgevoerd in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="c2fbe-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="c2fbe-139">Regels voor het verminderen van aanvalsoppervlakken aanpassen</span><span class="sxs-lookup"><span data-stu-id="c2fbe-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="c2fbe-140">Tijdens de evaluatie kunt u elke regel afzonderlijk configureren of bepaalde bestanden en processen uitsluiten van de evaluatie door de functie.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="c2fbe-141">Zie [Attack Surface Reduction Rules aanpassen](customize-attack-surface-reduction.md) voor informatie over het configureren van de functie met beheerhulpmiddelen, waaronder Groepsbeleid en MDM CSP-beleid.</span><span class="sxs-lookup"><span data-stu-id="c2fbe-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2fbe-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c2fbe-142">See also</span></span>

* [<span data-ttu-id="c2fbe-143">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="c2fbe-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="c2fbe-144">Auditmodus gebruiken om Windows Defender te evalueren</span><span class="sxs-lookup"><span data-stu-id="c2fbe-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="c2fbe-145">Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="c2fbe-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
