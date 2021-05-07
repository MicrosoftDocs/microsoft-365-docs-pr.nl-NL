---
title: Vertrouwelijkheidslabels gebruiken als voorwaarden in DLP-beleid
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: meer informatie over de services en itemtypen waarvoor u gevoeligheidslabels kunt gebruiken als voorwaarden in DLP-beleid
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162686"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="b9ddd-103">Vertrouwelijkheidslabels gebruiken als voorwaarden in DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="b9ddd-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="b9ddd-104">U kunt [vertrouwelijkheidslabels](sensitivity-labels.md) gebruiken als voorwaarde in DLP-beleid voor deze locaties:</span><span class="sxs-lookup"><span data-stu-id="b9ddd-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="b9ddd-105">Exchange Online-e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b9ddd-105">Exchange Online email messages</span></span>
- <span data-ttu-id="b9ddd-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b9ddd-106">SharePoint Online</span></span>
- <span data-ttu-id="b9ddd-107">OneDrive voor Bedrijven-sites</span><span class="sxs-lookup"><span data-stu-id="b9ddd-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="b9ddd-108">Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="b9ddd-108">Windows 10 devices</span></span>

<span data-ttu-id="b9ddd-109">Gevoeligheidslabels worden weergegeven als een optie in de lijst **Inhoud bevat**.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b9ddd-110">![gevoeligheidslabel als voorwaarde](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="b9ddd-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9ddd-111">**Gevoeligheidslabels** als voorwaarde zijn niet beschikbaar als u **Chat- en kanaalberichten in Teams** hebt geselecteerd als een locatie om het DLP-beleid toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="b9ddd-112">Ondersteunde items, scenario's en beleidstips</span><span class="sxs-lookup"><span data-stu-id="b9ddd-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="b9ddd-113">U kunt gevoeligheidslabels gebruiken als voorwaarden op deze items en in deze scenario's.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="b9ddd-114">Ondersteunde items</span><span class="sxs-lookup"><span data-stu-id="b9ddd-114">Supported items</span></span>

|<span data-ttu-id="b9ddd-115">Service</span><span class="sxs-lookup"><span data-stu-id="b9ddd-115">Service</span></span>  |<span data-ttu-id="b9ddd-116">Itemtype</span><span class="sxs-lookup"><span data-stu-id="b9ddd-116">Item type</span></span>  |<span data-ttu-id="b9ddd-117">Beschikbaar voor beleidstip</span><span class="sxs-lookup"><span data-stu-id="b9ddd-117">Available to policy tip</span></span>  |<span data-ttu-id="b9ddd-118">Afdwingbaar</span><span class="sxs-lookup"><span data-stu-id="b9ddd-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b9ddd-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ddd-119">Exchange</span></span>    |<span data-ttu-id="b9ddd-120">e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="b9ddd-120">email message</span></span>         |<span data-ttu-id="b9ddd-121">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-121">yes</span></span>         |<span data-ttu-id="b9ddd-122">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-122">yes</span></span>         |
|<span data-ttu-id="b9ddd-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ddd-123">Exchange</span></span>    |<span data-ttu-id="b9ddd-124">e-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="b9ddd-124">email attachment</span></span>         |<span data-ttu-id="b9ddd-125">nee \*</span><span class="sxs-lookup"><span data-stu-id="b9ddd-125">no \*</span></span>         |<span data-ttu-id="b9ddd-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="b9ddd-126">yes \*</span></span>         |
|<span data-ttu-id="b9ddd-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b9ddd-127">SharePoint Online</span></span>     |<span data-ttu-id="b9ddd-128">items in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b9ddd-128">items in SharePoint Online</span></span>         |<span data-ttu-id="b9ddd-129">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-129">yes</span></span>         |<span data-ttu-id="b9ddd-130">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-130">yes</span></span>         |
|<span data-ttu-id="b9ddd-131">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="b9ddd-131">OneDrive for Business</span></span>     |<span data-ttu-id="b9ddd-132">items</span><span class="sxs-lookup"><span data-stu-id="b9ddd-132">items</span></span>         |<span data-ttu-id="b9ddd-133">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-133">yes</span></span>         |<span data-ttu-id="b9ddd-134">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-134">yes</span></span>         |
|<span data-ttu-id="b9ddd-135">Teams</span><span class="sxs-lookup"><span data-stu-id="b9ddd-135">Teams</span></span>     |<span data-ttu-id="b9ddd-136">Teams en kanaalberichten</span><span class="sxs-lookup"><span data-stu-id="b9ddd-136">Teams and channel messages</span></span>         |<span data-ttu-id="b9ddd-137">niet van toepassing</span><span class="sxs-lookup"><span data-stu-id="b9ddd-137">not applicable</span></span>         |<span data-ttu-id="b9ddd-138">niet van toepassing</span><span class="sxs-lookup"><span data-stu-id="b9ddd-138">not applicable</span></span>         |
|<span data-ttu-id="b9ddd-139">Teams</span><span class="sxs-lookup"><span data-stu-id="b9ddd-139">Teams</span></span>     |<span data-ttu-id="b9ddd-140">bijlagen</span><span class="sxs-lookup"><span data-stu-id="b9ddd-140">attachments</span></span>         |<span data-ttu-id="b9ddd-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="b9ddd-141">yes \*\*</span></span>         |<span data-ttu-id="b9ddd-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="b9ddd-142">yes \*\*</span></span>         |
|<span data-ttu-id="b9ddd-143">Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="b9ddd-143">Windows 10 devices</span></span>     |<span data-ttu-id="b9ddd-144">items</span><span class="sxs-lookup"><span data-stu-id="b9ddd-144">items</span></span>         |<span data-ttu-id="b9ddd-145">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-145">yes</span></span>         |<span data-ttu-id="b9ddd-146">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-146">yes</span></span>         |
|<span data-ttu-id="b9ddd-147">MCAS (preview-versie)</span><span class="sxs-lookup"><span data-stu-id="b9ddd-147">MCAS (preview)</span></span> |<span data-ttu-id="b9ddd-148">items</span><span class="sxs-lookup"><span data-stu-id="b9ddd-148">items</span></span>         |<span data-ttu-id="b9ddd-149">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-149">yes</span></span>         |<span data-ttu-id="b9ddd-150">ja</span><span class="sxs-lookup"><span data-stu-id="b9ddd-150">yes</span></span>         |

<span data-ttu-id="b9ddd-151">\* Tijdens het verzenden worden DLP-detectie en afdwinging van gevoeligheidslabels in e-mailberichten en bijlagen ondersteund.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="b9ddd-152">DLP-beleidstips van e-mailbijlagen met gevoeligheidslabels worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="b9ddd-153">\*\* Bijlagen die via een privéchat of kanalen in Teams worden verzonden, worden automatisch geüpload naar OneDrive voor Bedrijven en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="b9ddd-154">Dus als SharePoint Online of OneDrive voor Bedrijven als locaties zijn opgenomen in uw DLP-beleid, worden gelabelde bijlagen die worden verzonden in Teams automatisch opgenomen in het bereik van deze voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="b9ddd-155">Teams als locatie hoeft niet te zijn geselecteerd in het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="b9ddd-156">Ondersteunde scenario's</span><span class="sxs-lookup"><span data-stu-id="b9ddd-156">Supported scenarios</span></span>

- <span data-ttu-id="b9ddd-157">Een DLP-beheerder kan een lijst met alle gevoeligheidslabels in de tenant zien wanneer ze ervoor kiezen om één of meer gevoeligheidslabels als voorwaarde op te nemen.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="b9ddd-158">Het gebruik van gevoeligheidslabels als voorwaarde wordt ondersteund voor alle werkbelastingen, zoals aangegeven in de bovenstaande ondersteuningsmatrix.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="b9ddd-159">DLP-beleidstips blijven zichtbaar in alle werkbelastingen (behalve Outlook Win32) voor DLP-beleid dat een gevoeligheidslabel als voorwaarde bevat.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="b9ddd-160">Gevoeligheidslabels worden ook weergegeven als onderdeel van het e-mailbericht met het incidentenrapport als een DLP-beleid met een gevoeligheidslabel als voorwaarde overeenkomt.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="b9ddd-161">Gevoeligheidslabeldetails worden ook weergegeven in het auditlogboek met DLP-regelovereenkomsten voor een DLP-beleid dat een gevoeligheidslabel als voorwaarde bevat.</span><span class="sxs-lookup"><span data-stu-id="b9ddd-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="b9ddd-162">Beleidstips ondersteunen</span><span class="sxs-lookup"><span data-stu-id="b9ddd-162">Support policy tips</span></span>


|<span data-ttu-id="b9ddd-163">Werkbelasting</span><span class="sxs-lookup"><span data-stu-id="b9ddd-163">Workload</span></span>  |<span data-ttu-id="b9ddd-164">Ondersteunde/niet-ondersteunde beleidstips</span><span class="sxs-lookup"><span data-stu-id="b9ddd-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="b9ddd-165">OWA</span><span class="sxs-lookup"><span data-stu-id="b9ddd-165">OWA</span></span> |    <span data-ttu-id="b9ddd-166">ondersteund</span><span class="sxs-lookup"><span data-stu-id="b9ddd-166">supported</span></span>     |
|<span data-ttu-id="b9ddd-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="b9ddd-167">Outlook Win 32</span></span>    |  <span data-ttu-id="b9ddd-168">niet ondersteund</span><span class="sxs-lookup"><span data-stu-id="b9ddd-168">not supported</span></span>       |
|<span data-ttu-id="b9ddd-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b9ddd-169">SharePoint</span></span>   |   <span data-ttu-id="b9ddd-170">ondersteund</span><span class="sxs-lookup"><span data-stu-id="b9ddd-170">supported</span></span>      |
|<span data-ttu-id="b9ddd-171">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="b9ddd-171">OneDrive for Business</span></span>    |    <span data-ttu-id="b9ddd-172">ondersteund</span><span class="sxs-lookup"><span data-stu-id="b9ddd-172">supported</span></span>     |
|<span data-ttu-id="b9ddd-173">eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="b9ddd-173">endpoint devices</span></span>   |  <span data-ttu-id="b9ddd-174">niet ondersteund</span><span class="sxs-lookup"><span data-stu-id="b9ddd-174">not supported</span></span>       |
