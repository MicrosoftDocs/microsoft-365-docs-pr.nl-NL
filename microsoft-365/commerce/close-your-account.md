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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376315"
---
# <a name="close-your-account"></a><span data-ttu-id="3bee1-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="3bee1-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3bee1-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3bee1-104">The admin center is changing.</span></span> <span data-ttu-id="3bee1-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3bee1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="3bee1-106">Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3bee1-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="3bee1-107">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="3bee1-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3bee1-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="3bee1-108">Before you begin</span></span>

<span data-ttu-id="3bee1-109">Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="3bee1-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="3bee1-110">U moet een globale beheerder of Factureringsbeheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3bee1-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="3bee1-111">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3bee1-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="3bee1-112">Stap 1: gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="3bee1-112">Step 1: Delete users</span></span>

<span data-ttu-id="3bee1-113">Verwijder alle gebruikers behalve één globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3bee1-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="3bee1-114">De globale beheerder voert de stappen uit om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="3bee1-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="3bee1-115">Voordat u de map aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="3bee1-116">Als gebruikers worden gesynchroniseerd vanuit on-premises, moet u eerst synchroniseren uitschakelen en vervolgens de gebruikers in de Cloud Directory verwijderen met behulp van de cmdlets van Azure portal of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bee1-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="3bee1-117">Zie <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">gebruikers van Gebruikersbeheer: een of meer gebruikers verwijderen</a>om gebruikers te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="3bee1-118">U kunt de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdlet Remove-MsolUser</a> ook gebruiken om gebruikers bulksgewijs te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="3bee1-119">Als uw organisatie gebruikmaakt van Active Directory die wordt gesynchroniseerd met Microsoft Azure Active Directory (Azure AD), verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bee1-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="3bee1-120">Zie voor instructies een <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk verwijdering van gebruikers in azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="3bee1-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="3bee1-121">Stap 2: alle actieve abonnementen annuleren</span><span class="sxs-lookup"><span data-stu-id="3bee1-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="3bee1-122">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="3bee1-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="3bee1-123">Zoek op het tabblad **Products** een actief abonnement.</span><span class="sxs-lookup"><span data-stu-id="3bee1-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="3bee1-124">Selecteer **meer acties** (drie puntjes) en selecteer vervolgens **abonnement annuleren**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="3bee1-125">Kies in het deelvenster **abonnement annuleren** een reden waarom u wilt opzeggen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="3bee1-126">U kunt ook feedback geven.</span><span class="sxs-lookup"><span data-stu-id="3bee1-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="3bee1-127">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-127">Select **Save**.</span></span>
5. <span data-ttu-id="3bee1-128">Herhaal de stappen 1 tot en met 4 om alle actieve abonnementen te annuleren.</span><span class="sxs-lookup"><span data-stu-id="3bee1-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="3bee1-129">Stap 3: alle uitgeschakelde abonnementen verwijderen</span><span class="sxs-lookup"><span data-stu-id="3bee1-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="3bee1-130">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="3bee1-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="3bee1-131">Selecteer op het tabblad **Products** een uitgeschakeld abonnement.</span><span class="sxs-lookup"><span data-stu-id="3bee1-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="3bee1-132">Selecteer op de pagina Details van abonnement in de sectie **Abonnementen en betalings instellingen** de optie **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="3bee1-133">Selecteer in het deelvenster **abonnement verwijderen** de optie **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="3bee1-134">Selecteer in het dialoogvenster **abonnement verwijderen** de optie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="3bee1-135">Herhaal de stappen 3 tot en met 5 voor elk uitgeschakeld abonnement totdat alle abonnementen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3bee1-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="3bee1-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">Neem contact op met de ondersteuning</a> als u een uitgeschakeld abonnement niet onmiddellijk kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="3bee1-137">Stap 4: multi-factor Authentication uitschakelen</span><span class="sxs-lookup"><span data-stu-id="3bee1-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="3bee1-138">Meld u aan bij het Beheercentrum met het account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3bee1-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="3bee1-139">Raadpleeg [beheerdersrollen in uw organisatie controleren](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)om te controleren welke rollen u hebt.</span><span class="sxs-lookup"><span data-stu-id="3bee1-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="3bee1-140">Ga naar de pagina **gebruikers** van  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active Users</a> .</span><span class="sxs-lookup"><span data-stu-id="3bee1-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="3bee1-141">Kies **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="3bee1-142">Schakel op de pagina multi-factor Authentication alle accounts uit, met uitzondering van het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3bee1-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="3bee1-143">U kunt ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen</a>.</span><span class="sxs-lookup"><span data-stu-id="3bee1-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="3bee1-144">Stap 5: de map verwijderen in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3bee1-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="3bee1-145">Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-Beheercentrum</a> met het account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3bee1-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="3bee1-146">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3bee1-147">Ga naar de organisatie die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bee1-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="3bee1-148">Selecteer **Tenant verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3bee1-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="3bee1-149">Als in uw organisatie een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles.</span><span class="sxs-lookup"><span data-stu-id="3bee1-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="3bee1-150">Wanneer u alle controles hebt uitgevoerd, selecteert u **verwijderen** om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="3bee1-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="3bee1-151">Wanneer u deze laatste stap hebt voltooid, wordt uw account met Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3bee1-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>