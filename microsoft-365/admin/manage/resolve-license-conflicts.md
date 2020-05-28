---
title: Licentieconflicten oplossen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Meer informatie over het oplossen van licentieconflicten met uw Microsoft 365 voor Bedrijven-abonnement.
ms.openlocfilehash: 05efe9e75b051ece900ba9defe047f1244b713a9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399666"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="cbf06-103">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="cbf06-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cbf06-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cbf06-104">The admin center is changing.</span></span> <span data-ttu-id="cbf06-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cbf06-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cbf06-106">We raden u aan de licenties te kopen die u nodig hebt voor uw abonnement voordat u nieuwe gebruikers maakt.</span><span class="sxs-lookup"><span data-stu-id="cbf06-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="cbf06-107">Op die manier kan een licentie worden toegewezen aan nieuwe gebruikers zodra hun gebruikersaccount is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cbf06-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="cbf06-108">Er ontstaan licentieconflicten als alle beschikbare licenties al zijn toegewezen aan gebruikers, maar enkele licenties zijn verlopen, of als u een licentie probeert te verwijderen die al aan een gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="cbf06-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="cbf06-109">Zie [Licenties uit uw abonnement verwijderen](../../commerce/licenses/remove-licenses-from-subscription.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cbf06-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="cbf06-110">Licentieconflicten weergeven</span><span class="sxs-lookup"><span data-stu-id="cbf06-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cbf06-111">Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="cbf06-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cbf06-112">Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="cbf06-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cbf06-113">Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="cbf06-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cbf06-114">Kijk in de kolom **Status** voor informatie over het conflict.</span><span class="sxs-lookup"><span data-stu-id="cbf06-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="cbf06-115">Als er een conflict is, ziet u een waarschuwingsbericht waarin staat dat een of meer gebruikers een geldige licentie nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="cbf06-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cbf06-116">De kolom **Status** wordt alleen weergegeven als er conflicten zijn.</span><span class="sxs-lookup"><span data-stu-id="cbf06-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="cbf06-117">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="cbf06-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="cbf06-118">U licentieconflicten oplossen door [meer licenties te kopen](../../commerce/licenses/buy-licenses.md) of door licenties te verwijderen van gebruikers die ze niet meer nodig [hebben.](remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="cbf06-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="cbf06-119">U kunt optioneel [een gebruikersaccount verwijderen om een licentie vrij te geven](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="cbf06-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cbf06-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cbf06-120">Related articles</span></span> 

[<span data-ttu-id="cbf06-121">Licenties toewijzen aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="cbf06-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="cbf06-122">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="cbf06-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
