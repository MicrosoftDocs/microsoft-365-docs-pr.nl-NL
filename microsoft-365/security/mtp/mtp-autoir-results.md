---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Wanneer u een geautomatiseerde onderzoek doet, kunt u de resultaten en de belangrijkste bevindingen bekijken
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, Details, herbemiddeling, autoair
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 6d3ffd9f9e28bc190093c19ce9013f9aca12d60e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198859"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="e3e5a-104">Details en resultaten van een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="e3e5a-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3e5a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e3e5a-105">**Applies to:**</span></span>
- <span data-ttu-id="e3e5a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e3e5a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e3e5a-107">Wanneer er een geautomatiseerd onderzoek plaatsvindt in Microsoft Threat Protection, is er informatie over dat onderzoek beschikbaar via en na het geautomatiseerde onderzoek proces.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="e3e5a-108">Als u de [benodigde machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks)hebt, kunt u deze gegevens bekijken in de weergave Details van onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="e3e5a-109">De weergave onderzoek Details biedt u de actuele status en de mogelijkheid om alle in behandeling zijnde acties goed te keuren.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Details van onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="e3e5a-111">De weergave onderzoek Details openen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-111">Open the investigation details view</span></span>

<span data-ttu-id="e3e5a-112">U kunt de weergave Details van onderzoek op een van de volgende manieren openen:</span><span class="sxs-lookup"><span data-stu-id="e3e5a-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="e3e5a-113">Selecteer een item in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="e3e5a-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="e3e5a-114">Selecteer een onderzoek op de pagina Details van incident</span><span class="sxs-lookup"><span data-stu-id="e3e5a-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="e3e5a-115">Selecteer een item in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="e3e5a-115">Select an item in the Action center</span></span>

<span data-ttu-id="e3e5a-116">Gebruik het Actiecentrum om acties weer te geven die goedkeuring in behandeling zijn (op het tabblad **in behandeling** ) of die al is goedgekeurd (op het tabblad **geschiedenis** ).</span><span class="sxs-lookup"><span data-stu-id="e3e5a-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="e3e5a-117">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e3e5a-118">Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="e3e5a-119">Selecteer een item op het tabblad **Onverwerkt** of **geschiedenis** .</span><span class="sxs-lookup"><span data-stu-id="e3e5a-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="e3e5a-120">Als u over de [juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks)beschikt, kunt u acties die in behandeling zijn, goedkeuren of weigeren.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="e3e5a-121">Een onderzoek openen op de pagina Details van incident</span><span class="sxs-lookup"><span data-stu-id="e3e5a-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="e3e5a-122">Gebruik een pagina met incident Details om gedetailleerde informatie over een incident te bekijken, waaronder waarschuwingen die informatie hebben geactiveerd over de betreffende apparaten, gebruikersaccounts of postvakken.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="e3e5a-123">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e3e5a-124">Kies in het navigatiedeelvenster de optie **incidenten**.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="e3e5a-125">Selecteer een item in de lijst om de weergave incident details te openen.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-125">Select an item in the list to open the incident details view.</span></span><br/>![Details van incident](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="e3e5a-127">Selecteer op het tabblad **onderzoek** een onderzoek in de lijst.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="e3e5a-128">Details van onderzoek</span><span class="sxs-lookup"><span data-stu-id="e3e5a-128">Investigation details</span></span>

<span data-ttu-id="e3e5a-129">U kunt de weergave Details van onderzoek gebruiken om eerdere, huidige en activiteiten activiteiten te zien die betrekking hebben op een onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="e3e5a-130">De weergave onderzoek Details lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="e3e5a-130">The investigation details view resembles the following image:</span></span>

![Details van onderzoek](../../media/mtp-air-investdetails.png)

<span data-ttu-id="e3e5a-132">In de weergave Details van onderzoek kunt u informatie weergeven over de tabbladen **onderzoek grafiek**, **waarschuwingen**, **apparaten**, **identiteiten**, **belangrijke bevindingen**, **entiteiten**, **Logboeken**en **acties in behandeling** , zoals in de volgende tabel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="e3e5a-133">Tabblad</span><span class="sxs-lookup"><span data-stu-id="e3e5a-133">Tab</span></span>    |<span data-ttu-id="e3e5a-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e3e5a-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="e3e5a-135">Onderzoek grafiek</span><span class="sxs-lookup"><span data-stu-id="e3e5a-135">Investigation graph</span></span>    |<span data-ttu-id="e3e5a-136">Geeft een visuele voorstelling van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="e3e5a-137">Geeft een voorbeeld weer van de weergave van de bedreigingen en lijsten</span><span class="sxs-lookup"><span data-stu-id="e3e5a-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="e3e5a-138">U kunt op een item in de grafiek klikken om meer informatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="e3e5a-139">Als u bijvoorbeeld op het pictogram **bedreigingen gevonden** klikt, gaat u naar het tabblad **belangrijkste bevindingen** .</span><span class="sxs-lookup"><span data-stu-id="e3e5a-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="e3e5a-140">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-140">Alerts</span></span> |<span data-ttu-id="e3e5a-141">Hier vindt u een overzicht van de waarschuwingen bij het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="e3e5a-142">Waarschuwingen zijn afkomstig van functies voor bedreigingsbeveiliging op de computer van een gebruiker, in Office-apps, de beveiliging van Cloud apps en andere functies van Microsoft 365 Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="e3e5a-143">Apparaten</span><span class="sxs-lookup"><span data-stu-id="e3e5a-143">Devices</span></span>|<span data-ttu-id="e3e5a-144">Lijst met machines die in het onderzoek zijn opgenomen, samen met het herstelniveau.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="e3e5a-145">Belangrijkste bevindingen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-145">Key findings</span></span>   |<span data-ttu-id="e3e5a-146">Dit bevat een overzicht van de resultaten van het onderzoek samen met de status en de beschikbare acties of in behandeling.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="e3e5a-147">Op dit tabblad kunt u acties in behandeling voor apparaten en identiteiten goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="e3e5a-148">Onderzoeksinstellingen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-148">Entities</span></span>   |<span data-ttu-id="e3e5a-149">Hier vindt u een lijst van gebruikersactiviteiten, bestanden, processen, services, Stuurprogramma's, IP-adressen, en permanente methoden voor het onderzoek, en over de status van de uitgevoerde acties.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="e3e5a-150">Inloggen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-150">Log</span></span>    |<span data-ttu-id="e3e5a-151">Een gedetailleerde weergave van alle stappen die tijdens het onderzoek zijn verricht, en de status.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="e3e5a-152">Acties in behandeling</span><span class="sxs-lookup"><span data-stu-id="e3e5a-152">Pending actions</span></span>    |<span data-ttu-id="e3e5a-153">Een lijst met items die moeten worden goedgekeurd om te worden voortgezet.</span><span class="sxs-lookup"><span data-stu-id="e3e5a-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="e3e5a-154">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-154">Next steps</span></span>

- [<span data-ttu-id="e3e5a-155">Acties met betrekking tot een automatisch onderzoek en antwoord goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="e3e5a-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

