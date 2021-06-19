---
title: Herstelacties controleren en beheren in Microsoft Defender voor Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028929"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="2c032-104">Herstelacties controleren en beheren in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c032-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="2c032-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2c032-105">**Applies to**</span></span>
- [<span data-ttu-id="2c032-106">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2c032-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="2c032-107">Aangezien geautomatiseerde onderzoeken op e-& samenwerkingsinhoud resulteren  in vonnissen, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2c032-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="2c032-108">In Microsoft Defender voor Office 365 kunnen herstelacties bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="2c032-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="2c032-109">E-mailberichten of clusters verwijderen</span><span class="sxs-lookup"><span data-stu-id="2c032-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="2c032-110">Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="2c032-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="2c032-111">Deze herstelacties worden alleen uitgevoerd als uw beveiligingsbewerkingsteam deze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="2c032-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="2c032-112">We raden u aan alle lopende acties zo snel mogelijk te bekijken en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="2c032-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="2c032-113">In sommige gevallen kunt u ingediende acties opnieuw overwegen.</span><span class="sxs-lookup"><span data-stu-id="2c032-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="2c032-114">U moet deel uitmaken van de zoekfunctie & voordat u acties ondernomen.</span><span class="sxs-lookup"><span data-stu-id="2c032-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="2c032-115">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="2c032-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="2c032-116">Er zijn vier verschillende manieren om acties voor automatisch onderzoek te vinden en uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="2c032-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="2c032-117">Incidentwachtrij</span><span class="sxs-lookup"><span data-stu-id="2c032-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="2c032-118">Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="2c032-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="2c032-119">Onderzoek zelf (toegankelijk via Incident of vanuit een waarschuwing)</span><span class="sxs-lookup"><span data-stu-id="2c032-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="2c032-120">Wachtrij voor onderzoeken en herstelonderzoeken</span><span class="sxs-lookup"><span data-stu-id="2c032-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="2c032-121">Incidentwachtrij</span><span class="sxs-lookup"><span data-stu-id="2c032-121">Incident queue</span></span>
1. <span data-ttu-id="2c032-122">Ga naar het [Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="2c032-123">Selecteer in het navigatiedeelvenster **Incidenten & waarschuwingen > incidenten.**</span><span class="sxs-lookup"><span data-stu-id="2c032-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="2c032-124">Selecteer een incidentnaam om de overzichtspagina te openen.</span><span class="sxs-lookup"><span data-stu-id="2c032-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="2c032-125">Selecteer het **tabblad Bewijs en** antwoord.</span><span class="sxs-lookup"><span data-stu-id="2c032-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="2c032-126">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2c032-126">Select an item in the list.</span></span> <span data-ttu-id="2c032-127">Het zijvenster wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2c032-127">Its side pane opens.</span></span>
6. <span data-ttu-id="2c032-128">In het zijdeelvenster kunt u acties goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="2c032-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="2c032-129">Onderzoekswachtrij</span><span class="sxs-lookup"><span data-stu-id="2c032-129">Investigation queue</span></span> 
1. <span data-ttu-id="2c032-130">Ga naar het [Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="2c032-131">Navigeer vanaf de pagina waarschuwingen/incidenten.</span><span class="sxs-lookup"><span data-stu-id="2c032-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="2c032-132">Ga op de pagina Onderzoek naar het **tabblad Acties in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="2c032-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="2c032-133">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2c032-133">Select an item in the list.</span></span> <span data-ttu-id="2c032-134">Het zijvenster wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2c032-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="2c032-135">In het zijdeelvenster kunt u acties goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="2c032-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="2c032-136">Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="2c032-136">Action center</span></span>
1. <span data-ttu-id="2c032-137">Ga naar het [Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="2c032-138">Selecteer actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="2c032-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="2c032-139">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="2c032-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="2c032-140">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="2c032-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="2c032-141">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="2c032-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="2c032-142">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="2c032-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="2c032-143">Wachtrij voor onderzoeken en herstelonderzoeken</span><span class="sxs-lookup"><span data-stu-id="2c032-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="2c032-144">Ga naar het [Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="2c032-145">Open lopende onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="2c032-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="2c032-146">Ga op de pagina Onderzoek naar het **tabblad Acties in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="2c032-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="2c032-147">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2c032-147">Select an item in the list.</span></span> <span data-ttu-id="2c032-148">Het zijvenster wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2c032-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="2c032-149">In het zijdeelvenster kunt u acties goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="2c032-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="2c032-150">Eén herstelactie wijzigen of ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="2c032-150">Change or undo one remediation action</span></span>

<span data-ttu-id="2c032-151">Er zijn twee verschillende manieren om ingediende acties te herzien:</span><span class="sxs-lookup"><span data-stu-id="2c032-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="2c032-152">Via het [geïntegreerde actiecentrum](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="2c032-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="2c032-153">Hoewel het [Office actiecentrum](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="2c032-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="2c032-154">Wijzigen of ongedaan maken via het geïntegreerde actiecentrum</span><span class="sxs-lookup"><span data-stu-id="2c032-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="2c032-155">Ga naar het [geïntegreerde actiecentrum](https://security.microsoft.com/action-center) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="2c032-156">Selecteer op **het** tabblad Geschiedenis een actie die u wilt wijzigen of ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="2c032-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="2c032-157">Selecteer in het deelvenster aan de rechterkant van het scherm de juiste actie (naar **postvak IN** **gaan,** naar ongewenste e-mail gaan, naar verwijderde **items** gaan , \*\*soft delete" of **hard delete).**</span><span class="sxs-lookup"><span data-stu-id="2c032-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="2c032-158">Wijzigen of ongedaan maken via het Office actiecentrum</span><span class="sxs-lookup"><span data-stu-id="2c032-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="2c032-159">Ga naar het [Office actiecentrum](https://security.microsoft.com/threatincidents) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c032-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="2c032-160">Selecteer de juiste herstel.</span><span class="sxs-lookup"><span data-stu-id="2c032-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="2c032-161">Klik in het zijdeelvenster op de vermelding voor e-mailinzendingen en wacht totdat de lijst wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="2c032-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="2c032-162">Wacht tot de knop Actie bovenaan staat en selecteer de knop Actie om het actietype te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2c032-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="2c032-163">Hierdoor worden de juiste acties aan de dag 2010 genomen.</span><span class="sxs-lookup"><span data-stu-id="2c032-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c032-164">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="2c032-164">Next steps</span></span>

- [<span data-ttu-id="2c032-165">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="2c032-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="2c032-166">Beheer/handmatige acties</span><span class="sxs-lookup"><span data-stu-id="2c032-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="2c032-167">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="2c032-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="2c032-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2c032-168">See also</span></span>

- [<span data-ttu-id="2c032-169">Details en resultaten van een geautomatiseerd onderzoek weergeven in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c032-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
