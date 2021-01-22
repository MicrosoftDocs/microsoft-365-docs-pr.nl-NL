---
title: Herstelacties in Microsoft 365 Defender
description: Een overzicht van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932848"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="b1c19-104">Herstelacties in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1c19-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1c19-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b1c19-105">**Applies to:**</span></span>
- <span data-ttu-id="b1c19-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1c19-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="b1c19-107">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="b1c19-107">Remediation actions</span></span>

<span data-ttu-id="b1c19-108">Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="b1c19-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="b1c19-109">Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="b1c19-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="b1c19-110">Andere herstelacties worden ondernomen op e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="b1c19-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="b1c19-111">Automatische onderzoeken worden voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="b1c19-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c19-112">Of herstelacties automatisch of alleen bij goedkeuring worden ondernomen, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b1c19-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="b1c19-113">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="b1c19-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="b1c19-114">Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1c19-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="b1c19-115">Hoe bedreigingen worden verteerd op apparaten</span><span class="sxs-lookup"><span data-stu-id="b1c19-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="b1c19-116">Bedreigingen en herstelacties voor e-mail & samenwerkingsinhoud</span><span class="sxs-lookup"><span data-stu-id="b1c19-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="b1c19-117">De volgende tabel bevat een overzicht van herstelacties die momenteel worden ondersteund in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="b1c19-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="b1c19-118">Herstelacties voor apparaten (eindpunt)</span><span class="sxs-lookup"><span data-stu-id="b1c19-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="b1c19-119">Herstelacties voor e-mail</span><span class="sxs-lookup"><span data-stu-id="b1c19-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="b1c19-120">- Pakket voor onderzoek verzamelen</span><span class="sxs-lookup"><span data-stu-id="b1c19-120">- Collect investigation package</span></span> <br/><span data-ttu-id="b1c19-121">- Isoleert apparaat (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="b1c19-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="b1c19-122">- Offboard machine</span><span class="sxs-lookup"><span data-stu-id="b1c19-122">- Offboard machine</span></span> <br/><span data-ttu-id="b1c19-123">- Uitvoering van releasecode</span><span class="sxs-lookup"><span data-stu-id="b1c19-123">- Release code execution</span></span> <br/><span data-ttu-id="b1c19-124">- In quarantaine worden vrijgegeven</span><span class="sxs-lookup"><span data-stu-id="b1c19-124">- Release from quarantine</span></span> <br/><span data-ttu-id="b1c19-125">- Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="b1c19-125">- Request sample</span></span> <br/><span data-ttu-id="b1c19-126">- De uitvoering van code beperken (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="b1c19-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="b1c19-127">- Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b1c19-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="b1c19-128">- Stoppen en quarantaine</span><span class="sxs-lookup"><span data-stu-id="b1c19-128">- Stop and quarantine</span></span>      |<span data-ttu-id="b1c19-129">- URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="b1c19-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="b1c19-130">- E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="b1c19-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="b1c19-131">- E-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="b1c19-131">- Quarantine email</span></span><br/><span data-ttu-id="b1c19-132">- Een e-mailbijlage in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="b1c19-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="b1c19-133">- Externe doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b1c19-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="b1c19-134">Herstelacties, in behandeling of al voltooid, kunnen worden bekeken in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)</span><span class="sxs-lookup"><span data-stu-id="b1c19-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="b1c19-135">Herstelacties die geautomatiseerde onderzoeken volgen</span><span class="sxs-lookup"><span data-stu-id="b1c19-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="b1c19-136">Wanneer een geautomatiseerd onderzoek is voltooid, wordt er een overeenkomst bereikt voor elk stukje bewijs dat daarbij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="b1c19-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="b1c19-137">Afhankelijk van de situatie worden herstelacties vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="b1c19-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="b1c19-138">In sommige gevallen worden er automatisch herstelacties ondernomen. In andere gevallen wachten herstelacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="b1c19-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="b1c19-139">Het hangt allemaal af van hoe [automatisch onderzoek en antwoorden zijn geconfigureerd.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="b1c19-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="b1c19-140">In de volgende tabel worden mogelijke voor- en resultaatresultaten vermeld:</span><span class="sxs-lookup"><span data-stu-id="b1c19-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="b1c19-141">16:</span><span class="sxs-lookup"><span data-stu-id="b1c19-141">Verdict</span></span>    | <span data-ttu-id="b1c19-142">Gebied</span><span class="sxs-lookup"><span data-stu-id="b1c19-142">Area</span></span>    | <span data-ttu-id="b1c19-143">Resultaten</span><span class="sxs-lookup"><span data-stu-id="b1c19-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="b1c19-144">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="b1c19-144">Malicious</span></span>    | <span data-ttu-id="b1c19-145">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="b1c19-145">Devices (endpoints)</span></span>    | <span data-ttu-id="b1c19-146">Herstelacties worden automatisch ondernomen (ervan uitgaande [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig- automatisch herstellen van **bedreigingen)**</span><span class="sxs-lookup"><span data-stu-id="b1c19-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="b1c19-147">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="b1c19-147">Malicious</span></span>    | <span data-ttu-id="b1c19-148">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="b1c19-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="b1c19-149">Aanbevolen herstelacties wachten op goedkeuring</span><span class="sxs-lookup"><span data-stu-id="b1c19-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="b1c19-150">Verdacht</span><span class="sxs-lookup"><span data-stu-id="b1c19-150">Suspicious</span></span>    | <span data-ttu-id="b1c19-151">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="b1c19-151">Devices or email content</span></span> | <span data-ttu-id="b1c19-152">Aanbevolen herstelacties wachten op goedkeuring</span><span class="sxs-lookup"><span data-stu-id="b1c19-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="b1c19-153">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="b1c19-153">No threats found</span></span>    | <span data-ttu-id="b1c19-154">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="b1c19-154">Devices or email content</span></span>    | <span data-ttu-id="b1c19-155">Er zijn geen herstelacties nodig</span><span class="sxs-lookup"><span data-stu-id="b1c19-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="b1c19-156">Herstelacties die handmatig worden ondernomen</span><span class="sxs-lookup"><span data-stu-id="b1c19-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="b1c19-157">Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan het team voor beveiligingsbewerkingen bepaalde herstelacties handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b1c19-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="b1c19-158">Dit zijn onder andere de volgende acties:</span><span class="sxs-lookup"><span data-stu-id="b1c19-158">These include the following actions:</span></span>

- <span data-ttu-id="b1c19-159">Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine.</span><span class="sxs-lookup"><span data-stu-id="b1c19-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="b1c19-160">Handmatige e-mailactie, zoals het verwijderen van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b1c19-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="b1c19-161">[Geavanceerde zoekactie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) op apparaten of e-mail.</span><span class="sxs-lookup"><span data-stu-id="b1c19-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="b1c19-162">[Verkenner-actie](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, het verwijderen van e-mail of het moeilijk verwijderen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="b1c19-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="b1c19-163">Handmatige [live antwoordactie,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals een bestand verwijderen, een proces stoppen en een geplande taak verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b1c19-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="b1c19-164">Live-actie met [Microsoft Defender voor eindpunt-API's,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)zoals het isoleren van een apparaat, het uitvoeren van een antivirusscan en het verkrijgen van informatie over een bestand.</span><span class="sxs-lookup"><span data-stu-id="b1c19-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="b1c19-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b1c19-165">Next steps</span></span>

- [<span data-ttu-id="b1c19-166">Naar het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="b1c19-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="b1c19-167">Acties in behandeling goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="b1c19-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="b1c19-168">Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken</span><span class="sxs-lookup"><span data-stu-id="b1c19-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
