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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Samenvatting: Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.'
ms.openlocfilehash: 59c86c869ed38c3e64ff19974660cf96ec4c715e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810432"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="5f5de-103">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="5f5de-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="5f5de-104">**Samenvatting:** Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.</span><span class="sxs-lookup"><span data-stu-id="5f5de-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="5f5de-105">In dit artikel worden algemene beheerbewerkingen beschreven voor een geïsoleerde SharePoint Online-teamsite.</span><span class="sxs-lookup"><span data-stu-id="5f5de-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="5f5de-106">Een nieuwe gebruiker toevoegen</span><span class="sxs-lookup"><span data-stu-id="5f5de-106">Add a new user</span></span>

<span data-ttu-id="5f5de-107">Wanneer iemand nieuwe lid wordt van de site, moet u beslissen over hun niveau van deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="5f5de-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="5f5de-108">Beheer: het nieuwe gebruikersaccount toevoegen aan de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="5f5de-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="5f5de-109">Actieve samenwerking: het gebruikersaccount toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="5f5de-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="5f5de-110">Weergeven: het gebruikersaccount toevoegen aan de toegangsgroep voor sitekijkers</span><span class="sxs-lookup"><span data-stu-id="5f5de-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="5f5de-111">Als u gebruikersaccounts en -groepen beheert via Ad DS (Active Directory Domain Services), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Office 365 Abonnement.</span><span class="sxs-lookup"><span data-stu-id="5f5de-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="5f5de-112">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5f5de-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="5f5de-113">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="5f5de-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="5f5de-114">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5f5de-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="5f5de-115">Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de hoofdnaam van de gebruiker (UPN), gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="5f5de-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="5f5de-116">Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="5f5de-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="5f5de-117">Een nieuwe groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="5f5de-117">Add a new group</span></span>

<span data-ttu-id="5f5de-118">Als u toegang wilt toevoegen aan een hele groep, moet u bepalen welk deelnameniveau alle leden van de groep op de site zijn:</span><span class="sxs-lookup"><span data-stu-id="5f5de-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="5f5de-119">Beheer: de groep toevoegen aan de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="5f5de-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="5f5de-120">Actieve samenwerking: de groep toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="5f5de-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="5f5de-121">Weergeven: de groep toevoegen aan de toegangsgroep voor sitekijkers</span><span class="sxs-lookup"><span data-stu-id="5f5de-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="5f5de-122">Als u gebruikersaccounts en -groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="5f5de-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="5f5de-123">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5f5de-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5f5de-124">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="5f5de-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="5f5de-125">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5f5de-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="5f5de-126">Gebruik vervolgens de volgende PowerShell-opdrachten:</span><span class="sxs-lookup"><span data-stu-id="5f5de-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="5f5de-127">Een gebruiker verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f5de-127">Remove a user</span></span>

<span data-ttu-id="5f5de-128">Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="5f5de-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="5f5de-129">Beheer: het gebruikersaccount verwijderen uit de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="5f5de-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="5f5de-130">Actieve samenwerking: het gebruikersaccount verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="5f5de-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="5f5de-131">Weergeven: het gebruikersaccount verwijderen uit de toegangsgroep voor sitekijkers</span><span class="sxs-lookup"><span data-stu-id="5f5de-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="5f5de-132">Als u gebruikersaccounts en -groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="5f5de-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="5f5de-133">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5f5de-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5f5de-134">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5f5de-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="5f5de-135">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5f5de-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="5f5de-136">Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de UPN, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="5f5de-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="5f5de-137">Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="5f5de-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="5f5de-138">Een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f5de-138">Remove a group</span></span>

<span data-ttu-id="5f5de-139">Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep uit de toegangsgroep waarvoor ze momenteel lid zijn op basis van hun deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="5f5de-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="5f5de-140">Beheer: de groep verwijderen uit de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="5f5de-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="5f5de-141">Actieve samenwerking: de groep verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="5f5de-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="5f5de-142">Bekijken: de groep verwijderen uit de toegangsgroep voor sitekijkers</span><span class="sxs-lookup"><span data-stu-id="5f5de-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="5f5de-143">Als u gebruikersaccounts en -groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Office 365 Abonnement.</span><span class="sxs-lookup"><span data-stu-id="5f5de-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="5f5de-144">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5f5de-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5f5de-145">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5f5de-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="5f5de-146">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5f5de-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="5f5de-147">Als u een groep uit een toegangsgroep wilt verwijderen met hun weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="5f5de-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="5f5de-148">Een submap voor documenten maken met aangepaste machtigingen</span><span class="sxs-lookup"><span data-stu-id="5f5de-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="5f5de-149">In sommige gevallen heeft een deel van de mensen die op de geïsoleerde site werken een meer privéplek nodig om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="5f5de-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="5f5de-150">Voor SharePoint Online-sites u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="5f5de-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="5f5de-151">Degenen zonder machtigingen zien de submap niet.</span><span class="sxs-lookup"><span data-stu-id="5f5de-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="5f5de-152">Ga als volgt te werk om een submap voor documenten met aangepaste machtigingen te maken:</span><span class="sxs-lookup"><span data-stu-id="5f5de-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="5f5de-153">Meld u aan bij Office 365 met een account dat lid is van de beheertoegangsgroep voor de site.</span><span class="sxs-lookup"><span data-stu-id="5f5de-153">Sign in to Office 365 with an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="5f5de-154">Zie Waar [moet u zich aanmelden bij Office 365 voor](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)hulp.</span><span class="sxs-lookup"><span data-stu-id="5f5de-154">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5f5de-155">Ga naar de geïsoleerde teamsite en klik op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="5f5de-156">Blader naar de map in de map met documenten die de submap met aangepaste machtigingen bevat, maak de map en open deze.</span><span class="sxs-lookup"><span data-stu-id="5f5de-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="5f5de-157">Klik **op Delen**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="5f5de-158">Klik **op Gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="5f5de-159">Klik **op Overnemen van machtigingen**stoppen en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5f5de-160">Klik **op Delen**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="5f5de-161">Klik **op Gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="5f5de-162">Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="5f5de-163">Klik op de pagina machtigingen op \*\* \<sitenaam> leden in de lijst\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f5de-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="5f5de-164">Selecteer **OK**op de **Remove users from group** **Actions** \*\* \<\*\* pagina sitenaam> leden het vinkje naast de toegangsgroep voor siteleden, klik op Acties, klik op Gebruikers uit de groep verwijderen en klik vervolgens op OK .</span><span class="sxs-lookup"><span data-stu-id="5f5de-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="5f5de-165">Als u specifieke leden aan deze submap wilt toevoegen, klikt u op **Nieuwe > Gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="5f5de-166">Typ **in** het dialoogvenster Delen de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="5f5de-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="5f5de-167">Vernieuw de webpagina om de nieuwe resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="5f5de-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="5f5de-168">Klik **onder Groepen** in de linkernavigatie op de \*\* \<sitenaam> groep Bezoekers\*\* en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap kunnen weergeven (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="5f5de-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="5f5de-169">Klik **onder Groepen** in de linkernavigatie op de \*\* \<sitenaam> groep Eigenaren\*\* en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de machtigingen in de submap kunnen beheren (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="5f5de-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="5f5de-170">Sluit het tabblad **Personen en groepen** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="5f5de-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f5de-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5f5de-171">See Also</span></span>

[<span data-ttu-id="5f5de-172">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="5f5de-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="5f5de-173">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="5f5de-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5f5de-174">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="5f5de-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



