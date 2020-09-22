---
title: Acties die in behandeling zijn, goedkeuren of weigeren na een geautomatiseerd onderzoek
description: Onderhoudscentrum gebruiken voor het beheren van acties met betrekking tot een automatisch onderzoek en antwoord
keywords: actie, centrum, autoair, automatisch, onderzoek, antwoord, herstel
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
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: dd7ded318c5ab0cf9aad47054ac04d5a2d353943
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199803"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="98190-104">Acties die in behandeling zijn, goedkeuren of weigeren na een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="98190-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98190-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="98190-105">**Applies to:**</span></span>
- <span data-ttu-id="98190-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="98190-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="98190-107">Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit resulteren in een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) die moeten worden goedgekeurd om verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="98190-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="98190-108">Als u bijvoorbeeld een cluster van e-mailberichten wilt verwijderen, of als u een bestand met quarantaine wilt verwijderen, moet u het bestand mogelijk verwijderen.</span><span class="sxs-lookup"><span data-stu-id="98190-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="98190-109">Het is belangrijk dat u de in behandeling zijnde acties zo snel mogelijk goedkeurt (of afwijst), zodat uw geautomatiseerde onderzoek op een redelijke manier kan worden voortgezet en voltooid.</span><span class="sxs-lookup"><span data-stu-id="98190-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="98190-110">Laat het ons weten als u denkt dat er een fout is opgetreden met een automatisch onderzoek en antwoord functies in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="98190-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="98190-111">Lees [hoe u in Microsoft Threat Protection onjuiste positief en negatief kunt rapporteren in de functies voor automatisch onderzoek en Reacties (lucht)](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="98190-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="98190-112">Acties die in behandeling zijn, kunnen worden gecontroleerd en goedgekeurd met behulp van het [Onderhoudscentrum](#review-a-pending-action-in-the-action-center) of de [weergave Details van onderzoek](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="98190-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="98190-113">U moet de [juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) hebben om herstelacties goed te keuren of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="98190-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="98190-114">Een actie in behandeling nakijken in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="98190-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="98190-115">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="98190-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="98190-116">Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**.</span><span class="sxs-lookup"><span data-stu-id="98190-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="98190-117">In het Actiecentrum selecteert u een item in de lijst op het tabblad **in behandeling** .</span><span class="sxs-lookup"><span data-stu-id="98190-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="98190-118">Als u een item selecteert in de kolom **onderzoek nummer** , wordt de pagina Details van onderzoek geopend.</span><span class="sxs-lookup"><span data-stu-id="98190-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="98190-119">Daar kunt u de resultaten van het onderzoek bekijken en de aanbevolen actie vervolgens goedkeuren of weigeren.</span><span class="sxs-lookup"><span data-stu-id="98190-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="98190-120">Als u een rij in de lijst selecteert, wordt er een flyout geopend waarin u informatie over dat item kunt weergeven.</span><span class="sxs-lookup"><span data-stu-id="98190-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Een actie goedkeuren of afwijzen](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="98190-122">Gebruik de koppelingen om een gekoppelde waarschuwing of een onderzoek te bekijken, en om de actie goed te keuren of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="98190-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="98190-123">Een actie in behandeling nakijken in de weergave Details van onderzoek</span><span class="sxs-lookup"><span data-stu-id="98190-123">Review a pending action in the investigation details view</span></span>

![Details van onderzoek](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="98190-125">Selecteer op de pagina [Details van onderzoek](mtp-autoir-results.md) het tabblad **acties in behandeling** (of **acties**). Items die in behandeling zijn, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="98190-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="98190-126">Selecteer een item in de lijst en kies vervolgens **goedkeuren** of **weigeren**.</span><span class="sxs-lookup"><span data-stu-id="98190-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="98190-127">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="98190-127">Next steps</span></span>

- [<span data-ttu-id="98190-128">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="98190-128">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="98190-129">In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="98190-129">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
