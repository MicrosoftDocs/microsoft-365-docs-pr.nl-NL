---
title: Herstelacties na geautomatiseerd onderzoek in Microsoft Threat Protection
description: Bekijk een overzicht van de acties voor herstel na de geautomatiseerde tests in Microsoft Threat Protection
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstel
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5106ef34f11cb43d74fa993fcdb820d6a5dce86f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429469"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="8627a-104">Herstelacties na geautomatiseerd onderzoek in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8627a-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8627a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8627a-105">**Applies to:**</span></span>
- <span data-ttu-id="8627a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8627a-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="8627a-107">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="8627a-107">Remediation actions</span></span>

<span data-ttu-id="8627a-108">Bij een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties herkend voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="8627a-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="8627a-109">Sommige soorten herstelbewerkingen worden uitgevoerd op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="8627a-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="8627a-110">Voor e-mail inhoud worden andere herstelacties gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8627a-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="8627a-111">Geautomatiseerd onderzoek na voltooiing van herstelacties worden uitgevoerd, goedgekeurd of afgekeurd.</span><span class="sxs-lookup"><span data-stu-id="8627a-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="8627a-112">De volgende tabel bevat een overzicht van herstelacties die momenteel worden ondersteund in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="8627a-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="8627a-113">Acties voor herstel van apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="8627a-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="8627a-114">Acties voor het herstel van e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="8627a-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="8627a-115">-Onderzoek pakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="8627a-115">- Collect investigation package</span></span> <br/><span data-ttu-id="8627a-116">-Isoleer apparaat (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="8627a-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="8627a-117">-Verwijderen-computer</span><span class="sxs-lookup"><span data-stu-id="8627a-117">- Offboard machine</span></span> <br/><span data-ttu-id="8627a-118">Uitvoering van uitvoering van programmacode</span><span class="sxs-lookup"><span data-stu-id="8627a-118">- Release code execution</span></span> <br/><span data-ttu-id="8627a-119">-Na quarantaine publicatie</span><span class="sxs-lookup"><span data-stu-id="8627a-119">- Release from quarantine</span></span> <br/><span data-ttu-id="8627a-120">-Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="8627a-120">- Request sample</span></span> <br/><span data-ttu-id="8627a-121">-Uitvoering van code beperken (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="8627a-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="8627a-122">-Virusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="8627a-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="8627a-123">-Stop en Quarantine</span><span class="sxs-lookup"><span data-stu-id="8627a-123">- Stop and quarantine</span></span>      |<span data-ttu-id="8627a-124">-Blok URL (time-of-klik)</span><span class="sxs-lookup"><span data-stu-id="8627a-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="8627a-125">-Tijdelijke e-mail-en cluster berichten verwijderen</span><span class="sxs-lookup"><span data-stu-id="8627a-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="8627a-126">-E-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="8627a-126">- Quarantine email</span></span><br/><span data-ttu-id="8627a-127">-Een e-mailbijlage in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="8627a-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="8627a-128">-Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8627a-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="8627a-129">Herstelacties, ongeacht of ze goedkeuring of al zijn voltooid, kunnen worden weergegeven in het [Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="8627a-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="8627a-130">Voor herstelacties volgen geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="8627a-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="8627a-131">Wanneer een geautomatiseerd onderzoek wordt voltooid, wordt een verdict voor elk bewijs van het bewijs bereikt.</span><span class="sxs-lookup"><span data-stu-id="8627a-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="8627a-132">Afhankelijk van het verdict worden herstelacties aangegeven.</span><span class="sxs-lookup"><span data-stu-id="8627a-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="8627a-133">In sommige gevallen worden herstelacties automatisch uitgevoerd. in andere gevallen zijn herstelacties in afwachting van goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="8627a-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="8627a-134">Het is alles afhankelijk van de manier waarop [automatisch onderzoek en beantwoorden zijn geconfigureerd](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="8627a-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="8627a-135">De volgende tabel bevat mogelijke Verdicts en resultaten:</span><span class="sxs-lookup"><span data-stu-id="8627a-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="8627a-136">Verdict</span><span class="sxs-lookup"><span data-stu-id="8627a-136">Verdict</span></span>    |<span data-ttu-id="8627a-137">Ziet</span><span class="sxs-lookup"><span data-stu-id="8627a-137">Area</span></span>    |<span data-ttu-id="8627a-138">Resultaten</span><span class="sxs-lookup"><span data-stu-id="8627a-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="8627a-139">Schadelijke</span><span class="sxs-lookup"><span data-stu-id="8627a-139">Malicious</span></span>    |<span data-ttu-id="8627a-140">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="8627a-140">Devices (endpoints)</span></span>    |<span data-ttu-id="8627a-141">Herstel stappen worden automatisch uitgevoerd (als u ervan uitgaat dat de [Apparaatgroepen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) van uw organisatie **automatisch**worden ingesteld op volledig herstelde bedreigingen)</span><span class="sxs-lookup"><span data-stu-id="8627a-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="8627a-142">Schadelijke</span><span class="sxs-lookup"><span data-stu-id="8627a-142">Malicious</span></span>    |<span data-ttu-id="8627a-143">E-mail inhoud (Url's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="8627a-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="8627a-144">Aanbevolen herstelacties wachten op goedkeuring</span><span class="sxs-lookup"><span data-stu-id="8627a-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8627a-145">Melden</span><span class="sxs-lookup"><span data-stu-id="8627a-145">Suspicious</span></span>    |<span data-ttu-id="8627a-146">Apparaten of e-mail inhoud</span><span class="sxs-lookup"><span data-stu-id="8627a-146">Devices or email content</span></span> |<span data-ttu-id="8627a-147">Aanbevolen herstelacties wachten op goedkeuring</span><span class="sxs-lookup"><span data-stu-id="8627a-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8627a-148">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="8627a-148">No threats found</span></span>    |<span data-ttu-id="8627a-149">Apparaten of e-mail inhoud</span><span class="sxs-lookup"><span data-stu-id="8627a-149">Devices or email content</span></span>    |<span data-ttu-id="8627a-150">Er zijn geen herstelacties nodig</span><span class="sxs-lookup"><span data-stu-id="8627a-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8627a-151">Of herstelacties automatisch of alleen na de goedkeuring worden uitgevoerd, hangt af van bepaalde instellingen, zoals het beleid van de groep apparaat van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8627a-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="8627a-152">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8627a-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="8627a-153">Geautomatiseerd onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="8627a-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="8627a-154">Hoe bedreigingen op apparaten worden hersteld</span><span class="sxs-lookup"><span data-stu-id="8627a-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="8627a-155">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8627a-155">Next steps</span></span>

- [<span data-ttu-id="8627a-156">Naar het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="8627a-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="8627a-157">Acties in behandeling goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="8627a-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="8627a-158">In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="8627a-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
