---
title: Herstelacties na geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955589"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="da700-104">Herstelacties na geautomatiseerde onderzoeken in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="da700-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="da700-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="da700-105">**Applies to:**</span></span>
- <span data-ttu-id="da700-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="da700-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="da700-107">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="da700-107">Remediation actions</span></span>

<span data-ttu-id="da700-108">Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="da700-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="da700-109">Sommige soorten herstelacties worden uitgevoerd op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="da700-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="da700-110">Andere herstelacties worden uitgevoerd op e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="da700-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="da700-111">Geautomatiseerde onderzoeken worden voltooid nadat herstelacties zijn uitgevoerd, goedgekeurd of afgewezen.</span><span class="sxs-lookup"><span data-stu-id="da700-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="da700-112">In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft-bedreigingsbeveiliging:</span><span class="sxs-lookup"><span data-stu-id="da700-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="da700-113">Apparaatherstelacties (eindpunt)</span><span class="sxs-lookup"><span data-stu-id="da700-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="da700-114">Acties voor e-mailherstel</span><span class="sxs-lookup"><span data-stu-id="da700-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="da700-115">Quarantainebestand</span><span class="sxs-lookup"><span data-stu-id="da700-115">Quarantine file</span></span><br/><span data-ttu-id="da700-116">Registersleutel verwijderen</span><span class="sxs-lookup"><span data-stu-id="da700-116">Remove registry key</span></span><br/><span data-ttu-id="da700-117">Kill proces</span><span class="sxs-lookup"><span data-stu-id="da700-117">Kill process</span></span> <br/><span data-ttu-id="da700-118">Service stoppen</span><span class="sxs-lookup"><span data-stu-id="da700-118">Stop service</span></span> <br/><span data-ttu-id="da700-119">Stuurprogramma uitschakelen</span><span class="sxs-lookup"><span data-stu-id="da700-119">Disable driver</span></span> <br/><span data-ttu-id="da700-120">Geplande taak verwijderen</span><span class="sxs-lookup"><span data-stu-id="da700-120">Remove scheduled task</span></span>      |<span data-ttu-id="da700-121">E-mailberichten of clusters verwijderen van soft</span><span class="sxs-lookup"><span data-stu-id="da700-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="da700-122">URL blokkeren (kliktijd)</span><span class="sxs-lookup"><span data-stu-id="da700-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="da700-123">Extern doorsturen van e-mail uitschakelen</span><span class="sxs-lookup"><span data-stu-id="da700-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="da700-124">Herstelacties, ongeacht of ze in behandeling zijn of al voltooid zijn, kunnen worden weergegeven in het [Onderhoudscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="da700-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="da700-125">Herstelacties volgen geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="da700-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="da700-126">Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel bereikt voor elk bewijsstuk betrokken, en saneringacties worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="da700-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="da700-127">In sommige gevallen worden herstelacties automatisch uitgevoerd; in andere gevallen wachten saneringsacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="da700-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="da700-128">De volgende tabel bevat mogelijke uitspraken en uitkomsten:</span><span class="sxs-lookup"><span data-stu-id="da700-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="da700-129">Oordeel</span><span class="sxs-lookup"><span data-stu-id="da700-129">Verdict</span></span>    |<span data-ttu-id="da700-130">Gebied</span><span class="sxs-lookup"><span data-stu-id="da700-130">Area</span></span>    |<span data-ttu-id="da700-131">Resultaten</span><span class="sxs-lookup"><span data-stu-id="da700-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="da700-132">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="da700-132">Malicious</span></span>    |<span data-ttu-id="da700-133">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="da700-133">Devices (endpoints)</span></span>    |<span data-ttu-id="da700-134">Herstelacties worden automatisch uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="da700-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="da700-135">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="da700-135">Malicious</span></span>    |<span data-ttu-id="da700-136">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="da700-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="da700-137">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="da700-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="da700-138">Verdachte</span><span class="sxs-lookup"><span data-stu-id="da700-138">Suspicious</span></span>    |<span data-ttu-id="da700-139">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="da700-139">Devices or email content</span></span> |<span data-ttu-id="da700-140">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="da700-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="da700-141">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="da700-141">No threats found</span></span>    |<span data-ttu-id="da700-142">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="da700-142">Devices or email content</span></span>    |<span data-ttu-id="da700-143">Er zijn geen herstelacties nodig</span><span class="sxs-lookup"><span data-stu-id="da700-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="da700-144">Een actie in behandeling controleren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="da700-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="da700-145">Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten!</span><span class="sxs-lookup"><span data-stu-id="da700-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="da700-146">[Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="da700-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="da700-147">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="da700-147">Next steps</span></span>

- [<span data-ttu-id="da700-148">Acties goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="da700-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="da700-149">Meer informatie over het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="da700-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
