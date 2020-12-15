---
title: Automatisch onderzoek en antwoord in Microsoft 365 Defender
description: Een overzicht van geautomatiseerde functies voor onderzoek en antwoord, ook wel zelfherstel genoemd, in Microsoft 365 Defender
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstel, zelfherstel
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683305"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="73204-104">Automatisch onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73204-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="73204-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="73204-105">**Applies to:**</span></span>
- <span data-ttu-id="73204-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73204-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="73204-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="73204-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="73204-108">U kunt [deze beoordelen in een testomgeving](https://aka.ms/mtp-trial-lab) of een [proefproject uitvoeren op de productie](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="73204-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="73204-109">Hoe automatisch onderzoek en automatische herherstel werken</span><span class="sxs-lookup"><span data-stu-id="73204-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="73204-110">Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="73204-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="73204-111">Het kan zeer lang voor het maken van waarschuwingen, met name wanneer nieuwe waarschuwingen worden gehouden wanneer een onderzoek wordt gehouden, zeer veel tijd in beslag nemen en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="73204-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="73204-112">Beveiligingsactiviteiten teams kunnen overspoeld worden door het doorschijnende volume van de bedreigingen die ze moeten controleren en beschermen.</span><span class="sxs-lookup"><span data-stu-id="73204-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="73204-113">Geautomatiseerd onderzoek en antwoord functies met zelfherstel in Microsoft 365 Defender kan u helpen.</span><span class="sxs-lookup"><span data-stu-id="73204-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="73204-114">Bekijk de volgende video om te zien hoe u dit doet:</span><span class="sxs-lookup"><span data-stu-id="73204-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="73204-115">In Microsoft 365 Defender werken geautomatiseerde onderzoek en antwoord met mogelijkheden voor automatisch herstel op uw apparaten, e-mail & inhoud en identiteiten.</span><span class="sxs-lookup"><span data-stu-id="73204-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="73204-116">In dit artikel wordt beschreven hoe automatisch onderzoek en reacties werken.</span><span class="sxs-lookup"><span data-stu-id="73204-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="73204-117">Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft 365 Defender configureren](mtp-configure-auto-investigation-response.md)voor het configureren van deze functies.</span><span class="sxs-lookup"><span data-stu-id="73204-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="73204-118">Uw eigen virtuele analist</span><span class="sxs-lookup"><span data-stu-id="73204-118">Your own virtual analyst</span></span>

<span data-ttu-id="73204-119">Voorbeeld van een virtuele analist in uw team van 1/laag 2-beveiligingsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="73204-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="73204-120">De virtuele analist imiteert de ideale stappen die beveiligingsactiviteiten ondernemen om bedreigingen te onderzoeken en te herstellen.</span><span class="sxs-lookup"><span data-stu-id="73204-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="73204-121">De virtuele assistent kan 24x7 werken, met onbeperkte capaciteit, en kan een aanzienlijke belasting van onderzoek en bedreiging doen.</span><span class="sxs-lookup"><span data-stu-id="73204-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="73204-122">Een dergelijke virtuele assistent kon de tijd in beslag nemen om te reageren, het team van uw beveiligingsactiviteiten vrijmaken voor andere belangrijke strategische projecten.</span><span class="sxs-lookup"><span data-stu-id="73204-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="73204-123">Als dit scenario klinkt als Science fictief, dan is het niet!</span><span class="sxs-lookup"><span data-stu-id="73204-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="73204-124">Zo'n virtuele analist maakt deel uit van uw Microsoft 365-Suite en de naam is *geautomatiseerd onderzoek en antwoord*.</span><span class="sxs-lookup"><span data-stu-id="73204-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="73204-125">Met geautomatiseerd onderzoek en antwoord kan uw bedrijfsvoering de capaciteit van uw organisatie ingrijpend verhogen om te zorgen voor beveiligingsmeldingen en incidenten.</span><span class="sxs-lookup"><span data-stu-id="73204-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="73204-126">Met automatisch onderzoek en antwoord kunt u de kosten van transacties met onderzoek-en herstel activiteiten reduceren en optimaal gebruikmaken van uw Threat Protection-Suite.</span><span class="sxs-lookup"><span data-stu-id="73204-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="73204-127">met geautomatiseerd onderzoek en antwoord zorgt u ervoor dat uw beveiligingsactiviteiten team:</span><span class="sxs-lookup"><span data-stu-id="73204-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="73204-128">Bepalen of een Threat een actie vereist;</span><span class="sxs-lookup"><span data-stu-id="73204-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="73204-129">Het uitvoeren (of aanbevelen) van alle benodigde herstelacties;</span><span class="sxs-lookup"><span data-stu-id="73204-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="73204-130">Bepalen welke aanvullende onderzoeken moeten worden gedaan; en</span><span class="sxs-lookup"><span data-stu-id="73204-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="73204-131">Herhaal het proces zo nodig voor andere meldingen.</span><span class="sxs-lookup"><span data-stu-id="73204-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="73204-132">Het proces voor automatisch onderzoek</span><span class="sxs-lookup"><span data-stu-id="73204-132">The automated investigation process</span></span>

<span data-ttu-id="73204-133">**Waarschuwing**  >  **incident**  >  **automatisch onderzoek**  >  **verdict**  >  **herstelactie**</span><span class="sxs-lookup"><span data-stu-id="73204-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="73204-134">Een waarschuwing met een trigger maakt een incident, dat een geautomatiseerd onderzoek kan starten.</span><span class="sxs-lookup"><span data-stu-id="73204-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="73204-135">Dat onderzoek kan resulteren in een of meer herstelacties.</span><span class="sxs-lookup"><span data-stu-id="73204-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="73204-136">In Microsoft 365 Defender verbindt elk automatisch onderzoek alle signalen in Microsoft Defender voor de identiteit, Microsoft Defender voor eindpunt en Defender voor Office 365, zoals in de volgende tabel wordt samengevat:</span><span class="sxs-lookup"><span data-stu-id="73204-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="73204-137">Onderzoeksinstellingen</span><span class="sxs-lookup"><span data-stu-id="73204-137">Entities</span></span> |<span data-ttu-id="73204-138">Service voor Threat Protection</span><span class="sxs-lookup"><span data-stu-id="73204-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="73204-139">Apparaten (ook wel eindpunten genoemd)</span><span class="sxs-lookup"><span data-stu-id="73204-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="73204-140">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="73204-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="73204-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="73204-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="73204-142">E-mail inhoud (bestanden en berichten in postvakken)</span><span class="sxs-lookup"><span data-stu-id="73204-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="73204-143">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="73204-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="73204-144">Bij elk onderzoek wordt Verdicts (*kwaadaardige*, *verdachte* of *geen bedreigingen gevonden*) voor elk onderzocht onderzoek.</span><span class="sxs-lookup"><span data-stu-id="73204-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="73204-145">Afhankelijk van het type bedreiging en het resultaat Verdict, worden herstelacties automatisch of na goedkeuring uitgevoerd door het team van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="73204-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="73204-146">Acties in behandeling en voltooid worden weergegeven in het [Actiecentrum](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="73204-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="73204-147">Wanneer een onderzoek wordt uitgevoerd, worden eventuele andere bijbehorende waarschuwingen toegevoegd aan het onderzoek totdat het onderzoek wordt voltooid.</span><span class="sxs-lookup"><span data-stu-id="73204-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="73204-148">Als een incriminated-entiteit elders wordt weergegeven, wordt het bereik van de geautomatiseerd onderzoek uitgebreid met die entiteit, en moet een algemeen beveiligings Playbook worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="73204-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="73204-149">Niet elke melding veroorzaakt een geautomatiseerd onderzoek en niet alle onderzoekresultaten met geautomatiseerde herstelacties; Dit is alles, afhankelijk van de manier waarop automatisch onderzoek en beantwoorden zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="73204-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="73204-150">Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft 365 Defender configureren](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="73204-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="73204-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="73204-151">Next steps</span></span>

- [<span data-ttu-id="73204-152">Zie de vereisten voor automatisch onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73204-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="73204-153">Automatisch onderzoek en antwoord configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="73204-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="73204-154">Meer informatie over het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="73204-154">Learn more about the Action center</span></span>](mtp-action-center.md)
