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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Beheer een geïsoleerde SharePoint Online-teamsite, voeg nieuwe gebruikers en groepen toe, verwijder gebruikers en groepen en maak een submap voor documenten met aangepaste machtigingen.
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755376"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="8445c-103">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="8445c-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="8445c-104">**Samenvatting:** Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.</span><span class="sxs-lookup"><span data-stu-id="8445c-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="8445c-105">In dit artikel worden algemene beheerbewerkingen voor een geïsoleerde SharePoint Online-teamsite beschreven.</span><span class="sxs-lookup"><span data-stu-id="8445c-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="8445c-106">Een nieuwe gebruiker toevoegen</span><span class="sxs-lookup"><span data-stu-id="8445c-106">Add a new user</span></span>

<span data-ttu-id="8445c-107">Wanneer iemand nieuw lid wordt van de site, moet u beslissen hun niveau van deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="8445c-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="8445c-108">Beheer: het nieuwe gebruikersaccount toevoegen aan de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="8445c-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="8445c-109">Actieve samenwerking: het gebruikersaccount toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="8445c-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="8445c-110">Bekijken: het gebruikersaccount toevoegen aan de groep die kijkers van de site openen</span><span class="sxs-lookup"><span data-stu-id="8445c-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="8445c-111">Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="8445c-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="8445c-112">Als u gebruikersaccounts en groepen beheert via Microsoft 365, u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8445c-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="8445c-113">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="8445c-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="8445c-114">Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="8445c-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="8445c-115">Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de gebruikersnaam (UPN), gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="8445c-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="8445c-116">Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="8445c-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="8445c-117">Een nieuwe groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="8445c-117">Add a new group</span></span>

<span data-ttu-id="8445c-118">Als u toegang wilt toevoegen tot een hele groep, moet u het deelnameniveau van alle leden van de groep op de site bepalen:</span><span class="sxs-lookup"><span data-stu-id="8445c-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="8445c-119">Beheer: de groep toevoegen aan de toegangsgroep sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="8445c-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="8445c-120">Actieve samenwerking: de groep toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="8445c-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="8445c-121">Bekijken: de groep toevoegen aan de groep die kijkers van de site openen</span><span class="sxs-lookup"><span data-stu-id="8445c-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="8445c-122">Als u gebruikersaccounts en groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="8445c-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="8445c-123">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8445c-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="8445c-124">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="8445c-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="8445c-125">Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="8445c-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="8445c-126">Gebruik vervolgens de volgende PowerShell-opdrachten:</span><span class="sxs-lookup"><span data-stu-id="8445c-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="8445c-127">Een gebruiker verwijderen</span><span class="sxs-lookup"><span data-stu-id="8445c-127">Remove a user</span></span>

<span data-ttu-id="8445c-128">Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze persoon uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="8445c-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="8445c-129">Beheer: het gebruikersaccount verwijderen uit de toegangsgroep van sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="8445c-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="8445c-130">Actieve samenwerking: het gebruikersaccount verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="8445c-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="8445c-131">Bekijken: het gebruikersaccount verwijderen uit de groep waar kijkers toegang tot hebben</span><span class="sxs-lookup"><span data-stu-id="8445c-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="8445c-132">Als u gebruikersaccounts en groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="8445c-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="8445c-133">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8445c-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="8445c-134">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8445c-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="8445c-135">Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="8445c-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="8445c-136">Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de UPN, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="8445c-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="8445c-137">Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="8445c-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="8445c-138">Een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="8445c-138">Remove a group</span></span>

<span data-ttu-id="8445c-139">Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep uit de toegangsgroep waarvoor ze momenteel lid zijn op basis van hun deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="8445c-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="8445c-140">Beheer: de groep verwijderen uit de toegangsgroep van sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="8445c-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="8445c-141">Actieve samenwerking: de groep verwijderen uit de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="8445c-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="8445c-142">Bekijken: de groep verwijderen uit de groep die kijkers van de site openen</span><span class="sxs-lookup"><span data-stu-id="8445c-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="8445c-143">Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="8445c-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="8445c-144">Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8445c-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="8445c-145">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8445c-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="8445c-146">Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="8445c-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="8445c-147">Als u een groep uit een toegangsgroep wilt verwijderen met hun weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="8445c-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="8445c-148">Een submap voor documenten maken met aangepaste machtigingen</span><span class="sxs-lookup"><span data-stu-id="8445c-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="8445c-149">In sommige gevallen heeft een deelverzameling van de mensen die op de geïsoleerde site werken een meer privéplek nodig om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="8445c-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="8445c-150">Voor SharePoint Online-sites u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8445c-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="8445c-151">Degenen zonder machtigingen zien de submap niet.</span><span class="sxs-lookup"><span data-stu-id="8445c-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="8445c-152">Ga als volgt te werk om een submap voor documenten met aangepaste machtigingen te maken:</span><span class="sxs-lookup"><span data-stu-id="8445c-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="8445c-153">Meld u aan bij een account dat lid is van de beheerderstoegangsgroep voor de site.</span><span class="sxs-lookup"><span data-stu-id="8445c-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="8445c-154">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="8445c-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="8445c-155">Ga naar de geïsoleerde teamsite en klik op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="8445c-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="8445c-156">Blader naar de map in de map documenten die de submap met aangepaste machtigingen bevat, maak de map en open deze vervolgens.</span><span class="sxs-lookup"><span data-stu-id="8445c-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="8445c-157">Klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="8445c-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="8445c-158">Klik **op Gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="8445c-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="8445c-159">Klik **op Overervingsmachtigingen stoppen**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8445c-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="8445c-160">Klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="8445c-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="8445c-161">Klik **op Gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="8445c-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="8445c-162">Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="8445c-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="8445c-163">Klik op de pagina machtigingen op \*\* \<site name> Leden in de lijst\*\*.</span><span class="sxs-lookup"><span data-stu-id="8445c-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="8445c-164">Selecteer op de pagina \*\* \<site name> Leden\*\* het vinkje naast de toegangsgroep voor siteleden, klik op **Acties,** klik op **Gebruikers uit de groep verwijderen**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="8445c-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="8445c-165">Als u specifieke leden aan deze submap wilt toevoegen, klikt u op **Nieuw > Gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8445c-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="8445c-166">Typ in het dialoogvenster **Delen** de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="8445c-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="8445c-167">Vernieuw de webpagina om de nieuwe resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8445c-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="8445c-168">Klik **onder Groepen** in de linkernavigatie op de groep \*\* \<site name> Bezoekers\*\* en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap kunnen weergeven (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="8445c-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="8445c-169">Klik onder **Groepen** in de linkernavigatie op de groep \*\* \<site name> Eigenaren\*\* en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de machtigingen in de submap kan beheren (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="8445c-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="8445c-170">Sluit het tabblad **Personen en groepen** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="8445c-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8445c-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8445c-171">See Also</span></span>

[<span data-ttu-id="8445c-172">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="8445c-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="8445c-173">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="8445c-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="8445c-174">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="8445c-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



