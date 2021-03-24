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
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fa73756aa9f350793c00a7e4a960c215627b712f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058618"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="c2788-104">Herstelacties in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2788-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2788-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c2788-105">**Applies to:**</span></span>
- <span data-ttu-id="c2788-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2788-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="c2788-107">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="c2788-107">Remediation actions</span></span>

<span data-ttu-id="c2788-108">Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="c2788-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="c2788-109">Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="c2788-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="c2788-110">Andere herstelacties worden ondernomen voor e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="c2788-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="c2788-111">Geautomatiseerde onderzoeken die zijn voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="c2788-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2788-112">Of herstelacties automatisch of alleen worden ondernomen op basis van goedkeuring, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c2788-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="c2788-113">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="c2788-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="c2788-114">Uw geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2788-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="c2788-115">Hoe bedreigingen worden gesaneerd op apparaten</span><span class="sxs-lookup"><span data-stu-id="c2788-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="c2788-116">Bedreigingen en herstelacties op e-mail & samenwerkingsinhoud</span><span class="sxs-lookup"><span data-stu-id="c2788-116">Threats and remediation actions on email & collaboration content</span></span>](../defender-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="c2788-117">In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c2788-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="c2788-118">Herstelacties voor apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="c2788-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="c2788-119">Herstelacties voor e-mail</span><span class="sxs-lookup"><span data-stu-id="c2788-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="c2788-120">- Onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="c2788-120">- Collect investigation package</span></span> <br/><span data-ttu-id="c2788-121">- Apparaat isoleren (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="c2788-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="c2788-122">- Offboard machine</span><span class="sxs-lookup"><span data-stu-id="c2788-122">- Offboard machine</span></span> <br/><span data-ttu-id="c2788-123">- Uitvoering van code vrijgeven</span><span class="sxs-lookup"><span data-stu-id="c2788-123">- Release code execution</span></span> <br/><span data-ttu-id="c2788-124">- Uit quarantaine worden gezet</span><span class="sxs-lookup"><span data-stu-id="c2788-124">- Release from quarantine</span></span> <br/><span data-ttu-id="c2788-125">- Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="c2788-125">- Request sample</span></span> <br/><span data-ttu-id="c2788-126">- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="c2788-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="c2788-127">- Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="c2788-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="c2788-128">- Stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="c2788-128">- Stop and quarantine</span></span>      |<span data-ttu-id="c2788-129">- URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="c2788-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="c2788-130">- E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="c2788-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="c2788-131">- E-mail in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="c2788-131">- Quarantine email</span></span><br/><span data-ttu-id="c2788-132">- Een e-mailbijlage in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="c2788-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="c2788-133">- Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c2788-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="c2788-134">Herstelacties, in behandeling of al voltooid, kunnen worden bekeken in het [Actiecentrum.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="c2788-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="c2788-135">Herstelacties die volgen op geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="c2788-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="c2788-136">Wanneer een geautomatiseerd onderzoek is voltooid, wordt een vonnis bereikt voor elk bewijs dat hierbij betrokken is.</span><span class="sxs-lookup"><span data-stu-id="c2788-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="c2788-137">Afhankelijk van de uitspraak worden herstelacties geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="c2788-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="c2788-138">In sommige gevallen worden herstelacties automatisch genomen. in andere gevallen wachten herstelacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="c2788-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="c2788-139">Het hangt allemaal af van hoe [geautomatiseerd onderzoek en antwoord zijn geconfigureerd.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="c2788-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="c2788-140">De volgende tabel bevat mogelijke vonnissen en resultaten:</span><span class="sxs-lookup"><span data-stu-id="c2788-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="c2788-141">Vonnis</span><span class="sxs-lookup"><span data-stu-id="c2788-141">Verdict</span></span>    | <span data-ttu-id="c2788-142">Gebied</span><span class="sxs-lookup"><span data-stu-id="c2788-142">Area</span></span>    | <span data-ttu-id="c2788-143">Resultaten</span><span class="sxs-lookup"><span data-stu-id="c2788-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="c2788-144">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="c2788-144">Malicious</span></span>    | <span data-ttu-id="c2788-145">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="c2788-145">Devices (endpoints)</span></span>    | <span data-ttu-id="c2788-146">Herstelacties worden automatisch ondernomen (ervan uitgaande [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig - automatisch bedreigingen **corrigeren)**</span><span class="sxs-lookup"><span data-stu-id="c2788-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="c2788-147">Schadelijk</span><span class="sxs-lookup"><span data-stu-id="c2788-147">Malicious</span></span>    | <span data-ttu-id="c2788-148">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="c2788-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="c2788-149">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="c2788-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="c2788-150">Verdacht</span><span class="sxs-lookup"><span data-stu-id="c2788-150">Suspicious</span></span>    | <span data-ttu-id="c2788-151">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="c2788-151">Devices or email content</span></span> | <span data-ttu-id="c2788-152">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="c2788-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="c2788-153">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="c2788-153">No threats found</span></span>    | <span data-ttu-id="c2788-154">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="c2788-154">Devices or email content</span></span>    | <span data-ttu-id="c2788-155">Er zijn geen herstelacties nodig</span><span class="sxs-lookup"><span data-stu-id="c2788-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="c2788-156">Herstelacties die handmatig worden ondernomen</span><span class="sxs-lookup"><span data-stu-id="c2788-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="c2788-157">Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan uw beveiligingsteam bepaalde herstelacties handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="c2788-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="c2788-158">Hieronder volgen de volgende acties:</span><span class="sxs-lookup"><span data-stu-id="c2788-158">These include the following actions:</span></span>

- <span data-ttu-id="c2788-159">Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine.</span><span class="sxs-lookup"><span data-stu-id="c2788-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="c2788-160">Handmatige e-mailactie, zoals het verwijderen van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="c2788-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="c2788-161">[Geavanceerde zoekactie](../defender-endpoint/advanced-hunting-overview.md) op apparaten of e-mail.</span><span class="sxs-lookup"><span data-stu-id="c2788-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="c2788-162">[Explorer-actie](../defender-365-security/threat-explorer.md) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, het verwijderen van e-mail of het moeilijk verwijderen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="c2788-162">[Explorer](../defender-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="c2788-163">Handmatige [livereactieactie,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak.</span><span class="sxs-lookup"><span data-stu-id="c2788-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="c2788-164">Live response action with [Microsoft Defender for Endpoint API's](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span><span class="sxs-lookup"><span data-stu-id="c2788-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c2788-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="c2788-165">Next steps</span></span>

- [<span data-ttu-id="c2788-166">Naar het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="c2788-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="c2788-167">Herstelacties weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="c2788-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="c2788-168">False positives/negatives verwerken in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="c2788-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
