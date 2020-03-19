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
ms.custom: ''
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account bij Microsoft.
ms.openlocfilehash: 3a193aea92ff384d53ce320a98cd9043d990b678
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812071"
---
# <a name="close-your-account"></a><span data-ttu-id="0d045-103">Uw account sluiten</span><span class="sxs-lookup"><span data-stu-id="0d045-103">Close your account</span></span>

<span data-ttu-id="0d045-104">Wanneer u uw account bij Microsoft sluit, worden alle gegevens met betrekking tot uw account verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d045-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="0d045-105">Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.</span><span class="sxs-lookup"><span data-stu-id="0d045-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="0d045-106">Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="0d045-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="0d045-107">Stap 1: Gebruikers verwijderen</span><span class="sxs-lookup"><span data-stu-id="0d045-107">Step 1: Delete users</span></span>

<span data-ttu-id="0d045-108">Verwijder alle gebruikers, behalve één globale beheerder die de stappen voltooit om het account te sluiten.</span><span class="sxs-lookup"><span data-stu-id="0d045-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="0d045-109">Voordat u de map aan het einde van dit proces verwijderen, moet u alle andere gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0d045-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="0d045-110">Als gebruikers worden gesynchroniseerd vanuit on-premises, schakel je de synchronisatie eerst uit en verwijder je de gebruikers in de cloudmap met behulp van de Azure-portal of Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0d045-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="0d045-111">Als u gebruikers wilt verwijderen, raadpleegt <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">u Beheerder gebruikersbeheer: Een of meer gebruikers verwijderen</a>.</span><span class="sxs-lookup"><span data-stu-id="0d045-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="0d045-112">U ook de cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell gebruiken om gebruikers in bulk te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0d045-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="0d045-113">Als uw organisatie Active Directory gebruikt die synchroniseert met Azure AD, verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d045-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="0d045-114">Zie <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulkgebruikers verwijderen in Azure Active Directory</a>voor instructies.</span><span class="sxs-lookup"><span data-stu-id="0d045-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="0d045-115">Stap 2: Alle actieve abonnementen opzeggen</span><span class="sxs-lookup"><span data-stu-id="0d045-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="0d045-116">Ga in het beheercentrum naar de pagina >  **Factureringsproducten**<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& services.</a></span><span class="sxs-lookup"><span data-stu-id="0d045-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="0d045-117">Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.</span><span class="sxs-lookup"><span data-stu-id="0d045-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="0d045-118">Zoek een actief abonnement en selecteer in de sectie **Instellingen & Acties** de optie Abonnement **annuleren**.</span><span class="sxs-lookup"><span data-stu-id="0d045-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="0d045-119">Volg de aanwijzingen om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0d045-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="0d045-120">Herhaal stap 1 tot en met 4 om alle actieve abonnementen op te zeggen.</span><span class="sxs-lookup"><span data-stu-id="0d045-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="0d045-121">Stap 3: Alle abonnementen voor uitgeschakelden verwijderen</span><span class="sxs-lookup"><span data-stu-id="0d045-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="0d045-122">Ga in het beheercentrum naar de pagina >  **Factureringsproducten**<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& services.</a></span><span class="sxs-lookup"><span data-stu-id="0d045-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="0d045-123">Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.</span><span class="sxs-lookup"><span data-stu-id="0d045-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="0d045-124">Selecteer Uitgeschakeld naast **de status Abonnement**. **Disabled**</span><span class="sxs-lookup"><span data-stu-id="0d045-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="0d045-125">Zoek een uitgeschakeld abonnement en selecteer in de sectie **Instellingen & Acties** de optie **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0d045-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="0d045-126">Schakel in het dialoogvenster **Abonnement verwijderen** het selectievakje Ik **begrijp het** effect in en selecteer Abonnement **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0d045-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="0d045-127">Herhaal stap 4 en 5 voor elk uitgeschakeld abonnement totdat alle abonnementen zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d045-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="0d045-128">Stap 4: Meervoudige verificatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="0d045-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="0d045-129">Ga in het beheercentrum naar de pagina **Gebruikers** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="0d045-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0d045-130">Kies **Multi-factor authenticatie**.</span><span class="sxs-lookup"><span data-stu-id="0d045-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="0d045-131">Schakel op de pagina multi-factor authenticatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0d045-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you’re currently using.</span></span>

<span data-ttu-id="0d045-132">U PowerShell ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen.</a></span><span class="sxs-lookup"><span data-stu-id="0d045-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="0d045-133">Stap 5: De map verwijderen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0d045-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="0d045-134">Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-beheercentrum</a> met een Algemeen Administrator-account.</span><span class="sxs-lookup"><span data-stu-id="0d045-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="0d045-135">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0d045-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="0d045-136">Schakel over naar de map die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0d045-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="0d045-137">Selecteer **Map verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0d045-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="0d045-138">Als uw directory een of meer controles niet haalt, ziet u een koppeling naar meer informatie over hoe u de controles doorstaan.</span><span class="sxs-lookup"><span data-stu-id="0d045-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="0d045-139">Nadat u alle controles hebt uitgevoerd, selecteert u **Verwijderen** om het proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0d045-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="0d045-140">Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d045-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
