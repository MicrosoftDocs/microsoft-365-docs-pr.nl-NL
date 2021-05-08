---
title: Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender
description: Krijg een overzicht van geautomatiseerde onderzoeks- en antwoordmogelijkheden, ook wel self-healing genoemd, in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, zelfherstel
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
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274566"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="58d0d-104">Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58d0d-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="58d0d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="58d0d-105">**Applies to:**</span></span>
- <span data-ttu-id="58d0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58d0d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="58d0d-107">Als uw organisatie Microsoft 365 [Defender](microsoft-365-defender.md)gebruikt, ontvangt uw beveiligingsteam een waarschuwing in het Microsoft 365-beveiligingscentrum wanneer een schadelijke of verdachte activiteit of artefact wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="58d0d-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="58d0d-108">Gezien de schijnbaar eindeloze stroom van bedreigingen die kunnen binnenstromen, worden beveiligingsteams vaak geconfronteerd met de uitdaging om het grote aantal waarschuwingen aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="58d0d-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="58d0d-109">Gelukkig bevat Microsoft 365 Defender geautomatiseerde onderzoeks- en antwoordmogelijkheden (AIR) die uw beveiligingsteam kunnen helpen bij het efficiënter en effectiever aanpakken van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-109">Fortunately, Microsoft 365 Defender includes automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="58d0d-110">Dit artikel bevat een overzicht van AIR en bevat koppelingen naar de volgende stappen en aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="58d0d-111">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="58d0d-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="58d0d-112">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="58d0d-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="58d0d-113">Hoe geautomatiseerd onderzoek en zelfherstel werken</span><span class="sxs-lookup"><span data-stu-id="58d0d-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="58d0d-114">Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="58d0d-115">Het kan erg tijdrovend zijn om prioriteit te geven aan waarschuwingen en deze te onderzoeken, met name wanneer er nieuwe waarschuwingen binnen blijven komen terwijl er een onderzoek wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="58d0d-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="58d0d-116">Beveiligingsbewerkingsteams kunnen zich overstelpt voelen door het grote aantal bedreigingen dat ze moeten bewaken en beschermen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="58d0d-117">Geautomatiseerde onderzoeks- en antwoordmogelijkheden, met self-heling, in Microsoft 365 Defender kan helpen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="58d0d-118">Bekijk de volgende video om te zien hoe zelfherstel werkt:</span><span class="sxs-lookup"><span data-stu-id="58d0d-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="58d0d-119">In Microsoft 365 Defender werkt automatisch onderzoek en antwoord met self-helende mogelijkheden op uw apparaten, e-mail & inhoud en identiteiten.</span><span class="sxs-lookup"><span data-stu-id="58d0d-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="58d0d-120">In dit artikel wordt beschreven hoe geautomatiseerd onderzoek en antwoord werken.</span><span class="sxs-lookup"><span data-stu-id="58d0d-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="58d0d-121">Zie Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 [Defender om deze mogelijkheden te configureren.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="58d0d-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="58d0d-122">Uw eigen virtuele analist</span><span class="sxs-lookup"><span data-stu-id="58d0d-122">Your own virtual analyst</span></span>

<span data-ttu-id="58d0d-123">Imagine virtuele analist in uw beveiligingsteam van Tier 1 of Tier 2.</span><span class="sxs-lookup"><span data-stu-id="58d0d-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="58d0d-124">De virtuele analist bootst de ideale stappen na die beveiligingsbewerkingen zouden ondernemen om bedreigingen te onderzoeken en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="58d0d-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="58d0d-125">De virtuele analist kan 24x7 werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingsremediatie op zich nemen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="58d0d-126">Een dergelijke virtuele analist kan de tijd om te reageren aanzienlijk verminderen, waardoor uw team voor beveiligingsactiviteiten vrij komt voor andere belangrijke bedreigingen of strategische projecten.</span><span class="sxs-lookup"><span data-stu-id="58d0d-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="58d0d-127">Als dit scenario klinkt als sciencefiction, is dat niet zo.</span><span class="sxs-lookup"><span data-stu-id="58d0d-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="58d0d-128">Een dergelijke virtuele analist maakt deel uit van Microsoft 365 Defender-suite en de naam is *geautomatiseerd onderzoek en antwoord.*</span><span class="sxs-lookup"><span data-stu-id="58d0d-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="58d0d-129">Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan uw beveiligingsteam de capaciteit van uw organisatie voor beveiligingswaarschuwingen en incidenten aanzienlijk vergroten.</span><span class="sxs-lookup"><span data-stu-id="58d0d-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="58d0d-130">Met geautomatiseerde onderzoeken en antwoorden kunt u de kosten van het omgaan met onderzoek- en antwoordactiviteiten verlagen en het beste uit uw suite voor bedreigingsbeveiliging halen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-130">With automated investigation and response, you can reduce the cost of dealing with investigation and response activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="58d0d-131">Geautomatiseerde onderzoeks- en antwoordmogelijkheden helpen uw team voor beveiligingsbewerkingen door:</span><span class="sxs-lookup"><span data-stu-id="58d0d-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="58d0d-132">Bepalen of een bedreiging actie vereist.</span><span class="sxs-lookup"><span data-stu-id="58d0d-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="58d0d-133">Het nemen (of aanbevelen van) de benodigde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="58d0d-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="58d0d-134">Bepalen of en welke andere onderzoeken moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="58d0d-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="58d0d-135">Herhaal het proces zo nodig voor andere waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="58d0d-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="58d0d-136">Het geautomatiseerde onderzoeksproces</span><span class="sxs-lookup"><span data-stu-id="58d0d-136">The automated investigation process</span></span>

<span data-ttu-id="58d0d-137">Met een waarschuwing wordt een incident gemaakt dat een geautomatiseerd onderzoek kan starten.</span><span class="sxs-lookup"><span data-stu-id="58d0d-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="58d0d-138">Het geautomatiseerde onderzoek resulteert in een vonnis voor elk bewijs.</span><span class="sxs-lookup"><span data-stu-id="58d0d-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="58d0d-139">Vonnissen kunnen zijn:</span><span class="sxs-lookup"><span data-stu-id="58d0d-139">Verdicts can be:</span></span>
- <span data-ttu-id="58d0d-140">*Schadelijk*</span><span class="sxs-lookup"><span data-stu-id="58d0d-140">*Malicious*</span></span>
- <span data-ttu-id="58d0d-141">*Verdacht*</span><span class="sxs-lookup"><span data-stu-id="58d0d-141">*Suspicious*</span></span> 
- <span data-ttu-id="58d0d-142">*Geen bedreigingen gevonden*</span><span class="sxs-lookup"><span data-stu-id="58d0d-142">*No threats found*</span></span> 

<span data-ttu-id="58d0d-143">Herstelacties voor schadelijke of verdachte entiteiten worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="58d0d-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="58d0d-144">Voorbeelden van herstelacties zijn:</span><span class="sxs-lookup"><span data-stu-id="58d0d-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="58d0d-145">Een bestand in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="58d0d-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="58d0d-146">Een proces stoppen</span><span class="sxs-lookup"><span data-stu-id="58d0d-146">Stopping a process</span></span>
- <span data-ttu-id="58d0d-147">Een apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="58d0d-147">Isolating a device</span></span>
- <span data-ttu-id="58d0d-148">Een URL blokkeren</span><span class="sxs-lookup"><span data-stu-id="58d0d-148">Blocking a URL</span></span> 
- <span data-ttu-id="58d0d-149">Andere acties</span><span class="sxs-lookup"><span data-stu-id="58d0d-149">Other actions</span></span>

<span data-ttu-id="58d0d-150">Zie Herstelacties in Microsoft 365 [Defender voor meer informatie.](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="58d0d-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="58d0d-151">Afhankelijk van [hoe](m365d-configure-auto-investigation-response.md) geautomatiseerde onderzoeks- en antwoordmogelijkheden voor uw organisatie zijn geconfigureerd, worden herstelacties automatisch of alleen uitgevoerd na goedkeuring door uw beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="58d0d-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="58d0d-152">Alle acties, in behandeling of voltooid, worden weergegeven in het [Actiecentrum.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="58d0d-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="58d0d-153">Terwijl een onderzoek wordt uitgevoerd, worden eventuele andere gerelateerde waarschuwingen toegevoegd aan het onderzoek totdat het is voltooid.</span><span class="sxs-lookup"><span data-stu-id="58d0d-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="58d0d-154">Als een betrokken entiteit ergens anders wordt gezien, wordt het bereik van het geautomatiseerde onderzoek uitgebreid met deze entiteit en wordt het onderzoeksproces herhaald.</span><span class="sxs-lookup"><span data-stu-id="58d0d-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="58d0d-155">In Microsoft 365 Defender correleert elk geautomatiseerd onderzoek signalen in Microsoft Defender voor identiteit, Microsoft Defender voor eindpunt en Microsoft Defender voor Office 365, zoals samengevat in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="58d0d-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="58d0d-156">Entiteiten</span><span class="sxs-lookup"><span data-stu-id="58d0d-156">Entities</span></span> |<span data-ttu-id="58d0d-157">Bedreigingsbeveiligingsservices</span><span class="sxs-lookup"><span data-stu-id="58d0d-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="58d0d-158">Apparaten (ook wel eindpunten of machines genoemd)</span><span class="sxs-lookup"><span data-stu-id="58d0d-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="58d0d-159">Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="58d0d-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="58d0d-160">On-premises Active Directory-gebruikers, entiteitsgedrag en activiteiten</span><span class="sxs-lookup"><span data-stu-id="58d0d-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="58d0d-161">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="58d0d-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="58d0d-162">E-mailinhoud (e-mailberichten die bestanden en URL's kunnen bevatten)</span><span class="sxs-lookup"><span data-stu-id="58d0d-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="58d0d-163">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="58d0d-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="58d0d-164">Niet elke waarschuwing activeert een geautomatiseerd onderzoek en niet elk onderzoek resulteert in geautomatiseerde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="58d0d-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="58d0d-165">Dit hangt af van de configuratie van geautomatiseerde onderzoeken en antwoorden voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="58d0d-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="58d0d-166">Zie [Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="58d0d-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="58d0d-167">Een lijst met onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="58d0d-167">Viewing a list of investigations</span></span>

<span data-ttu-id="58d0d-168">Als u onderzoeken wilt bekijken, gaat u naar de **pagina Incidenten.**</span><span class="sxs-lookup"><span data-stu-id="58d0d-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="58d0d-169">Selecteer een incident en selecteer vervolgens het **tabblad Onderzoeken.** Zie Details en resultaten van een geautomatiseerd onderzoek voor [meer informatie.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="58d0d-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="58d0d-170">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="58d0d-170">Next steps</span></span>

- [<span data-ttu-id="58d0d-171">Bekijk de vereisten voor geautomatiseerd onderzoek en antwoord</span><span class="sxs-lookup"><span data-stu-id="58d0d-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="58d0d-172">Geautomatiseerd onderzoek en antwoord configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="58d0d-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="58d0d-173">Meer informatie over het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="58d0d-173">Learn more about the Action center</span></span>](m365d-action-center.md)
