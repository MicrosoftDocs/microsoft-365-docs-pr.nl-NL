---
title: Acties die in behandeling zijn na een geautomatiseerd onderzoek goedkeuren of weigeren
description: Het Actiecentrum gebruiken om acties te beheren met betrekking tot geautomatiseerd onderzoek en antwoorden
keywords: actie, center, autoair, geautomatiseerd, onderzoek, reactie, herstel
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
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930376"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="0dc52-104">Acties die in behandeling zijn na een geautomatiseerd onderzoek goedkeuren of weigeren</span><span class="sxs-lookup"><span data-stu-id="0dc52-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0dc52-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0dc52-105">**Applies to:**</span></span>
- <span data-ttu-id="0dc52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0dc52-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0dc52-107">Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit leiden tot een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) waarvoor goedkeuring is vereist om verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="0dc52-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="0dc52-108">Bijvoorbeeld: een cluster e-mailberichten moet mogelijk worden verwijderd of een in quarantaine geplaatst bestand moet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0dc52-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="0dc52-109">Het is belangrijk dat u acties in behandeling zo snel mogelijk goed (of afkeurt) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid.</span><span class="sxs-lookup"><span data-stu-id="0dc52-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="0dc52-110">Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en antwoordfuncties in Microsoft 365 Defender, laat het ons dan weten.</span><span class="sxs-lookup"><span data-stu-id="0dc52-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="0dc52-111">Zie Hoe u fout-positieven/negatieven rapporteert in mogelijkheden voor geautomatiseerd onderzoek en reactie [(AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="0dc52-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="0dc52-112">Acties die in behandeling zijn, kunnen worden beoordeeld en goedgekeurd in het [Actiecentrum](#review-a-pending-action-in-the-action-center) of in de [weergave met details van het onderzoek.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="0dc52-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="0dc52-113">U moet de [juiste machtigingen hebben om](mtp-action-center.md#required-permissions-for-action-center-tasks) herstelacties goed of af te keuren.</span><span class="sxs-lookup"><span data-stu-id="0dc52-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="0dc52-114">Zie Vereisten voor geautomatiseerd onderzoek en antwoorden [in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0dc52-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="0dc52-115">Een actie in behandeling controleren in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="0dc52-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="0dc52-116">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0dc52-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="0dc52-117">Kies Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="0dc52-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="0dc52-118">Selecteer een item in de lijst in **het** actiecentrum op het tabblad In behandeling.</span><span class="sxs-lookup"><span data-stu-id="0dc52-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="0dc52-119">Als u een item selecteert in de kolom **Voor onderzoek,** wordt de pagina met details van het onderzoek geopend.</span><span class="sxs-lookup"><span data-stu-id="0dc52-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="0dc52-120">Daar kunt u de resultaten van het onderzoek bekijken en vervolgens de aanbevolen actie goedkeuren of weigeren.</span><span class="sxs-lookup"><span data-stu-id="0dc52-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="0dc52-121">Als u een rij in de lijst selecteert, wordt een flyout geopend waarin u informatie over dat item kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="0dc52-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Een actie goedkeuren of weigeren](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="0dc52-123">Gebruik de koppelingen om een bijbehorende waarschuwing of een onderzoek weer te geven en de actie goed of af te keuren.</span><span class="sxs-lookup"><span data-stu-id="0dc52-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="0dc52-124">Een actie in behandeling bekijken in de weergave details van het onderzoek</span><span class="sxs-lookup"><span data-stu-id="0dc52-124">Review a pending action in the investigation details view</span></span>

![Details van onderzoek](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="0dc52-126">Selecteer op [een detailpagina voor](mtp-autoir-results.md) onderzoek het tabblad **Acties** in behandeling. Items die nog moeten worden goedgekeurd, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0dc52-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="0dc52-127">Selecteer een item in de lijst en kies Vervolgens **Goedkeuren** of **Weigeren.**</span><span class="sxs-lookup"><span data-stu-id="0dc52-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="0dc52-128">Voltooide acties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="0dc52-128">Undo completed actions</span></span>

<span data-ttu-id="0dc52-129">Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn gemaakt, ongeacht of deze acties automatisch of handmatig zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0dc52-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="0dc52-130">In het actiecentrum kunt u op het **tabblad Geschiedenis** de volgende acties ongedaan maken:</span><span class="sxs-lookup"><span data-stu-id="0dc52-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="0dc52-131">Actiebron</span><span class="sxs-lookup"><span data-stu-id="0dc52-131">Action source</span></span> | <span data-ttu-id="0dc52-132">Ondersteunde acties</span><span class="sxs-lookup"><span data-stu-id="0dc52-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="0dc52-133">- Automatisch onderzoek</span><span class="sxs-lookup"><span data-stu-id="0dc52-133">- Automated investigation</span></span> <br/><span data-ttu-id="0dc52-134">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0dc52-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="0dc52-135">- Acties voor handmatige antwoorden</span><span class="sxs-lookup"><span data-stu-id="0dc52-135">- Manual response actions</span></span> | <span data-ttu-id="0dc52-136">- Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="0dc52-136">- Isolate device</span></span> <br/><span data-ttu-id="0dc52-137">- Uitvoering van code beperken</span><span class="sxs-lookup"><span data-stu-id="0dc52-137">- Restrict code execution</span></span> <br/><span data-ttu-id="0dc52-138">- Een bestand in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="0dc52-138">- Quarantine a file</span></span> <br/><span data-ttu-id="0dc52-139">- Een registersleutel verwijderen</span><span class="sxs-lookup"><span data-stu-id="0dc52-139">- Remove a registry key</span></span> <br/><span data-ttu-id="0dc52-140">- Een service stoppen</span><span class="sxs-lookup"><span data-stu-id="0dc52-140">- Stop a service</span></span> <br/><span data-ttu-id="0dc52-141">- Een stuurprogramma uitschakelen</span><span class="sxs-lookup"><span data-stu-id="0dc52-141">- Disable a driver</span></span> <br/><span data-ttu-id="0dc52-142">- Een geplande taak verwijderen</span><span class="sxs-lookup"><span data-stu-id="0dc52-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="0dc52-143">Een herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="0dc52-143">To undo a remediation action</span></span>

1. <span data-ttu-id="0dc52-144">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0dc52-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="0dc52-145">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="0dc52-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="0dc52-146">Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**</span><span class="sxs-lookup"><span data-stu-id="0dc52-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="0dc52-147">Een bestand uit quarantaine verwijderen op meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="0dc52-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="0dc52-148">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="0dc52-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="0dc52-149">Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine.**</span><span class="sxs-lookup"><span data-stu-id="0dc52-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="0dc52-150">Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand op Toepassen op **X** en selecteer vervolgens **Ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="0dc52-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0dc52-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="0dc52-151">Next steps</span></span>

- [<span data-ttu-id="0dc52-152">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="0dc52-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="0dc52-153">Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken</span><span class="sxs-lookup"><span data-stu-id="0dc52-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
