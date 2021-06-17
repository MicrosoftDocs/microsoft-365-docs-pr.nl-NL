---
title: Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren
description: Bekijk hoe aanvalsoppervlakverkorting aanvallen zou blokkeren en voorkomen met het aangepaste demoprogramma.
keywords: Aanvalsoppervlakverminking, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, evaluate, test, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a5fa8e46de0a6561d3377ce77e38bd59aa97f3c4
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984722"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="0e178-104">Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren</span><span class="sxs-lookup"><span data-stu-id="0e178-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e178-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0e178-105">**Applies to:**</span></span>

- [<span data-ttu-id="0e178-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0e178-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0e178-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e178-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0e178-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0e178-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e178-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0e178-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="0e178-110">Met de regels voor het verminderen van aanvallen kunt u voorkomen dat acties die gewoonlijk door malware worden gebruikt om apparaten of netwerken te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="0e178-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="0e178-111">Met de regels voor het verminderen van aanvallen kunt u veel van de veelgebruikte toegangspunten sluiten die door malware en ransomware worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0e178-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span>

<span data-ttu-id="0e178-112">Stel regels voor het verminderen van aanvallen in voor apparaten met een van de volgende versies en versies van Windows:</span><span class="sxs-lookup"><span data-stu-id="0e178-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="0e178-113">Windows 10 Pro, [versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="0e178-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0e178-114">Windows 10 Enterprise, [versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger</span><span class="sxs-lookup"><span data-stu-id="0e178-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0e178-115">Windows Server, [versie 1803 (halfjaarlijks kanaal)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger</span><span class="sxs-lookup"><span data-stu-id="0e178-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="0e178-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0e178-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> <span data-ttu-id="0e178-117">Het inschakelen van regels voor het beperken van aanvallen op Windows Server 2016 kan leiden tot onverwachte resultaten en gevolgen voor de serverprestaties.</span><span class="sxs-lookup"><span data-stu-id="0e178-117">Enabling attack service reduction rules on Windows Server 2016 might lead to unexpected results, and impact server performance.</span></span> <span data-ttu-id="0e178-118">We raden u af om regels voor het verlagen van de surface voor aanvallen in te stellen of te implementeren op niet-ondersteunde platforms.</span><span class="sxs-lookup"><span data-stu-id="0e178-118">We do not recommend enabling or deploying attack surface reduction rules to unsupported platforms.</span></span>

<span data-ttu-id="0e178-119">Lees hoe u regels voor het verminderen van aanvallen kunt evalueren door [de auditmodus in](audit-windows-defender.md) te schakelen om de functie rechtstreeks in uw organisatie te testen.</span><span class="sxs-lookup"><span data-stu-id="0e178-119">Learn how to evaluate attack surface reduction rules by [enabling audit mode](audit-windows-defender.md) to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="0e178-120">U kunt ook naar de website voor demoscenario's van Microsoft Defender voor [Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.</span><span class="sxs-lookup"><span data-stu-id="0e178-120">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="0e178-121">Controlemodus gebruiken om de impact te meten</span><span class="sxs-lookup"><span data-stu-id="0e178-121">Use audit mode to measure impact</span></span>

<span data-ttu-id="0e178-122">Schakel regels voor het verminderen van aanvallen in de auditmodus in om een record weer te geven van apps die zouden zijn geblokkeerd als de functie volledig was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0e178-122">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="0e178-123">Test hoe de functie in uw organisatie werkt om ervoor te zorgen dat deze geen invloed heeft op uw line-of-business-apps.</span><span class="sxs-lookup"><span data-stu-id="0e178-123">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="0e178-124">U kunt ook een idee krijgen van hoe vaak de regels worden gebruikt tijdens normaal gebruik.</span><span class="sxs-lookup"><span data-stu-id="0e178-124">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="0e178-125">Gebruik de volgende PowerShell-cmdlet als u een regel voor het verminderen van het oppervlak van een aanval wilt inschakelen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="0e178-125">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="0e178-126">Waar `<rule ID>` is een [GUID-waarde van de regel voor de beperking van het aanvalsoppervlak](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="0e178-126">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="0e178-127">Gebruik de volgende PowerShell-cmdlet als u alle extra regels voor het verlagen van de surface-aanvallen wilt inschakelen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="0e178-127">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="0e178-128">Als u volledig wilt controleren hoe de regels voor het verlagen van de surface voor aanvallen in uw organisatie werken, moet u een beheerhulpmiddel gebruiken om deze instelling te implementeren op apparaten in uw netwerk(en).</span><span class="sxs-lookup"><span data-stu-id="0e178-128">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="0e178-129">U kunt ook configuratieserviceproviders (MDM) (Group Policy, Intune) of Mobile Device Management (MDM) gebruiken om de instelling te configureren en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="0e178-129">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="0e178-130">Meer informatie in het [hoofdartikel Van de surface-beperkingsregels van](attack-surface-reduction.md) Attack.</span><span class="sxs-lookup"><span data-stu-id="0e178-130">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="0e178-131">Gebeurtenissen voor het verminderen van aanvallen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="0e178-131">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="0e178-132">Als u apps wilt bekijken die zijn geblokkeerd, opent u Gebeurtenisviewer en filtert u op Gebeurtenis-id 1121 in het Microsoft-Windows-Windows Defender/Operationeel logboek.</span><span class="sxs-lookup"><span data-stu-id="0e178-132">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="0e178-133">In de volgende tabel worden alle netwerkbeveiligingsgebeurtenissen vermeld.</span><span class="sxs-lookup"><span data-stu-id="0e178-133">The following table lists all network protection events.</span></span>

<span data-ttu-id="0e178-134">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="0e178-134">Event ID</span></span> | <span data-ttu-id="0e178-135">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0e178-135">Description</span></span>
-|-
 <span data-ttu-id="0e178-136">5007</span><span class="sxs-lookup"><span data-stu-id="0e178-136">5007</span></span> | <span data-ttu-id="0e178-137">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="0e178-137">Event when settings are changed</span></span>
 <span data-ttu-id="0e178-138">1121</span><span class="sxs-lookup"><span data-stu-id="0e178-138">1121</span></span> | <span data-ttu-id="0e178-139">Gebeurtenis wanneer een regel voor het verminderen van het aanvalsoppervlak wordt gebruikt in de blokmodus</span><span class="sxs-lookup"><span data-stu-id="0e178-139">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="0e178-140">1122</span><span class="sxs-lookup"><span data-stu-id="0e178-140">1122</span></span> | <span data-ttu-id="0e178-141">Gebeurtenis wanneer een regel voor het verminderen van het oppervlak van een aanval wordt uitgevoerd in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="0e178-141">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="0e178-142">Regels voor het verminderen van aanvalsoppervlakken aanpassen</span><span class="sxs-lookup"><span data-stu-id="0e178-142">Customize attack surface reduction rules</span></span>

<span data-ttu-id="0e178-143">Tijdens de evaluatie kunt u elke regel afzonderlijk configureren of bepaalde bestanden en processen uitsluiten van de evaluatie door de functie.</span><span class="sxs-lookup"><span data-stu-id="0e178-143">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="0e178-144">Zie [Attack Surface Reduction Rules aanpassen](customize-attack-surface-reduction.md) voor informatie over het configureren van de functie met beheerhulpmiddelen, waaronder Groepsbeleid en MDM CSP-beleid.</span><span class="sxs-lookup"><span data-stu-id="0e178-144">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e178-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0e178-145">See also</span></span>

- [<span data-ttu-id="0e178-146">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="0e178-146">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="0e178-147">Auditmodus gebruiken om Windows Defender te evalueren</span><span class="sxs-lookup"><span data-stu-id="0e178-147">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
- [<span data-ttu-id="0e178-148">Veelgestelde vragen over het verminderen van kwetsbaarheid voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="0e178-148">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
