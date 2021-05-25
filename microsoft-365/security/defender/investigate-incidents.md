---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Incidenten met betrekking tot apparaten, gebruikers en postvakken onderzoeken.
keywords: incident, incidenten, analyseren, reactie, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
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
ms.openlocfilehash: 865aa9dc34a91be251d6f7772da5cc686f9641a4
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651309"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="0cebf-104">Incidenten in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0cebf-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0cebf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0cebf-105">**Applies to:**</span></span>

- <span data-ttu-id="0cebf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cebf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0cebf-107">Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijs van al uw apparaten, gebruikers en postvakken tot een incident om u een uitgebreid overzicht te geven van de hele breedte van een aanval.</span><span class="sxs-lookup"><span data-stu-id="0cebf-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="0cebf-108">In een incident analyseert u de waarschuwingen die van invloed zijn op uw netwerk, begrijpt u wat ze betekenen en colleert u het bewijs zodat u een effectief herstelplan kunt maken.</span><span class="sxs-lookup"><span data-stu-id="0cebf-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="0cebf-109">Eerste onderzoek</span><span class="sxs-lookup"><span data-stu-id="0cebf-109">Initial investigation</span></span>

<span data-ttu-id="0cebf-110">Voordat u de details bekijkt, bekijkt u de eigenschappen en samenvatting van het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="0cebf-111">U kunt beginnen met het selecteren van het incident in de kolom vinkje.</span><span class="sxs-lookup"><span data-stu-id="0cebf-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="0cebf-112">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Voorbeeld van het selecteren van een incident in de kolom vinkje":::

<span data-ttu-id="0cebf-114">Wanneer u dit doet, wordt een overzichtsvenster geopend met belangrijke informatie over het incident, zoals ernst, aan wie het is toegewezen en de [MITRE-att-&CK-categorieën &trade; ](https://attack.mitre.org/) voor het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="0cebf-115">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Voorbeeld van het overzichtsvenster voor een incident":::

<span data-ttu-id="0cebf-117">Hier kunt u Incidentpagina **openen selecteren.**</span><span class="sxs-lookup"><span data-stu-id="0cebf-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="0cebf-118">Hiermee opent u de hoofdpagina voor het incident, waar u meer overzichtsinformatie en tabbladen vindt voor waarschuwingen, apparaten, gebruikers, onderzoeken en bewijs.</span><span class="sxs-lookup"><span data-stu-id="0cebf-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="0cebf-119">U kunt ook de hoofdpagina voor een incident openen door de naam van het incident te selecteren in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="0cebf-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="0cebf-120">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="0cebf-120">Summary</span></span>

<span data-ttu-id="0cebf-121">Op **de** pagina Overzicht ziet u een momentopname van de belangrijkste dingen die u van het incident kunt zien.</span><span class="sxs-lookup"><span data-stu-id="0cebf-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="0cebf-123">De aanvalscategorieën geven u een visuele en numerieke weergave van de voortgang van de aanval ten opzichte van de kill chain.</span><span class="sxs-lookup"><span data-stu-id="0cebf-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="0cebf-124">Net als bij andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd op het [MITRE ATT-&&trade; CK-framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="0cebf-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="0cebf-125">In de sectie bereik ziet u een lijst met de belangrijkste beïnvloede activa die deel uitmaken van dit incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="0cebf-126">Als er specifieke informatie over dit activum is, zoals risiconiveau, onderzoeksprioriteit en taggen op de activa, wordt dit ook in deze sectie aan de oppervlakte gebracht.</span><span class="sxs-lookup"><span data-stu-id="0cebf-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="0cebf-127">De tijdlijn met waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen zijn opgetreden, evenals de redenen waarom deze waarschuwingen zijn gekoppeld aan dit incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="0cebf-128">En als laatste: de sectie bewijs bevat een overzicht van het aantal verschillende artefacten dat is opgenomen in het incident en de herstelstatus, zodat u direct kunt vaststellen of u actie moet ondernemen.</span><span class="sxs-lookup"><span data-stu-id="0cebf-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="0cebf-129">Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident waar u rekening mee moet houden.</span><span class="sxs-lookup"><span data-stu-id="0cebf-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="0cebf-130">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="0cebf-130">Alerts</span></span>

<span data-ttu-id="0cebf-131">Op het **tabblad** Waarschuwing kunt u de waarschuwingswachtrij weergeven voor waarschuwingen met betrekking tot het incident en andere informatie over het incident, zoals:</span><span class="sxs-lookup"><span data-stu-id="0cebf-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="0cebf-132">Ernst.</span><span class="sxs-lookup"><span data-stu-id="0cebf-132">Severity.</span></span>
- <span data-ttu-id="0cebf-133">De entiteiten die betrokken waren bij de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="0cebf-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="0cebf-134">De bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="0cebf-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="0cebf-135">De reden waarom ze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-135">The reason they were linked together.</span></span>

<span data-ttu-id="0cebf-136">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Voorbeeld van een pagina Waarschuwingen voor een incident":::

<span data-ttu-id="0cebf-138">Standaard worden de waarschuwingen chronologisch geordend, zodat u kunt zien hoe het incident zich in de tijd heeft afgespeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="0cebf-139">Wanneer u een waarschuwing selecteert binnen een incident, Microsoft 365 Defender de waarschuwingsgegevens die specifiek zijn voor de context van het algemene incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="0cebf-140">U kunt de gebeurtenissen van de waarschuwing zien, welke andere geactiveerde waarschuwingen de huidige waarschuwing hebben veroorzaakt, en alle betrokken entiteiten en activiteiten die betrokken zijn bij de aanval, waaronder bestanden, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="0cebf-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="0cebf-141">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Voorbeeld van een waarschuwingsgegevenspagina binnen een incident":::

<span data-ttu-id="0cebf-143">Deze pagina met incidentenmelding bestaat uit de volgende secties:</span><span class="sxs-lookup"><span data-stu-id="0cebf-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="0cebf-144">Waarschuwingsverhaal, met een overzicht van wat er is gebeurd</span><span class="sxs-lookup"><span data-stu-id="0cebf-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="0cebf-145">Gerelateerde gebeurtenissen en waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="0cebf-145">Related events and alerts</span></span>
- <span data-ttu-id="0cebf-146">Overzichtsdetails</span><span class="sxs-lookup"><span data-stu-id="0cebf-146">Summary details</span></span>

<span data-ttu-id="0cebf-147">Lees hoe u de waarschuwingswachtrij en waarschuwingspagina's kunt gebruiken in [waarschuwingen onderzoeken.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0cebf-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="0cebf-148">Apparaten</span><span class="sxs-lookup"><span data-stu-id="0cebf-148">Devices</span></span>

<span data-ttu-id="0cebf-149">Op **het** tabblad Apparaten vindt u alle apparaten die met het incident te maken hebben.</span><span class="sxs-lookup"><span data-stu-id="0cebf-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="0cebf-150">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Voorbeeld van een pagina Apparaten voor een incident":::

<span data-ttu-id="0cebf-152">U kunt het vinkje voor een apparaat selecteren om details van het apparaat, adreslijstgegevens, actieve waarschuwingen en aangemelde gebruikers te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0cebf-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="0cebf-153">Selecteer de naam van het apparaat om apparaatgegevens weer te geven in de apparaatvoorraad van Microsoft Defender for Endpoints.</span><span class="sxs-lookup"><span data-stu-id="0cebf-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Voorbeeld van een pagina met apparaten voor Microsoft Defender voor eindpunten":::

<span data-ttu-id="0cebf-155">Op de apparaatpagina kunt u aanvullende informatie over het apparaat verzamelen, zoals alle waarschuwingen, een tijdlijn en beveiligingsaanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="0cebf-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="0cebf-156">Op het tabblad  Tijdlijn kunt u bijvoorbeeld door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen bekijken die op de computer in chronologische volgorde worden waargenomen, afgewisseld met de waarschuwingen die zijn opgeheven.</span><span class="sxs-lookup"><span data-stu-id="0cebf-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="0cebf-157">U kunt op aanvraag scans uitvoeren op een apparaatpagina.</span><span class="sxs-lookup"><span data-stu-id="0cebf-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="0cebf-158">Kies in Microsoft 365 beveiligingscentrum de optie **Eindpunten > Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="0cebf-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="0cebf-159">Selecteer een apparaat met waarschuwingen en voer een antivirusscan uit.</span><span class="sxs-lookup"><span data-stu-id="0cebf-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="0cebf-160">Acties, zoals antivirusscans, worden bijgespoord en zijn zichtbaar op de **pagina Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="0cebf-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="0cebf-161">Zie De scan uitvoeren [Microsoft Defender Antivirus apparaten voor meer informatie.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="0cebf-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="0cebf-162">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="0cebf-162">Users</span></span>

<span data-ttu-id="0cebf-163">Het **tabblad** Gebruikers bevat alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="0cebf-164">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

<span data-ttu-id="0cebf-166">U kunt het vinkje selecteren voor een gebruiker om details van de bedreiging, blootstelling en contactgegevens van het gebruikersaccount te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0cebf-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="0cebf-167">Selecteer de gebruikersnaam om meer details van het gebruikersaccount te zien.</span><span class="sxs-lookup"><span data-stu-id="0cebf-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="0cebf-168">Meer informatie over het weergeven van aanvullende gebruikersgegevens en het beheren van de gebruikers van een incident in [het onderzoeken van gebruikers.](investigate-users.md)</span><span class="sxs-lookup"><span data-stu-id="0cebf-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="0cebf-169">Postvakken</span><span class="sxs-lookup"><span data-stu-id="0cebf-169">Mailboxes</span></span>

<span data-ttu-id="0cebf-170">Het **tabblad Postvakken** bevat alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="0cebf-171">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Voorbeeld van een pagina Postvakken voor een incident":::

<span data-ttu-id="0cebf-173">U kunt het vinkje voor een postvak selecteren om een lijst met actieve waarschuwingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0cebf-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="0cebf-174">Selecteer de naam van het postvak om extra postvakgegevens te zien op de explorerpagina voor Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="0cebf-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="0cebf-175">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0cebf-175">Investigations</span></span>

<span data-ttu-id="0cebf-176">Het **tabblad Onderzoeken** bevat alle geautomatiseerde onderzoeken [die](m365d-autoir.md) worden veroorzaakt door waarschuwingen bij dit incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="0cebf-177">De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="0cebf-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Voorbeeld van een pagina Onderzoeken voor een incident":::

<span data-ttu-id="0cebf-179">Selecteer een onderzoek om naar de pagina Details van het onderzoek te gaan voor volledige informatie over de status van het onderzoek en de herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="0cebf-179">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="0cebf-180">Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden deze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van het herstellen van incidenten.</span><span class="sxs-lookup"><span data-stu-id="0cebf-180">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="0cebf-181">Zie Geautomatiseerd onderzoek en antwoord [in Microsoft 365 Defender voor meer informatie.](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="0cebf-181">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="0cebf-182">Bewijs en antwoord</span><span class="sxs-lookup"><span data-stu-id="0cebf-182">Evidence and Response</span></span>

<span data-ttu-id="0cebf-183">Op **het tabblad Bewijs** en antwoord ziet u alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-183">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="0cebf-184">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-184">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Voorbeeld van een pagina Bewijs en antwoord voor een incident":::

<span data-ttu-id="0cebf-186">Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u informatie krijgt over de belangrijke e-mailberichten, bestanden, processen, services, IP-adressen en meer.</span><span class="sxs-lookup"><span data-stu-id="0cebf-186">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="0cebf-187">Op deze manier kunt u potentiële bedreigingen in het incident snel opsporen en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0cebf-187">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="0cebf-188">Elk van de geanalyseerde entiteiten is gemarkeerd met een vonnis (Schadelijk, Verdacht, Schoon) en een herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="0cebf-188">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="0cebf-189">Op deze manier begrijpt u de herstelstatus van het hele incident en welke volgende stappen u kunt ondernemen.</span><span class="sxs-lookup"><span data-stu-id="0cebf-189">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="0cebf-190">Graph (in voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="0cebf-190">Graph (in preview)</span></span>

<span data-ttu-id="0cebf-191">Met het nieuwe **Graph** (in voorbeeld), kunt u het volgende zien:</span><span class="sxs-lookup"><span data-stu-id="0cebf-191">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="0cebf-192">De verbinding van waarschuwingen met de beïnvloede activa in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0cebf-192">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="0cebf-193">Welke entiteiten zijn gerelateerd aan welke waarschuwingen en hoe ze deel uitmaken van het verhaal van de aanval.</span><span class="sxs-lookup"><span data-stu-id="0cebf-193">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="0cebf-194">De waarschuwingen voor het incident.</span><span class="sxs-lookup"><span data-stu-id="0cebf-194">The alerts for the incident.</span></span>

<span data-ttu-id="0cebf-195">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0cebf-195">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Voorbeeld van een Graph pagina voor een incident":::

<span data-ttu-id="0cebf-197">De incidentgrafiek helpt u snel het volledige bereik van de aanval te begrijpen door de verschillende verdachte entiteiten die deel uitmaken van de aanval te verbinden met hun gerelateerde assets, zoals gebruikers, apparaten en postvakken.</span><span class="sxs-lookup"><span data-stu-id="0cebf-197">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="0cebf-198">U kunt nu begrijpen hoe de aanval zich in de afgelopen tijd via uw netwerk heeft verspreid, waar de aanval is gestart en hoe ver de aanval is gegaan.</span><span class="sxs-lookup"><span data-stu-id="0cebf-198">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0cebf-199">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="0cebf-199">Next steps</span></span>

<span data-ttu-id="0cebf-200">Zo nodig:</span><span class="sxs-lookup"><span data-stu-id="0cebf-200">As needed:</span></span>

- [<span data-ttu-id="0cebf-201">De waarschuwingen van een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0cebf-201">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="0cebf-202">De gebruikers van een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0cebf-202">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="0cebf-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0cebf-203">See also</span></span>

- [<span data-ttu-id="0cebf-204">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="0cebf-204">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0cebf-205">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="0cebf-205">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="0cebf-206">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="0cebf-206">Manage incidents</span></span>](manage-incidents.md)

