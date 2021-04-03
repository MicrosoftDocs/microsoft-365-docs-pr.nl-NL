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
ms.openlocfilehash: 0ee0a649a9adb93ecdbb1cd9dbedbc04dfb46ba0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579744"
---
# <a name="close-your-account"></a><span data-ttu-id="442c8-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="442c8-103">Close your account</span></span>

<span data-ttu-id="442c8-104">Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="442c8-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="442c8-105">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="442c8-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="442c8-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="442c8-106">Before you begin</span></span>

<span data-ttu-id="442c8-107">Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="442c8-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="442c8-108">U moet een Globale of Factureringsbeheerder zijn om de stappen in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="442c8-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="442c8-109">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="442c8-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="442c8-110">Stap 1: Gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="442c8-110">Step 1: Delete users</span></span>

<span data-ttu-id="442c8-111">Verwijder alle gebruikers, behalve één globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="442c8-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="442c8-112">De globale beheerder voltooit de stappen om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="442c8-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="442c8-113">Voordat u de adreslijst aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="442c8-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="442c8-114">Als gebruikers on-premises worden gesynchroniseerd, moet u eerst synchronisatie uitschakelen en vervolgens de gebruikers in de cloudmap verwijderen met behulp van de Azure-portal of Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="442c8-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="442c8-115">Zie Gebruikersbeheerbeheerder als u gebruikers wilt <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">verwijderen: Een of meer gebruikers verwijderen.</a></span><span class="sxs-lookup"><span data-stu-id="442c8-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="442c8-116">U kunt ook de <a href="https://go.microsoft.com/fwlink/?linkid=842230">cmdlet Remove-MsolUser</a> PowerShell gebruiken om gebruikers bulksgewijs te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="442c8-116">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="442c8-117">Als uw organisatie Active Directory gebruikt dat wordt gesynchroniseerd met Microsoft Azure Active Directory (Azure AD), verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="442c8-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="442c8-118">Zie Gebruikers <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">bulksgewijs verwijderen in Azure Active Directory</a>voor instructies.</span><span class="sxs-lookup"><span data-stu-id="442c8-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="442c8-119">Stap 2: Alle actieve abonnementen opzeggen</span><span class="sxs-lookup"><span data-stu-id="442c8-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="442c8-120">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="442c8-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="442c8-121">Zoek op **het** tabblad Producten naar een actief abonnement.</span><span class="sxs-lookup"><span data-stu-id="442c8-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="442c8-122">Selecteer **Meer acties** (drie puntjes) en selecteer **Abonnement annuleren**.</span><span class="sxs-lookup"><span data-stu-id="442c8-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="442c8-123">Kies in het deelvenster **Abonnement annuleren** een reden waarom u wilt opzeggen.</span><span class="sxs-lookup"><span data-stu-id="442c8-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="442c8-124">Geef desgewenst feedback.</span><span class="sxs-lookup"><span data-stu-id="442c8-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="442c8-125">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="442c8-125">Select **Save**.</span></span>
5. <span data-ttu-id="442c8-126">Herhaal stap 1 tot en met 4 om alle actieve abonnementen te annuleren.</span><span class="sxs-lookup"><span data-stu-id="442c8-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="442c8-127">Stap 3: Alle uitgeschakelde abonnementen verwijderen</span><span class="sxs-lookup"><span data-stu-id="442c8-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="442c8-128">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="442c8-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="442c8-129">Selecteer op **het** tabblad Producten een uitgeschakeld abonnement.</span><span class="sxs-lookup"><span data-stu-id="442c8-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="442c8-130">Selecteer op de pagina Abonnementsgegevens in de sectie **Abonnements-** en betalingsinstellingen de optie **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="442c8-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="442c8-131">Selecteer in **het deelvenster** Abonnement verwijderen de optie **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="442c8-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="442c8-132">Selecteer ja **in het** dialoogvenster Abonnement **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="442c8-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="442c8-133">Herhaal stap 3 tot en met 5 voor elk uitgeschakeld abonnement totdat alle abonnementen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="442c8-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="442c8-134">Als u een uitgeschakeld abonnement niet direct kunt verwijderen, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">neem dan contact op met ondersteuning</a></span><span class="sxs-lookup"><span data-stu-id="442c8-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="442c8-135">Stap 4: Meervoudige verificatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="442c8-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="442c8-136">Meld u aan bij het beheercentrum met een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="442c8-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="442c8-137">Zie Beheerdersrollen controleren in uw organisatie als u wilt controleren welke rollen [u hebt.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="442c8-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="442c8-138">Ga naar de **pagina Actieve** gebruikers  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">van gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="442c8-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="442c8-139">Kies **Meervoudige verificatie.**</span><span class="sxs-lookup"><span data-stu-id="442c8-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="442c8-140">Schakel op de pagina meervoudige verificatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="442c8-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="442c8-141">U kunt <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell ook gebruiken om meervoudige</a>verificatie voor meerdere gebruikers uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="442c8-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="442c8-142">Stap 5: De adreslijst verwijderen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="442c8-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="442c8-143">Meld u aan bij <a href="https://aad.portal.azure.com/" target="_blank">het Azure AD-beheercentrum</a> met een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="442c8-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="442c8-144">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="442c8-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="442c8-145">Ga naar de organisatie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="442c8-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="442c8-146">Selecteer **Tenant verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="442c8-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="442c8-147">Als uw organisatie een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles.</span><span class="sxs-lookup"><span data-stu-id="442c8-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="442c8-148">Nadat u alle controles hebt uitgevoerd, **selecteert u Verwijderen om** het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="442c8-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="442c8-149">Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="442c8-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>