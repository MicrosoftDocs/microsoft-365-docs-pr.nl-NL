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
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782991"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="4d04c-104">Acties weergeven en beheren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="4d04c-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4d04c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4d04c-105">**Applies to:**</span></span>
- <span data-ttu-id="4d04c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d04c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4d04c-107">Bedreigingsbeveiligingsfuncties in Microsoft 365 Defender kunnen leiden tot bepaalde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="4d04c-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="4d04c-108">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="4d04c-108">Here are some examples:</span></span>

- <span data-ttu-id="4d04c-109">[Geautomatiseerde onderzoeken kunnen](m365d-autoir.md) leiden tot herstelacties die automatisch worden ondernomen of die wachten op uw goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="4d04c-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await your approval.</span></span>
- <span data-ttu-id="4d04c-110">Antivirus-, antimalware- en andere functies voor bedreigingsbeveiliging kunnen leiden tot herstelacties, zoals het blokkeren van een bestand, URL of proces of het verzenden van een artefact naar quarantaine.</span><span class="sxs-lookup"><span data-stu-id="4d04c-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="4d04c-111">Uw beveiligingsteam kan handmatig herstelacties uitvoeren, zoals [](advanced-hunting-overview.md) tijdens geavanceerde zoekacties of tijdens het onderzoeken van [waarschuwingen](investigate-alerts.md) of [incidenten.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="4d04c-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4d04c-112">U moet de [juiste machtigingen hebben om](m365d-action-center.md#required-permissions-for-action-center-tasks) herstelacties goed te keuren of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="4d04c-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="4d04c-113">Zie de vereisten voor [meer informatie.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="4d04c-113">For more information, see the [prerequisites](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="4d04c-114">Acties in behandeling bekijken in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="4d04c-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="4d04c-115">Het is belangrijk om acties in behandeling zo snel mogelijk goed te keuren (of af te wijzen), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid.</span><span class="sxs-lookup"><span data-stu-id="4d04c-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

1. <span data-ttu-id="4d04c-116">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="4d04c-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="4d04c-117">Kies actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="4d04c-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="4d04c-118">Selecteer in het actiecentrum **op** het tabblad In behandeling een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="4d04c-118">In the Action center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="4d04c-119">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="4d04c-119">Its flyout pane opens.</span></span> <span data-ttu-id="4d04c-120">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4d04c-120">Here's an example.</span></span>

   ![Een actie goedkeuren of weigeren](../../media/air-actioncenter-itemselected.png)

4. <span data-ttu-id="4d04c-122">Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="4d04c-122">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="4d04c-123">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="4d04c-123">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="4d04c-124">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="4d04c-124">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="4d04c-125">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="4d04c-125">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="4d04c-126">Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4d04c-126">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="4d04c-127">Voltooide acties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="4d04c-127">Undo completed actions</span></span>

<span data-ttu-id="4d04c-128">Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn ondernomen, ongeacht of deze acties automatisch of handmatig zijn ondernomen.</span><span class="sxs-lookup"><span data-stu-id="4d04c-128">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="4d04c-129">In het actiecentrum op het tabblad **Geschiedenis** kunt u een van de volgende acties ongedaan maken:</span><span class="sxs-lookup"><span data-stu-id="4d04c-129">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="4d04c-130">Actiebron</span><span class="sxs-lookup"><span data-stu-id="4d04c-130">Action source</span></span> | <span data-ttu-id="4d04c-131">Ondersteunde acties</span><span class="sxs-lookup"><span data-stu-id="4d04c-131">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="4d04c-132">- Geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="4d04c-132">- Automated investigation</span></span> <br/><span data-ttu-id="4d04c-133">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="4d04c-133">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="4d04c-134">- Handmatige antwoordacties</span><span class="sxs-lookup"><span data-stu-id="4d04c-134">- Manual response actions</span></span> | <span data-ttu-id="4d04c-135">- Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="4d04c-135">- Isolate device</span></span> <br/><span data-ttu-id="4d04c-136">- Codeuitvoering beperken</span><span class="sxs-lookup"><span data-stu-id="4d04c-136">- Restrict code execution</span></span> <br/><span data-ttu-id="4d04c-137">- Een bestand in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="4d04c-137">- Quarantine a file</span></span> <br/><span data-ttu-id="4d04c-138">- Een registersleutel verwijderen</span><span class="sxs-lookup"><span data-stu-id="4d04c-138">- Remove a registry key</span></span> <br/><span data-ttu-id="4d04c-139">- Een service stoppen</span><span class="sxs-lookup"><span data-stu-id="4d04c-139">- Stop a service</span></span> <br/><span data-ttu-id="4d04c-140">- Een stuurprogramma uitschakelen</span><span class="sxs-lookup"><span data-stu-id="4d04c-140">- Disable a driver</span></span> <br/><span data-ttu-id="4d04c-141">- Een geplande taak verwijderen</span><span class="sxs-lookup"><span data-stu-id="4d04c-141">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="4d04c-142">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="4d04c-142">Undo one remediation action</span></span>

1. <span data-ttu-id="4d04c-143">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="4d04c-143">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="4d04c-144">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="4d04c-144">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="4d04c-145">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**</span><span class="sxs-lookup"><span data-stu-id="4d04c-145">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="4d04c-146">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="4d04c-146">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="4d04c-147">Ga naar het Actiecentrum ( https://security.microsoft.com/action-center) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="4d04c-147">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="4d04c-148">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="4d04c-148">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="4d04c-149">Selecteer items met hetzelfde actietype.</span><span class="sxs-lookup"><span data-stu-id="4d04c-149">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="4d04c-150">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="4d04c-150">A flyout pane opens.</span></span>

3. <span data-ttu-id="4d04c-151">Selecteer ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="4d04c-151">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="4d04c-152">Een bestand verwijderen uit quarantaine op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="4d04c-152">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="4d04c-153">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="4d04c-153">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="4d04c-154">Selecteer op **het** tabblad Geschiedenis een bestand met het actietype **Quarantainebestand.**</span><span class="sxs-lookup"><span data-stu-id="4d04c-154">On the **History** tab, select a file that has a **Quarantine file** Action type.</span></span>

3. <span data-ttu-id="4d04c-155">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="4d04c-155">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d04c-156">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="4d04c-156">Next steps</span></span>

- [<span data-ttu-id="4d04c-157">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="4d04c-157">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="4d04c-158">Fout-positieven of onwaar-negatieven adresseert</span><span class="sxs-lookup"><span data-stu-id="4d04c-158">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
