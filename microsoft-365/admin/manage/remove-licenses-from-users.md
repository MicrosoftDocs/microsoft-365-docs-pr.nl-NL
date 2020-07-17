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
description: Meer informatie over het losmaken van licenties van gebruikersaccounts.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015933"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="3b4cc-103">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3b4cc-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-104">The admin center is changing.</span></span> <span data-ttu-id="3b4cc-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3b4cc-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="3b4cc-106">U licenties van gebruikers niet-verrijzen op de pagina **Actieve gebruikers** of op de pagina **Licenties.**</span><span class="sxs-lookup"><span data-stu-id="3b4cc-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="3b4cc-107">De methode die u gebruikt, is afhankelijk van de vraag of u productlicenties van specifieke gebruikers wilt onttekenen of licenties van gebruikers van een specifiek product wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="3b4cc-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="3b4cc-108">Before you begin</span></span>

- <span data-ttu-id="3b4cc-109">U moet een globale, licentie, gebruikersbeheerder zijn om licenties niet te vertekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="3b4cc-110">Zie [Informatie over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="3b4cc-111">U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b4cc-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="3b4cc-112">U ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) waaraan een licentie is toegewezen om hun licentie beschikbaar te maken voor andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="3b4cc-113">Wanneer u een gebruikersaccount verwijdert, is de licentie onmiddellijk beschikbaar om aan iemand anders toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="3b4cc-114">De pagina Licenties gebruiken om licenties niet te plaatsen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="3b4cc-115">Wanneer u de pagina **Licenties** gebruikt om licenties niet te plaatsen, u licenties voor een specifiek product voor maximaal 20 gebruikers onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="3b4cc-116">Ga in het beheercentrum **Billing** naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="3b4cc-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3b4cc-117">Selecteer het product waarvoor u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="3b4cc-118">Selecteer de gebruikers waarvoor u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="3b4cc-119">Selecteer **Licenties voor ondestekenen**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="3b4cc-120">Selecteer Onteken in het vak **Licenties voor ondestekenen.** **Unassign**</span><span class="sxs-lookup"><span data-stu-id="3b4cc-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="3b4cc-121">De pagina Actieve gebruikers gebruiken om licenties niet te plaatsen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="3b4cc-122">Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties niet te plaatsen, u productlicenties van gebruikers onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="3b4cc-123">Licenties van één gebruiker niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="3b4cc-124">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-125">Selecteer de rij van de gebruiker waarvoor u een licentie wilt onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="3b4cc-126">Selecteer in het rechterdeelvenster **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="3b4cc-127">Vouw de sectie **Licenties** uit, schakel de vakken uit voor de licenties die u wilt toewijzen en selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="3b4cc-128">Licenties van één gebruiker niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="3b4cc-129">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-130">Kies de gebruiker waarvoor u de licentie wilt onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="3b4cc-131">Selecteer Rechts in de rij **Productlicenties** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3b4cc-132">Schakel in het deelvenster **Productlicenties** de schakelaar in op de **positie Uit** voor de licentie die u niet wilt toewijzen voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="3b4cc-133">Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden de licentie en alle services onder die licentie voor die gebruiker niet ondertekend.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="3b4cc-134">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="3b4cc-135">Licenties van één gebruiker niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="3b4cc-136">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-137">Kies de gebruiker waarvoor u de licentie wilt onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="3b4cc-138">Selecteer Rechts in de rij **Productlicenties** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3b4cc-139">Schakel in het deelvenster **Productlicenties** de schakelaar in op de **positie Uit** voor de licentie die u niet wilt toewijzen voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="3b4cc-140">Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden de licentie en alle services onder die licentie voor die gebruiker niet ondertekend.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="3b4cc-141">Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="3b4cc-142">Licenties van meerdere gebruikers niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="3b4cc-143">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-144">Selecteer de kringen naast de namen van de gebruikers waarvoor u licenties wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="3b4cc-145">Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="3b4cc-146">Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3b4cc-147">Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten **Replace** \> **vervangen**in.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="3b4cc-148">Licenties van meerdere gebruikers niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="3b4cc-149">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-150">Selecteer de vakken naast de namen van de gebruikers waarvoor u alle licenties wilt onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="3b4cc-151">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3b4cc-152">Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3b4cc-153">Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten sluiten **vervangen** \> **Close** \> **Close**in.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="3b4cc-154">Licenties van meerdere gebruikers niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="3b4cc-155">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b4cc-156">Selecteer de vakken naast de namen van de gebruikers waarvoor u alle licenties wilt onttekenen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="3b4cc-157">Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3b4cc-158">Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3b4cc-159">Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten sluiten **vervangen** \> **Close** \> **Close**in.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="3b4cc-160">Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?</span><span class="sxs-lookup"><span data-stu-id="3b4cc-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="3b4cc-161">Wanneer een licentie van een gebruiker wordt verwijderd, worden gegevens die aan dat account zijn gekoppeld, gedurende 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="3b4cc-162">Na de respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="3b4cc-163">Bestanden die zijn opgeslagen in OneDrive voor Bedrijven worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="3b4cc-164">Zie [Retentie en verwijdering](https://docs.microsoft.com/onedrive/retention-and-deletion)van OneDrive voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="3b4cc-165">Wanneer de licentie wordt verwijderd, is het postvak van de gebruiker niet langer doorzoekbaar met behulp van een eDiscovery-tool, zoals Content Search of Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="3b4cc-166">Zie 'Zoeken naar gekoppelde of gedelicentieerde postvakken' in [Content Search in Microsoft 365 voor](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="3b4cc-167">Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, u met Exchange Online de postvakgegevens van een verwijderd gebruikersaccount bewaren met behulp van [inactieve postvakken](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="3b4cc-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="3b4cc-168">Zie [Inactieve postvakken maken en beheren in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="3b4cc-169">[Zie Een voormalige werknemer](../add-users/remove-former-employee.md)verwijderen voor meer informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u daarna toegang tot de gegevens krijgen.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="3b4cc-170">Als u de licentie van een gebruiker verwijdert en Office-apps nog steeds zijn geïnstalleerd, worden [er in Office product- en activeringsfouten zonder licentie](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) weergegeven wanneer deze Office-apps gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b4cc-171">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="3b4cc-171">Next steps</span></span>

<span data-ttu-id="3b4cc-172">Als u [de ongebruikte licenties](../../managed-desktop/get-started/assign-licenses.md)niet opnieuw wilt toewijzen aan andere gebruikers, u overwegen [de licenties uit uw abonnement](../../commerce/licenses/buy-licenses.md) te verwijderen, zodat u niet voor meer licenties betaalt dan u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="3b4cc-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="3b4cc-173">Gerelateerde inhoud</span><span class="sxs-lookup"><span data-stu-id="3b4cc-173">Related content</span></span>

<span data-ttu-id="3b4cc-174">[Licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3b4cc-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="3b4cc-175">[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3b4cc-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="3b4cc-176">[Abonnementen en licenties begrijpen in Microsoft 365 voor bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3b4cc-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>