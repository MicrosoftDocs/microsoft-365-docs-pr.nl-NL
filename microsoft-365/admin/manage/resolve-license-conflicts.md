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
description: Meer informatie over het oplossen van licentie conflicten met uw Microsoft 365 voor bedrijven-abonnement.
ms.openlocfilehash: a7f0b5cbca98a0550954e322c6fbe51d93627ee4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645081"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="dd32c-103">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="dd32c-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dd32c-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="dd32c-104">The admin center is changing.</span></span> <span data-ttu-id="dd32c-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="dd32c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="dd32c-106">U wordt aangeraden de licenties die u nodig hebt voor uw abonnement te kopen voordat u nieuwe gebruikers maakt.</span><span class="sxs-lookup"><span data-stu-id="dd32c-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="dd32c-107">Op die manier kan een licentie worden toegewezen aan nieuwe gebruikers zodra hun gebruikersaccount is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="dd32c-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="dd32c-108">Er ontstaan licentieconflicten als alle beschikbare licenties al zijn toegewezen aan gebruikers, maar enkele licenties zijn verlopen, of als u een licentie probeert te verwijderen die al aan een gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="dd32c-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="dd32c-109">Zie [licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dd32c-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="dd32c-110">Licentieconflicten weergeven</span><span class="sxs-lookup"><span data-stu-id="dd32c-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dd32c-111">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="dd32c-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="dd32c-112">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="dd32c-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dd32c-113">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="dd32c-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="dd32c-114">Kijk in de kolom **Status** voor informatie over het conflict.</span><span class="sxs-lookup"><span data-stu-id="dd32c-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="dd32c-115">Als er sprake is van een conflict, wordt er een waarschuwing weergegeven, die aangeeft dat een of meer gebruikers een geldige licentie nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="dd32c-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd32c-116">De kolom **Status** wordt alleen weergegeven als er conflicten zijn.</span><span class="sxs-lookup"><span data-stu-id="dd32c-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="dd32c-117">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="dd32c-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="dd32c-118">U kunt licentie conflicten oplossen door [meer licenties te kopen](../../commerce/licenses/buy-licenses.md) of door [licenties te verwijderen van gebruikers die ze niet meer nodig hebben](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="dd32c-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="dd32c-119">U kunt optioneel [een gebruikersaccount verwijderen om een licentie vrij te geven](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="dd32c-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="dd32c-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="dd32c-120">Related articles</span></span>

[<span data-ttu-id="dd32c-121">Licenties toewijzen aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="dd32c-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="dd32c-122">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="dd32c-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
