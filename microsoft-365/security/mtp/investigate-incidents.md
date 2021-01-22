---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Analyseer incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incident, incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
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
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926892"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="16731-104">Incidenten in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="16731-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="16731-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="16731-105">**Applies to:**</span></span>

- <span data-ttu-id="16731-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16731-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="16731-107">Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijsstukken van al uw apparaten, gebruikers en postvakken, zodat u een uitgebreid overzicht krijgt van de volledige breedte van een aanval.</span><span class="sxs-lookup"><span data-stu-id="16731-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="16731-108">Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat deze betekenen en bewaa gegevens die bij de incidenten horen, zodat u een effectief herstelplan kunt bedenken.</span><span class="sxs-lookup"><span data-stu-id="16731-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="16731-109">Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="16731-109">Investigate an incident</span></span>

1. <span data-ttu-id="16731-110">Selecteer een incident in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="16731-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="16731-111">Er wordt een zijpaneel geopend met een voorbeeld van belangrijke informatie, zoals status, ernst, categorieën en de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="16731-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Afbeelding van het zijpaneel voor incidenten](../../media/incident-side-panel.png)

2. <span data-ttu-id="16731-113">Selecteer **Incidentpagina openen.**</span><span class="sxs-lookup"><span data-stu-id="16731-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="16731-114">Hiermee opent u de pagina voor incidenten, waar u meer informatie over incidenten, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijs) vindt.</span><span class="sxs-lookup"><span data-stu-id="16731-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="16731-115">Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.</span><span class="sxs-lookup"><span data-stu-id="16731-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="16731-116">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="16731-116">Incident overview</span></span>

<span data-ttu-id="16731-117">Op de overzichtspagina ziet u een momentopname van de belangrijkste dingen die u moet zien over het incident.</span><span class="sxs-lookup"><span data-stu-id="16731-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Afbeelding van de overzichtspagina voor incidenten](../../media/incidents-overview.png)

<span data-ttu-id="16731-119">De aanvalscategorieën geven u een visuele en numerieke weergave van hoe geavanceerd de aanval is vorderen ten opzichte van de kill chain.</span><span class="sxs-lookup"><span data-stu-id="16731-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="16731-120">Microsoft 365 Defender is, net als andere beveiligingsproducten van Microsoft, afgestemd op de [MITRE ATT &trade;&CK-framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="16731-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="16731-121">De sectie Bereik bevat een lijst met belangrijkste beïnvloede activa die deel uitmaken van dit incident.</span><span class="sxs-lookup"><span data-stu-id="16731-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="16731-122">Als er specifieke informatie over deze activum is, zoals risiconiveau, prioriteit van het onderzoek en labelen op de assets, wordt dit ook in deze sectie be gegeven.</span><span class="sxs-lookup"><span data-stu-id="16731-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="16731-123">De tijdlijn met waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen hebben plaatsgevonden, evenals de redenen waarom deze waarschuwingen aan dit incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="16731-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="16731-124">Ten laatste bevat de informatiesectie een overzicht van hoeveel verschillende artefacten bij het incident zijn betrokken en wat de herstelstatus is, zodat u onmiddellijk kunt bepalen of er aan uw kant actie moet worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="16731-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="16731-125">Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te bieden in de belangrijkste kenmerken van het incident waar u rekening mee moet houden.</span><span class="sxs-lookup"><span data-stu-id="16731-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="16731-126">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="16731-126">Alerts</span></span>

<span data-ttu-id="16731-127">U kunt alle waarschuwingen met betrekking tot het incident en andere informatie over deze meldingen weergeven, zoals ernst, entiteiten die zijn betrokken bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365) en de reden waarom deze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="16731-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Afbeelding van de pagina voor incidentenwaarschuwingen](../../media/incident-alerts.png)

<span data-ttu-id="16731-129">Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval in de tijd heeft afgespeeld.</span><span class="sxs-lookup"><span data-stu-id="16731-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="16731-130">Als u op een waarschuwing klikt, wordt u naar de relevante waarschuwingspagina geleid, waar u een uitgebreid onderzoek naar die waarschuwing kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="16731-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="16731-131">Apparaten</span><span class="sxs-lookup"><span data-stu-id="16731-131">Devices</span></span>

<span data-ttu-id="16731-132">Het tabblad Apparaten bevat alle apparaten waarop waarschuwingen met betrekking tot het incident worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="16731-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="16731-133">Als u op de naam klikt van de computer waarop de aanval is uitgevoerd, gaat u naar de pagina Computer van de computer waar u waarschuwingen kunt zien die hierop zijn geactiveerd en gerelateerde gebeurtenissen die zijn verstrekt om onderzoek te gemakt.</span><span class="sxs-lookup"><span data-stu-id="16731-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Afbeelding van het tabblad computers van een incident](../../media/incident-machines.png)

<span data-ttu-id="16731-135">Als u het tabblad Tijdlijn selecteert, kunt u door de tijdlijn van de computer bladeren en alle gebeurtenissen en het gedrag op de computer in chronologische volgorde bekijken, afgewisseld met de waarschuwingen omhoog.</span><span class="sxs-lookup"><span data-stu-id="16731-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="16731-136">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="16731-136">Users</span></span>

<span data-ttu-id="16731-137">Bekijk gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaald incident.</span><span class="sxs-lookup"><span data-stu-id="16731-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="16731-138">Als u op de gebruikersnaam klikt, gaat u naar de pagina Cloud-app-beveiliging van de gebruiker, waar nader onderzoek kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="16731-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Afbeelding van het tabblad Gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="16731-140">Postvakken</span><span class="sxs-lookup"><span data-stu-id="16731-140">Mailboxes</span></span>

<span data-ttu-id="16731-141">Onderzoek postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan een incident.</span><span class="sxs-lookup"><span data-stu-id="16731-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="16731-142">Als u nog meer werk wilt doen, opent u Microsoft Defender voor Office 365 wanneer u de e-mailwaarschuwing selecteert, waar u herstelacties kunt ondernemen.</span><span class="sxs-lookup"><span data-stu-id="16731-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="16731-144">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="16731-144">Investigations</span></span>

<span data-ttu-id="16731-145">Selecteer **Onderzoeken om** alle geautomatiseerde onderzoeken te zien die zijn geactiveerd door waarschuwingen in dit incident.</span><span class="sxs-lookup"><span data-stu-id="16731-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="16731-146">De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring van acties door analisten, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="16731-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Afbeelding van het tabblad Onderzoeken van een incident](../../media/incident-investigations.png)

<span data-ttu-id="16731-148">Selecteer een onderzoek om naar de pagina met onderzoeksgegevens te gaan voor volledige informatie over het onderzoek en de herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="16731-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="16731-149">Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden ze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van de oplossing voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="16731-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="16731-150">Bewijs</span><span class="sxs-lookup"><span data-stu-id="16731-150">Evidence</span></span>

<span data-ttu-id="16731-151">Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services, e-mails en meer.</span><span class="sxs-lookup"><span data-stu-id="16731-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="16731-152">Hiermee kunt u potentiële bedreigingen in het incident snel detecteren en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="16731-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Afbeelding van het tabblad Bewijs van een incident](../../media/incident-evidence.png)

<span data-ttu-id="16731-154">Elk van de geanalyseerde entiteiten wordt gemarkeerd met een uitspraak (Schadelijk, Verdacht, Opsschoon), evenals een herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="16731-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="16731-155">Dit helpt u inzicht te krijgen in de herstelstatus van het hele incident en wat de volgende stappen zijn die kunnen worden ondernomen om het incident verder te herstellen.</span><span class="sxs-lookup"><span data-stu-id="16731-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="16731-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="16731-156">Related topics</span></span>

- [<span data-ttu-id="16731-157">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="16731-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="16731-158">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="16731-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="16731-159">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="16731-159">Manage incidents</span></span>](manage-incidents.md)

