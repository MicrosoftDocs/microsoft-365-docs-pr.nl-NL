---
title: Herstelacties in Microsoft Defender voor Office 365 bekijken en beheren
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 Abonnement 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: a11e9ee6a4c2426951fe2b4aa4f2dd08d1931f1c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287111"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="71355-104">Herstelacties in Office 365 bekijken en beheren</span><span class="sxs-lookup"><span data-stu-id="71355-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="71355-105">Wanneer geautomatiseerde onderzoeken op e-& resultaten van samenwerking  resulteren in resultaten, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="71355-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="71355-106">In Microsoft Defender voor Office 365 kunnen herstelacties optreden:</span><span class="sxs-lookup"><span data-stu-id="71355-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="71355-107">Een URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="71355-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="71355-108">E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="71355-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="71355-109">E-mail- of e-mailbijlagen quarantining</span><span class="sxs-lookup"><span data-stu-id="71355-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="71355-110">Extern doorsturen van e-mail uitschakelen</span><span class="sxs-lookup"><span data-stu-id="71355-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="71355-111">Deze herstelacties worden pas ondernomen als het beveiligingsteam ze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="71355-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="71355-112">We raden u aan acties die in behandeling zijn zo snel mogelijk te beoordelen en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="71355-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="71355-113">In sommige gevallen kunt u een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="71355-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="71355-114">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="71355-114">**Applies to**</span></span>
- [<span data-ttu-id="71355-115">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="71355-115">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="71355-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71355-116">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="71355-117">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="71355-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="71355-118">Ga naar het Microsoft 365-beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="71355-118">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="71355-119">Selecteer Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="71355-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="71355-120">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="71355-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="71355-121">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="71355-121">Select an item in the list.</span></span> <span data-ttu-id="71355-122">Het deelvenster flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="71355-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="71355-123">Controleer de informatie in het deelvenster Flyout en ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="71355-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="71355-124">Selecteer **De pagina Onderzoek openen om** meer details over het onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="71355-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="71355-125">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="71355-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="71355-126">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="71355-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="71355-127">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="71355-127">Undo one remediation action</span></span>

1. <span data-ttu-id="71355-128">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="71355-128">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="71355-129">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="71355-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="71355-130">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**</span><span class="sxs-lookup"><span data-stu-id="71355-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="71355-131">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="71355-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="71355-132">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="71355-132">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="71355-133">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="71355-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="71355-134">Zorg ervoor dat u items met hetzelfde actietype selecteert.</span><span class="sxs-lookup"><span data-stu-id="71355-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="71355-135">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="71355-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="71355-136">Selecteer Ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="71355-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="71355-137">Een bestand uit quarantaine verwijderen op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="71355-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="71355-138">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="71355-138">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="71355-139">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine.**</span><span class="sxs-lookup"><span data-stu-id="71355-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="71355-140">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer vervolgens **Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="71355-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="71355-141">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="71355-141">Next steps</span></span>

- [<span data-ttu-id="71355-142">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="71355-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="71355-143">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="71355-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="71355-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="71355-144">See also</span></span>

- [<span data-ttu-id="71355-145">Details en resultaten van een geautomatiseerd onderzoek in Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="71355-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
