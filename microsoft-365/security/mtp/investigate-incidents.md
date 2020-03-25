---
title: Incidenten in Microsoft Threat Protection onderzoeken
description: Analyseer incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928960"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="53209-104">Incidenten in Microsoft Threat Protection onderzoeken</span><span class="sxs-lookup"><span data-stu-id="53209-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="53209-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="53209-105">**Applies to:**</span></span>

- <span data-ttu-id="53209-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="53209-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="53209-107">Microsoft Threat Protection verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijsmateriaal van al uw apparaten, gebruikers en postvakken om u een uitgebreide blik te geven op de gehele breedte van een aanval.</span><span class="sxs-lookup"><span data-stu-id="53209-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="53209-108">Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat ze betekenen en verwerk bewijsmateriaal in verband met de incidenten, zodat u een effectief herstelplan opstellen.</span><span class="sxs-lookup"><span data-stu-id="53209-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="53209-109">Onderzoek een incident</span><span class="sxs-lookup"><span data-stu-id="53209-109">Investigate an incident</span></span>

1. <span data-ttu-id="53209-110">Selecteer een incident in de wachtrij voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="53209-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="53209-111">Hiermee wordt een zijpaneel geopend en wordt een voorbeeld gegeven van belangrijke informatie zoals status, ernst, categorieën en de getroffen entiteiten.</span><span class="sxs-lookup"><span data-stu-id="53209-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Afbeelding van het zijpaneel van incident](../../media/incident-side-panel.png)

2. <span data-ttu-id="53209-113">Selecteer **De pagina Incident openen openen**.</span><span class="sxs-lookup"><span data-stu-id="53209-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="53209-114">Hiermee wordt de incidentpagina geopend waar u meer informatie vindt over incidentdetails, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijsmateriaal).</span><span class="sxs-lookup"><span data-stu-id="53209-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="53209-115">Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.</span><span class="sxs-lookup"><span data-stu-id="53209-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="53209-116">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="53209-116">Incident overview</span></span>

<span data-ttu-id="53209-117">De overzichtspagina geeft u een momentopname van de belangrijkste dingen om op te merken over het incident.</span><span class="sxs-lookup"><span data-stu-id="53209-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Afbeelding van de overzichtspagina voor incidenten](../../media/incidents-overview.png)

<span data-ttu-id="53209-119">De aanvalscategorieën geven u een visueel en numeriek beeld van hoe geavanceerd de aanval is gevorderd tegen de kill chain.</span><span class="sxs-lookup"><span data-stu-id="53209-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="53209-120">Net als bij andere Microsoft-beveiligingsproducten is Microsoft Threat Protection afgestemd op het [MITRE&trade; ATT-&CK-framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="53209-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="53209-121">De sectie scope geeft u een lijst met de belangrijkste getroffen activa die deel uitmaken van dit incident.</span><span class="sxs-lookup"><span data-stu-id="53209-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="53209-122">Als er specifieke informatie over dit actief, zoals risiconiveau, onderzoek prioriteit evenals eventuele tagging op de activa zal dit ook naar boven komen in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="53209-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="53209-123">De tijdlijn van waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen hebben plaatsgevonden, evenals de redenen waarom deze waarschuwingen verband houden met dit incident.</span><span class="sxs-lookup"><span data-stu-id="53209-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="53209-124">En ten slotte - het bewijs sectie biedt een samenvatting van hoeveel verschillende artefacten werden opgenomen in het incident en hun herstelstatus, zodat u onmiddellijk identificeren of er actie nodig is aan uw kant.</span><span class="sxs-lookup"><span data-stu-id="53209-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="53209-125">Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident waar u zich bewust van moet zijn.</span><span class="sxs-lookup"><span data-stu-id="53209-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="53209-126">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="53209-126">Alerts</span></span>

<span data-ttu-id="53209-127">U alle waarschuwingen met betrekking tot het incident en andere informatie over het incident bekijken, zoals ernst, entiteiten die betrokken waren bij de waarschuwing, de bron van de waarschuwingen (Azure ATP, Microsoft Defender ATP, Office 365 ATP) en de reden waarom ze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="53209-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span>

![Afbeelding van de pagina incidentmeldingen](../../media/incident-alerts.png)

<span data-ttu-id="53209-129">Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst zien hoe de aanval in de loop van de tijd is afgespeeld.</span><span class="sxs-lookup"><span data-stu-id="53209-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="53209-130">Als u op elke waarschuwing klikt, leidt u naar de relevante waarschuwingspagina waar u een diepgaand onderzoek naar die waarschuwing uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="53209-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="53209-131">Apparaten</span><span class="sxs-lookup"><span data-stu-id="53209-131">Devices</span></span>

<span data-ttu-id="53209-132">Op het tabblad Apparaten worden alle apparaten weergegeven waar waarschuwingen met betrekking tot het incident worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="53209-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="53209-133">Als u op de naam klikt van de machine waar de aanval is uitgevoerd, navigeert u naar de machinepagina, waar u waarschuwingen zien die erop zijn geactiveerd en gerelateerde gebeurtenissen die worden verstrekt om het onderzoek te vergemakkelijken.</span><span class="sxs-lookup"><span data-stu-id="53209-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Afbeelding van het tabblad machines van een incident](../../media/incident-machines.png)

<span data-ttu-id="53209-135">Als u het tabblad Tijdlijn selecteert, u door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen die op de machine worden waargenomen in chronologische volgorde bekijken, afgewisseld met de opgehaalde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="53209-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="53209-136">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="53209-136">Users</span></span>

<span data-ttu-id="53209-137">Bekijk gebruikers waarvan is vastgesteld dat ze deel uitmaken van of gerelateerd zijn aan een bepaald incident.</span><span class="sxs-lookup"><span data-stu-id="53209-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="53209-138">Als u op de gebruikersnaam klikt, navigeert u naar de cloud-appbeveiligingspagina van de gebruiker, waar verder onderzoek kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="53209-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Afbeelding van het tabblad gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="53209-140">Postvakken</span><span class="sxs-lookup"><span data-stu-id="53209-140">Mailboxes</span></span>

<span data-ttu-id="53209-141">Onderzoek postvakken waarvan is vastgesteld dat ze deel uitmaken van of gerelateerd zijn aan een incident.</span><span class="sxs-lookup"><span data-stu-id="53209-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="53209-142">Als u verder onderzoekswerk wilt doen, opent u de waarschuwing voor e-mailgerelateerde meldingen van Office 365 Advanced Threat Protection, waar u herstelacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="53209-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>

![Afbeelding van het postvaktabblad van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="53209-144">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="53209-144">Investigations</span></span>

<span data-ttu-id="53209-145">Selecteer **Onderzoeken** om alle geautomatiseerde onderzoeken te zien die worden geactiveerd door waarschuwingen in dit incident.</span><span class="sxs-lookup"><span data-stu-id="53209-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="53209-146">De onderzoeken voeren herstelacties uit of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd om uit te voeren in Microsoft Defender ATP en Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="53209-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![Afbeelding van het tabblad onderzoeken van een incident](../../media/incident-investigations.png)

<span data-ttu-id="53209-148">Selecteer een onderzoek om naar de pagina Details van het Onderzoek te navigeren om volledige informatie over de status van het onderzoek en de herstelstatus te krijgen.</span><span class="sxs-lookup"><span data-stu-id="53209-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="53209-149">Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden ze weergegeven op het tabblad In behandeling zijnde acties. Onderneem actie als onderdeel van incidentherstel.</span><span class="sxs-lookup"><span data-stu-id="53209-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="53209-150">Bewijs</span><span class="sxs-lookup"><span data-stu-id="53209-150">Evidence</span></span>

<span data-ttu-id="53209-151">Microsoft Threat Protection onderzoekt automatisch de ondersteunde gebeurtenissen en verdachte entiteiten van alle incidenten in de waarschuwingen, zodat u automatisch wordt gereageerd en informatie krijgt over de belangrijke bestanden, processen, services, e-mails en meer.</span><span class="sxs-lookup"><span data-stu-id="53209-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="53209-152">Dit helpt bij het snel detecteren en blokkeren van potentiële bedreigingen in het incident.</span><span class="sxs-lookup"><span data-stu-id="53209-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Afbeelding van het bewijstabblad van een incident](../../media/incident-evidence.png)

<span data-ttu-id="53209-154">Elk van de geanalyseerde entiteiten zal worden gemarkeerd met een vonnis (Kwaadaardig, Verdacht, Schoon) en een herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="53209-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="53209-155">Dit helpt u bij het begrijpen van de herstelstatus van het gehele incident en wat de volgende stappen zijn die kunnen worden genomen om verder te herstellen.</span><span class="sxs-lookup"><span data-stu-id="53209-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="53209-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="53209-156">Related topics</span></span>

- [<span data-ttu-id="53209-157">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="53209-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="53209-158">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="53209-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="53209-159">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="53209-159">Manage incidents</span></span>](manage-incidents.md)

