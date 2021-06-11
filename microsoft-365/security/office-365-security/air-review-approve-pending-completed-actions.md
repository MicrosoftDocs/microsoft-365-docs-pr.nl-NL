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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904126"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="5f7c4-104">Herstelacties controleren en beheren in Office 365</span><span class="sxs-lookup"><span data-stu-id="5f7c4-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="5f7c4-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="5f7c4-105">**Applies to**</span></span>
- [<span data-ttu-id="5f7c4-106">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5f7c4-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5f7c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f7c4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5f7c4-108">Aangezien geautomatiseerde onderzoeken op e-& samenwerkingsinhoud resulteren  in vonnissen, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="5f7c4-109">In Microsoft Defender voor Office 365 kunnen herstelacties bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="5f7c4-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="5f7c4-110">Een URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="5f7c4-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="5f7c4-111">E-mailberichten of clusters verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f7c4-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="5f7c4-112">E-mail- of e-mailbijlagen quarantining</span><span class="sxs-lookup"><span data-stu-id="5f7c4-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="5f7c4-113">Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="5f7c4-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="5f7c4-114">Deze herstelacties worden alleen uitgevoerd als uw beveiligingsbewerkingsteam deze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="5f7c4-115">We raden u aan alle lopende acties zo snel mogelijk te bekijken en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="5f7c4-116">In sommige gevallen kunt u een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="5f7c4-117">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="5f7c4-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="5f7c4-118">Ga naar de Microsoft 365 Defender-portal <https://security.microsoft.com> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="5f7c4-119">Selecteer actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="5f7c4-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="5f7c4-120">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="5f7c4-121">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-121">Select an item in the list.</span></span> <span data-ttu-id="5f7c4-122">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="5f7c4-123">Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="5f7c4-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="5f7c4-124">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="5f7c4-125">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="5f7c4-126">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="5f7c4-127">Eén herstelactie wijzigen of ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="5f7c4-127">Change or undo one remediation action</span></span>

1. <span data-ttu-id="5f7c4-128">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="5f7c4-129">Selecteer op **het** tabblad Geschiedenis een actie die u wilt wijzigen of ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-129">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="5f7c4-130">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**</span><span class="sxs-lookup"><span data-stu-id="5f7c4-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="change-or-undo-multiple-remediation-actions"></a><span data-ttu-id="5f7c4-131">Meerdere herstelacties wijzigen of ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="5f7c4-131">Change or undo multiple remediation actions</span></span>

1. <span data-ttu-id="5f7c4-132">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="5f7c4-133">Selecteer op **het** tabblad Geschiedenis de acties die u wilt wijzigen of ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-133">On the **History** tab, select the actions that you want to change or undo.</span></span> <span data-ttu-id="5f7c4-134">Selecteer items met hetzelfde actietype.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="5f7c4-135">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="5f7c4-136">Selecteer Ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="5f7c4-137">Een bestand verwijderen uit quarantaine op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="5f7c4-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="5f7c4-138">Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="5f7c4-139">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="5f7c4-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="5f7c4-140">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="5f7c4-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5f7c4-141">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="5f7c4-141">Next steps</span></span>

- [<span data-ttu-id="5f7c4-142">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="5f7c4-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="5f7c4-143">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="5f7c4-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="5f7c4-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5f7c4-144">See also</span></span>

- [<span data-ttu-id="5f7c4-145">Details en resultaten van een geautomatiseerd onderzoek weergeven in Office 365</span><span class="sxs-lookup"><span data-stu-id="5f7c4-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
