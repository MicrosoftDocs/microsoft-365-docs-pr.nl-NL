---
title: Licenties aan gebruikers toewijzen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Handleiding over het toewijzen van licenties aan gebruikers.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015945"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="de621-103">Licenties aan gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="de621-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="de621-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="de621-104">The admin center is changing.</span></span> <span data-ttu-id="de621-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="de621-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="de621-106">U kunt licenties toewijzen aan gebruikers op de pagina **Actieve gebruikers** of op de pagina **Licenties**.</span><span class="sxs-lookup"><span data-stu-id="de621-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="de621-107">De methode die u gebruikt, is afhankelijk van of u productlicenties wilt toewijzen aan specifieke gebruikers of gebruikerslicenties wilt toewijzen aan een specifiek product.</span><span class="sxs-lookup"><span data-stu-id="de621-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="de621-108">[Informatie over het toevoegen van een gebruiker en tegelijkertijd toewijzen van een licentie](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="de621-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="de621-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="de621-109">Before you begin</span></span>

- <span data-ttu-id="de621-110">U moet algemeen, licentie-, of gebruikersbeheerder zijn om licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="de621-111">Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="de621-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="de621-112">U kunt [licenties toewijzen aan gebruikersaccounts met Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="de621-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="de621-113">Voor groepslicenties, zie [Licenties toewijzen aan gebruikers op basis van groepslidmaatschap in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="de621-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="de621-114">Sommige services, zoals Sway, worden automatisch aan gebruikers toegewezen.Het is niet nodig deze afzonderlijk toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="de621-115">Gebruik de pagina Licenties om licenties aan gebruikers toe te wijzen</span><span class="sxs-lookup"><span data-stu-id="de621-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="de621-116">Met behulp van de pagina **Licenties** kunt u licenties voor een specifiek product toewijzen aan maximaal 20 gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="de621-117">Op de pagina **Licenties** wordt een lijst weergegeven met alle producten waarvoor u een abonnement hebt.</span><span class="sxs-lookup"><span data-stu-id="de621-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="de621-118">U ziet ook het totale aantal licenties voor elk product, het aantal toegewezen licenties en het aantal beschikbare licenties.</span><span class="sxs-lookup"><span data-stu-id="de621-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="de621-119">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="de621-120">Selecteer een product.</span><span class="sxs-lookup"><span data-stu-id="de621-120">Select a product.</span></span>
3. <span data-ttu-id="de621-121">Selecteer **Licenties toewijzen** op de pagina met productdetails.</span><span class="sxs-lookup"><span data-stu-id="de621-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="de621-122">Begin in het deelvenster **Licenties toewijzen aan gebruikers** met het typen van een naam en kies de naam in de resultaten om deze aan de lijst toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="de621-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="de621-123">U kunt maximaal 20 gebruikers tegelijk toevoegen.</span><span class="sxs-lookup"><span data-stu-id="de621-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="de621-124">Selecteer **Apps en services in- of uitschakelen** om de toegang tot bepaalde items toe te wijzen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="de621-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="de621-125">Wanneer u klaar bent, selecteert u achtereenvolgens **Toewijzen** en **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="de621-126">Als er een conflict is, wordt er een bericht weergegeven waarin wordt uitgelegd wat het probleem is en hoe u dit kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="de621-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="de621-127">Als u bijvoorbeeld licenties hebt geselecteerd die conflicterende services bevatten, moet u de services die bij elke licentie zijn opgenomen controleren en het opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="de621-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="de621-128">De apps en services wijzigen waartoe een gebruiker toegang heeft</span><span class="sxs-lookup"><span data-stu-id="de621-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="de621-129">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="de621-130">Selecteer op de pagina **Licenties** de rij voor een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="de621-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="de621-131">Selecteer of deselecteer in het rechterdeelvenster de apps en services waarvoor u toegang wilt verlenen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="de621-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="de621-132">Wanneer u klaar bent, selecteert u achtereenvolgens **Opslaan** en **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="de621-133">Licenties toewijzen met de pagina Actieve gebruikers</span><span class="sxs-lookup"><span data-stu-id="de621-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="de621-134">Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties toe te wijzen, wijst u gebruikerslicenties aan producten toe.</span><span class="sxs-lookup"><span data-stu-id="de621-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="de621-135">Licenties toewijzen aan meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="de621-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="de621-136">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-137">Selecteer de cirkels naast de namen van de gebruikers aan wie u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="de621-138">Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="de621-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="de621-139">Selecteer in het deelvenster **Productlicenties beheren** **Toevoegen aan bestaande productlicentietoewijzingen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="de621-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="de621-140">Zet de wisselknop in het deelvenster **Toevoegen aan bestaande producten** op **Aan** voor de licentie die u wilt toewijzen aan de geselecteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="de621-141">De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="de621-142">U kunt beperken welke services beschikbaar zijn voor de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="de621-143">Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.</span><span class="sxs-lookup"><span data-stu-id="de621-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="de621-144">Selecteer onderaan het deelvenster **Toevoegen** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="de621-145">Licenties toewijzen aan meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="de621-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="de621-146">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-147">Vink de selectievakjes aan naast de namen van de gebruikers aan wie u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="de621-148">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="de621-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="de621-149">Selecteer in het deelvenster **Producten toewijzen** **Toevoegen aan bestaande productlicentietoewijzingen** \> \*\* Volgende\*\*.</span><span class="sxs-lookup"><span data-stu-id="de621-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="de621-150">Zet de wisselknop op **Aan** voor de licenties die u wilt toewijzen aan de geselecteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="de621-151">De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="de621-152">U kunt beperken welke services beschikbaar zijn voor de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="de621-153">Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.</span><span class="sxs-lookup"><span data-stu-id="de621-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="de621-154">Selecteer onderaan in het deelvenster **Toevoegen aan bestaande producten** **Toevoegen** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="de621-155">Licenties toewijzen aan meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="de621-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="de621-156">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-157">Vink de selectievakjes aan naast de namen van de gebruikers aan wie u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="de621-158">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="de621-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="de621-159">Selecteer in het deelvenster **Producten toewijzen** **Toevoegen aan bestaande productlicentietoewijzingen** \> \*\* Volgende\*\*.</span><span class="sxs-lookup"><span data-stu-id="de621-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="de621-160">Zet de wisselknop op **Aan** voor de licenties die u wilt toewijzen aan de geselecteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="de621-161">De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="de621-162">U kunt beperken welke services beschikbaar zijn voor de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="de621-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="de621-163">Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.</span><span class="sxs-lookup"><span data-stu-id="de621-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="de621-164">Selecteer onderaan in het deelvenster **Toevoegen aan bestaande producten** **Toevoegen** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="de621-165">Licenties aan een enkele gebruiker toewijzen</span><span class="sxs-lookup"><span data-stu-id="de621-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="de621-166">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-167">Selecteer de rij van de gebruiker aan wie u een licentie wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="de621-168">Selecteer in het rechterdeelvenster **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="de621-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="de621-169">Vouw de sectie **Licenties** uit en schakel de selectievakjes in voor de licenties die u wilt toewijzen. Selecteer vervolgens **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="de621-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="de621-170">Licenties aan een enkele gebruiker toewijzen</span><span class="sxs-lookup"><span data-stu-id="de621-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="de621-171">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-172">Vink het selectievakje aan naast de naam van de gebruiker aan wie u een licentie wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="de621-173">Selecteer de optie **Bewerken** in het rechterdeelvenster in de rij **Productlicenties**.</span><span class="sxs-lookup"><span data-stu-id="de621-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="de621-174">Zet in het deelvenster **Productlicenties** de wisselknop op **Aan** voor de licentie die u aan deze gebruiker wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="de621-175">De standaardinstelling is dat alle services die zijn gekoppeld aan die licentie, automatisch worden toegewezen aan de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="de621-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="de621-176">U kunt beperken welke services beschikbaar zijn voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="de621-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="de621-177">Zet de wisselknoppen op **Uit** voor de services waarvan die gebruiker geen gebruik mag maken.</span><span class="sxs-lookup"><span data-stu-id="de621-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="de621-178">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="de621-179">Licenties aan een enkele gebruiker toewijzen</span><span class="sxs-lookup"><span data-stu-id="de621-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="de621-180">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="de621-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="de621-181">Vink het selectievakje aan naast de naam van de gebruiker aan wie u een licentie wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="de621-182">Selecteer de optie **Bewerken** in het rechterdeelvenster in de rij **Productlicenties**.</span><span class="sxs-lookup"><span data-stu-id="de621-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="de621-183">Zet in het deelvenster **Productlicenties** de wisselknop op **Aan** voor de licentie die u aan deze gebruiker wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="de621-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="de621-184">De standaardinstelling is dat alle services die zijn gekoppeld aan die licentie, automatisch worden toegewezen aan de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="de621-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="de621-185">U kunt beperken welke services beschikbaar zijn voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="de621-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="de621-186">Zet de wisselknoppen op **Uit** voor de services waarvan die gebruiker geen gebruik mag maken.</span><span class="sxs-lookup"><span data-stu-id="de621-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="de621-187">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="de621-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="de621-188">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="de621-188">Next steps</span></span>

<span data-ttu-id="de621-189">Als de Office-apps nog niet door uw gebruikers zijn geïnstalleerd, kunt u de [Aan de slag-handleiding voor werknemers](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) delen met uw gebruikers om dingen in te stellen, zoals [Microsoft 365 of Office 2019 op een pc of Mac downloaden en installeren](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) en [Office-apps en e-mail op een mobiel apparaat instellen](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="de621-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="de621-190">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="de621-190">Related content</span></span>

<span data-ttu-id="de621-191">[Informatie over abonnementen en licenties](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="de621-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="de621-192">[Licenties van gebruikers intrekken](remove-licenses-from-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="de621-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="de621-193">[Licenties kopen of intrekken voor uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="de621-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>