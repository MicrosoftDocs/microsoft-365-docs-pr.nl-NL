---
title: Waarschuwingen controleren in Microsoft Defender voor Eindpunt
description: Bekijk waarschuwingsgegevens, inclusief een gevisualiseerd waarschuwingsverhaal en details voor elke stap van de keten.
keywords: incident, incidenten, machines, apparaten, gebruikers, waarschuwingen, waarschuwing, onderzoek, grafiek, bewijs
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844020"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a08b2-104">Waarschuwingen controleren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a08b2-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a08b2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a08b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="a08b2-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a08b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="a08b2-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a08b2-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a08b2-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a08b2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="a08b2-109">De waarschuwingspagina in Microsoft Defender voor Eindpunt biedt volledige context voor de waarschuwing door aanvalssignalen en waarschuwingen met betrekking tot de geselecteerde waarschuwing te combineren om een gedetailleerd waarschuwingsverhaal te maken.</span><span class="sxs-lookup"><span data-stu-id="a08b2-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="a08b2-110">Maak snel een triage, onderzoek en onderneemt effectieve actie bij waarschuwingen die van invloed zijn op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a08b2-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="a08b2-111">Begrijp waarom ze zijn geactiveerd en hun impact vanaf één locatie.</span><span class="sxs-lookup"><span data-stu-id="a08b2-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="a08b2-112">Meer informatie in dit overzicht.</span><span class="sxs-lookup"><span data-stu-id="a08b2-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="a08b2-113">Aan de slag met een waarschuwing</span><span class="sxs-lookup"><span data-stu-id="a08b2-113">Getting started with an alert</span></span>

<span data-ttu-id="a08b2-114">Als u de naam van een waarschuwing selecteert in Defender voor Eindpunt, wordt u op de waarschuwingspagina geplaatst.</span><span class="sxs-lookup"><span data-stu-id="a08b2-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="a08b2-115">Op de waarschuwingspagina worden alle gegevens weergegeven in de context van de geselecteerde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="a08b2-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="a08b2-116">Elke waarschuwingspagina bestaat uit 4 secties:</span><span class="sxs-lookup"><span data-stu-id="a08b2-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="a08b2-117">**De waarschuwingstitel** toont de naam van de waarschuwing en is er om u eraan te herinneren welke waarschuwing uw huidige onderzoek is gestart, ongeacht wat u op de pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a08b2-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="a08b2-118">[**Getroffen assets**](#review-affected-assets) bevat kaarten van apparaten en gebruikers die door deze waarschuwing worden beïnvloed en die klikbaar zijn voor meer informatie en acties.</span><span class="sxs-lookup"><span data-stu-id="a08b2-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="a08b2-119">In **het waarschuwingsverhaal** worden alle entiteiten weergegeven die betrekking hebben op de waarschuwing, verbonden door een boomweergave.</span><span class="sxs-lookup"><span data-stu-id="a08b2-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="a08b2-120">De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt.</span><span class="sxs-lookup"><span data-stu-id="a08b2-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="a08b2-121">Entiteiten in het waarschuwingsverhaal kunnen worden uitgebreid en erop klikken om aanvullende informatie te verstrekken en de reactie te versnellen doordat u acties kunt uitvoeren in de context van de waarschuwingspagina.</span><span class="sxs-lookup"><span data-stu-id="a08b2-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="a08b2-122">Gebruik het waarschuwingsverhaal om uw onderzoek te starten.</span><span class="sxs-lookup"><span data-stu-id="a08b2-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="a08b2-123">Lees hoe u waarschuwingen [kunt onderzoeken in Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="a08b2-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="a08b2-124">In **het detailvenster** worden eerst de details van de geselecteerde waarschuwing weergegeven, met details en acties met betrekking tot deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="a08b2-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="a08b2-125">Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt het detailvenster gewijzigd in contextuele informatie en acties voor het geselecteerde object.</span><span class="sxs-lookup"><span data-stu-id="a08b2-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="a08b2-126">Noteer de detectiestatus voor uw waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="a08b2-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="a08b2-127">Voorkomen: de poging tot verdachte actie is vermeden.</span><span class="sxs-lookup"><span data-stu-id="a08b2-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="a08b2-128">Een bestand is bijvoorbeeld niet op schijf geschreven of uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a08b2-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="a08b2-129">![Een waarschuwingspagina met bedreiging is voorkomen](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="a08b2-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="a08b2-130">Geblokkeerd: verdacht gedrag is uitgevoerd en vervolgens geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="a08b2-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="a08b2-131">Een proces is bijvoorbeeld uitgevoerd, maar omdat het vervolgens verdacht gedrag vertoonde, is het proces beëindigd.</span><span class="sxs-lookup"><span data-stu-id="a08b2-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="a08b2-132">![Een waarschuwingspagina met bedreiging is geblokkeerd](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="a08b2-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="a08b2-133">Gedetecteerd: er is een aanval gedetecteerd en is mogelijk nog actief.</span><span class="sxs-lookup"><span data-stu-id="a08b2-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="a08b2-134">![Er is een waarschuwingspagina met bedreiging gedetecteerd](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="a08b2-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="a08b2-135">U kunt vervolgens ook de geautomatiseerde onderzoeksdetails *bekijken* in het detailvenster van uw waarschuwing, om te zien welke acties al zijn ondernomen en de beschrijving van de waarschuwing voor aanbevolen acties te lezen.</span><span class="sxs-lookup"><span data-stu-id="a08b2-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Een fragment van het detailvenster met de waarschuwingsbeschrijving en de secties voor automatisch onderzoek gemarkeerd](images/alert-air-and-alert-description.png)

<span data-ttu-id="a08b2-137">Andere informatie die beschikbaar is in het detailvenster wanneer de waarschuwing wordt geopend, omvat MITRE-technieken, bron en aanvullende contextuele details.</span><span class="sxs-lookup"><span data-stu-id="a08b2-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="a08b2-138">Beïnvloede activa controleren</span><span class="sxs-lookup"><span data-stu-id="a08b2-138">Review affected assets</span></span>

<span data-ttu-id="a08b2-139">Als u een apparaat of een gebruikerskaart selecteert in de betreffende activasecties, schakelt u over naar de details van het apparaat of de gebruiker in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="a08b2-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="a08b2-140">**Voor apparaten** worden in het detailvenster gegevens over het apparaat zelf weergegeven, zoals Domein, Besturingssysteem en IP.</span><span class="sxs-lookup"><span data-stu-id="a08b2-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="a08b2-141">Actieve waarschuwingen en de aangemelde gebruikers op dat apparaat zijn ook beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a08b2-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="a08b2-142">U kunt direct actie ondernemen door het apparaat te isoleren, de uitvoering van apps te beperken of een antivirusscan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a08b2-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="a08b2-143">U kunt ook een onderzoekspakket verzamelen, een geautomatiseerd onderzoek starten of naar de apparaatpagina gaan om het te onderzoeken vanuit het oogpunt van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a08b2-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Een fragment van het detailvenster wanneer een apparaat is geselecteerd](images/device-page-details.png)

- <span data-ttu-id="a08b2-145">**Voor gebruikers** worden in het detailvenster gedetailleerde gebruikersgegevens weergegeven, zoals de SAM-naam en de SID van de gebruiker, evenals aanmeldingstypen die door deze gebruiker zijn uitgevoerd en eventuele waarschuwingen en incidenten die hiermee verband houden.</span><span class="sxs-lookup"><span data-stu-id="a08b2-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="a08b2-146">U kunt *Gebruikerspagina openen selecteren om* het onderzoek voort te zetten vanuit het standpunt van die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a08b2-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Een fragment van het detailvenster wanneer een gebruiker is geselecteerd](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="a08b2-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a08b2-148">Related topics</span></span>

- [<span data-ttu-id="a08b2-149">De wachtrij voor incidenten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="a08b2-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="a08b2-150">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a08b2-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a08b2-151">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="a08b2-151">Manage incidents</span></span>](manage-incidents.md)
