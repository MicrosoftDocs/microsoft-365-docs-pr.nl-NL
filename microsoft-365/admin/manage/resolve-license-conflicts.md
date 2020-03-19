---
title: Licentieconflicten oplossen in Office 365 voor Bedrijven
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Meer informatie over het oplossen van licentieconflicten met uw Abonnement op Office 365 voor Bedrijven.
ms.openlocfilehash: 63464951c4f1fd568248ca5c43da9f8c94347711
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812507"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="8c77d-103">Licentieconflicten oplossen in Office 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="8c77d-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="8c77d-104">We raden u aan de licenties te kopen die u nodig hebt voor uw abonnement voordat u nieuwe gebruikers maakt.</span><span class="sxs-lookup"><span data-stu-id="8c77d-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="8c77d-105">Op die manier kan een licentie worden toegewezen aan nieuwe gebruikers zodra hun gebruikersaccount is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8c77d-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="8c77d-106">Er ontstaan licentieconflicten als alle beschikbare licenties al zijn toegewezen aan gebruikers, maar enkele licenties zijn verlopen, of als u een licentie probeert te verwijderen die al aan een gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8c77d-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="8c77d-107">Zie [Licenties uit uw abonnement verwijderen voor](../../commerce/licenses/remove-licenses-from-subscription.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8c77d-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="8c77d-108">Licentieconflicten weergeven</span><span class="sxs-lookup"><span data-stu-id="8c77d-108">How do I view license conflicts?</span></span>

1. <span data-ttu-id="8c77d-109">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a> **Billing**</span><span class="sxs-lookup"><span data-stu-id="8c77d-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="8c77d-110">Als u Office 365 Germany gebruikt, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties.</a></span><span class="sxs-lookup"><span data-stu-id="8c77d-110">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="8c77d-111">Als u Office 365 gebruikt dat wordt beheerd door 21Vianet, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties.</a></span><span class="sxs-lookup"><span data-stu-id="8c77d-111">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="8c77d-112">Kijk in de kolom **Status** voor informatie over het conflict.</span><span class="sxs-lookup"><span data-stu-id="8c77d-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="8c77d-113">Als er een conflict is, ziet u een waarschuwingsbericht waarin staat dat een of meer gebruikers een geldige licentie nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="8c77d-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c77d-114">De kolom **Status** wordt alleen weergegeven als er conflicten zijn.</span><span class="sxs-lookup"><span data-stu-id="8c77d-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="8c77d-115">Licentieconflicten oplossen</span><span class="sxs-lookup"><span data-stu-id="8c77d-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="8c77d-116">U licentieconflicten oplossen door [meer licenties](../../commerce/licenses/buy-licenses.md) te kopen of door licenties te verwijderen van gebruikers die ze niet meer [nodig hebben.](remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="8c77d-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="8c77d-117">U kunt optioneel [een gebruikersaccount verwijderen om een licentie vrij te geven](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="8c77d-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8c77d-118">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8c77d-118">Related articles</span></span> 

[<span data-ttu-id="8c77d-119">Licenties toewijzen aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="8c77d-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="8c77d-120">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="8c77d-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
