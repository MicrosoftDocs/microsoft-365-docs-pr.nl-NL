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
ms.date: 01/29/2021
ms.openlocfilehash: f0c42bef1b090412a7a6422fe029323b645e90df
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275070"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="ec134-104">Herstelacties controleren en beheren in Office 365</span><span class="sxs-lookup"><span data-stu-id="ec134-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="ec134-105">Aangezien geautomatiseerde onderzoeken op e-& samenwerkingsinhoud resulteren  in vonnissen, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ec134-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="ec134-106">In Microsoft Defender voor Office 365 kunnen herstelacties bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="ec134-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="ec134-107">Een URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="ec134-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="ec134-108">E-mailberichten of clusters verwijderen</span><span class="sxs-lookup"><span data-stu-id="ec134-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="ec134-109">E-mail- of e-mailbijlagen quarantining</span><span class="sxs-lookup"><span data-stu-id="ec134-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="ec134-110">Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ec134-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="ec134-111">Deze herstelacties worden alleen uitgevoerd als uw beveiligingsbewerkingsteam deze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="ec134-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="ec134-112">We raden u aan alle lopende acties zo snel mogelijk te bekijken en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="ec134-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="ec134-113">In sommige gevallen kunt u een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="ec134-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="ec134-114">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ec134-114">**Applies to**</span></span>
- [<span data-ttu-id="ec134-115">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ec134-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ec134-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec134-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="ec134-117">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="ec134-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="ec134-118">Ga naar het Microsoft 365 beveiligingscentrum ( <https://security.microsoft.com> ) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="ec134-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="ec134-119">Selecteer actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="ec134-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="ec134-120">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="ec134-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="ec134-121">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ec134-121">Select an item in the list.</span></span> <span data-ttu-id="ec134-122">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="ec134-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="ec134-123">Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="ec134-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="ec134-124">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="ec134-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="ec134-125">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="ec134-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="ec134-126">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="ec134-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="ec134-127">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="ec134-127">Undo one remediation action</span></span>

1. <span data-ttu-id="ec134-128">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="ec134-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ec134-129">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="ec134-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="ec134-130">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**</span><span class="sxs-lookup"><span data-stu-id="ec134-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="ec134-131">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="ec134-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="ec134-132">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="ec134-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ec134-133">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="ec134-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="ec134-134">Selecteer items met hetzelfde actietype.</span><span class="sxs-lookup"><span data-stu-id="ec134-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="ec134-135">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="ec134-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="ec134-136">Selecteer Ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="ec134-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="ec134-137">Een bestand verwijderen uit quarantaine op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="ec134-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="ec134-138">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="ec134-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ec134-139">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="ec134-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="ec134-140">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="ec134-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec134-141">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ec134-141">Next steps</span></span>

- [<span data-ttu-id="ec134-142">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="ec134-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="ec134-143">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="ec134-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="ec134-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ec134-144">See also</span></span>

- [<span data-ttu-id="ec134-145">Details en resultaten van een geautomatiseerd onderzoek weergeven in Office 365</span><span class="sxs-lookup"><span data-stu-id="ec134-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
