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
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142691"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="a2c90-104">Herstelacties in Office 365 bekijken en beheren</span><span class="sxs-lookup"><span data-stu-id="a2c90-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="a2c90-105">Wanneer geautomatiseerde onderzoeken op e-& resultaten van samenwerking  resulteren in resultaten, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a2c90-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="a2c90-106">In Microsoft Defender voor Office 365 kunnen herstelacties optreden:</span><span class="sxs-lookup"><span data-stu-id="a2c90-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="a2c90-107">Een URL blokkeren (time-of-click)</span><span class="sxs-lookup"><span data-stu-id="a2c90-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="a2c90-108">E-mailberichten of clusters zacht verwijderen</span><span class="sxs-lookup"><span data-stu-id="a2c90-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="a2c90-109">E-mail- of e-mailbijlagen quarantining</span><span class="sxs-lookup"><span data-stu-id="a2c90-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="a2c90-110">Extern doorsturen van e-mail uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a2c90-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="a2c90-111">Deze herstelacties worden alleen uitgevoerd als het beveiligingsteam ze goedkeurt.</span><span class="sxs-lookup"><span data-stu-id="a2c90-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="a2c90-112">We raden u aan acties die in behandeling zijn zo snel mogelijk te beoordelen en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="a2c90-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="a2c90-113">In sommige gevallen kunt u een herstelactie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="a2c90-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="a2c90-114">Acties in behandeling goedkeuren (of weigeren)</span><span class="sxs-lookup"><span data-stu-id="a2c90-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="a2c90-115">Ga naar het Microsoft 365-beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a2c90-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="a2c90-116">Selecteer Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="a2c90-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="a2c90-117">Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="a2c90-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="a2c90-118">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a2c90-118">Select an item in the list.</span></span> <span data-ttu-id="a2c90-119">Het deelvenster flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="a2c90-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="a2c90-120">Bekijk de informatie in het deelvenster Flyout en ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="a2c90-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="a2c90-121">Selecteer **De pagina Onderzoek openen** om meer details over het onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a2c90-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="a2c90-122">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="a2c90-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="a2c90-123">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="a2c90-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="a2c90-124">Eén herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a2c90-124">Undo one remediation action</span></span>

1. <span data-ttu-id="a2c90-125">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a2c90-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="a2c90-126">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a2c90-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="a2c90-127">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**</span><span class="sxs-lookup"><span data-stu-id="a2c90-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="a2c90-128">Meerdere herstelacties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a2c90-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="a2c90-129">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a2c90-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="a2c90-130">Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a2c90-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="a2c90-131">Zorg ervoor dat u items met hetzelfde actietype selecteert.</span><span class="sxs-lookup"><span data-stu-id="a2c90-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="a2c90-132">Er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="a2c90-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="a2c90-133">Selecteer Ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="a2c90-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="a2c90-134">Een bestand uit quarantaine verwijderen op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="a2c90-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="a2c90-135">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="a2c90-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="a2c90-136">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Quarantaine van het **actietype.**</span><span class="sxs-lookup"><span data-stu-id="a2c90-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="a2c90-137">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand op Toepassen op **X** en selecteer vervolgens **Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="a2c90-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2c90-138">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a2c90-138">Next steps</span></span>

- [<span data-ttu-id="a2c90-139">Bedreigingsverkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="a2c90-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="a2c90-140">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="a2c90-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="a2c90-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a2c90-141">See also</span></span>

- [<span data-ttu-id="a2c90-142">Details en resultaten van een geautomatiseerd onderzoek in Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="a2c90-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
