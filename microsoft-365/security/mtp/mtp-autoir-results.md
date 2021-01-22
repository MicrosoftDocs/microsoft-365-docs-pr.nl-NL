---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Tijdens en na een geautomatiseerd onderzoek kunt u de resultaten en de belangrijkste resultaten bekijken
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, herstel, autoair
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
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930364"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="fa3e4-104">Details en resultaten van een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="fa3e4-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fa3e4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-105">**Applies to:**</span></span>
- <span data-ttu-id="fa3e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa3e4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fa3e4-107">Wanneer een geautomatiseerd onderzoek plaatsvindt in Microsoft 365 Defender, zijn details over dat onderzoek beschikbaar tijdens en na het proces van geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="fa3e4-108">Als u de [benodigde machtigingen hebt,](mtp-action-center.md#required-permissions-for-action-center-tasks)kunt u deze details bekijken in een weergave met details van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="fa3e4-109">De detailweergave voor onderzoek bevat de actuele status en de mogelijkheid om acties die in behandeling zijn goed te keuren.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Details van onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="fa3e4-111">De weergave met onderzoeksgegevens openen</span><span class="sxs-lookup"><span data-stu-id="fa3e4-111">Open the investigation details view</span></span>

<span data-ttu-id="fa3e4-112">U kunt de weergave met onderzoeksgegevens op een van de volgende manieren openen:</span><span class="sxs-lookup"><span data-stu-id="fa3e4-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="fa3e4-113">Een item selecteren in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="fa3e4-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="fa3e4-114">Een onderzoek selecteren op een pagina met incidentdetails</span><span class="sxs-lookup"><span data-stu-id="fa3e4-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="fa3e4-115">Een item selecteren in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="fa3e4-115">Select an item in the Action center</span></span>

<span data-ttu-id="fa3e4-116">Gebruik het Actiecentrum om acties weer te  geven die in behandeling zijn (op het tabblad In behandeling) of die al zijn goedgekeurd (op het **tabblad** Geschiedenis).</span><span class="sxs-lookup"><span data-stu-id="fa3e4-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="fa3e4-117">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="fa3e4-118">Kies Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="fa3e4-119">Selecteer een item **op het** tabblad In behandeling **of** Geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="fa3e4-120">Als u de [benodigde machtigingen hebt,](mtp-action-center.md#required-permissions-for-action-center-tasks)kunt u acties in behandeling goedkeuren (of weigeren).</span><span class="sxs-lookup"><span data-stu-id="fa3e4-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="fa3e4-121">Een onderzoek openen vanaf een pagina met details van een incident</span><span class="sxs-lookup"><span data-stu-id="fa3e4-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="fa3e4-122">Gebruik een pagina met incidentgegevens om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die informatie hebben geactiveerd over getroffen apparaten, gebruikersaccounts of postvakken.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="fa3e4-123">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="fa3e4-124">Kies Incidenten in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="fa3e4-125">Selecteer een item in de lijst om de weergave met details van het incident te openen.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-125">Select an item in the list to open the incident details view.</span></span><br/>![Details van incident](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="fa3e4-127">Selecteer op **het tabblad Onderzoeken** een onderzoek in de lijst.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="fa3e4-128">Details van onderzoek</span><span class="sxs-lookup"><span data-stu-id="fa3e4-128">Investigation details</span></span>

<span data-ttu-id="fa3e4-129">Gebruik de weergave met onderzoeksgegevens om activiteiten uit het verleden, de huidige en in behandeling die betrekking hebben op een onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="fa3e4-130">De weergave met onderzoeksgegevens lijkt op de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="fa3e4-130">The investigation details view resembles the following image:</span></span>

![Details van onderzoek](../../media/mtp-air-investdetails.png)

<span data-ttu-id="fa3e4-132">In de weergave Details van onderzoek kunt u informatie zien in de grafiek Onderzoek,  **Waarschuwingen,**  **Apparaten,** **Identiteiten,** Belangrijkste **bevindingen,** Entiteiten, **Logboek** en Acties in behandeling, die in de volgende tabel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="fa3e4-133">Tab</span><span class="sxs-lookup"><span data-stu-id="fa3e4-133">Tab</span></span> | <span data-ttu-id="fa3e4-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fa3e4-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="fa3e4-135">**Onderzoeksgrafiek**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-135">**Investigation graph**</span></span>   | <span data-ttu-id="fa3e4-136">Biedt een visuele weergave van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="fa3e4-137">Hiermee worden entiteiten en lijsten met gevonden bedreigingen weergegeven, samen met waarschuwingen en of er acties wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="fa3e4-138">U kunt op een item in de grafiek klikken om meer details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="fa3e4-139">Als u bijvoorbeeld op het pictogram **Bedreigingen gevonden** klikt, gaat u naar het tabblad **Belangrijke resultaten.**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="fa3e4-140">**Waarschuwingen**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-140">**Alerts**</span></span>    | <span data-ttu-id="fa3e4-141">Hier worden waarschuwingen vermeld die aan het onderzoek zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="fa3e4-142">Waarschuwingen kunnen afkomstig zijn van functies voor risicobeveiliging op de computer van een gebruiker, in Office-apps, Cloud App-beveiliging en andere functies van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="fa3e4-143">**Apparaten**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-143">**Devices**</span></span> | <span data-ttu-id="fa3e4-144">Vermeldt machines die zijn opgenomen in het onderzoek, samen met het herstelniveau.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="fa3e4-145">**Belangrijkste resultaten**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-145">**Key findings**</span></span>  | <span data-ttu-id="fa3e4-146">Hier vindt u de resultaten van het onderzoek, samen met de status en acties die zijn ondernomen of in behandeling zijn.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="fa3e4-147">U kunt acties in behandeling goedkeuren voor apparaten en identiteiten op dit tabblad.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="fa3e4-148">**Entiteiten**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-148">**Entities**</span></span>  | <span data-ttu-id="fa3e4-149">Bevat gebruikersactiviteiten, bestanden, processen, services, stuurprogramma's, IP-adressen en persistentiemethoden die aan het onderzoek zijn gekoppeld, samen met de status en de ondernomen acties.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="fa3e4-150">**Logboek**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-150">**Log**</span></span>    | <span data-ttu-id="fa3e4-151">Biedt een gedetailleerde weergave van alle stappen die zijn ondernomen tijdens het onderzoek, samen met de status.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="fa3e4-152">**Acties in behandeling**</span><span class="sxs-lookup"><span data-stu-id="fa3e4-152">**Pending actions**</span></span> | <span data-ttu-id="fa3e4-153">Hier worden items vermeld waarvoor goedkeuring is vereist om verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="fa3e4-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="fa3e4-154">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="fa3e4-154">Next steps</span></span>

- [<span data-ttu-id="fa3e4-155">Acties met betrekking tot geautomatiseerd onderzoek en antwoorden goedkeuren of weigeren</span><span class="sxs-lookup"><span data-stu-id="fa3e4-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="fa3e4-156">Herstelacties bekijken</span><span class="sxs-lookup"><span data-stu-id="fa3e4-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
