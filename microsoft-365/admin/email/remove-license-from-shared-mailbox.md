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
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445493"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="1bb18-103">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="1bb18-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1bb18-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1bb18-104">The admin center is changing.</span></span> <span data-ttu-id="1bb18-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="1bb18-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="1bb18-106">Voor gedeelde postvakken is meestal geen licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="1bb18-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="1bb18-107">Volg deze instructies voor het verwijderen van een licentie uit een gedeeld postvak, zodat u deze kunt toewijzen aan een gebruiker of de licentie moet retourneren, zodat u niet betaalt voor een licentie die u niet nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="1bb18-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="1bb18-108">Voor de volgende scenario's is een licentie vereist:</span><span class="sxs-lookup"><span data-stu-id="1bb18-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="1bb18-109">Het gedeelde Postvak heeft meer dan 50 GB opslagruimte in gebruik.</span><span class="sxs-lookup"><span data-stu-id="1bb18-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="1bb18-110">Het gedeelde Postvak gebruikt in-place archivering.</span><span class="sxs-lookup"><span data-stu-id="1bb18-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="1bb18-111">Het gedeelde Postvak wordt in de wachtstand geplaatst.</span><span class="sxs-lookup"><span data-stu-id="1bb18-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="1bb18-112">De licentie verwijderen</span><span class="sxs-lookup"><span data-stu-id="1bb18-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1bb18-113">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1bb18-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1bb18-114">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1bb18-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1bb18-115">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="1bb18-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="1bb18-116">Selecteer het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="1bb18-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="1bb18-117">Selecteer op het tabblad **licenties en apps** de optie **licenties** en schakel het selectievakje uit van de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1bb18-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="1bb18-118">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1bb18-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="1bb18-119">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie**gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1bb18-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1bb18-120">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="1bb18-120">You're still paying for the license.</span></span> <span data-ttu-id="1bb18-121">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1bb18-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="1bb18-122">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1bb18-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1bb18-123">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1bb18-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1bb18-124">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="1bb18-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="1bb18-125">Selecteer het gedeelde Postvak en selecteer vervolgens **bewerken** naast **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="1bb18-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="1bb18-126">Stel op de pagina **product licenties** de wisselknop op **uit** voor de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1bb18-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="1bb18-127">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1bb18-127">Select **Save**.</span></span>

5. <span data-ttu-id="1bb18-128">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie**gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1bb18-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1bb18-129">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="1bb18-129">You're still paying for the license.</span></span> <span data-ttu-id="1bb18-130">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1bb18-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1bb18-131">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1bb18-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1bb18-132">U moet de licentie verwijderen van de pagina actieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1bb18-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1bb18-133">U kunt de licentie niet verwijderen van de pagina gedeeld postvak omdat de licenties gebruikersinstellingen zijn.</span><span class="sxs-lookup"><span data-stu-id="1bb18-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="1bb18-134">Selecteer het gedeelde Postvak en selecteer vervolgens **bewerken** naast **product licenties**.</span><span class="sxs-lookup"><span data-stu-id="1bb18-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="1bb18-135">Stel op de pagina **product licenties** de wisselknop op **uit** voor de licentie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1bb18-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="1bb18-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1bb18-136">Select **Save**.</span></span>

5. <span data-ttu-id="1bb18-137">Wanneer u terugkeert naar de pagina **actieve gebruikers** , wordt de status van het gedeelde Postvak zonder **licentie**gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1bb18-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1bb18-138">U betaalt nog steeds voor de licentie.</span><span class="sxs-lookup"><span data-stu-id="1bb18-138">You're still paying for the license.</span></span> <span data-ttu-id="1bb18-139">Als u wilt stoppen met betalen, [verwijdert u de licentie uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1bb18-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="1bb18-140">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="1bb18-140">Related articles</span></span>

[<span data-ttu-id="1bb18-141">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="1bb18-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1bb18-142">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="1bb18-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="1bb18-143">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="1bb18-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="1bb18-144">Een gebruikerspostvak converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="1bb18-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="1bb18-145">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="1bb18-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
