---
title: Acties weergeven en beheren in het actiecentrum
description: Het actiecentrum gebruiken om herstelacties weer te zien en te beheren
keywords: actie, center, autoair, geautomatiseerd, onderzoek, antwoord, herstel
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7106f5d2e740d2b4cacbcaeb0b9391095bbeb356
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592022"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="a077b-104">Acties weergeven en beheren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="a077b-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a077b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a077b-105">**Applies to:**</span></span>
- <span data-ttu-id="a077b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a077b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a077b-107">Bedreigingsbeveiligingsfuncties in Microsoft 365 Defender kunnen leiden tot bepaalde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="a077b-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="a077b-108">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="a077b-108">Here are some examples:</span></span>
- <span data-ttu-id="a077b-109">[Geautomatiseerde onderzoeken kunnen](m365d-autoir.md) leiden tot herstelacties die automatisch worden ondernomen of die moeten worden goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="a077b-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="a077b-110">Antivirus-, antimalware- en andere functies voor bedreigingsbeveiliging kunnen leiden tot herstelacties, zoals het blokkeren van een bestand, URL of proces of het verzenden van een artefact naar quarantaine.</span><span class="sxs-lookup"><span data-stu-id="a077b-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="a077b-111">Uw beveiligingsteam kan handmatig herstelacties uitvoeren, zoals [](advanced-hunting-overview.md) tijdens geavanceerde zoekacties of tijdens het onderzoeken van [waarschuwingen](investigate-alerts.md) of [incidenten.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="a077b-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a077b-112">U moet de [juiste machtigingen hebben om](m365d-action-center.md#required-permissions-for-action-center-tasks) herstelacties goed te keuren of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="a077b-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="a077b-113">Zie Vereisten voor geautomatiseerd onderzoek en antwoord [in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a077b-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="a077b-114">Acties in behandeling bekijken in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="a077b-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="a077b-115">Het is belangrijk om acties in behandeling zo snel mogelijk goed te keuren (of af te wijzen), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid.</span><span class="sxs-lookup"><span data-stu-id="a077b-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Een actie goedkeuren of weigeren](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="a077b-117">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a077b-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a077b-118">Kies actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="a077b-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a077b-119">Selecteer in het Actiecentrum **op** het tabblad In behandeling een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a077b-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="a077b-120">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="a077b-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="a077b-121">Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="a077b-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="a077b-122">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="a077b-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="a077b-123">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="a077b-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="a077b-124">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="a077b-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="a077b-125">Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a077b-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="a077b-126">Voltooide acties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a077b-126">Undo completed actions</span></span>

<span data-ttu-id="a077b-127">Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn ondernomen, ongeacht of deze acties automatisch of handmatig zijn ondernomen.</span><span class="sxs-lookup"><span data-stu-id="a077b-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="a077b-128">In het actiecentrum op het tabblad **Geschiedenis** kunt u een van de volgende acties ongedaan maken:</span><span class="sxs-lookup"><span data-stu-id="a077b-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="a077b-129">Actiebron</span><span class="sxs-lookup"><span data-stu-id="a077b-129">Action source</span></span> | <span data-ttu-id="a077b-130">Ondersteunde acties</span><span class="sxs-lookup"><span data-stu-id="a077b-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="a077b-131">- Geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="a077b-131">- Automated investigation</span></span> <br/><span data-ttu-id="a077b-132">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a077b-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="a077b-133">- Handmatige antwoordacties</span><span class="sxs-lookup"><span data-stu-id="a077b-133">- Manual response actions</span></span> | <span data-ttu-id="a077b-134">- Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="a077b-134">- Isolate device</span></span> <br/><span data-ttu-id="a077b-135">- Codeuitvoering beperken</span><span class="sxs-lookup"><span data-stu-id="a077b-135">- Restrict code execution</span></span> <br/><span data-ttu-id="a077b-136">- Een bestand in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="a077b-136">- Quarantine a file</span></span> <br/><span data-ttu-id="a077b-137">- Een registersleutel verwijderen</span><span class="sxs-lookup"><span data-stu-id="a077b-137">- Remove a registry key</span></span> <br/><span data-ttu-id="a077b-138">- Een service stoppen</span><span class="sxs-lookup"><span data-stu-id="a077b-138">- Stop a service</span></span> <br/><span data-ttu-id="a077b-139">- Een stuurprogramma uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a077b-139">- Disable a driver</span></span> <br/><span data-ttu-id="a077b-140">- Een geplande taak verwijderen</span><span class="sxs-lookup"><span data-stu-id="a077b-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="a077b-141">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a077b-141">Undo one remediation action</span></span>

1. <span data-ttu-id="a077b-142">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a077b-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="a077b-143">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a077b-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="a077b-144">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**</span><span class="sxs-lookup"><span data-stu-id="a077b-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="a077b-145">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a077b-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="a077b-146">Ga naar het Actiecentrum ( https://security.microsoft.com/action-center) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a077b-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="a077b-147">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a077b-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="a077b-148">Selecteer items met hetzelfde actietype.</span><span class="sxs-lookup"><span data-stu-id="a077b-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="a077b-149">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="a077b-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="a077b-150">Selecteer ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="a077b-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="a077b-151">Een bestand verwijderen uit quarantaine op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="a077b-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="a077b-152">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a077b-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="a077b-153">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="a077b-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="a077b-154">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="a077b-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a077b-155">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a077b-155">Next steps</span></span>

- [<span data-ttu-id="a077b-156">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="a077b-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="a077b-157">Meer informatie over het verwerken van onwaar positieven/negatieven (als u er een krijgt)</span><span class="sxs-lookup"><span data-stu-id="a077b-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
