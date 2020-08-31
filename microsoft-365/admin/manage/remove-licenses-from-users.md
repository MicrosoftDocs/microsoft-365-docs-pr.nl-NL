---
title: Licenties van gebruikers verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Leer hoe u licenties van gebruikersaccounts intrekken.
ms.date: 07/01/2020
ms.openlocfilehash: 4441fd253c4cf5304562900bf31869eb4e0f21ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306537"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="aea88-103">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="aea88-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="aea88-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="aea88-104">The admin center is changing.</span></span> <span data-ttu-id="aea88-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="aea88-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="aea88-106">U kunt licenties toewijzen aan gebruikers op de pagina **actieve gebruikers** of op de pagina **licenties** .</span><span class="sxs-lookup"><span data-stu-id="aea88-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="aea88-107">Welke methode u gebruikt, is afhankelijk van de vraag of u productlicenties wilt intrekken voor specifieke gebruikers of gebruikerslicenties wilt intrekken voor een specifiek product.</span><span class="sxs-lookup"><span data-stu-id="aea88-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="aea88-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="aea88-108">Before you begin</span></span>

- <span data-ttu-id="aea88-109">U moet een globale, licentie, gebruikersbeheerder zijn om licenties op te heffen.</span><span class="sxs-lookup"><span data-stu-id="aea88-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="aea88-110">Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aea88-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="aea88-111">U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="aea88-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="aea88-112">U kunt ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) waaraan een licentie is toegewezen om de licentie beschikbaar te maken voor andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="aea88-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="aea88-113">Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="aea88-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="aea88-114">De pagina licenties gebruiken om licenties op te heffen</span><span class="sxs-lookup"><span data-stu-id="aea88-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="aea88-115">Wanneer u de pagina **licenties** gebruikt om licenties te detoewijzen, schaft u de toewijzingen voor een specifiek product aan voor maximaal 20 gebruikers.</span><span class="sxs-lookup"><span data-stu-id="aea88-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="aea88-116">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="aea88-117">Selecteer het product waarvoor u licenties wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="aea88-118">Selecteer de gebruikers voor wie u de licenties wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="aea88-119">Selecteer **licenties intrekken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="aea88-120">Selecteer in het vak **licenties intrekken** de optie **intrekken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="aea88-121">De pagina actieve gebruikers gebruiken om licenties op te heffen</span><span class="sxs-lookup"><span data-stu-id="aea88-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="aea88-122">Wanneer u de pagina **actieve gebruikers** gebruikt om licenties op te heffen, moet u productlicenties van gebruikers intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="aea88-123">Licenties intrekken voor één gebruiker</span><span class="sxs-lookup"><span data-stu-id="aea88-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="aea88-124">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-125">Selecteer de rij van de gebruiker voor wie u een licentie wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="aea88-126">Selecteer in het rechterdeelvenster **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="aea88-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="aea88-127">Vouw de sectie **licenties** uit, schakel de vakjes uit voor de licenties die u wilt intrekken en selecteer vervolgens **wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aea88-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="aea88-128">Licenties intrekken voor één gebruiker</span><span class="sxs-lookup"><span data-stu-id="aea88-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="aea88-129">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-130">Selecteer de gebruiker voor wie u de licentie wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="aea88-131">Selecteer aan de rechterkant in de rij **product licenties** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="aea88-132">Zet in het deelvenster **product licenties** de wisselknop op **uit** voor de licentie die u wilt intrekken voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="aea88-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="aea88-133">Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, wordt die licentie en alle services onder die licentie voor die gebruiker opheffen.</span><span class="sxs-lookup"><span data-stu-id="aea88-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="aea88-134">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="aea88-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="aea88-135">Licenties intrekken voor één gebruiker</span><span class="sxs-lookup"><span data-stu-id="aea88-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="aea88-136">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-137">Selecteer de gebruiker voor wie u de licentie wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="aea88-138">Selecteer aan de rechterkant in de rij **product licenties** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="aea88-139">Zet in het deelvenster **product licenties** de wisselknop op **uit** voor de licentie die u wilt intrekken voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="aea88-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="aea88-140">Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, wordt die licentie en alle services onder die licentie voor die gebruiker opheffen.</span><span class="sxs-lookup"><span data-stu-id="aea88-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="aea88-141">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="aea88-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="aea88-142">Licenties intrekken voor meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="aea88-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="aea88-143">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-144">Schakel de vakjes in naast de namen van de gebruikers voor wie u een licentie wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="aea88-145">Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="aea88-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="aea88-146">Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="aea88-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="aea88-147">Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in en selecteer vervolgens sluiten **vervangen** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="aea88-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="aea88-148">Licenties intrekken voor meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="aea88-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="aea88-149">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-150">Schakel de selectievakjes in naast de namen van de gebruikers waarvoor u alle licenties wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="aea88-151">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="aea88-152">Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="aea88-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="aea88-153">Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in **en selecteer vervolgens sluiten** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="aea88-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="aea88-154">Licenties intrekken voor meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="aea88-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="aea88-155">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="aea88-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="aea88-156">Schakel de selectievakjes in naast de namen van de gebruikers waarvoor u alle licenties wilt intrekken.</span><span class="sxs-lookup"><span data-stu-id="aea88-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="aea88-157">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="aea88-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="aea88-158">Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="aea88-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="aea88-159">Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in **en selecteer vervolgens sluiten** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="aea88-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="aea88-160">Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?</span><span class="sxs-lookup"><span data-stu-id="aea88-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="aea88-161">Wanneer een licentie van een gebruiker wordt verwijderd, worden de gegevens die aan dat account zijn gekoppeld, 30 dagen lang bewaard.</span><span class="sxs-lookup"><span data-stu-id="aea88-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="aea88-162">Na de termijn van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="aea88-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="aea88-163">Bestanden die zijn opgeslagen in OneDrive voor bedrijven, worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-Beheercentrum of wordt verwijderd via Active Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="aea88-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="aea88-164">Zie voor meer informatie [OneDrive-behoud en-verwijdering](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="aea88-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="aea88-165">Wanneer de licentie is verwijderd, kunt u het postvak van de gebruiker niet meer doorzoeken met behulp van een eDiscovery-hulpprogramma, zoals inhoud zoeken of Geavanceerd eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aea88-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="aea88-166">Zie voor meer informatie het artikel over het zoeken in een verbinding met een verbinding met de postvakken in [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="aea88-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="aea88-167">Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u in Exchange Online de postvakgegevens van een verwijderd gebruikersaccount bewaren met [inactieve postvakken](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="aea88-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="aea88-168">Zie [inactieve postvakken in Exchange Online maken en beheren](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aea88-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="aea88-169">Zie [een voormalige werknemer verwijderen](../add-users/remove-former-employee.md)voor informatie over het blokkeren van toegang van een gebruiker tot microsoft 365-gegevens na verwijdering van de licentie en over hoe u later toegang krijgt tot de gegevens.</span><span class="sxs-lookup"><span data-stu-id="aea88-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="aea88-170">Als u de licentie van een gebruiker verwijdert en er nog steeds Office-apps zijn geïnstalleerd, zien ze de [fouten met producten zonder licentie en activeringen in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) wanneer ze Office-apps gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aea88-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aea88-171">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="aea88-171">Next steps</span></span>

<span data-ttu-id="aea88-172">Als u niet [de ongebruikte licenties opnieuw wilt toewijzen aan andere gebruikers](../../managed-desktop/get-started/assign-licenses.md), kunt u overwegen om [de licenties van uw abonnement te verwijderen](../../commerce/licenses/buy-licenses.md) zodat u niet meer licenties betaalt dan u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="aea88-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="aea88-173">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aea88-173">Related content</span></span>

<span data-ttu-id="aea88-174">[Licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="aea88-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="aea88-175">[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="aea88-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="aea88-176">Meer [informatie over abonnementen en licenties in Microsoft 365 voor bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="aea88-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>