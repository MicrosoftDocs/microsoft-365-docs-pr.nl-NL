---
title: Automatisch onderzoek en antwoorden in Microsoft 365 Defender
description: Krijg een overzicht van geautomatiseerde onderzoeks- en antwoordmogelijkheden, ook wel zelf-moeten worden genoemd, in Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-in
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930328"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="e3aa3-104">Automatisch onderzoek en antwoorden in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3aa3-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3aa3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e3aa3-105">**Applies to:**</span></span>
- <span data-ttu-id="e3aa3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3aa3-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="e3aa3-107">Wilt u ervaring met Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e3aa3-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="e3aa3-108">U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="e3aa3-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="e3aa3-109">Hoe automatisch onderzoek en zelf-herstel werken</span><span class="sxs-lookup"><span data-stu-id="e3aa3-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="e3aa3-110">Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw team voor beveiligingsactiviteiten om naar deze waarschuwingen te kijken en stappen te ondernemen om uw organisatie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e3aa3-111">Het geven van prioriteit aan waarschuwingen en het onderzoeken van waarschuwingen kan erg veel tijd in beslag nemen, vooral wanneer er steeds nieuwe waarschuwingen binnen komen terwijl er een onderzoek bezig is.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="e3aa3-112">Teams met beveiligingsbewerkingen kunnen overstelpt worden door het grote aantal bedreigingen die ze moeten controleren en beveiligen tegen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="e3aa3-113">Automatische onderzoeks- en antwoordmogelijkheden, met self-moeten, in Microsoft 365 Defender kunnen helpen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="e3aa3-114">Bekijk de volgende video om te zien hoe uw werk werkt:</span><span class="sxs-lookup"><span data-stu-id="e3aa3-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="e3aa3-115">In Microsoft 365 Defender werken geautomatiseerde onderzoeken en antwoorden met self-functionaliteit op uw apparaten, e-mailen & inhoud en identiteiten.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="e3aa3-116">In dit artikel wordt beschreven hoe automatisch onderzoek en antwoorden werken.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="e3aa3-117">Zie Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren [in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)om deze mogelijkheden te configureren.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="e3aa3-118">Uw eigen virtuele analist</span><span class="sxs-lookup"><span data-stu-id="e3aa3-118">Your own virtual analyst</span></span>

<span data-ttu-id="e3aa3-119">Stel dat u een virtuele analist hebt in uw beveiligingsteam voor Laag 1/Laag 2.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="e3aa3-120">De virtuele analist nabootst de ideale stappen die beveiligingsbewerkingen moeten uitvoeren om bedreigingen te onderzoeken en te herstellen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="e3aa3-121">De virtuele assistent zou 24x7 kunnen werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingen herstellen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="e3aa3-122">Een dergelijke virtuele assistent kan de tijd om te reageren aanzienlijk verminderen, waardoor het team voor beveiligingsactiviteiten vrij komt voor andere belangrijke strategische projecten.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="e3aa3-123">Als dit scenario klinkt als sciencefiction, is dat niet het geval.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="e3aa3-124">Een dergelijke virtuele analist maakt deel uit van uw Microsoft 365 Defender-suite en de naam is *geautomatiseerd onderzoek en reactie.*</span><span class="sxs-lookup"><span data-stu-id="e3aa3-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="e3aa3-125">Dankzij automatisch onderzoek en automatisch antwoord kan het team voor beveiligingsactiviteiten de capaciteit van uw organisatie om te gaan met beveiligingswaarschuwingen en -incidenten aanzienlijk verhogen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="e3aa3-126">Met geautomatiseerd onderzoek en automatisch onderzoek kunt u de kosten van onderzoeken en herstelactiviteiten verminderen en het beste uit uw suite voor bedreigingsbeveiliging halen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="e3aa3-127">Geautomatiseerde onderzoeken en antwoorden helpt uw team voor beveiligingsbewerkingen door:</span><span class="sxs-lookup"><span data-stu-id="e3aa3-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="e3aa3-128">Bepalen of actie moet worden ondernomen voor een bedreiging;</span><span class="sxs-lookup"><span data-stu-id="e3aa3-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="e3aa3-129">Eventuele benodigde herstelacties uitvoeren (of aanbevelen);</span><span class="sxs-lookup"><span data-stu-id="e3aa3-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="e3aa3-130">Bepalen welke aanvullende onderzoeken moeten worden uitgevoerd; en</span><span class="sxs-lookup"><span data-stu-id="e3aa3-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="e3aa3-131">Herhaal dit proces indien nodig voor andere waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="e3aa3-132">Het proces van automatisch onderzoek</span><span class="sxs-lookup"><span data-stu-id="e3aa3-132">The automated investigation process</span></span>

<span data-ttu-id="e3aa3-133">**Waarschuwing**  >  **incident**  >  **geautomatiseerd onderzoek**  >  **één**  >  **herstelactie**</span><span class="sxs-lookup"><span data-stu-id="e3aa3-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="e3aa3-134">Een geactiveerde waarschuwing maakt een incident, dat een geautomatiseerd onderzoek kan starten.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="e3aa3-135">Dit onderzoek kan leiden tot een of meer herstelacties.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="e3aa3-136">In Microsoft 365 Defender correleren elk geautomatiseerd onderzoek signalen tussen Microsoft Defender for Identity, Microsoft Defender voor Eindpunt en Defender voor Office 365, zoals samengevat in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="e3aa3-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="e3aa3-137">Entiteiten</span><span class="sxs-lookup"><span data-stu-id="e3aa3-137">Entities</span></span> |<span data-ttu-id="e3aa3-138">Bedreigingsbeveiligingsservices</span><span class="sxs-lookup"><span data-stu-id="e3aa3-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="e3aa3-139">Apparaten (ook wel eindpunten genoemd)</span><span class="sxs-lookup"><span data-stu-id="e3aa3-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="e3aa3-140">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e3aa3-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="e3aa3-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e3aa3-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="e3aa3-142">E-mailinhoud (bestanden en berichten in postvakken)</span><span class="sxs-lookup"><span data-stu-id="e3aa3-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="e3aa3-143">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e3aa3-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="e3aa3-144">Elk onderzoek genereert onderzoek (*Kwaadaardige,* *Verdachte* of Geen bedreigingen *gevonden)* voor elk stukje onderzoek dat wordt onderzocht.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="e3aa3-145">Afhankelijk van het type bedreiging en het resulterende resultaat, vinden herstelacties automatisch of na goedkeuring door het beveiligingsteam van uw organisatie plaats.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="e3aa3-146">Acties in behandeling en voltooid worden weergegeven in het [Actiecentrum.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="e3aa3-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="e3aa3-147">Wanneer een onderzoek wordt uitgevoerd, worden alle andere gerelateerde waarschuwingen die zich voordoen, toegevoegd aan het onderzoek totdat het is voltooid.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="e3aa3-148">Als een belaste entiteit ergens anders wordt gezien, wordt het bereik van het geautomatiseerde onderzoek uitgebreid met die entiteit en wordt er een algemene beveiligings playbook uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3aa3-149">Niet elke waarschuwing activeert een geautomatiseerd onderzoek en niet elk onderzoek resulteert in automatische herstelacties. Dit is allemaal afhankelijk van hoe automatisch onderzoek en antwoorden voor uw organisatie zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e3aa3-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="e3aa3-150">Zie [Mogelijkheden voor geautomatiseerd onderzoek en antwoorden configureren in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="e3aa3-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="e3aa3-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e3aa3-151">Next steps</span></span>

- [<span data-ttu-id="e3aa3-152">Bekijk de vereisten voor geautomatiseerd onderzoek en antwoorden in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3aa3-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="e3aa3-153">Geautomatiseerd onderzoek en automatisch onderzoek voor uw organisatie configureren</span><span class="sxs-lookup"><span data-stu-id="e3aa3-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="e3aa3-154">Meer informatie over het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="e3aa3-154">Learn more about the Action center</span></span>](mtp-action-center.md)
