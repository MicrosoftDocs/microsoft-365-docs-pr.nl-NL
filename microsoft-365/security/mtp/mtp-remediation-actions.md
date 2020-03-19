---
title: Herstelacties naar aanleiding van geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Krijg een overzicht van herstelacties die geautomatiseerde onderzoeken volgen in Microsoft Threat Protection
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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "42811370"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="a3ddc-104">Herstelacties naar aanleiding van geautomatiseerde onderzoeken in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a3ddc-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="a3ddc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3ddc-105">**Applies to:**</span></span>
- <span data-ttu-id="a3ddc-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a3ddc-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="a3ddc-107">Saneringsacties</span><span class="sxs-lookup"><span data-stu-id="a3ddc-107">Remediation actions</span></span>

<span data-ttu-id="a3ddc-108">Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="a3ddc-109">Sommige soorten van sanering acties worden genomen op apparaten, ook wel aangeduid als eindpunten.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="a3ddc-110">Andere herstelacties worden uitgevoerd op e-mailinhoud.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="a3ddc-111">Geautomatiseerde onderzoeken worden voltooid nadat herstelacties zijn genomen, goedgekeurd of afgewezen.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="a3ddc-112">In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="a3ddc-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="a3ddc-113">Herstelacties voor apparaat (eindpunt)</span><span class="sxs-lookup"><span data-stu-id="a3ddc-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="a3ddc-114">Acties voor e-mailherstel</span><span class="sxs-lookup"><span data-stu-id="a3ddc-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="a3ddc-115">Quarantainebestand</span><span class="sxs-lookup"><span data-stu-id="a3ddc-115">Quarantine file</span></span><br/><span data-ttu-id="a3ddc-116">Registersleutel verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-116">Remove registry key</span></span><br/><span data-ttu-id="a3ddc-117">Dodenproces</span><span class="sxs-lookup"><span data-stu-id="a3ddc-117">Kill process</span></span> <br/><span data-ttu-id="a3ddc-118">Service stoppen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-118">Stop service</span></span> <br/><span data-ttu-id="a3ddc-119">Stuurprogramma uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-119">Disable driver</span></span> <br/><span data-ttu-id="a3ddc-120">Geplande taak verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-120">Remove scheduled task</span></span>      |<span data-ttu-id="a3ddc-121">E-mailberichten of clusters voor soft delete</span><span class="sxs-lookup"><span data-stu-id="a3ddc-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="a3ddc-122">URL blokkeren (tijd van klikken)</span><span class="sxs-lookup"><span data-stu-id="a3ddc-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="a3ddc-123">Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="a3ddc-124">Herstelacties, of ze nu in behandeling zijn met goedkeuring of al voltooid zijn, kunnen worden weergegeven in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)</span><span class="sxs-lookup"><span data-stu-id="a3ddc-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="a3ddc-125">Vonnissen en resultaten na geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a3ddc-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="a3ddc-126">Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel bereikt voor elk bewijsstuk dat betrokken is, en worden saneringsacties geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="a3ddc-127">In sommige gevallen worden saneringsacties automatisch uitgevoerd; in andere gevallen wachten saneringsacties op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="a3ddc-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="a3ddc-128">In de volgende tabel worden mogelijke vonnissen en resultaten opgesomd:</span><span class="sxs-lookup"><span data-stu-id="a3ddc-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="a3ddc-129">Oordeel</span><span class="sxs-lookup"><span data-stu-id="a3ddc-129">Verdict</span></span>    |<span data-ttu-id="a3ddc-130">Gebied</span><span class="sxs-lookup"><span data-stu-id="a3ddc-130">Area</span></span>   |<span data-ttu-id="a3ddc-131">Resultaten</span><span class="sxs-lookup"><span data-stu-id="a3ddc-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="a3ddc-132">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="a3ddc-132">Malicious</span></span>  |<span data-ttu-id="a3ddc-133">Apparaten (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="a3ddc-133">Devices (endpoints)</span></span>    |<span data-ttu-id="a3ddc-134">Herstelacties worden automatisch uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a3ddc-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="a3ddc-135">Kwaadaardige</span><span class="sxs-lookup"><span data-stu-id="a3ddc-135">Malicious</span></span>  |<span data-ttu-id="a3ddc-136">E-mailinhoud (URL's of bijlagen)</span><span class="sxs-lookup"><span data-stu-id="a3ddc-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="a3ddc-137">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="a3ddc-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="a3ddc-138">Verdachte</span><span class="sxs-lookup"><span data-stu-id="a3ddc-138">Suspicious</span></span> |<span data-ttu-id="a3ddc-139">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="a3ddc-139">Devices or email content</span></span> |<span data-ttu-id="a3ddc-140">Aanbevolen herstelacties zijn in afwachting van goedkeuring</span><span class="sxs-lookup"><span data-stu-id="a3ddc-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="a3ddc-141">Schoon</span><span class="sxs-lookup"><span data-stu-id="a3ddc-141">Clean</span></span>  |<span data-ttu-id="a3ddc-142">Apparaten of e-mailinhoud</span><span class="sxs-lookup"><span data-stu-id="a3ddc-142">Devices or email content</span></span>   |<span data-ttu-id="a3ddc-143">Er zijn geen saneringsacties nodig</span><span class="sxs-lookup"><span data-stu-id="a3ddc-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="a3ddc-144">Een lopende actie in het actiecentrum bekijken</span><span class="sxs-lookup"><span data-stu-id="a3ddc-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="a3ddc-145">Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerd onderzoek en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten!</span><span class="sxs-lookup"><span data-stu-id="a3ddc-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="a3ddc-146">[Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="a3ddc-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a3ddc-147">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-147">Next steps</span></span>

- [<span data-ttu-id="a3ddc-148">Acties goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="a3ddc-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="a3ddc-149">Meer informatie over het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="a3ddc-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
