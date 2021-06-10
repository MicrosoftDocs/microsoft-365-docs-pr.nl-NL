---
title: Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren
description: Meer informatie over de geautomatiseerde onderzoeksstroom in Microsoft Defender voor Eindpunt.
keywords: geautomatiseerd, onderzoek, detectie, Microsoft Defender voor Eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: e52471e1b3e9ee3a410de493b536f9d360d60624
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844440"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="a93aa-104">Overzicht van geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a93aa-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a93aa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a93aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="a93aa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a93aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a93aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a93aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="a93aa-108">Wilt u zien hoe het werkt?</span><span class="sxs-lookup"><span data-stu-id="a93aa-108">Want to see how it works?</span></span> <span data-ttu-id="a93aa-109">Bekijk de volgende video:</span><span class="sxs-lookup"><span data-stu-id="a93aa-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="a93aa-110">De technologie in geautomatiseerd onderzoek maakt gebruik van verschillende inspectiealgoritmen en is gebaseerd op processen die worden gebruikt door beveiligingsanalisten.</span><span class="sxs-lookup"><span data-stu-id="a93aa-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="a93aa-111">Air-mogelijkheden zijn ontworpen om waarschuwingen te onderzoeken en onmiddellijk actie te ondernemen om inbreuken op te lossen.</span><span class="sxs-lookup"><span data-stu-id="a93aa-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="a93aa-112">Air-mogelijkheden verminderen het alarmvolume aanzienlijk, zodat beveiligingsbewerkingen zich kunnen richten op geavanceerdere bedreigingen en andere hoogwaardige initiatieven.</span><span class="sxs-lookup"><span data-stu-id="a93aa-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="a93aa-113">Alle herstelacties, in behandeling of voltooid, worden bijgeplaatst in het [Actiecentrum.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="a93aa-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="a93aa-114">In het Actiecentrum worden acties in behandeling goedgekeurd (of geweigerd) en kunnen voltooide acties zo nodig ongedaan worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a93aa-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="a93aa-115">Dit artikel bevat een overzicht van AIR en bevat koppelingen naar de volgende stappen en aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="a93aa-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="a93aa-116">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a93aa-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="a93aa-117">[Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="a93aa-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="a93aa-118">Hoe het geautomatiseerde onderzoek begint</span><span class="sxs-lookup"><span data-stu-id="a93aa-118">How the automated investigation starts</span></span>

<span data-ttu-id="a93aa-119">Een geautomatiseerd onderzoek kan beginnen wanneer een waarschuwing wordt geactiveerd of wanneer een beveiligingsoperator het onderzoek start.</span><span class="sxs-lookup"><span data-stu-id="a93aa-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="a93aa-120">Situatie</span><span class="sxs-lookup"><span data-stu-id="a93aa-120">Situation</span></span>  |<span data-ttu-id="a93aa-121">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="a93aa-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="a93aa-122">Er wordt een waarschuwing geactiveerd</span><span class="sxs-lookup"><span data-stu-id="a93aa-122">An alert is triggered</span></span>     | <span data-ttu-id="a93aa-123">In het algemeen wordt een geautomatiseerd onderzoek gestart wanneer een [waarschuwing](review-alerts.md) wordt geactiveerd en er een [incident](view-incidents-queue.md) wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a93aa-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="a93aa-124">Stel dat een schadelijk bestand zich op een apparaat bevindt.</span><span class="sxs-lookup"><span data-stu-id="a93aa-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="a93aa-125">Wanneer dat bestand wordt gedetecteerd, wordt er een waarschuwing geactiveerd en wordt een incident gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a93aa-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="a93aa-126">Er wordt een geautomatiseerd onderzoek gestart op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a93aa-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="a93aa-127">Aangezien andere waarschuwingen worden gegenereerd vanwege hetzelfde bestand op andere apparaten, worden ze toegevoegd aan het bijbehorende incident en aan het geautomatiseerde onderzoek.</span><span class="sxs-lookup"><span data-stu-id="a93aa-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="a93aa-128">Er wordt handmatig een onderzoek gestart</span><span class="sxs-lookup"><span data-stu-id="a93aa-128">An investigation is started manually</span></span>     | <span data-ttu-id="a93aa-129">Een geautomatiseerd onderzoek kan handmatig worden gestart door uw beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="a93aa-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="a93aa-130">Stel dat een beveiligingsoperator een lijst met apparaten bekijkt en merkt dat een apparaat een hoog risiconiveau heeft.</span><span class="sxs-lookup"><span data-stu-id="a93aa-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="a93aa-131">De beveiligingsoperator kan het apparaat in de lijst selecteren om de flyout te openen en vervolgens Automatisch onderzoek **starten te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="a93aa-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="a93aa-132">Hoe het bereik van een geautomatiseerd onderzoek wordt uitgebreid</span><span class="sxs-lookup"><span data-stu-id="a93aa-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="a93aa-133">Terwijl een onderzoek wordt uitgevoerd, worden alle andere waarschuwingen die van het apparaat worden gegenereerd, toegevoegd aan een lopend geautomatiseerd onderzoek totdat dat onderzoek is voltooid.</span><span class="sxs-lookup"><span data-stu-id="a93aa-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="a93aa-134">Bovendien worden deze apparaten toegevoegd aan het onderzoek als dezelfde bedreiging op andere apparaten wordt gezien.</span><span class="sxs-lookup"><span data-stu-id="a93aa-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="a93aa-135">Als een belastende entiteit wordt gezien op een ander apparaat, wordt het geautomatiseerde onderzoeksproces uitgebreid met dat apparaat en wordt een algemene beveiligingss playbook gestart op dat apparaat.</span><span class="sxs-lookup"><span data-stu-id="a93aa-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="a93aa-136">Als er tijdens dit uitbreidingsproces 10 of meer apparaten uit dezelfde entiteit worden gevonden, moet deze uitbreidingsactie worden goedgekeurd en is deze zichtbaar op het tabblad Acties in **behandeling.**</span><span class="sxs-lookup"><span data-stu-id="a93aa-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="a93aa-137">Hoe bedreigingen worden gesaneerd</span><span class="sxs-lookup"><span data-stu-id="a93aa-137">How threats are remediated</span></span>

<span data-ttu-id="a93aa-138">Wanneer waarschuwingen worden geactiveerd en een geautomatiseerd onderzoek wordt uitgevoerd, wordt een vonnis gegenereerd voor elk bewijs dat wordt onderzocht.</span><span class="sxs-lookup"><span data-stu-id="a93aa-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="a93aa-139">Vonnissen kunnen worden</span><span class="sxs-lookup"><span data-stu-id="a93aa-139">Verdicts can be</span></span> 
- <span data-ttu-id="a93aa-140">*Schadelijk*;</span><span class="sxs-lookup"><span data-stu-id="a93aa-140">*Malicious*;</span></span>
- <span data-ttu-id="a93aa-141">*Verdacht*; of</span><span class="sxs-lookup"><span data-stu-id="a93aa-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="a93aa-142">*Er zijn geen bedreigingen gevonden.*</span><span class="sxs-lookup"><span data-stu-id="a93aa-142">*No threats found*.</span></span> 

<span data-ttu-id="a93aa-143">Wanneer vonnissen worden bereikt, kunnen geautomatiseerde onderzoeken leiden tot een of meer herstelacties.</span><span class="sxs-lookup"><span data-stu-id="a93aa-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="a93aa-144">Voorbeelden van herstelacties zijn het verzenden van een bestand naar quarantaine, het stoppen van een service, het verwijderen van een geplande taak en meer.</span><span class="sxs-lookup"><span data-stu-id="a93aa-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="a93aa-145">Zie Herstelacties [voor meer informatie.](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="a93aa-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="a93aa-146">Afhankelijk van het automatiseringsniveau dat is ingesteld voor uw organisatie en andere beveiligingsinstellingen, kunnen herstelacties automatisch [of](automation-levels.md) alleen plaatsvinden na goedkeuring door uw beveiligingsbewerkingsteam.</span><span class="sxs-lookup"><span data-stu-id="a93aa-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="a93aa-147">Extra beveiligingsinstellingen die van invloed kunnen zijn op automatische herstelmaatregelen, zijn onder andere bescherming tegen mogelijk [ongewenste toepassingen](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span><span class="sxs-lookup"><span data-stu-id="a93aa-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="a93aa-148">Alle herstelacties, in behandeling of voltooid, worden bijgeplaatst in het [Actiecentrum.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="a93aa-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="a93aa-149">Zo nodig kan uw beveiligingsbewerkingsteam een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="a93aa-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="a93aa-150">Zie Herstelacties controleren en goedkeuren na een geautomatiseerd onderzoek voor meer [informatie.](/microsoft-365/security/defender-endpoint/manage-auto-investigation)</span><span class="sxs-lookup"><span data-stu-id="a93aa-150">To learn more, see [Review and approve remediation actions following an automated investigation](/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="a93aa-151">Bekijk de nieuwe, geïntegreerde onderzoekspagina in het Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="a93aa-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="a93aa-152">Zie [(NIEUW!) voor meer informatie. Geïntegreerde onderzoekspagina](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span><span class="sxs-lookup"><span data-stu-id="a93aa-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="a93aa-153">Vereisten voor AIR</span><span class="sxs-lookup"><span data-stu-id="a93aa-153">Requirements for AIR</span></span>

<span data-ttu-id="a93aa-154">Uw organisatie moet Defender voor Eindpunt hebben (zie [Minimumvereisten voor Microsoft Defender voor Eindpunt](minimum-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="a93aa-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="a93aa-155">Op dit moment ondersteunt AIR alleen de volgende besturingssysteemversies:</span><span class="sxs-lookup"><span data-stu-id="a93aa-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="a93aa-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a93aa-156">Windows Server 2019</span></span>
- <span data-ttu-id="a93aa-157">Windows 10 versie 1709 (os build 16299.1085 met [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) of hoger</span><span class="sxs-lookup"><span data-stu-id="a93aa-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="a93aa-158">Windows 10 versie 1803 (os build 17134.704 met [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)of hoger</span><span class="sxs-lookup"><span data-stu-id="a93aa-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="a93aa-159">Windows 10, versie [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) of hoger</span><span class="sxs-lookup"><span data-stu-id="a93aa-159">Windows 10, version [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="a93aa-160">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a93aa-160">Next steps</span></span>

- [<span data-ttu-id="a93aa-161">Meer informatie over automatiseringsniveaus</span><span class="sxs-lookup"><span data-stu-id="a93aa-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="a93aa-162">Zie de interactieve handleiding: Bedreigingen onderzoeken en corrigeren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a93aa-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="a93aa-163">Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a93aa-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="a93aa-164">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a93aa-164">See also</span></span>

- [<span data-ttu-id="a93aa-165">PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="a93aa-165">PUA protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="a93aa-166">Geautomatiseerd onderzoek en antwoord in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a93aa-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="a93aa-167">Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a93aa-167">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-autoir)
