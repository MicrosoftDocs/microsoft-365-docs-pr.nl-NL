---
title: Een geïsoleerde SharePoint Online-teamsite beheren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Beheer een geïsoleerde SharePoint Online-teamsite, voeg nieuwe gebruikers en groepen toe, verwijder gebruikers en groepen en maak een submap voor documenten met aangepaste machtigingen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059866"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c7b5c-103">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="c7b5c-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c7b5c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-104">**Applies to**</span></span>
- [<span data-ttu-id="c7b5c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c7b5c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c7b5c-106">Abonnement 1 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c7b5c-106">Microsoft Defender for Office 365 plan 1</span></span>](defender-for-office-365.md)
- <span data-ttu-id="c7b5c-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c7b5c-107">SharePoint Online</span></span> 

 <span data-ttu-id="c7b5c-108">**Overzicht:** Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="c7b5c-109">In dit artikel worden algemene beheerbewerkingen beschreven voor een geïsoleerde SharePoint Online-teamsite.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="c7b5c-110">Een nieuwe gebruiker toevoegen</span><span class="sxs-lookup"><span data-stu-id="c7b5c-110">Add a new user</span></span>

<span data-ttu-id="c7b5c-111">Wanneer iemand nieuw lid wordt van de site, moet u het deelnameniveau van de site bepalen:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="c7b5c-112">Beheer: Het nieuwe gebruikersaccount toevoegen aan de toegangsgroep voor sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="c7b5c-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="c7b5c-113">Actieve samenwerking: Het gebruikersaccount toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="c7b5c-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="c7b5c-114">Weergeven: Het gebruikersaccount toevoegen aan de groep sitekijkers</span><span class="sxs-lookup"><span data-stu-id="c7b5c-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="c7b5c-115">Als u gebruikersaccounts en groepen beheert via Ad DS (Active Directory Domain Services), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="c7b5c-116">Als u gebruikersaccounts en groepen beheert via Microsoft 365, kunt u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="c7b5c-117">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="c7b5c-118">Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c7b5c-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="c7b5c-119">Als u een gebruikersaccount wilt toevoegen aan een access-groep met de naam van de gebruikersnaam (UPN), gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="c7b5c-120">Als u een gebruikersaccount wilt toevoegen aan een access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="c7b5c-121">Een nieuwe groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="c7b5c-121">Add a new group</span></span>

<span data-ttu-id="c7b5c-122">Als u toegang wilt toevoegen aan een hele groep, moet u het deelnameniveau bepalen van alle leden van de groep op de site:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="c7b5c-123">Beheer: De groep toevoegen aan de toegangsgroep voor sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="c7b5c-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="c7b5c-124">Actieve samenwerking: De groep toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="c7b5c-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="c7b5c-125">Weergeven: De groep toevoegen aan de groep sitekijkers</span><span class="sxs-lookup"><span data-stu-id="c7b5c-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="c7b5c-126">Als u gebruikersaccounts en groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="c7b5c-127">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="c7b5c-128">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="c7b5c-129">Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c7b5c-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="c7b5c-130">Gebruik vervolgens de volgende PowerShell-opdrachten:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="c7b5c-131">Een gebruiker verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7b5c-131">Remove a user</span></span>

<span data-ttu-id="c7b5c-132">Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn of haar deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="c7b5c-133">Beheer: Het gebruikersaccount verwijderen uit de toegangsgroep voor sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="c7b5c-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="c7b5c-134">Actieve samenwerking: Het gebruikersaccount verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="c7b5c-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="c7b5c-135">Weergeven: Het gebruikersaccount verwijderen uit de groep toegang van sitekijkers</span><span class="sxs-lookup"><span data-stu-id="c7b5c-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="c7b5c-136">Als u gebruikersaccounts en groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="c7b5c-137">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="c7b5c-138">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="c7b5c-139">Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c7b5c-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="c7b5c-140">Als u een gebruikersaccount wilt verwijderen uit een access-groep met de UPN, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="c7b5c-141">Als u een gebruikersaccount wilt verwijderen uit een access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="c7b5c-142">Een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7b5c-142">Remove a group</span></span>

<span data-ttu-id="c7b5c-143">Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep uit de toegangsgroep waarvan ze momenteel lid zijn op basis van hun deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="c7b5c-144">Beheer: De groep verwijderen uit de toegangsgroep voor sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="c7b5c-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="c7b5c-145">Actieve samenwerking: De groep verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="c7b5c-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="c7b5c-146">Weergeven: De groep verwijderen uit de groep toegang van sitekijkers</span><span class="sxs-lookup"><span data-stu-id="c7b5c-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="c7b5c-147">Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="c7b5c-148">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="c7b5c-149">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="c7b5c-150">Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c7b5c-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="c7b5c-151">Als u een groep wilt verwijderen uit een access-groep met de weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="c7b5c-152">Een submap voor documenten maken met aangepaste machtigingen</span><span class="sxs-lookup"><span data-stu-id="c7b5c-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="c7b5c-153">In sommige gevallen moet een subset van de personen die op de geïsoleerde site werken, een meer privélocatie hebben om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="c7b5c-154">Voor SharePoint Online-sites kunt u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="c7b5c-155">Personen zonder machtigingen zien de submap niet.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="c7b5c-156">Ga als volgt te werk om een submap voor documenten te maken met aangepaste machtigingen:</span><span class="sxs-lookup"><span data-stu-id="c7b5c-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="c7b5c-157">Meld u aan bij een account dat lid is van de groep beheerderstoegang voor de site.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="c7b5c-158">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="c7b5c-159">Ga naar de geïsoleerde teamsite en klik op **Documenten.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="c7b5c-160">Blader naar de map in de map met documenten met de submap met aangepaste machtigingen, maak de map en open deze.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="c7b5c-161">Klik **op Delen.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-161">Click **Share**.</span></span>

5. <span data-ttu-id="c7b5c-162">Klik **op Gedeeld met > Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="c7b5c-163">Klik **op Machtigingen stoppen en** klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="c7b5c-164">Klik **op Delen.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-164">Click **Share**.</span></span>

8. <span data-ttu-id="c7b5c-165">Klik **op Gedeeld met > Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="c7b5c-166">Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="c7b5c-167">Klik op de pagina Machtigingen op **\<site name> Leden in de lijst**.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="c7b5c-168">Selecteer op **\<site name> de** pagina Leden het vinkje naast de groep siteledentoegang, klik op **Acties,** klik op **Gebruikers** verwijderen uit groep en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="c7b5c-169">Als u specifieke leden wilt toevoegen aan deze submap, klikt u op **Nieuwe > Gebruikers toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="c7b5c-170">Typ in **het** dialoogvenster Delen de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik vervolgens op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="c7b5c-171">Vernieuw de webpagina om de nieuwe resultaten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="c7b5c-172">Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Bezoekers en gebruik stap 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap (zo nodig) kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="c7b5c-173">Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Eigenaren en gebruik stap 11-14 om de set gebruikersaccounts op te geven die de machtigingen in de submap (zo nodig) kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="c7b5c-174">Sluit het **tabblad Personen en groepen** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7b5c-175">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c7b5c-175">See Also</span></span>

[<span data-ttu-id="c7b5c-176">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="c7b5c-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="c7b5c-177">Een team configureren met beveiligingsisolatie</span><span class="sxs-lookup"><span data-stu-id="c7b5c-177">Configure a team with security isolation</span></span>](/microsoft-365/solutions/secure-teams-security-isolation)
