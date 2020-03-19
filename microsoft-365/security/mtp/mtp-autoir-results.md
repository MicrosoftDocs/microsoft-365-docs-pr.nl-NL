---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Tijdens en na een geautomatiseerd onderzoek u de resultaten en de belangrijkste bevindingen
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, sanering, autoair
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
ms.openlocfilehash: 6b3bc068e5da99e02a64463891e32d137c448d64
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805916"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="6829a-104">Details en resultaten van een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="6829a-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="6829a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6829a-105">**Applies to:**</span></span>
- <span data-ttu-id="6829a-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6829a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6829a-107">Wanneer een geautomatiseerd onderzoek plaatsvindt in Microsoft Threat Protection, zijn details over dat onderzoek beschikbaar tijdens en na het geautomatiseerde onderzoeksproces.</span><span class="sxs-lookup"><span data-stu-id="6829a-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="6829a-108">Als u over de [benodigde machtigingen beschikt,](mtp-action-center.md#required-permissions-for-action-center-tasks)u deze gegevens bekijken in een weergave met onderzoeksdetails.</span><span class="sxs-lookup"><span data-stu-id="6829a-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="6829a-109">De weergave Onderzoeksgegevens biedt u een up-to-date status en de mogelijkheid om lopende acties goed te keuren.</span><span class="sxs-lookup"><span data-stu-id="6829a-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="6829a-111">De weergave Onderzoeksdetails openen</span><span class="sxs-lookup"><span data-stu-id="6829a-111">Open the investigation details view</span></span>

<span data-ttu-id="6829a-112">U de weergave onderzoeksgegevens openen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="6829a-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="6829a-113">Een item selecteren in het onderhoudscentrum</span><span class="sxs-lookup"><span data-stu-id="6829a-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="6829a-114">Een onderzoek selecteren op een pagina met informatie over incidenten</span><span class="sxs-lookup"><span data-stu-id="6829a-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="6829a-115">Een item selecteren in het onderhoudscentrum</span><span class="sxs-lookup"><span data-stu-id="6829a-115">Select an item in the Action center</span></span>

<span data-ttu-id="6829a-116">Gebruik het actiecentrum om acties weer te geven die in behandeling zijn (op het tabblad **In behandeling)** of die al zijn goedgekeurd (op het tabblad **Geschiedenis).**</span><span class="sxs-lookup"><span data-stu-id="6829a-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="6829a-117">Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="6829a-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6829a-118">Kies in het navigatiedeelvenster **het onderhoudscentrum**.</span><span class="sxs-lookup"><span data-stu-id="6829a-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="6829a-119">Selecteer op het tabblad **Inbehandeling** of **Geschiedenis** een item.</span><span class="sxs-lookup"><span data-stu-id="6829a-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="6829a-120">Als u over de [benodigde machtigingen beschikt,](mtp-action-center.md#required-permissions-for-action-center-tasks)u lopende acties goedkeuren (of afwijzen).</span><span class="sxs-lookup"><span data-stu-id="6829a-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="6829a-121">Een onderzoek openen vanaf een pagina met informatie over incidenten</span><span class="sxs-lookup"><span data-stu-id="6829a-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="6829a-122">Gebruik een pagina met incidentgegevens om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die zijn geactiveerd voor informatie over getroffen apparaten, gebruikersaccounts of postvakken.</span><span class="sxs-lookup"><span data-stu-id="6829a-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="6829a-123">Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="6829a-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6829a-124">Kies **incidenten**in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="6829a-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="6829a-125">Selecteer een item in de lijst om de weergave incidentdetails te openen.</span><span class="sxs-lookup"><span data-stu-id="6829a-125">Select an item in the list to open the incident details view.</span></span><br/>![Incidentdetails](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="6829a-127">Selecteer op het tabblad **Onderzoeken** een onderzoek in de lijst.</span><span class="sxs-lookup"><span data-stu-id="6829a-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="6829a-128">Details van het onderzoek</span><span class="sxs-lookup"><span data-stu-id="6829a-128">Investigation details</span></span>

<span data-ttu-id="6829a-129">Gebruik de weergave Onderzoeksgegevens om eerdere, huidige en in behandeling zijnde activiteiten met betrekking tot een onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="6829a-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="6829a-130">De weergave Onderzoeksdetails lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="6829a-130">The investigation details view resembles the following image:</span></span>

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

<span data-ttu-id="6829a-132">In de weergave Onderzoekdetails u informatie zien in de grafiek **Onderzoek**, **Waarschuwingen**, **Apparaten**, **Identiteiten**, **Belangrijkste bevindingen**, **Entiteiten,** **Logboek**en In **behandeling zijnde acties,** beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6829a-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="6829a-133">Tab</span><span class="sxs-lookup"><span data-stu-id="6829a-133">Tab</span></span>    |<span data-ttu-id="6829a-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6829a-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="6829a-135">Onderzoeksgrafiek</span><span class="sxs-lookup"><span data-stu-id="6829a-135">Investigation graph</span></span>    |<span data-ttu-id="6829a-136">Geeft een visuele weergave van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="6829a-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="6829a-137">Hiermee worden entiteiten en lijsten weergegeven die worden gevonden, samen met waarschuwingen en of acties wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="6829a-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="6829a-138">U op een item in de grafiek klikken om meer details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6829a-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="6829a-139">Als u bijvoorbeeld op het pictogram **Bedreigingen hebt gevonden,** gaat u naar het tabblad **Belangrijkste bevindingen.**</span><span class="sxs-lookup"><span data-stu-id="6829a-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="6829a-140">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="6829a-140">Alerts</span></span> |<span data-ttu-id="6829a-141">Geeft lijsten met waarschuwingen die aan het onderzoek zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="6829a-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="6829a-142">Waarschuwingen kunnen afkomstig zijn van functies voor bedreigingsbeveiliging op de machine van een gebruiker, in Office-apps, Cloud App-beveiliging en andere functies voor bedreigingsbeveiliging van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6829a-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="6829a-143">Apparaten</span><span class="sxs-lookup"><span data-stu-id="6829a-143">Devices</span></span>|<span data-ttu-id="6829a-144">Lijsten machines die in het onderzoek zijn opgenomen, samen met het saneringsniveau.</span><span class="sxs-lookup"><span data-stu-id="6829a-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="6829a-145">Belangrijkste bevindingen</span><span class="sxs-lookup"><span data-stu-id="6829a-145">Key findings</span></span>   |<span data-ttu-id="6829a-146">Geeft een overzicht van de resultaten van het onderzoek, samen met de status en de genomen acties of in behandeling zijnde.</span><span class="sxs-lookup"><span data-stu-id="6829a-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="6829a-147">U lopende acties voor apparaten en identiteiten op dit tabblad goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="6829a-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="6829a-148">Entiteiten</span><span class="sxs-lookup"><span data-stu-id="6829a-148">Entities</span></span>   |<span data-ttu-id="6829a-149">Hiermee worden gebruikersactiviteiten, bestanden, processen, services, stuurprogramma's, IP-adressen en persistentiemethoden weergegeven die aan het onderzoek zijn gekoppeld, samen met de status en de genomen acties.</span><span class="sxs-lookup"><span data-stu-id="6829a-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="6829a-150">Log</span><span class="sxs-lookup"><span data-stu-id="6829a-150">Log</span></span>    |<span data-ttu-id="6829a-151">Geeft een gedetailleerd overzicht van alle stappen die tijdens het onderzoek zijn genomen, samen met de status.</span><span class="sxs-lookup"><span data-stu-id="6829a-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="6829a-152">Lopende acties</span><span class="sxs-lookup"><span data-stu-id="6829a-152">Pending actions</span></span>    |<span data-ttu-id="6829a-153">Hiermee worden items weergegeven waarvoor goedkeuring nodig is.</span><span class="sxs-lookup"><span data-stu-id="6829a-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="6829a-154">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="6829a-154">Next steps</span></span>

- [<span data-ttu-id="6829a-155">Een overzicht van machtigingen voor het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="6829a-155">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)

- [<span data-ttu-id="6829a-156">Acties in verband met geautomatiseerd onderzoek en respons goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="6829a-156">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

