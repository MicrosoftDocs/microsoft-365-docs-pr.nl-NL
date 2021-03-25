---
title: Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender
description: Een overzicht krijgen van geautomatiseerde onderzoeks- en antwoordmogelijkheden, ook wel self-healing genoemd, in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, zelfherstel
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
ms.openlocfilehash: 8ed6f1ccd6587d6c618974a123f0d5d42a44e753
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199631"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="09b36-104">Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09b36-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="09b36-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="09b36-105">**Applies to:**</span></span>
- <span data-ttu-id="09b36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09b36-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="09b36-107">Als uw organisatie [Microsoft 365 Defender](microsoft-365-defender.md)gebruikt, ontvangt uw beveiligingsteam een waarschuwing wanneer een schadelijk of verdacht artefact wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="09b36-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="09b36-108">Gezien de schijnbaar eindeloze stroom van bedreigingen die binnenstromen, worden beveiligingsteams vaak geconfronteerd met uitdagingen bij het aanpakken van het grote aantal waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="09b36-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="09b36-109">Gelukkig bevat Microsoft 365 Defender geautomatiseerde mogelijkheden voor onderzoek en herstel (AIR) die uw beveiligingsteam kunnen helpen om bedreigingen efficiënter en effectiever aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="09b36-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="09b36-110">Dit artikel bevat een overzicht van AIR en bevat koppelingen naar de volgende stappen en aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="09b36-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="09b36-111">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="09b36-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="09b36-112">U kunt [het project evalueren in een labomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of uw [pilotproject uitvoeren in productie.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="09b36-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="09b36-113">Hoe geautomatiseerd onderzoek en zelfherstel werken</span><span class="sxs-lookup"><span data-stu-id="09b36-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="09b36-114">Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="09b36-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="09b36-115">Het kan erg tijdrovend zijn om prioriteit te geven aan waarschuwingen en deze te onderzoeken, met name wanneer er nieuwe waarschuwingen binnen blijven komen terwijl er een onderzoek wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="09b36-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="09b36-116">Beveiligingsbewerkingsteams kunnen zich overstelpt voelen door het grote aantal bedreigingen dat ze moeten bewaken en beschermen.</span><span class="sxs-lookup"><span data-stu-id="09b36-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="09b36-117">Geautomatiseerde onderzoeks- en antwoordmogelijkheden, met self-heling, in Microsoft 365 Defender kunnen u helpen.</span><span class="sxs-lookup"><span data-stu-id="09b36-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="09b36-118">Bekijk de volgende video om te zien hoe zelfherstel werkt:</span><span class="sxs-lookup"><span data-stu-id="09b36-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="09b36-119">In Microsoft 365 Defender werkt automatisch onderzoek en antwoord met self-helende mogelijkheden op uw apparaten, e-mail & inhoud en identiteiten.</span><span class="sxs-lookup"><span data-stu-id="09b36-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="09b36-120">In dit artikel wordt beschreven hoe geautomatiseerd onderzoek en antwoord werken.</span><span class="sxs-lookup"><span data-stu-id="09b36-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="09b36-121">Zie Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren [in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)om deze mogelijkheden te configureren.</span><span class="sxs-lookup"><span data-stu-id="09b36-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="09b36-122">Uw eigen virtuele analist</span><span class="sxs-lookup"><span data-stu-id="09b36-122">Your own virtual analyst</span></span>

<span data-ttu-id="09b36-123">Stel u voor dat u een virtuele analist hebt in uw beveiligingsteam van Tier 1 of Tier 2.</span><span class="sxs-lookup"><span data-stu-id="09b36-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="09b36-124">De virtuele analist bootst de ideale stappen na die beveiligingsbewerkingen zouden ondernemen om bedreigingen te onderzoeken en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="09b36-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="09b36-125">De virtuele assistent kan 24x7 werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingssanering op zich nemen.</span><span class="sxs-lookup"><span data-stu-id="09b36-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="09b36-126">Een dergelijke virtuele assistent kan de tijd om te reageren aanzienlijk verminderen, waardoor uw team voor beveiligingsbewerkingen vrij komt voor andere belangrijke strategische projecten.</span><span class="sxs-lookup"><span data-stu-id="09b36-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="09b36-127">Als dit scenario klinkt als sciencefiction, is dat niet zo.</span><span class="sxs-lookup"><span data-stu-id="09b36-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="09b36-128">Een dergelijke virtuele analist maakt deel uit van uw Microsoft 365 Defender-suite en de naam is *geautomatiseerd onderzoek en antwoord.*</span><span class="sxs-lookup"><span data-stu-id="09b36-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="09b36-129">Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan uw beveiligingsteam de capaciteit van uw organisatie voor beveiligingswaarschuwingen en incidenten aanzienlijk vergroten.</span><span class="sxs-lookup"><span data-stu-id="09b36-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="09b36-130">Met geautomatiseerde onderzoeken en antwoorden kunt u de kosten van het omgaan met onderzoek- en herstelactiviteiten verlagen en het beste uit uw suite voor bedreigingsbeveiliging halen.</span><span class="sxs-lookup"><span data-stu-id="09b36-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="09b36-131">Geautomatiseerde onderzoeks- en antwoordmogelijkheden helpen uw team voor beveiligingsbewerkingen door:</span><span class="sxs-lookup"><span data-stu-id="09b36-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="09b36-132">Bepalen of een bedreiging actie vereist;</span><span class="sxs-lookup"><span data-stu-id="09b36-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="09b36-133">Het nemen (of aanbevelen van) de benodigde herstelacties;</span><span class="sxs-lookup"><span data-stu-id="09b36-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="09b36-134">Bepalen of en welke andere onderzoeken moeten worden uitgevoerd; en</span><span class="sxs-lookup"><span data-stu-id="09b36-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="09b36-135">Herhaal het proces zo nodig voor andere waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="09b36-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="09b36-136">Het geautomatiseerde onderzoeksproces</span><span class="sxs-lookup"><span data-stu-id="09b36-136">The automated investigation process</span></span>

<span data-ttu-id="09b36-137">Met een waarschuwing wordt een incident gemaakt dat een geautomatiseerd onderzoek kan starten.</span><span class="sxs-lookup"><span data-stu-id="09b36-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="09b36-138">Het geautomatiseerde onderzoek resulteert in een vonnis voor elk bewijs.</span><span class="sxs-lookup"><span data-stu-id="09b36-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="09b36-139">Vonnissen kunnen zijn:</span><span class="sxs-lookup"><span data-stu-id="09b36-139">Verdicts can be:</span></span>
- <span data-ttu-id="09b36-140">*Schadelijk*;</span><span class="sxs-lookup"><span data-stu-id="09b36-140">*Malicious*;</span></span>
- <span data-ttu-id="09b36-141">*Verdacht*; of</span><span class="sxs-lookup"><span data-stu-id="09b36-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="09b36-142">*Er zijn geen bedreigingen gevonden.*</span><span class="sxs-lookup"><span data-stu-id="09b36-142">*No threats found*.</span></span> 

<span data-ttu-id="09b36-143">Herstelacties voor schadelijke of verdachte entiteiten worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="09b36-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="09b36-144">Voorbeelden van herstelacties zijn:</span><span class="sxs-lookup"><span data-stu-id="09b36-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="09b36-145">Een bestand in quarantaine plaatsen;</span><span class="sxs-lookup"><span data-stu-id="09b36-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="09b36-146">Een proces stoppen;</span><span class="sxs-lookup"><span data-stu-id="09b36-146">Stopping a process;</span></span>
- <span data-ttu-id="09b36-147">Een apparaat isoleren;</span><span class="sxs-lookup"><span data-stu-id="09b36-147">Isolating a device;</span></span>
- <span data-ttu-id="09b36-148">Een URL blokkeren; en</span><span class="sxs-lookup"><span data-stu-id="09b36-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="09b36-149">andere acties.</span><span class="sxs-lookup"><span data-stu-id="09b36-149">other actions.</span></span> <span data-ttu-id="09b36-150">(Zie [Herstelacties in Microsoft 365 Defender](m365d-remediation-actions.md).)</span><span class="sxs-lookup"><span data-stu-id="09b36-150">(See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).)</span></span>

<span data-ttu-id="09b36-151">Afhankelijk van [hoe](m365d-configure-auto-investigation-response.md) geautomatiseerde onderzoeks- en antwoordmogelijkheden voor uw organisatie zijn geconfigureerd, worden herstelacties automatisch of alleen uitgevoerd na goedkeuring door uw beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="09b36-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="09b36-152">Alle acties, in behandeling of voltooid, worden weergegeven in het [Actiecentrum.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="09b36-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="09b36-153">Terwijl een onderzoek wordt uitgevoerd, worden eventuele andere gerelateerde waarschuwingen toegevoegd aan het onderzoek totdat het is voltooid.</span><span class="sxs-lookup"><span data-stu-id="09b36-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="09b36-154">Als een belastende entiteit ergens anders wordt gezien, wordt het bereik van het geautomatiseerde onderzoek uitgebreid met deze entiteit en wordt het onderzoeksproces herhaald.</span><span class="sxs-lookup"><span data-stu-id="09b36-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="09b36-155">In Microsoft 365 Defender correleert elk geautomatiseerd onderzoek signalen in Microsoft Defender voor identiteit, Microsoft Defender voor Eindpunt en Defender voor Office 365, zoals samengevat in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="09b36-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="09b36-156">Entiteiten</span><span class="sxs-lookup"><span data-stu-id="09b36-156">Entities</span></span> |<span data-ttu-id="09b36-157">Bedreigingsbeveiligingsservices</span><span class="sxs-lookup"><span data-stu-id="09b36-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="09b36-158">Apparaten (ook wel eindpunten genoemd, ook wel machines genoemd)</span><span class="sxs-lookup"><span data-stu-id="09b36-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |[<span data-ttu-id="09b36-159">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="09b36-159">Microsoft Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md)<br/>[<span data-ttu-id="09b36-160">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="09b36-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="09b36-161">E-mailinhoud (e-mailberichten die bestanden en URL's kunnen bevatten)</span><span class="sxs-lookup"><span data-stu-id="09b36-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="09b36-162">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="09b36-162">Microsoft Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> <span data-ttu-id="09b36-163">Niet elke waarschuwing activeert een geautomatiseerd onderzoek en niet elk onderzoek resulteert in geautomatiseerde herstelacties. dit hangt af van de configuratie van geautomatiseerde onderzoeken en antwoorden voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09b36-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="09b36-164">Zie [Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="09b36-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="09b36-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="09b36-165">Next steps</span></span>

- [<span data-ttu-id="09b36-166">Bekijk de vereisten voor geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09b36-166">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="09b36-167">Geautomatiseerd onderzoek en antwoord configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="09b36-167">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="09b36-168">Meer informatie over het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="09b36-168">Learn more about the Action center</span></span>](m365d-action-center.md)
