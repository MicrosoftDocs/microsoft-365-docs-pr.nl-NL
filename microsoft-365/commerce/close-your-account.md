---
title: Uw account sluiten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account bij Microsoft.
ms.openlocfilehash: f399a1ba4d67abf5982c111e9b915f02324150a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402176"
---
# <a name="close-your-account"></a><span data-ttu-id="87d80-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="87d80-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="87d80-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="87d80-104">The admin center is changing.</span></span> <span data-ttu-id="87d80-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="87d80-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="87d80-106">Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="87d80-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="87d80-107">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="87d80-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="87d80-108">Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="87d80-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="87d80-109">Stap 1: Gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="87d80-109">Step 1: Delete users</span></span>

<span data-ttu-id="87d80-110">Verwijder alle gebruikers, behalve één globale beheerder die de stappen voltooit om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="87d80-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="87d80-111">Voordat u de map aan het einde van dit proces verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="87d80-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="87d80-112">Als gebruikers worden gesynchroniseerd vanuit on-premises, schakel je de synchronisatie eerst uit en verwijder je de gebruikers in de cloudmap met behulp van de Azure-portal of Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="87d80-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="87d80-113">Als u gebruikers wilt verwijderen, raadpleegt <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">u Beheerder gebruikersbeheer: Een of meer gebruikers verwijderen</a>.</span><span class="sxs-lookup"><span data-stu-id="87d80-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="87d80-114">U ook de cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell gebruiken om gebruikers in bulk te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="87d80-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="87d80-115">Als uw organisatie Active Directory gebruikt die synchroniseert met Azure AD, verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="87d80-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="87d80-116">Zie <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulkgebruikers verwijderen in Azure Active Directory</a>voor instructies.</span><span class="sxs-lookup"><span data-stu-id="87d80-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="87d80-117">Stap 2: Alle actieve abonnementen opzeggen</span><span class="sxs-lookup"><span data-stu-id="87d80-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="87d80-118">Ga in het beheercentrum naar de pagina **Facturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a></span><span class="sxs-lookup"><span data-stu-id="87d80-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="87d80-119">Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.</span><span class="sxs-lookup"><span data-stu-id="87d80-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="87d80-120">Zoek een actief abonnement en selecteer in de sectie **Instellingen & Acties** de optie Abonnement **annuleren**.</span><span class="sxs-lookup"><span data-stu-id="87d80-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="87d80-121">Volg de aanwijzingen om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="87d80-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="87d80-122">Herhaal stap 1 tot en met 4 om alle actieve abonnementen op te zeggen.</span><span class="sxs-lookup"><span data-stu-id="87d80-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="87d80-123">Stap 3: Alle abonnementen voor uitgeschakelden verwijderen</span><span class="sxs-lookup"><span data-stu-id="87d80-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="87d80-124">Ga in het beheercentrum naar de pagina **Facturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a></span><span class="sxs-lookup"><span data-stu-id="87d80-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="87d80-125">Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.</span><span class="sxs-lookup"><span data-stu-id="87d80-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="87d80-126">Selecteer Uitgeschakeld naast **de status Abonnement**. **Disabled**</span><span class="sxs-lookup"><span data-stu-id="87d80-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="87d80-127">Zoek een uitgeschakeld abonnement en selecteer in de sectie **Instellingen & Acties** de optie **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="87d80-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="87d80-128">Schakel in het dialoogvenster **Abonnement verwijderen** het selectievakje Ik **begrijp het** effect in en selecteer Abonnement **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="87d80-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="87d80-129">Herhaal stap 4 en 5 voor elk uitgeschakeld abonnement totdat alle abonnementen zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="87d80-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="87d80-130">Stap 4: Meervoudige verificatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="87d80-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="87d80-131">Ga in het beheercentrum **Users**naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Gebruikers actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="87d80-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="87d80-132">Kies **Multi-factor authenticatie**.</span><span class="sxs-lookup"><span data-stu-id="87d80-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="87d80-133">Schakel op de pagina multi-factor authenticatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="87d80-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="87d80-134">U PowerShell ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen.</a></span><span class="sxs-lookup"><span data-stu-id="87d80-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="87d80-135">Stap 5: De map verwijderen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="87d80-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="87d80-136">Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-beheercentrum</a> met een Algemeen Administrator-account.</span><span class="sxs-lookup"><span data-stu-id="87d80-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="87d80-137">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="87d80-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="87d80-138">Schakel over naar de map die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="87d80-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="87d80-139">Selecteer **Map verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="87d80-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="87d80-140">Als uw directory een of meer controles niet haalt, ziet u een koppeling naar meer informatie over hoe u de controles doorstaan.</span><span class="sxs-lookup"><span data-stu-id="87d80-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="87d80-141">Nadat u alle controles hebt uitgevoerd, selecteert u **Verwijderen** om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="87d80-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="87d80-142">Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="87d80-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
