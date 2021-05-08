---
title: Herstelacties in Microsoft 365 Defender
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 80546d44bc1ba222c736b397a272f9f1f1a01d4a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269466"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="bae9b-104">Herstelacties in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bae9b-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bae9b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bae9b-105">**Applies to:**</span></span>
- <span data-ttu-id="bae9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bae9b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bae9b-107">Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="bae9b-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="bae9b-108">Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="bae9b-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="bae9b-109">Andere herstelacties worden ondernomen voor e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="bae9b-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="bae9b-110">Geautomatiseerde onderzoeken die zijn voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="bae9b-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bae9b-111">Of herstelacties automatisch of alleen worden ondernomen op basis van goedkeuring, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="bae9b-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="bae9b-112">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="bae9b-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="bae9b-113">Uw geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bae9b-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="bae9b-114">Hoe bedreigingen worden gesaneerd op apparaten</span><span class="sxs-lookup"><span data-stu-id="bae9b-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="bae9b-115">Bedreigingen en herstelacties op e-mail & samenwerkingsinhoud</span><span class="sxs-lookup"><span data-stu-id="bae9b-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="bae9b-116">In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bae9b-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="bae9b-117">Herstelacties voor apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="bae9b-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="bae9b-118">Herstelacties voor e-mail</span><span class="sxs-lookup"><span data-stu-id="bae9b-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="bae9b-119">- Onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="bae9b-119">- Collect investigation package</span></span> <br/><span data-ttu-id="bae9b-120">- Apparaat isoleren (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="bae9b-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="bae9b-121">- Offboard machine</span><span class="sxs-lookup"><span data-stu-id="bae9b-121">- Offboard machine</span></span> <br/><span data-ttu-id="bae9b-122">- Uitvoering van code vrijgeven</span><span class="sxs-lookup"><span data-stu-id="bae9b-122">- Release code execution</span></span> <br/><span data-ttu-id="bae9b-123">- Uit quarantaine worden gezet</span><span class="sxs-lookup"><span data-stu-id="bae9b-123">- Release from quarantine</span></span> <br/><span data-ttu-id="bae9b-124">- Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="bae9b-124">- Request sample</span></span> <br/><span data-ttu-id="bae9b-125">- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="bae9b-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="bae9b-126">- Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="bae9b-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="bae9b-127">- Stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="bae9b-127">- Stop and quarantine</span></span>      |<span data-ttu-id="bae9b-128">- URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="bae9b-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="bae9b-129">- E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="bae9b-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="bae9b-130">- E-mail in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="bae9b-130">- Quarantine email</span></span><br/><span data-ttu-id="bae9b-131">- Een e-mailbijlage in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="bae9b-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="bae9b-132">- Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="bae9b-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="bae9b-133">Herstelacties, in behandeling of al voltooid, kunnen worden bekeken in het [Actiecentrum.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="bae9b-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="bae9b-134">Herstelacties die volgen op geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="bae9b-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="bae9b-135">Wanneer een geautomatiseerd onderzoek is voltooid, wordt een vonnis bereikt voor elk bewijs dat hierbij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="bae9b-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="bae9b-136">Afhankelijk van de uitspraak worden herstelacties geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="bae9b-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="bae9b-137">In sommige gevallen worden herstelacties automatisch genomen. in andere gevallen wachten herstelacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="bae9b-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="bae9b-138">Het hangt allemaal af van hoe [geautomatiseerd onderzoek en antwoord zijn geconfigureerd.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="bae9b-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="bae9b-139">De volgende tabel bevat mogelijke vonnissen en resultaten:</span><span class="sxs-lookup"><span data-stu-id="bae9b-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="bae9b-140">Vonnis</span><span class="sxs-lookup"><span data-stu-id="bae9b-140">Verdict</span></span>    | <span data-ttu-id="bae9b-141">Betrokken entiteiten</span><span class="sxs-lookup"><span data-stu-id="bae9b-141">Affected entities</span></span>    | <span data-ttu-id="bae9b-142">Resultaten</span><span class="sxs-lookup"><span data-stu-id="bae9b-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="bae9b-143">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="bae9b-143">Malicious</span></span>    | <span data-ttu-id="bae9b-144">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="bae9b-144">Devices (endpoints)</span></span>    | <span data-ttu-id="bae9b-145">Herstelacties worden automatisch ondernomen (ervan uitgaande [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig - automatisch bedreigingen **corrigeren)**</span><span class="sxs-lookup"><span data-stu-id="bae9b-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="bae9b-146">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="bae9b-146">Malicious</span></span>    | <span data-ttu-id="bae9b-147">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="bae9b-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="bae9b-148">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="bae9b-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="bae9b-149">Verdacht</span><span class="sxs-lookup"><span data-stu-id="bae9b-149">Suspicious</span></span>    | <span data-ttu-id="bae9b-150">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="bae9b-150">Devices or email content</span></span> | <span data-ttu-id="bae9b-151">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="bae9b-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="bae9b-152">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="bae9b-152">No threats found</span></span>    | <span data-ttu-id="bae9b-153">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="bae9b-153">Devices or email content</span></span>    | <span data-ttu-id="bae9b-154">Er zijn geen herstelacties nodig</span><span class="sxs-lookup"><span data-stu-id="bae9b-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="bae9b-155">Herstelacties die handmatig worden ondernomen</span><span class="sxs-lookup"><span data-stu-id="bae9b-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="bae9b-156">Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan uw beveiligingsteam bepaalde herstelacties handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bae9b-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="bae9b-157">Deze omvatten de volgende:</span><span class="sxs-lookup"><span data-stu-id="bae9b-157">These include the following:</span></span>

- <span data-ttu-id="bae9b-158">Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine</span><span class="sxs-lookup"><span data-stu-id="bae9b-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="bae9b-159">Handmatige e-mailactie, zoals het verwijderen van e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="bae9b-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="bae9b-160">[Geavanceerde zoekactie](../defender-endpoint/advanced-hunting-overview.md) op apparaten of e-mail</span><span class="sxs-lookup"><span data-stu-id="bae9b-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="bae9b-161">[Explorer-actie](../office-365-security/threat-explorer.md) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, zacht verwijderen van e-mail of moeilijk verwijderen van e-mail</span><span class="sxs-lookup"><span data-stu-id="bae9b-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="bae9b-162">Handmatige [livereactieactie,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak</span><span class="sxs-lookup"><span data-stu-id="bae9b-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="bae9b-163">Live response action with [Microsoft Defender for Endpoint API's](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running a antivirus scan, and getting information about a file</span><span class="sxs-lookup"><span data-stu-id="bae9b-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="bae9b-164">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="bae9b-164">Next steps</span></span>

- [<span data-ttu-id="bae9b-165">Naar het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="bae9b-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="bae9b-166">Herstelacties weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="bae9b-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="bae9b-167">Fout-positieven of onwaar-negatieven adresseert</span><span class="sxs-lookup"><span data-stu-id="bae9b-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
