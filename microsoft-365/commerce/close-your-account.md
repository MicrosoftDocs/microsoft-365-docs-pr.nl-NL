---
title: Uw account sluiten
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account met Microsoft.
ms.openlocfilehash: 19e9a92a90f7c88cc150844ab451bc71d63e4c4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911660"
---
# <a name="close-your-account"></a><span data-ttu-id="28a1c-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="28a1c-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="28a1c-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="28a1c-104">The admin center is changing.</span></span> <span data-ttu-id="28a1c-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="28a1c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="28a1c-106">Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28a1c-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="28a1c-107">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="28a1c-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28a1c-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="28a1c-108">Before you begin</span></span>

<span data-ttu-id="28a1c-109">Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="28a1c-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="28a1c-110">U moet een Globale of Factureringsbeheerder zijn om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="28a1c-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="28a1c-111">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="28a1c-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="28a1c-112">Stap 1: Gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="28a1c-112">Step 1: Delete users</span></span>

<span data-ttu-id="28a1c-113">Verwijder alle gebruikers, behalve één globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="28a1c-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="28a1c-114">De globale beheerder voltooit de stappen om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="28a1c-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="28a1c-115">Voordat u de adreslijst aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28a1c-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="28a1c-116">Als gebruikers on-premises worden gesynchroniseerd, moet u eerst synchronisatie uitschakelen en vervolgens de gebruikers in de cloudmap verwijderen met behulp van de Azure-portal of Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="28a1c-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="28a1c-117">Zie Gebruikersbeheerbeheerder als u gebruikers wilt <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">verwijderen: Een of meer gebruikers verwijderen.</a></span><span class="sxs-lookup"><span data-stu-id="28a1c-117">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="28a1c-118">U kunt ook de <a href="https://go.microsoft.com/fwlink/?linkid=842230">cmdlet Remove-MsolUser</a> PowerShell gebruiken om gebruikers bulksgewijs te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28a1c-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="28a1c-119">Als uw organisatie Active Directory gebruikt dat wordt gesynchroniseerd met Microsoft Azure Active Directory (Azure AD), verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28a1c-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="28a1c-120">Zie Gebruikers <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">bulksgewijs verwijderen in Azure Active Directory</a>voor instructies.</span><span class="sxs-lookup"><span data-stu-id="28a1c-120">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="28a1c-121">Stap 2: Alle actieve abonnementen opzeggen</span><span class="sxs-lookup"><span data-stu-id="28a1c-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="28a1c-122">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="28a1c-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="28a1c-123">Zoek op **het** tabblad Producten naar een actief abonnement.</span><span class="sxs-lookup"><span data-stu-id="28a1c-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="28a1c-124">Selecteer **Meer acties** (drie puntjes) en selecteer **Abonnement annuleren**.</span><span class="sxs-lookup"><span data-stu-id="28a1c-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="28a1c-125">Kies in het deelvenster **Abonnement annuleren** een reden waarom u wilt opzeggen.</span><span class="sxs-lookup"><span data-stu-id="28a1c-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="28a1c-126">Geef desgewenst feedback.</span><span class="sxs-lookup"><span data-stu-id="28a1c-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="28a1c-127">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="28a1c-127">Select **Save**.</span></span>
5. <span data-ttu-id="28a1c-128">Herhaal stap 1 tot en met 4 om alle actieve abonnementen te annuleren.</span><span class="sxs-lookup"><span data-stu-id="28a1c-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="28a1c-129">Stap 3: Alle uitgeschakelde abonnementen verwijderen</span><span class="sxs-lookup"><span data-stu-id="28a1c-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="28a1c-130">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="28a1c-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="28a1c-131">Selecteer op **het** tabblad Producten een uitgeschakeld abonnement.</span><span class="sxs-lookup"><span data-stu-id="28a1c-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="28a1c-132">Selecteer op de pagina Abonnementsgegevens in de sectie **Abonnements-** en betalingsinstellingen de optie **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28a1c-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="28a1c-133">Selecteer in **het deelvenster** Abonnement verwijderen de optie **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28a1c-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="28a1c-134">Selecteer ja **in het** dialoogvenster Abonnement **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28a1c-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="28a1c-135">Herhaal stap 3 tot en met 5 voor elk uitgeschakeld abonnement totdat alle abonnementen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28a1c-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="28a1c-136">Als u een uitgeschakeld abonnement niet direct kunt verwijderen, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">neem dan contact op met ondersteuning</a></span><span class="sxs-lookup"><span data-stu-id="28a1c-136">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="28a1c-137">Stap 4: Meervoudige verificatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="28a1c-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="28a1c-138">Meld u aan bij het beheercentrum met een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="28a1c-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="28a1c-139">Zie Beheerdersrollen controleren in uw organisatie als u wilt controleren welke rollen [u hebt.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="28a1c-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="28a1c-140">Ga naar de **pagina Actieve** gebruikers  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">van gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="28a1c-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="28a1c-141">Kies **Meervoudige verificatie.**</span><span class="sxs-lookup"><span data-stu-id="28a1c-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="28a1c-142">Schakel op de pagina meervoudige verificatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="28a1c-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="28a1c-143">U kunt <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell ook gebruiken om meervoudige</a>verificatie voor meerdere gebruikers uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="28a1c-143">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="28a1c-144">Stap 5: De adreslijst verwijderen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="28a1c-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="28a1c-145">Meld u aan bij <a href="https://aad.portal.azure.com/" target="_blank">het Azure AD-beheercentrum</a> met een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="28a1c-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="28a1c-146">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="28a1c-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="28a1c-147">Ga naar de organisatie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28a1c-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="28a1c-148">Selecteer **Tenant verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28a1c-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="28a1c-149">Als uw organisatie een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles.</span><span class="sxs-lookup"><span data-stu-id="28a1c-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="28a1c-150">Nadat u alle controles hebt uitgevoerd, **selecteert u Verwijderen om** het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="28a1c-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="28a1c-151">Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28a1c-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>