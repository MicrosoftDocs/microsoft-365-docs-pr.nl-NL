---
title: In behandeling zijnde acties goedkeuren of afwijzen na een geautomatiseerd onderzoek
description: Het Onderhoudscentrum gebruiken om acties te beheren met betrekking tot geautomatiseerd onderzoek en respons
keywords: actie, centrum, autoair, geautomatiseerd, onderzoek, respons, sanering
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 725d22629d2c81a0edf8f329602214afddde6511
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808464"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="ab1b4-104">In behandeling zijnde acties goedkeuren of afwijzen na een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="ab1b4-104">Approve or reject pending actions following an automated investigation</span></span>

<span data-ttu-id="ab1b4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ab1b4-105">**Applies to:**</span></span>
- <span data-ttu-id="ab1b4-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ab1b4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ab1b4-107">Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit resulteren in een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) waarvoor goedkeuring nodig is.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="ab1b4-108">Een cluster van e-mailberichten moet bijvoorbeeld worden verwijderd of een bestand in quarantaine moet mogelijk worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="ab1b4-109">Het is belangrijk om in afwachting van acties zo snel mogelijk goed te keuren (of af te wijzen), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="ab1b4-110">Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten!</span><span class="sxs-lookup"><span data-stu-id="ab1b4-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="ab1b4-111">Zie [Hoe valse positieven/negatieven in geautomatiseerde onderzoeks- en reactiemogelijkheden (AIR) kunnen worden gemeld in Microsoft Threat Protection.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="ab1b4-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="ab1b4-112">Lopende acties kunnen worden beoordeeld en goedgekeurd met behulp van het [actiecentrum](#review-a-pending-action-in-the-action-center) of de [weergave onderzoeksdetails](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="ab1b4-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="ab1b4-113">U moet [over de juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) beschikken om herstelacties goed te keuren of af te wijzen.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="ab1b4-114">Een actie in behandeling controleren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="ab1b4-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="ab1b4-115">Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="ab1b4-116">Kies In het navigatiedeelvenster de optie **Actiecentrum**.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="ab1b4-117">Selecteer in het Onderhoudscentrum op het tabblad **In behandeling** een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="ab1b4-118">Als u een item selecteert in de kolom **Onderzoeksnummer,** wordt de pagina met onderzoeksdetails geopend.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="ab1b4-119">Daar u de resultaten van het onderzoek bekijken en vervolgens de aanbevolen actie goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="ab1b4-120">Als u een rij in de lijst selecteert, wordt er een flyout geopend, waar u informatie over dat item bekijken.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Een actie goedkeuren of afwijzen](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="ab1b4-122">Gebruik de koppelingen om een bijbehorende waarschuwing of een onderzoek weer te geven en de actie goed te keuren of af te wijzen.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="ab1b4-123">Een lopende actie in de weergave onderzoeksdetails bekijken</span><span class="sxs-lookup"><span data-stu-id="ab1b4-123">Review a pending action in the investigation details view</span></span>

![Onderzoeksdetails](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="ab1b4-125">Selecteer op een pagina [met onderzoeksdetails](mtp-autoir-results.md) het tabblad **In behandeling zijnde acties** (of **Acties).**</span><span class="sxs-lookup"><span data-stu-id="ab1b4-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="ab1b4-126">Selecteer een item in de lijst en kies **Goedkeuren** of **Weigeren**.</span><span class="sxs-lookup"><span data-stu-id="ab1b4-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ab1b4-127">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ab1b4-127">Next steps</span></span>

- [<span data-ttu-id="ab1b4-128">Meer informatie over het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="ab1b4-128">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="ab1b4-129">Meer informatie over incidenten</span><span class="sxs-lookup"><span data-stu-id="ab1b4-129">Learn more about incidents</span></span>](incidents-overview.md)

- [<span data-ttu-id="ab1b4-130">Meer informatie over jagen</span><span class="sxs-lookup"><span data-stu-id="ab1b4-130">Learn about hunting</span></span>](advanced-hunting-overview.md)
