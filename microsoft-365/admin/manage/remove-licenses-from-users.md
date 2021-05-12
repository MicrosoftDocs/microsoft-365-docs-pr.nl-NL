---
title: Licenties van gebruikers verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Meer informatie over het verwijderen van licenties van gebruikersaccounts.
ms.date: 07/01/2020
ms.openlocfilehash: 6f2cbf65e1d6a38a4b1ed00976d4dd473d7331e9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332412"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="5401f-103">Licenties van gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="5401f-103">Unassign licenses from users</span></span>

<span data-ttu-id="5401f-104">U kunt licenties van gebruikers op  de pagina Actieve gebruikers of op de pagina **Licenties verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="5401f-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="5401f-105">De methode die u gebruikt, is afhankelijk van of u productlicenties van specifieke gebruikers wilt inleveren of gebruikerslicenties van een bepaald product wilt inleveren.</span><span class="sxs-lookup"><span data-stu-id="5401f-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="5401f-106">Als beheerder kunt u geen licenties toewijzen of verwijderen voor een self-service aankoopabonnement dat door een gebruiker in uw organisatie is gekocht.</span><span class="sxs-lookup"><span data-stu-id="5401f-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="5401f-107">U kunt [self-service aankoopabonnementen overnemen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)en vervolgens licenties toewijzen of opheffen.</span><span class="sxs-lookup"><span data-stu-id="5401f-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5401f-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="5401f-108">Before you begin</span></span>

- <span data-ttu-id="5401f-109">U moet een globale, licentie- en gebruikersbeheerder zijn om licenties te ontlenen.</span><span class="sxs-lookup"><span data-stu-id="5401f-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="5401f-110">Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5401f-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="5401f-111">U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5401f-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="5401f-112">U kunt ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) die aan een licentie zijn toegewezen om hun licentie beschikbaar te maken voor andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5401f-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="5401f-113">Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="5401f-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="5401f-114">Gebruik de pagina Licenties om licenties niet toe te staan</span><span class="sxs-lookup"><span data-stu-id="5401f-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="5401f-115">Wanneer u de pagina **Licenties** gebruikt om licenties niet toe te staan, kunt u licenties voor een specifiek product voor maximaal 20 gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5401f-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5401f-116">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="5401f-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5401f-117">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.</span><span class="sxs-lookup"><span data-stu-id="5401f-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5401f-118">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.</span><span class="sxs-lookup"><span data-stu-id="5401f-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5401f-119">Selecteer het product waarvoor u licenties wilt inleveren.</span><span class="sxs-lookup"><span data-stu-id="5401f-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="5401f-120">Selecteer de gebruikers waarvoor u licenties wilt inleveren.</span><span class="sxs-lookup"><span data-stu-id="5401f-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="5401f-121">Selecteer **Licenties niet toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="5401f-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="5401f-122">Selecteer in **het vak Licenties niet** toewijzen de optie Niet **toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="5401f-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="5401f-123">De pagina Actieve gebruikers gebruiken om licenties niet toe te staan</span><span class="sxs-lookup"><span data-stu-id="5401f-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="5401f-124">Wanneer u de pagina **Actieve gebruikers gebruikt** om licenties niet toe te staan, ontsiert u productlicenties van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5401f-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="5401f-125">Licenties van één gebruiker niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="5401f-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="5401f-126">Ga in het beheercentrum naar de pagina **Gebruikers** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5401f-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5401f-127">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="5401f-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5401f-128">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="5401f-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5401f-129">Selecteer de rij van de gebruiker voor wie u een licentie wilt ontlenen.</span><span class="sxs-lookup"><span data-stu-id="5401f-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="5401f-130">Selecteer in het rechterdeelvenster **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="5401f-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="5401f-131">Vouw de **sectie Licenties** uit, schakel de vakken uit voor de licenties die u niet wilt toewijzen en selecteer Vervolgens **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="5401f-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="5401f-132">Licenties van meerdere gebruikers niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="5401f-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5401f-133">Ga in het beheercentrum naar de pagina **Gebruikers** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5401f-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5401f-134">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="5401f-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5401f-135">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="5401f-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5401f-136">Selecteer de cirkels naast de namen van de gebruikers voor wie u licenties wilt ontlenen.</span><span class="sxs-lookup"><span data-stu-id="5401f-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="5401f-137">Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="5401f-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="5401f-138">Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="5401f-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="5401f-139">Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje **Alle productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **vervolgens Sluiten** \> **vervangen.**</span><span class="sxs-lookup"><span data-stu-id="5401f-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="5401f-140">Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?</span><span class="sxs-lookup"><span data-stu-id="5401f-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="5401f-141">Wanneer een licentie van een gebruiker wordt verwijderd, worden gegevens die aan dat account zijn gekoppeld, 30 dagen in bezit gehouden.</span><span class="sxs-lookup"><span data-stu-id="5401f-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="5401f-142">Na de respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="5401f-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="5401f-143">Bestanden die zijn opgeslagen in OneDrive voor Bedrijven, worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="5401f-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="5401f-144">Zie [OneDrive-bewaring en -verwijdering voor meer informatie.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="5401f-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="5401f-145">Wanneer de licentie wordt verwijderd, kan het postvak van de gebruiker niet meer worden doorzocht met behulp van een eDiscovery-hulpprogramma, zoals Zoeken naar inhoud of Geavanceerd eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5401f-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="5401f-146">Zie 'Verbroken of niet-gelicentieerde postvakken zoeken' in Inhoud zoeken [in Microsoft 365](../../compliance/content-search.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5401f-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="5401f-147">Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u met Exchange Online de postvakgegevens van een verwijderd gebruikersaccount behouden met [inactieve postvakken.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5401f-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="5401f-148">Zie Inactieve postvakken maken en beheren in Exchange Online voor [meer informatie.](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="5401f-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="5401f-149">Zie Een voormalige werknemer verwijderen voor informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u daarna toegang tot de gegevens [kunt krijgen.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="5401f-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="5401f-150">Als u de licentie van een gebruiker verwijdert en er nog Steeds Office-apps zijn geïnstalleerd, zien ze product- en [activeringsfouten](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) zonder licentie in Office wanneer ze Office-apps gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5401f-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5401f-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="5401f-151">Next steps</span></span>

<span data-ttu-id="5401f-152">Als u de ongebruikte licenties niet opnieuw wilt toewijzen aan [](../../commerce/licenses/buy-licenses.md) andere [gebruikers,](../../managed-desktop/get-started/assign-licenses.md)kunt u overwegen om de licenties uit uw abonnement te verwijderen, zodat u niet meer licenties betaalt dan u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="5401f-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="5401f-153">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="5401f-153">Related content</span></span>

<span data-ttu-id="5401f-154">[Licenties verwijderen uit uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5401f-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="5401f-155">[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5401f-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="5401f-156">[Meer informatie over abonnementen en licenties in Microsoft 365 voor Bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5401f-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
