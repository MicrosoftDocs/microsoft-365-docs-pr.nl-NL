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
ms.openlocfilehash: 40d0d8a14e0dd340d931a1c43425854b96702c65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407092"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="8b285-104">Herstelacties in Office 365 bekijken en beheren</span><span class="sxs-lookup"><span data-stu-id="8b285-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="8b285-105">Wanneer geautomatiseerde onderzoeken op e-& resultaten van samenwerking  resulteren in resultaten, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8b285-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="8b285-106">In Microsoft Defender voor Office 365 kunnen herstelacties het volgende omvatten:</span><span class="sxs-lookup"><span data-stu-id="8b285-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="8b285-107">Een URL blokkeren (tijd-van-klik)</span><span class="sxs-lookup"><span data-stu-id="8b285-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="8b285-108">E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="8b285-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="8b285-109">E-mail- of e-mailbijlagen quarantining</span><span class="sxs-lookup"><span data-stu-id="8b285-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="8b285-110">Extern doorsturen van e-mail uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8b285-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="8b285-111">Deze herstelacties worden alleen uitgevoerd als het beveiligingsteam ze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="8b285-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="8b285-112">We raden u aan acties die in behandeling zijn zo snel mogelijk te beoordelen en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="8b285-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="8b285-113">In sommige gevallen kunt u een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="8b285-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="8b285-114">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8b285-114">**Applies to**</span></span>
- [<span data-ttu-id="8b285-115">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8b285-115">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8b285-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b285-116">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="8b285-117">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="8b285-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="8b285-118">Ga naar het Microsoft 365-beveiligingscentrum <https://security.microsoft.com> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8b285-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="8b285-119">Selecteer Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="8b285-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="8b285-120">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="8b285-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="8b285-121">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="8b285-121">Select an item in the list.</span></span> <span data-ttu-id="8b285-122">Het deelvenster flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="8b285-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="8b285-123">Bekijk de informatie in het deelvenster Flyout en ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="8b285-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="8b285-124">Selecteer **De pagina Onderzoek openen om** meer details over het onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8b285-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="8b285-125">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="8b285-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="8b285-126">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="8b285-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="8b285-127">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="8b285-127">Undo one remediation action</span></span>

1. <span data-ttu-id="8b285-128">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8b285-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8b285-129">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="8b285-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="8b285-130">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**</span><span class="sxs-lookup"><span data-stu-id="8b285-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="8b285-131">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="8b285-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="8b285-132">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8b285-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8b285-133">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="8b285-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="8b285-134">Zorg ervoor dat u items selecteert met hetzelfde actietype.</span><span class="sxs-lookup"><span data-stu-id="8b285-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="8b285-135">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="8b285-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="8b285-136">Selecteer Ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="8b285-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="8b285-137">Een bestand uit quarantaine verwijderen op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="8b285-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="8b285-138">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8b285-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8b285-139">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Quarantaine van het **actietype.**</span><span class="sxs-lookup"><span data-stu-id="8b285-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="8b285-140">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer vervolgens **Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="8b285-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8b285-141">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8b285-141">Next steps</span></span>

- [<span data-ttu-id="8b285-142">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="8b285-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="8b285-143">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="8b285-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="8b285-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8b285-144">See also</span></span>

- [<span data-ttu-id="8b285-145">Details en resultaten van een geautomatiseerd onderzoek in Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="8b285-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
