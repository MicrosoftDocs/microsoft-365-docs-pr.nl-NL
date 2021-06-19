---
title: Licenties aan gebruikers toewijzen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Wijs licenties toe afhankelijk van of u productlicenties wilt toewijzen aan specifieke gebruikers of gebruikerslicenties wilt toewijzen aan een specifiek product.
ms.date: 04/26/2021
ms.openlocfilehash: c8e5c6a648f08aaba97fe05e19a5cfa0cada2174
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007007"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="53d69-103">Licenties aan gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="53d69-103">Assign licenses to users</span></span>

<span data-ttu-id="53d69-104">U kunt licenties toewijzen aan gebruikers op de pagina **Actieve gebruikers** of op de pagina **Licenties**.</span><span class="sxs-lookup"><span data-stu-id="53d69-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="53d69-105">De methode die u gebruikt, is afhankelijk van of u productlicenties wilt toewijzen aan specifieke gebruikers of gebruikerslicenties wilt toewijzen aan een specifiek product.</span><span class="sxs-lookup"><span data-stu-id="53d69-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="53d69-106">Als beheerder kunt u geen licenties toewijzen of verwijderen voor een self-service aankoopabonnement dat door een gebruiker in uw organisatie is gekocht.</span><span class="sxs-lookup"><span data-stu-id="53d69-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="53d69-107">U kunt [self-service aankoopabonnementen overnemen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)en vervolgens licenties toewijzen of opheffen.</span><span class="sxs-lookup"><span data-stu-id="53d69-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="53d69-108">[Informatie over het toevoegen van een gebruiker en tegelijkertijd toewijzen van een licentie](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="53d69-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="53d69-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="53d69-109">Before you begin</span></span>

- <span data-ttu-id="53d69-110">U moet algemeen, licentie-, of gebruikersbeheerder zijn om licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="53d69-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="53d69-111">Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53d69-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="53d69-112">U kunt [Microsoft 365-licenties toewijzen aan gebruikersaccounts met PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="53d69-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="53d69-113">Voor groepslicenties, zie [Licenties toewijzen aan gebruikers op basis van groepslidmaatschap in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="53d69-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="53d69-114">Sommige services, zoals Sway, worden automatisch aan gebruikers toegewezen.Het is niet nodig deze afzonderlijk toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="53d69-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="53d69-115">Gebruik de pagina Licenties om licenties aan gebruikers toe te wijzen</span><span class="sxs-lookup"><span data-stu-id="53d69-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="53d69-116">Met behulp van de pagina **Licenties** kunt u licenties voor een specifiek product toewijzen aan maximaal 20 gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53d69-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="53d69-117">Op de pagina **Licenties** wordt een lijst weergegeven met alle producten waarvoor u een abonnement hebt.</span><span class="sxs-lookup"><span data-stu-id="53d69-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="53d69-118">U ziet ook het totale aantal licenties voor elk product, het aantal toegewezen licenties en het aantal beschikbare licenties.</span><span class="sxs-lookup"><span data-stu-id="53d69-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="53d69-119">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="53d69-120">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="53d69-121">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="53d69-122">Selecteer een product.</span><span class="sxs-lookup"><span data-stu-id="53d69-122">Select a product.</span></span>
3. <span data-ttu-id="53d69-123">Selecteer **Licenties toewijzen** op de pagina met productdetails.</span><span class="sxs-lookup"><span data-stu-id="53d69-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="53d69-124">Begin in het deelvenster **Licenties toewijzen aan gebruikers** met het typen van een naam en kies de naam in de resultaten om deze aan de lijst toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="53d69-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="53d69-125">U kunt maximaal 20 gebruikers tegelijk toevoegen.</span><span class="sxs-lookup"><span data-stu-id="53d69-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="53d69-126">Selecteer **Apps en services in- of uitschakelen** om de toegang tot bepaalde items toe te wijzen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="53d69-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="53d69-127">Wanneer u klaar bent, selecteert u achtereenvolgens **Toewijzen** en **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="53d69-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="53d69-128">Als er een conflict is, wordt er een bericht weergegeven waarin wordt uitgelegd wat het probleem is en hoe u dit kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="53d69-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="53d69-129">Als u bijvoorbeeld licenties hebt geselecteerd die conflicterende services bevatten, moet u de services die bij elke licentie zijn opgenomen controleren en het opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="53d69-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="53d69-130">De apps en services wijzigen waartoe een gebruiker toegang heeft</span><span class="sxs-lookup"><span data-stu-id="53d69-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="53d69-131">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="53d69-132">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="53d69-133">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="53d69-134">Selecteer op de pagina **Licenties** de rij voor een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="53d69-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="53d69-135">Selecteer of deselecteer in het rechterdeelvenster de apps en services waarvoor u toegang wilt verlenen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="53d69-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="53d69-136">Wanneer u klaar bent, selecteert u achtereenvolgens **Opslaan** en **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="53d69-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="53d69-137">Licenties toewijzen met de pagina Actieve gebruikers</span><span class="sxs-lookup"><span data-stu-id="53d69-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="53d69-138">Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties toe te wijzen, wijst u gebruikerslicenties aan producten toe.</span><span class="sxs-lookup"><span data-stu-id="53d69-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="53d69-139">Licenties toewijzen aan meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="53d69-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="53d69-140">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="53d69-141">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="53d69-142">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="53d69-143">Selecteer de cirkels naast de namen van de gebruikers aan wie u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="53d69-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="53d69-144">Selecteer bovenaan de optie **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="53d69-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="53d69-145">Selecteer in het deelvenster **Productlicenties beheren** de optie **Meer toewijzen: De bestaande licenties behouden en meer toewijzen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="53d69-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="53d69-146">Schakel onder **Licenties** het selectievakje in voor de licenties die u beschikbaar wilt stellen voor de geselecteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53d69-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="53d69-p107">De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers. Als u wilt beperken welke services beschikbaar zijn voor de gebruikers, schakelt u de selectievakjes uit voor de services die u niet beschikbaar wilt maken voor de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53d69-p107">By default, all services associated with those licenses are automatically assigned to the users. You can limit which services are available to the users. Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="53d69-150">Selecteer onderaan het deelvenster de optie **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53d69-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="53d69-151">Mogelijk moet u extra licenties kopen als u niet genoeg licenties voor iedereen hebt.</span><span class="sxs-lookup"><span data-stu-id="53d69-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="53d69-152">Als u licenties wilt toewijzen voor een groot aantal gebruikers, gebruikt u [Licenties toewijzen aan gebruikers op groepslidmaatschap in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="53d69-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="53d69-153">Licenties aan een enkele gebruiker toewijzen</span><span class="sxs-lookup"><span data-stu-id="53d69-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="53d69-154">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="53d69-155">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="53d69-156">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="53d69-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="53d69-157">Selecteer de rij van de gebruiker aan wie u een licentie wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="53d69-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="53d69-158">Selecteer in het rechterdeelvenster **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="53d69-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="53d69-159">Vouw de sectie **Licenties** uit en schakel de selectievakjes in voor de licenties die u wilt toewijzen. Selecteer vervolgens **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53d69-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="53d69-160">Een licentie toewijzen aan een gastgebruiker</span><span class="sxs-lookup"><span data-stu-id="53d69-160">Assign a license to a guest user</span></span>

<span data-ttu-id="53d69-161">U kunt gastgebruikers uitnodigen om samen te werken met uw organisatie in het Azure Active Directory-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="53d69-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="53d69-162">Raadpleeg [Wat is gastgebruikerstoegang in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b) voor meer informatie over gastgebruikers.</span><span class="sxs-lookup"><span data-stu-id="53d69-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="53d69-163">Raadpleeg [Snelstart: Gastgebruikers toevoegen aan uw adreslijst in de Azure-portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal) als u geen gastgebruikers hebt.</span><span class="sxs-lookup"><span data-stu-id="53d69-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53d69-164">U moet een globale beheerder zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="53d69-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="53d69-165">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory-beheercentrum</a></span><span class="sxs-lookup"><span data-stu-id="53d69-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="53d69-166">Kies **Gebruikers** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="53d69-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="53d69-167">Kies **Filters toevoegen** op de pagina **Gebruikers | Alle gebruikers (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="53d69-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="53d69-168">Kies **Gebruikerstype** in het menu **Een veld kiezen** en vervolgens **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="53d69-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="53d69-169">Kies **Gast** in het volgende menu.</span><span class="sxs-lookup"><span data-stu-id="53d69-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="53d69-170">Kies in de lijst met resultaten de gebruiker die een licentie nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="53d69-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="53d69-171">Kies **Licenties** onder **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="53d69-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="53d69-172">Kies **Opdrachten**.</span><span class="sxs-lookup"><span data-stu-id="53d69-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="53d69-173">Kies het product waarvoor u een licentie wilt toewijzen op de pagina **Licentietoewijzingen bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="53d69-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="53d69-174">Schakel aan de rechterkant de selectievakjes uit voor de services waarvoor u wilt dat de gastgebruiker geen toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="53d69-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="53d69-175">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53d69-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="53d69-176">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="53d69-176">Next steps</span></span>

<span data-ttu-id="53d69-177">Als de Office-apps nog niet door uw gebruikers zijn geïnstalleerd, kunt u de [Aan de slag-handleiding voor werknemers](../../business-video/employee-quick-setup.md) delen met uw gebruikers om dingen in te stellen, zoals [Microsoft 365 of Office 2019 op een pc of Mac downloaden en installeren](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) en [Office-apps en e-mail op een mobiel apparaat instellen](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="53d69-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="53d69-178">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="53d69-178">Related content</span></span>

<span data-ttu-id="53d69-179">[Informatie over abonnementen en licenties](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="53d69-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="53d69-180">[Licenties van gebruikers intrekken](remove-licenses-from-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="53d69-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="53d69-181">[Licenties kopen of intrekken voor uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="53d69-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
