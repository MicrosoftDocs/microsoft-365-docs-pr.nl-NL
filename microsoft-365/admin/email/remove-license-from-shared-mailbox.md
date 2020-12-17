---
title: Een licentie uit een gedeeld postvak verwijderen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Licentie uit een gedeeld postvak verwijderen om het aan een andere gebruiker toe te wijzen. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698301"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f85de-103">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="f85de-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f85de-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f85de-104">The admin center is changing.</span></span> <span data-ttu-id="f85de-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f85de-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f85de-106">Voor gedeelde postvakken is meestal geen licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="f85de-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f85de-107">Volg deze instructies voor het verwijderen van een licentie uit een gedeeld postvak, zodat u deze kunt toewijzen aan een gebruiker of de licentie moet retourneren, zodat u niet betaalt voor een licentie die u niet nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="f85de-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="f85de-108">Voor de volgende scenario's is een licentie vereist:</span><span class="sxs-lookup"><span data-stu-id="f85de-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="f85de-109">Het gedeelde Postvak heeft meer dan 50 GB opslagruimte in gebruik.</span><span class="sxs-lookup"><span data-stu-id="f85de-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f85de-110">Het gedeelde Postvak gebruikt in-place archivering.</span><span class="sxs-lookup"><span data-stu-id="f85de-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f85de-111">Het gedeelde Postvak wordt in de wachtstand geplaatst.</span><span class="sxs-lookup"><span data-stu-id="f85de-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="f85de-112">Voor het gedeelde Postvak is een Microsoft Defender-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="f85de-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="f85de-113">De licentie verwijderen</span><span class="sxs-lookup"><span data-stu-id="f85de-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f85de-114">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="f85de-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f85de-115">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f85de-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f85de-116">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="f85de-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="f85de-117">Selecteer het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="f85de-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f85de-118">Selecteer op het tabblad **licenties en apps** de optie **licenties** en schakel het selectievakje uit van de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f85de-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f85de-119">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f85de-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="f85de-120">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie** gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f85de-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f85de-121">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="f85de-121">You're still paying for the license.</span></span> <span data-ttu-id="f85de-122">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f85de-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f85de-123">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="f85de-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f85de-124">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f85de-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f85de-125">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="f85de-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f85de-126">Selecteer het gedeelde Postvak en selecteer vervolgens **bewerken** naast **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="f85de-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f85de-127">Stel op de pagina **product licenties** de wisselknop op **uit** voor de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f85de-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f85de-128">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f85de-128">Select **Save**.</span></span>

5. <span data-ttu-id="f85de-129">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie** gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f85de-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f85de-130">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="f85de-130">You're still paying for the license.</span></span> <span data-ttu-id="f85de-131">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f85de-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f85de-132">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="f85de-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f85de-133">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f85de-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f85de-134">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="f85de-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f85de-135">Selecteer het gedeelde Postvak en selecteer vervolgens **bewerken** naast **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="f85de-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f85de-136">Stel op de pagina **product licenties** de wisselknop op **uit** voor de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f85de-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f85de-137">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f85de-137">Select **Save**.</span></span>

5. <span data-ttu-id="f85de-138">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie** gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f85de-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f85de-139">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="f85de-139">You're still paying for the license.</span></span> <span data-ttu-id="f85de-140">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f85de-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="f85de-141">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f85de-141">Related articles</span></span>

[<span data-ttu-id="f85de-142">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="f85de-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f85de-143">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="f85de-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f85de-144">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="f85de-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f85de-145">Een gebruikerspostvak converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="f85de-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f85de-146">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="f85de-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
