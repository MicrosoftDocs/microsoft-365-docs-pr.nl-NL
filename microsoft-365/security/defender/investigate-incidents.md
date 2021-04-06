---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Incidenten met betrekking tot apparaten, gebruikers en postvakken analyseren.
keywords: incident, incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592094"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="75eae-104">Incidenten in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="75eae-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75eae-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="75eae-105">**Applies to:**</span></span>

- <span data-ttu-id="75eae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75eae-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75eae-107">Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijzen van al uw apparaten, gebruikers en postvakken om u een uitgebreid overzicht te geven van de hele breedte van een aanval.</span><span class="sxs-lookup"><span data-stu-id="75eae-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="75eae-108">Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat ze betekenen en beslep bewijs dat aan de incidenten is gekoppeld, zodat u een effectief herstelplan kunt bedenken.</span><span class="sxs-lookup"><span data-stu-id="75eae-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="75eae-109">Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="75eae-109">Investigate an incident</span></span>

1. <span data-ttu-id="75eae-110">Selecteer een incident in de wachtrij voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="75eae-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="75eae-111">Een zijpaneel wordt geopend en geeft een voorbeeld van belangrijke informatie, zoals status, ernst, categorieën en de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="75eae-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Afbeelding van het zijpaneel incident](../../media/incident-side-panel.png)

2. <span data-ttu-id="75eae-113">Selecteer **Incidentpagina openen.**</span><span class="sxs-lookup"><span data-stu-id="75eae-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="75eae-114">Hiermee opent u de pagina met incidenten waar u meer informatie vindt over incidentgegevens, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijs).</span><span class="sxs-lookup"><span data-stu-id="75eae-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="75eae-115">Controleer de waarschuwingen, apparaten, gebruikers en andere entiteiten die betrokken zijn bij het incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="75eae-116">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="75eae-116">Incident overview</span></span>

<span data-ttu-id="75eae-117">Op de overzichtspagina ziet u een momentopname van de belangrijkste dingen die u kunt zien over het incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Afbeelding van de overzichtspagina incidenten](../../media/incidents-overview.png)

<span data-ttu-id="75eae-119">De aanvalscategorieën geven u een visuele en numerieke weergave van de voortgang van de aanval ten opzichte van de kill chain.</span><span class="sxs-lookup"><span data-stu-id="75eae-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="75eae-120">Net als bij andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd op het [MITRE ATT-&&trade; CK-framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="75eae-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="75eae-121">In de sectie bereik ziet u een lijst met de belangrijkste beïnvloede activa die deel uitmaken van dit incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="75eae-122">Als er specifieke informatie over dit activum is, zoals risiconiveau, onderzoeksprioriteit en taggen op de activa, wordt dit ook in deze sectie aan de oppervlakte gebracht.</span><span class="sxs-lookup"><span data-stu-id="75eae-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="75eae-123">De tijdlijn voor waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen zijn opgetreden, evenals de redenen waarom deze waarschuwingen zijn gekoppeld aan dit incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="75eae-124">En als laatste: de sectie bewijs bevat een overzicht van het aantal verschillende artefacten dat is opgenomen in het incident en de herstelstatus, zodat u direct kunt vaststellen of er actie moet worden ondernomen aan uw kant.</span><span class="sxs-lookup"><span data-stu-id="75eae-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="75eae-125">Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident dat u moet weten.</span><span class="sxs-lookup"><span data-stu-id="75eae-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="75eae-126">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="75eae-126">Alerts</span></span>

<span data-ttu-id="75eae-127">U kunt alle waarschuwingen bekijken die betrekking hebben op het incident en andere informatie over het incident, zoals ernst, entiteiten die betrokken waren bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365) en de reden waarom ze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="75eae-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Afbeelding van de pagina met incidentenwaarschuwingen](../../media/incident-alerts.png)

<span data-ttu-id="75eae-129">Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval in de tijd is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="75eae-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="75eae-130">Als u op elke waarschuwing klikt, gaat u naar de relevante waarschuwingspagina waar u een uitgebreid onderzoek naar die waarschuwing kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="75eae-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="75eae-131">Informatie over het gebruik van waarschuwingspagina's en de geïntegreerde waarschuwingswachtrij in [Waarschuwingen onderzoeken](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="75eae-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="75eae-132">Apparaten</span><span class="sxs-lookup"><span data-stu-id="75eae-132">Devices</span></span>

<span data-ttu-id="75eae-133">Het tabblad Apparaten bevat alle apparaten waar waarschuwingen met betrekking tot het incident worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="75eae-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="75eae-134">Als u op de naam klikt van de computer waarop de aanval is uitgevoerd, gaat u naar de pagina Machine, waar u waarschuwingen kunt zien die zijn geactiveerd op de computer en gerelateerde gebeurtenissen die zijn verstrekt om het onderzoek te soepeeren.</span><span class="sxs-lookup"><span data-stu-id="75eae-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Afbeelding van het tabblad Machines van een incident](../../media/incident-machines.png)

<span data-ttu-id="75eae-136">Als u het tabblad Tijdlijn selecteert, kunt u door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen op de computer in chronologische volgorde bekijken, afgewisseld met de waarschuwingen die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="75eae-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="75eae-137">U kunt op aanvraag scans uitvoeren op een apparaatpagina.</span><span class="sxs-lookup"><span data-stu-id="75eae-137">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="75eae-138">Kies in het Microsoft 365-beveiligingscentrum de optie **Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="75eae-138">In the Microsoft 365 security center, choose **Device inventory**.</span></span> <span data-ttu-id="75eae-139">Selecteer een apparaat met waarschuwingen en voer een antivirusscan uit.</span><span class="sxs-lookup"><span data-stu-id="75eae-139">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="75eae-140">Acties, zoals antivirusscans, worden bijgespoord en zijn zichtbaar op de **pagina Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="75eae-140">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="75eae-141">Zie Microsoft Defender Antivirus scan uitvoeren [op apparaten voor meer informatie.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="75eae-141">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>


## <a name="users"></a><span data-ttu-id="75eae-142">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="75eae-142">Users</span></span>

<span data-ttu-id="75eae-143">Zie gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaald incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-143">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="75eae-144">Als u op de gebruikersnaam klikt, gaat u naar de pagina Cloud App-beveiliging van de gebruiker, waar verder onderzoek kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="75eae-144">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Afbeelding van het tabblad Gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="75eae-146">Postvakken</span><span class="sxs-lookup"><span data-stu-id="75eae-146">Mailboxes</span></span>

<span data-ttu-id="75eae-147">Onderzoek postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan een incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-147">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="75eae-148">Als u verder onderzoek wilt doen, opent u Microsoft Defender voor Office 365 door de waarschuwing voor e-mail te selecteren, waar u herstelacties kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="75eae-148">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="75eae-150">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="75eae-150">Investigations</span></span>

<span data-ttu-id="75eae-151">Selecteer **Onderzoeken om** alle geautomatiseerde onderzoeken te zien die worden veroorzaakt door waarschuwingen in dit incident.</span><span class="sxs-lookup"><span data-stu-id="75eae-151">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="75eae-152">De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="75eae-152">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Afbeelding van het tabblad Onderzoeken van een incident](../../media/incident-investigations.png)

<span data-ttu-id="75eae-154">Selecteer een onderzoek om naar de pagina Details van het onderzoek te gaan voor volledige informatie over de status van het onderzoek en de herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="75eae-154">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="75eae-155">Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden deze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van het herstellen van incidenten.</span><span class="sxs-lookup"><span data-stu-id="75eae-155">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="75eae-156">Bewijs</span><span class="sxs-lookup"><span data-stu-id="75eae-156">Evidence</span></span>

<span data-ttu-id="75eae-157">Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services, e-mailberichten en meer.</span><span class="sxs-lookup"><span data-stu-id="75eae-157">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="75eae-158">Op deze manier kunt u potentiële bedreigingen in het incident snel opsporen en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="75eae-158">This helps quickly detect and block potential threats in the incident.</span></span>

![Afbeelding van het tabblad Bewijs van een incident](../../media/incident-evidence.png)

<span data-ttu-id="75eae-160">Elk van de geanalyseerde entiteiten wordt gemarkeerd met een vonnis (Schadelijk, Verdacht, Schoon) en een herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="75eae-160">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="75eae-161">Dit helpt u bij het begrijpen van de herstelstatus van het hele incident en wat de volgende stappen zijn die kunnen worden genomen om verder te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="75eae-161">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75eae-162">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="75eae-162">Related topics</span></span>

- [<span data-ttu-id="75eae-163">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="75eae-163">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="75eae-164">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="75eae-164">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="75eae-165">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="75eae-165">Manage incidents</span></span>](manage-incidents.md)

