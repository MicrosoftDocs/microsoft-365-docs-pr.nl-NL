---
title: Saneringsacties na geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering
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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502935"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="24bfd-104">Saneringsacties na geautomatiseerde onderzoeken in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="24bfd-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="24bfd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="24bfd-105">**Applies to:**</span></span>
- <span data-ttu-id="24bfd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="24bfd-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="24bfd-107">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="24bfd-107">Remediation actions</span></span>

<span data-ttu-id="24bfd-108">Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="24bfd-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="24bfd-109">Sommige soorten herstelacties worden uitgevoerd op apparaten, ook wel eindpunten genoemd.</span><span class="sxs-lookup"><span data-stu-id="24bfd-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="24bfd-110">Andere herstelacties worden uitgevoerd op e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="24bfd-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="24bfd-111">Geautomatiseerde onderzoeken die worden voltooid nadat herstelmaatregelen zijn uitgevoerd, goedgekeurd of afgewezen.</span><span class="sxs-lookup"><span data-stu-id="24bfd-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="24bfd-112">In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="24bfd-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="24bfd-113">Herstelacties voor apparaten (eindpunt)</span><span class="sxs-lookup"><span data-stu-id="24bfd-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="24bfd-114">Acties voor het herstellen van e-mail</span><span class="sxs-lookup"><span data-stu-id="24bfd-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="24bfd-115">- Verzamel onderzoekspakket</span><span class="sxs-lookup"><span data-stu-id="24bfd-115">- Collect investigation package</span></span> <br/><span data-ttu-id="24bfd-116">- Isoleren apparaat (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="24bfd-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="24bfd-117">- Buitenboordmachine</span><span class="sxs-lookup"><span data-stu-id="24bfd-117">- Offboard machine</span></span> <br/><span data-ttu-id="24bfd-118">- Release code uitvoering</span><span class="sxs-lookup"><span data-stu-id="24bfd-118">- Release code execution</span></span> <br/><span data-ttu-id="24bfd-119">- Loslaten uit quarantaine</span><span class="sxs-lookup"><span data-stu-id="24bfd-119">- Release from quarantine</span></span> <br/><span data-ttu-id="24bfd-120">- Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="24bfd-120">- Request sample</span></span> <br/><span data-ttu-id="24bfd-121">- Code-uitvoering beperken (deze actie kan ongedaan worden gemaakt)</span><span class="sxs-lookup"><span data-stu-id="24bfd-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="24bfd-122">- Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="24bfd-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="24bfd-123">- Stoppen en in quarantaine</span><span class="sxs-lookup"><span data-stu-id="24bfd-123">- Stop and quarantine</span></span>      |<span data-ttu-id="24bfd-124">- URL blokkeren (tijd-van-klik)</span><span class="sxs-lookup"><span data-stu-id="24bfd-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="24bfd-125">- Soft verwijderen van e-mailberichten of clusters</span><span class="sxs-lookup"><span data-stu-id="24bfd-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="24bfd-126">- Quarantaine e-mail</span><span class="sxs-lookup"><span data-stu-id="24bfd-126">- Quarantine email</span></span><br/><span data-ttu-id="24bfd-127">- Een e-mailbijlage in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="24bfd-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="24bfd-128">- Externe e-maildoorschakeling uitschakelen</span><span class="sxs-lookup"><span data-stu-id="24bfd-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="24bfd-129">Herstelacties, of ze nu goedgekeurd zijn of al zijn voltooid, kunnen worden weergegeven in het [Onderhoudscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="24bfd-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="24bfd-130">Saneringsacties volgen op geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="24bfd-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="24bfd-131">Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel geveld voor elk betrokken bewijsstuk en worden saneringsacties geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="24bfd-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="24bfd-132">In sommige gevallen worden herstelmaatregelen automatisch ondernomen; in andere gevallen wachten saneringsacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="24bfd-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="24bfd-133">In de volgende tabel worden mogelijke uitspraken en uitkomsten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="24bfd-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="24bfd-134">Oordeel</span><span class="sxs-lookup"><span data-stu-id="24bfd-134">Verdict</span></span>    |<span data-ttu-id="24bfd-135">Gebied</span><span class="sxs-lookup"><span data-stu-id="24bfd-135">Area</span></span>    |<span data-ttu-id="24bfd-136">Resultaten</span><span class="sxs-lookup"><span data-stu-id="24bfd-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="24bfd-137">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="24bfd-137">Malicious</span></span>    |<span data-ttu-id="24bfd-138">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="24bfd-138">Devices (endpoints)</span></span>    |<span data-ttu-id="24bfd-139">Herstelacties worden automatisch uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="24bfd-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="24bfd-140">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="24bfd-140">Malicious</span></span>    |<span data-ttu-id="24bfd-141">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="24bfd-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="24bfd-142">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="24bfd-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="24bfd-143">Verdachte</span><span class="sxs-lookup"><span data-stu-id="24bfd-143">Suspicious</span></span>    |<span data-ttu-id="24bfd-144">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="24bfd-144">Devices or email content</span></span> |<span data-ttu-id="24bfd-145">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="24bfd-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="24bfd-146">Geen bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="24bfd-146">No threats found</span></span>    |<span data-ttu-id="24bfd-147">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="24bfd-147">Devices or email content</span></span>    |<span data-ttu-id="24bfd-148">Er zijn geen saneringsacties nodig</span><span class="sxs-lookup"><span data-stu-id="24bfd-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="24bfd-149">Een lopende actie in het Actiecentrum bekijken</span><span class="sxs-lookup"><span data-stu-id="24bfd-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="24bfd-150">Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten!</span><span class="sxs-lookup"><span data-stu-id="24bfd-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="24bfd-151">[Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="24bfd-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="24bfd-152">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="24bfd-152">Next steps</span></span>

- [<span data-ttu-id="24bfd-153">Acties goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="24bfd-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="24bfd-154">Meer informatie over het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="24bfd-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
