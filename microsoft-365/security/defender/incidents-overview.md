---
title: Incidenten in Microsoft 365 Defender
description: Incidenten op verschillende apparaten, gebruikers en postvakken onderzoeken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759492"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="66173-104">Incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66173-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66173-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="66173-105">**Applies to:**</span></span>
- <span data-ttu-id="66173-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66173-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="66173-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="66173-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="66173-108">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="66173-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="66173-109">Een incident in Microsoft 365 Defender is een verzameling van gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten.</span><span class="sxs-lookup"><span data-stu-id="66173-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="66173-110">Microsoft 365-services en -apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren.</span><span class="sxs-lookup"><span data-stu-id="66173-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="66173-111">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval.</span><span class="sxs-lookup"><span data-stu-id="66173-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="66173-112">Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="66173-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="66173-113">Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="66173-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="66173-114">Omdat het lastig en tijdrovend kan zijn om de afzonderlijke waarschuwingen samen te cirkelen om inzicht te krijgen in een aanval, worden de waarschuwingen en de bijbehorende informatie automatisch samengevoegd tot een incident.</span><span class="sxs-lookup"><span data-stu-id="66173-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hoe Microsoft 365 Defender gebeurtenissen van entiteiten correleert in een incident":::

<span data-ttu-id="66173-116">Bekijk dit korte overzicht van incidenten in Microsoft 365 Defender (4 minuten).</span><span class="sxs-lookup"><span data-stu-id="66173-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="66173-117">Door gerelateerde waarschuwingen in een incident te groeperen, krijgt u een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="66173-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="66173-118">U kunt bijvoorbeeld het volgende zien:</span><span class="sxs-lookup"><span data-stu-id="66173-118">For example, you can see:</span></span>

- <span data-ttu-id="66173-119">Waar de aanval is begonnen.</span><span class="sxs-lookup"><span data-stu-id="66173-119">Where the attack started.</span></span>
- <span data-ttu-id="66173-120">Welke tactieken zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="66173-120">What tactics were used.</span></span>
- <span data-ttu-id="66173-121">Hoe ver de aanval is gegaan in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="66173-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="66173-122">Het bereik van de aanval, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="66173-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="66173-123">Alle gegevens die aan de aanval zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="66173-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="66173-124">Als [dit is ingeschakeld,](m365d-enable.md)kan Microsoft 365 Defender automatisch waarschuwingen onderzoeken en oplossen via automatisering en kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="66173-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="66173-125">U kunt ook aanvullende herstelstappen uitvoeren om de aanval op te lossen.</span><span class="sxs-lookup"><span data-stu-id="66173-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="66173-126">Incidenten en waarschuwingen in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="66173-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="66173-127">U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle lancering van het Microsoft 365-beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="66173-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="66173-128">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="66173-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="De pagina Incidenten in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="66173-130">Als u een incidentnaam selecteert, wordt een overzicht van het incident weergegeven en krijgt u toegang tot tabbladen met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="66173-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="66173-132">De extra tabbladen voor een incident zijn:</span><span class="sxs-lookup"><span data-stu-id="66173-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="66173-133">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="66173-133">Alerts</span></span> 

  <span data-ttu-id="66173-134">Alle waarschuwingen met betrekking tot het incident en de bijbehorende informatie.</span><span class="sxs-lookup"><span data-stu-id="66173-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="66173-135">Apparaten</span><span class="sxs-lookup"><span data-stu-id="66173-135">Devices</span></span>

  <span data-ttu-id="66173-136">Alle apparaten die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="66173-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="66173-137">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="66173-137">Users</span></span>

  <span data-ttu-id="66173-138">Alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="66173-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="66173-139">Postvakken</span><span class="sxs-lookup"><span data-stu-id="66173-139">Mailboxes</span></span>

  <span data-ttu-id="66173-140">Alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="66173-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="66173-141">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="66173-141">Investigations</span></span>

  <span data-ttu-id="66173-142">Alle automatische onderzoeken die worden veroorzaakt door waarschuwingen bij het incident.</span><span class="sxs-lookup"><span data-stu-id="66173-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="66173-143">Bewijs en antwoord</span><span class="sxs-lookup"><span data-stu-id="66173-143">Evidence and Response</span></span>

  <span data-ttu-id="66173-144">Alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.</span><span class="sxs-lookup"><span data-stu-id="66173-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="66173-145">Hier is de relatie tussen een incident en de gegevens en de tabbladen van een incident in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="66173-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="De relatie van een incident en de gegevens ervan met de tabbladen van een incident in het Microsoft 365-beveiligingscentrum":::

## <a name="next-step"></a><span data-ttu-id="66173-147">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="66173-147">Next step</span></span>

<span data-ttu-id="66173-148">De incidentenwachtrij van de pagina **Incidenten** bevat de meest recente incidenten.</span><span class="sxs-lookup"><span data-stu-id="66173-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="66173-149">Hier kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="66173-149">From here, you can:</span></span>

- <span data-ttu-id="66173-150">Bekijk welke incidenten prioriteit [moeten krijgen op](incident-queue.md) basis van ernst en andere factoren.</span><span class="sxs-lookup"><span data-stu-id="66173-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="66173-151">Voer een [onderzoek uit](investigate-incidents.md) naar een incident.</span><span class="sxs-lookup"><span data-stu-id="66173-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="66173-152">[Beheer incidenten,](manage-incidents.md)waaronder het wijzigen van de naam, het toewijzen, classificeren en toevoegen van tags voor uw werkstroom voor incidentbeheer.</span><span class="sxs-lookup"><span data-stu-id="66173-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
