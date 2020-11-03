---
title: Gebeurtenissen onderzoeken in Microsoft 365 Defender
description: Analyseren van incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incident, incidenten, computers, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, Graph, bewijzen
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846746"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="ccc74-104">Gebeurtenissen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccc74-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ccc74-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ccc74-105">**Applies to:**</span></span>

- <span data-ttu-id="ccc74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccc74-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ccc74-107">Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, assets, onderzoeken en bewijzen van op uw apparaten, gebruikers en postvakken, zodat u een allesomvattende uitstraling krijgt.</span><span class="sxs-lookup"><span data-stu-id="ccc74-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="ccc74-108">Onderzoek welke meldingen van invloed zijn op uw netwerk, begrijpt wat ze betekenen, en sorteer het bewijs dat u een effectief herstelabonnement kunt opstellen.</span><span class="sxs-lookup"><span data-stu-id="ccc74-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="ccc74-109">Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ccc74-109">Investigate an incident</span></span>

1. <span data-ttu-id="ccc74-110">Selecteer een incident in de wachtrij met incidenten.</span><span class="sxs-lookup"><span data-stu-id="ccc74-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="ccc74-111">Er wordt een deelvenster geopend met een voorbeeld van belangrijke informatie, zoals status, Ernst, categorieën en de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="ccc74-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Afbeelding van het deelvenster incidenten](../../media/incident-side-panel.png)

2. <span data-ttu-id="ccc74-113">Selecteer **incident pagina openen**.</span><span class="sxs-lookup"><span data-stu-id="ccc74-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="ccc74-114">De incident pagina wordt geopend, waar u meer informatie, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoek, bewijs) kunt vinden.</span><span class="sxs-lookup"><span data-stu-id="ccc74-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="ccc74-115">Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="ccc74-116">Overzicht van incident</span><span class="sxs-lookup"><span data-stu-id="ccc74-116">Incident overview</span></span>

<span data-ttu-id="ccc74-117">De pagina overzicht bevat een overzicht van de belangrijkste punten die u moet weten over het incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Afbeelding van de pagina overzicht van incidenten](../../media/incidents-overview.png)

<span data-ttu-id="ccc74-119">De categorieën aanval bieden een visuele en numerieke weergave van de werking van de aanval waarmee de aanval verloopt.</span><span class="sxs-lookup"><span data-stu-id="ccc74-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="ccc74-120">Net als met andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd met de [Mitre &trade; att&verzonken](https://attack.mitre.org/) raam.</span><span class="sxs-lookup"><span data-stu-id="ccc74-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="ccc74-121">De sectie bereik biedt een lijst met de meest voorkomende activa die deel uitmaken van dit incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="ccc74-122">Als er specifieke informatie is over dit activum, zoals risiconiveau, prioriteit van onderzoek en labels voor de activa, wordt dit ook in deze sectie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ccc74-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="ccc74-123">De tijdlijn van waarschuwingen biedt een sneak peek in de chronologische volgorde waarin de waarschuwingen zijn opgetreden, en de redenen waarom deze meldingen zijn gekoppeld aan dit incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="ccc74-124">En last-the documentatie-sectie biedt een overzicht van het aantal verschillende artefacten in het incident en de status van herstel, zodat u direct kunt nagaan of een actie aan uw end is vereist.</span><span class="sxs-lookup"><span data-stu-id="ccc74-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="ccc74-125">Dit overzicht is een overzicht van de belangrijkste kenmerken van het incident waarvan u op de hoogte moet zijn.</span><span class="sxs-lookup"><span data-stu-id="ccc74-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="ccc74-126">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="ccc74-126">Alerts</span></span>

<span data-ttu-id="ccc74-127">U kunt alle meldingen weergeven die zijn gerelateerd aan het incident en andere informatie over de meldingen, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender voor Office 365) en de reden waarop ze zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ccc74-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Afbeelding van de pagina incident waarschuwingen](../../media/incident-alerts.png)

<span data-ttu-id="ccc74-129">Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval gedurende een bepaalde periode wordt afgespeeld.</span><span class="sxs-lookup"><span data-stu-id="ccc74-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="ccc74-130">Als u op een melding klikt, gaat u naar de desbetreffende waarschuwingspagina waar u een uitgebreid onderzoek van de melding kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ccc74-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="ccc74-131">Apparaten</span><span class="sxs-lookup"><span data-stu-id="ccc74-131">Devices</span></span>

<span data-ttu-id="ccc74-132">Op het tabblad apparaten worden alle apparaten weergegeven waarop waarschuwingen met betrekking tot het incident zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ccc74-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="ccc74-133">Als u op de naam van de computer klikt waarop de aanval is uitgevoerd, gaat u naar de pagina met de computer waar u meldingen kunt bekijken die zijn geactiveerd voor de computer en voor gerelateerde gebeurtenissen die zijn ingeschakeld om onderzoek te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="ccc74-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Afbeelding van het tabblad machines van een incident](../../media/incident-machines.png)

<span data-ttu-id="ccc74-135">Als u het tabblad tijdlijn selecteert, kunt u door de tijdlijn op de computer schuiven en alle gebeurtenissen en gedragingen op de computer in chronologische volgorde weergeven, waarbij de waarschuwingen zijn getreden.</span><span class="sxs-lookup"><span data-stu-id="ccc74-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="ccc74-136">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="ccc74-136">Users</span></span>

<span data-ttu-id="ccc74-137">Gebruikers weergeven die zijn geïdentificeerd om deel te nemen aan of die zijn gerelateerd aan een bepaald incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="ccc74-138">Als u op de gebruikersnaam klikt, gaat u naar de pagina beveiliging van de Cloud app van de gebruiker waar u verder onderzoek kunt verrichten.</span><span class="sxs-lookup"><span data-stu-id="ccc74-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Afbeelding van het tabblad gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="ccc74-140">Postbus</span><span class="sxs-lookup"><span data-stu-id="ccc74-140">Mailboxes</span></span>

<span data-ttu-id="ccc74-141">Onderzoek postvakken die zijn geïdentificeerd om deel te nemen aan of die zijn gerelateerd aan een incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="ccc74-142">Om verder onderzoek te doen, wordt het selecteren van de e-mail gerelateerde melding geopend Microsoft Defender voor Office 365, waarop u herstelbewerkingen kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ccc74-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="ccc74-144">Tests</span><span class="sxs-lookup"><span data-stu-id="ccc74-144">Investigations</span></span>

<span data-ttu-id="ccc74-145">Selecteer **onderzoek** om alle geautomatiseerde onderzoeken te zien die zijn geactiveerd door waarschuwingen in dit incident.</span><span class="sxs-lookup"><span data-stu-id="ccc74-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="ccc74-146">Het onderzoek voert herstelacties uit of wacht op goedkeuring van de analist van acties, afhankelijk van de manier waarop u uw geautomatiseerde onderzoek hebt geconfigureerd voor het uitvoeren van Microsoft Defender voor eindpunten en Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccc74-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Afbeelding van het tabblad onderzoek van een incident](../../media/incident-investigations.png)

<span data-ttu-id="ccc74-148">Selecteer een onderzoek om te navigeren naar de pagina met het onderzoeksteam voor volledige informatie over de status van onderzoek en herstel.</span><span class="sxs-lookup"><span data-stu-id="ccc74-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="ccc74-149">Als er voor de goedkeuring een actie is ondergebracht, wordt deze weergegeven in het tabblad acties in behandeling. Onderneem actie als onderdeel van het herstel van incidenten.</span><span class="sxs-lookup"><span data-stu-id="ccc74-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="ccc74-150">Voldoende</span><span class="sxs-lookup"><span data-stu-id="ccc74-150">Evidence</span></span>

<span data-ttu-id="ccc74-151">Microsoft 365 Defender onderzoekt automatisch de ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch antwoord en informatie krijgt over de belangrijkste bestanden, processen, services, e-mailberichten en meer.</span><span class="sxs-lookup"><span data-stu-id="ccc74-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="ccc74-152">Hiermee kunt u potentiële bedreigingen in het incident snel detecteren en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ccc74-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Afbeelding van het tabblad bewijs van een incident](../../media/incident-evidence.png)

<span data-ttu-id="ccc74-154">Alle geanalyseerde entiteiten worden gemarkeerd met een Verdict (kwaadaardige, verdacht, schoon) en een herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="ccc74-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="ccc74-155">Dit helpt u bij de informatie over de herstelstatus van het hele incident en de volgende stappen waarmee u verder kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="ccc74-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccc74-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ccc74-156">Related topics</span></span>

- [<span data-ttu-id="ccc74-157">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="ccc74-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ccc74-158">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="ccc74-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ccc74-159">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="ccc74-159">Manage incidents</span></span>](manage-incidents.md)

