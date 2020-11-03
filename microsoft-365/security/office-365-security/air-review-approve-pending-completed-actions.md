---
title: In behandeling zijnde herstelacties controleren en goedkeuren in een automatisch onderzoek en antwoord
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over herstelacties in de functies voor automatisch onderzoek en antwoord in Microsoft Defender voor Office 365, abonnement 2.
ms.openlocfilehash: 7dc5c0ba2e320e3f140d26e79e5c2e4a8fde79d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844558"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="d2d03-104">In behandeling zijnde of voltooide herstelacties bekijken na een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="d2d03-104">View pending or completed remediation actions following an automated investigation in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



![Actie pagina AIR onderzoek](../../media/air-investigationactionspage.png)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="d2d03-106">Acties in behandeling goedkeuren of weigeren</span><span class="sxs-lookup"><span data-stu-id="d2d03-106">Approve (or reject) pending actions</span></span>

<span data-ttu-id="d2d03-107">Tijdens het bekijken [van de details van een onderzoek](air-view-investigation-results.md)kunt u de acties voor herstel in behandeling goedkeuren of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="d2d03-107">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="d2d03-108">U wordt aangeraden dit zo snel mogelijk te doen, zodat uw geautomatiseerde onderzoek wordt voltooid.</span><span class="sxs-lookup"><span data-stu-id="d2d03-108">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2d03-109">U moet de juiste machtigingen hebben om herstelacties goed te keuren of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="d2d03-109">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="d2d03-110">Zie de [vereiste machtigingen voor het gebruik van lucht mogelijkheden](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="d2d03-110">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="d2d03-111">Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="d2d03-111">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="d2d03-112">U gaat nu naar de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="d2d03-112">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="d2d03-113">Ga naar onderzoek voor **Threat Management**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="d2d03-113">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="d2d03-114">Selecteer een item in de kolom **id** van de lijst met onderzoek.</span><span class="sxs-lookup"><span data-stu-id="d2d03-114">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="d2d03-115">Selecteer het tabblad **acties** .</span><span class="sxs-lookup"><span data-stu-id="d2d03-115">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="d2d03-116">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="d2d03-116">Select an item in the list.</span></span> <span data-ttu-id="d2d03-117">(Hiermee activeert u de knoppen goedkeuren en negeren).</span><span class="sxs-lookup"><span data-stu-id="d2d03-117">(This activates the Approve and Reject buttons.)</span></span>

6. <span data-ttu-id="d2d03-118">Bekijk de beschikbare gegevens voor elk item dat u hebt geselecteerd, en keur vervolgens de actie (s) goed of af.</span><span class="sxs-lookup"><span data-stu-id="d2d03-118">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
   - <span data-ttu-id="d2d03-119">**Hiermee kunt** u beginnen met herstellen.</span><span class="sxs-lookup"><span data-stu-id="d2d03-119">**Approve** allows remediation to begin.</span></span>
   - <span data-ttu-id="d2d03-120">Bij **negeren** wordt geen verdere actie ondernomen</span><span class="sxs-lookup"><span data-stu-id="d2d03-120">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2d03-121">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="d2d03-121">Next steps</span></span>

- [<span data-ttu-id="d2d03-122">Details en resultaten van een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="d2d03-122">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

- [<span data-ttu-id="d2d03-123">De bedreigings Verkenner gebruiken</span><span class="sxs-lookup"><span data-stu-id="d2d03-123">Use Threat Explorer</span></span>](threat-explorer.md)
