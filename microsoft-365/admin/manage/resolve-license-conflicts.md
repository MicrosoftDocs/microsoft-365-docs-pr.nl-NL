---
title: Licentieconflicten oplossen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Meer informatie over het oplossen van licentieconflicten met uw Microsoft 365 voor Bedrijven-abonnement.
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915180"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="d1859-103">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="d1859-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d1859-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d1859-104">The admin center is changing.</span></span> <span data-ttu-id="d1859-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d1859-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d1859-106">Het is raadzaam om de licenties te kopen die u nodig hebt voor uw abonnement voordat u nieuwe gebruikers maakt.</span><span class="sxs-lookup"><span data-stu-id="d1859-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="d1859-107">Op die manier kan een licentie worden toegewezen aan nieuwe gebruikers zodra hun gebruikersaccount is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d1859-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="d1859-108">Er ontstaan licentieconflicten als alle beschikbare licenties al zijn toegewezen aan gebruikers, maar enkele licenties zijn verlopen, of als u een licentie probeert te verwijderen die al aan een gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d1859-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="d1859-109">Zie Licenties van [uw abonnement verwijderen voor meer informatie.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="d1859-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="d1859-110">Licentieconflicten weergeven</span><span class="sxs-lookup"><span data-stu-id="d1859-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1859-111">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="d1859-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d1859-112">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="d1859-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1859-113">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="d1859-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d1859-114">Kijk in de kolom **Status** voor informatie over het conflict.</span><span class="sxs-lookup"><span data-stu-id="d1859-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="d1859-115">Als er een conflict is, ziet u een waarschuwingsbericht met de melding dat een of meer gebruikers een geldige licentie nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="d1859-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1859-116">De kolom **Status** wordt alleen weergegeven als er conflicten zijn.</span><span class="sxs-lookup"><span data-stu-id="d1859-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="d1859-117">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="d1859-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="d1859-118">U kunt licentieconflicten oplossen door meer licenties [te kopen](../../commerce/licenses/buy-licenses.md) of door licenties te verwijderen van gebruikers die ze niet meer [nodig hebben.](remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="d1859-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="d1859-119">U kunt optioneel [een gebruikersaccount verwijderen om een licentie vrij te geven](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d1859-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d1859-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d1859-120">Related articles</span></span>

[<span data-ttu-id="d1859-121">Licenties toewijzen aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="d1859-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="d1859-122">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1859-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)