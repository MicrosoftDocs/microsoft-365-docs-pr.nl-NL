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
ms.openlocfilehash: 9545c43ee27fb000149776527030b04b5e807a5c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638373"
---
# <a name="close-your-account"></a><span data-ttu-id="d10ff-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="d10ff-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d10ff-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d10ff-104">The admin center is changing.</span></span> <span data-ttu-id="d10ff-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d10ff-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d10ff-106">Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d10ff-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="d10ff-107">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="d10ff-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="d10ff-108">Voordat u met deze procedure begint, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="d10ff-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="d10ff-109">Stap 1: gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="d10ff-109">Step 1: Delete users</span></span>

<span data-ttu-id="d10ff-110">Verwijder alle gebruikers behalve één globale beheerder die de stappen uitvoert om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="d10ff-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="d10ff-111">Voordat u de map aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d10ff-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="d10ff-112">Als gebruikers worden gesynchroniseerd vanuit on-premises, moet u eerst synchroniseren uitschakelen en vervolgens de gebruikers in de Cloud Directory verwijderen met behulp van de cmdlets van Azure portal of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d10ff-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="d10ff-113">Zie <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">gebruikers van Gebruikersbeheer: een of meer gebruikers verwijderen</a>om gebruikers te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d10ff-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="d10ff-114">U kunt de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdlet Remove-MsolUser</a> ook gebruiken om gebruikers bulksgewijs te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d10ff-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="d10ff-115">Als uw organisatie gebruikmaakt van Active Directory die wordt gesynchroniseerd met Azure AD, moet u in plaats daarvan het gebruikersaccount uit Active Directory verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d10ff-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="d10ff-116">Zie voor instructies een <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk verwijdering van gebruikers in azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="d10ff-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="d10ff-117">Stap 2: alle actieve abonnementen annuleren</span><span class="sxs-lookup"><span data-stu-id="d10ff-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="d10ff-118">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="d10ff-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="d10ff-119">Als de lijst met abonnementen in de **tabel** weergave wordt weergegeven, selecteert u **kaarten**aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="d10ff-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="d10ff-120">Zoek een actief abonnement en selecteer in de sectie **instellingen & acties** de optie **abonnement opzeggen**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="d10ff-121">Volg de aanwijzingen om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d10ff-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="d10ff-122">Herhaal de stappen 1 tot en met 4 om alle actieve abonnementen te annuleren.</span><span class="sxs-lookup"><span data-stu-id="d10ff-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="d10ff-123">Stap 3: alle uitgeschakelde abonnementen verwijderen</span><span class="sxs-lookup"><span data-stu-id="d10ff-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="d10ff-124">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="d10ff-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="d10ff-125">Als de lijst met abonnementen in de **tabel** weergave wordt weergegeven, selecteert u **kaarten**aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="d10ff-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="d10ff-126">Selecteer naast **status van abonnement**de optie **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="d10ff-127">Zoek een uitgeschakeld abonnement, en selecteer in de sectie **instellingen & acties** de optie **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="d10ff-128">Schakel in het dialoogvenster **abonnement verwijderen** het selectievakje **Ik weet het effect** in en selecteer vervolgens **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="d10ff-129">Herhaal de stappen 4 en 5 totdat alle abonnementen zijn verwijderd voor elk uitgeschakeld abonnement.</span><span class="sxs-lookup"><span data-stu-id="d10ff-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="d10ff-130">Stap 4: multi-factor Authentication uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d10ff-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="d10ff-131">Ga in het Beheercentrum naar de pagina **gebruikers**van  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active Users</a> .</span><span class="sxs-lookup"><span data-stu-id="d10ff-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d10ff-132">Kies **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="d10ff-133">Schakel op de pagina multi-factor Authentication alle accounts uit, met uitzondering van het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d10ff-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="d10ff-134">U kunt ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen</a>.</span><span class="sxs-lookup"><span data-stu-id="d10ff-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="d10ff-135">Stap 5: de map verwijderen in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d10ff-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="d10ff-136">Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-Beheercentrum</a> met het account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="d10ff-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="d10ff-137">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="d10ff-138">Ga naar de map die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d10ff-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="d10ff-139">Selecteer **map verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="d10ff-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="d10ff-140">Als er in de Directory een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles.</span><span class="sxs-lookup"><span data-stu-id="d10ff-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="d10ff-141">Wanneer u alle controles hebt uitgevoerd, selecteert u **verwijderen** om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d10ff-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="d10ff-142">Wanneer u deze laatste stap hebt voltooid, wordt uw account met Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d10ff-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
