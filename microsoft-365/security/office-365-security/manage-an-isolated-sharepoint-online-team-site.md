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
description: U kunt een geïsoleerde SharePoint Online-team site beheren, nieuwe gebruikers en groepen toevoegen, gebruikers en groepen verwijderen en de submap documenten maken met aangepaste machtigingen.
ms.openlocfilehash: e63cd6d17bf30ce6d236e38673b33cf054940eac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200617"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="58776-103">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="58776-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="58776-104">**Overzicht:** Beheer de geïsoleerde SharePoint Online-team site met deze procedures.</span><span class="sxs-lookup"><span data-stu-id="58776-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="58776-105">In dit artikel worden veelvoorkomende beheerbewerkingen beschreven voor een geïsoleerde SharePoint Online-team site.</span><span class="sxs-lookup"><span data-stu-id="58776-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="58776-106">Een nieuwe gebruiker toevoegen</span><span class="sxs-lookup"><span data-stu-id="58776-106">Add a new user</span></span>

<span data-ttu-id="58776-107">Wanneer iemand nieuwe lid is van de site, moet u het niveau van deelname aan de site bepalen:</span><span class="sxs-lookup"><span data-stu-id="58776-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="58776-108">Beheer: het nieuwe gebruikersaccount toevoegen aan de groep sitebeheerders toegang</span><span class="sxs-lookup"><span data-stu-id="58776-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="58776-109">Actieve samenwerking: het gebruikersaccount toevoegen aan de groep toegang tot siteleden</span><span class="sxs-lookup"><span data-stu-id="58776-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="58776-110">Weergeven: het gebruikersaccount toevoegen aan de groep toegang tot sitebezoekers</span><span class="sxs-lookup"><span data-stu-id="58776-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="58776-111">Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="58776-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="58776-112">Als u gebruikersaccounts en groepen beheert via Microsoft 365, kunt u het Microsoft 365-Beheercentrum of Microsoft PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="58776-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="58776-113">Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste gebruikers aan de juiste toegangsgroepen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="58776-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="58776-114">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="58776-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="58776-115">Gebruik het volgende PowerShell-opdracht blok om een gebruikersaccount toe te voegen aan een Access-groep met de UPN (User Principal Name) van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="58776-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="58776-116">Gebruik het volgende PowerShell-opdracht blok om een gebruikersaccount toe te voegen aan een Access-groep met de bijbehorende schermnaam:</span><span class="sxs-lookup"><span data-stu-id="58776-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="58776-117">Een nieuwe groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="58776-117">Add a new group</span></span>

<span data-ttu-id="58776-118">Als u toegang wilt tot een volledige groep, moet u het niveau van deelname aan de leden van de groep op de site bepalen:</span><span class="sxs-lookup"><span data-stu-id="58776-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="58776-119">Beheer: de groep toevoegen aan de groep sitebeheerders toegang</span><span class="sxs-lookup"><span data-stu-id="58776-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="58776-120">Actieve samenwerking: de groep toevoegen aan de groep toegang tot siteleden</span><span class="sxs-lookup"><span data-stu-id="58776-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="58776-121">Weergave: de groep toevoegen aan de groep toegang tot sitebezoekers</span><span class="sxs-lookup"><span data-stu-id="58776-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="58776-122">Als u gebruikersaccounts en groepen beheert via Active Directory, voegt u de juiste groepen toe aan de juiste groepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="58776-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="58776-123">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="58776-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="58776-124">Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="58776-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="58776-125">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="58776-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="58776-126">Gebruik de volgende PowerShell-opdrachten:</span><span class="sxs-lookup"><span data-stu-id="58776-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="58776-127">Een gebruiker verwijderen</span><span class="sxs-lookup"><span data-stu-id="58776-127">Remove a user</span></span>

<span data-ttu-id="58776-128">Wanneer iemands toegang moet worden verwijderd van de site, verwijdert u deze uit de Access-groep waarvan ze momenteel lid zijn op basis van hun deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="58776-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="58776-129">Beheer: Verwijder het gebruikersaccount uit de groep sitebeheerders toegang</span><span class="sxs-lookup"><span data-stu-id="58776-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="58776-130">Actieve samenwerking: Verwijder het gebruikersaccount uit de groep toegang tot siteleden.</span><span class="sxs-lookup"><span data-stu-id="58776-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="58776-131">Weergave: Verwijder het gebruikersaccount uit de groep sitebezoekers toegang</span><span class="sxs-lookup"><span data-stu-id="58776-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="58776-132">Als u gebruikersaccounts en groepen via Active Directory beheert, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="58776-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="58776-133">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="58776-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="58776-134">Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen, en groepen waarmee u de juiste gebruikers uit de juiste toegangsgroepen kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="58776-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="58776-135">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="58776-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="58776-136">Als u een gebruikersaccount wilt verwijderen uit een Access-groep met de UPN, gebruikt u het volgende PowerShell-opdracht blok:</span><span class="sxs-lookup"><span data-stu-id="58776-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="58776-137">Als u een gebruikersaccount wilt verwijderen uit een Access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdracht blok:</span><span class="sxs-lookup"><span data-stu-id="58776-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="58776-138">Een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="58776-138">Remove a group</span></span>

<span data-ttu-id="58776-139">Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep van de Access-groep waarvan ze lid zijn op basis van hun deelname aan de site:</span><span class="sxs-lookup"><span data-stu-id="58776-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="58776-140">Beheer: de groep verwijderen uit de groep sitebeheerders toegang</span><span class="sxs-lookup"><span data-stu-id="58776-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="58776-141">Actieve samenwerking: de groep verwijderen uit de groep Siteleden toegang</span><span class="sxs-lookup"><span data-stu-id="58776-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="58776-142">Weergeven: de groep verwijderen uit de groep sitebezoekers toegang</span><span class="sxs-lookup"><span data-stu-id="58776-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="58776-143">Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de betreffende groepen uit de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="58776-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="58776-144">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:</span><span class="sxs-lookup"><span data-stu-id="58776-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="58776-145">Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="58776-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="58776-146">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="58776-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="58776-147">Als u een groep wilt verwijderen uit een Access-groep met behulp van hun scherm namen, gebruikt u het volgende PowerShell-opdracht blok:</span><span class="sxs-lookup"><span data-stu-id="58776-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="58776-148">Een submap documenten maken met aangepaste machtigingen</span><span class="sxs-lookup"><span data-stu-id="58776-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="58776-149">In sommige gevallen moet een subset van de personen die werken in de geïsoleerde site een meer persoonlijke plaats hebben om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="58776-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="58776-150">Voor SharePoint Online-sites kunt u in de map documenten van de site een submap maken en aangepaste machtigingen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="58776-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="58776-151">Gebruikers zonder machtigingen krijgen de submap niet te zien.</span><span class="sxs-lookup"><span data-stu-id="58776-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="58776-152">Ga als volgt te werk om een submap van een document met aangepaste machtigingen te maken:</span><span class="sxs-lookup"><span data-stu-id="58776-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="58776-153">Meld u aan bij een account dat lid is van de groep beheerderstoegang voor de site.</span><span class="sxs-lookup"><span data-stu-id="58776-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="58776-154">Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="58776-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="58776-155">Ga naar de geïsoleerde team site en klik op **documenten**.</span><span class="sxs-lookup"><span data-stu-id="58776-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="58776-156">Blader naar de map in de map documenten die de submap met aangepaste machtigingen bevat, maak de map en open deze.</span><span class="sxs-lookup"><span data-stu-id="58776-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="58776-157">Klik op **delen**.</span><span class="sxs-lookup"><span data-stu-id="58776-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="58776-158">Klik op **gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="58776-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="58776-159">Klik op **overname van machtigingen stoppen**en vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="58776-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="58776-160">Klik op **delen**.</span><span class="sxs-lookup"><span data-stu-id="58776-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="58776-161">Klik op **gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="58776-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="58776-162">Klik op **machtigingen verlenen > gedeeld met > Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="58776-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="58776-163">Klik op de pagina Machtigingen op \*\* \<site name> leden in de lijst\*\*.</span><span class="sxs-lookup"><span data-stu-id="58776-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="58776-164">Schakel op de pagina \*\* \<site name> leden\*\* het selectievakje in naast de groep Siteleden toegang, klik op **acties**, klik op **gebruikers uit groep verwijderen**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="58776-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="58776-165">Als u specifieke leden aan deze submap wilt toevoegen, klikt u op **nieuw > gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="58776-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="58776-166">Typ in het dialoogvenster **delen** de namen van de gebruikersaccounts waarmee u kunt samenwerken aan bestanden in de submap en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="58776-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="58776-167">Vernieuw de webpagina om de nieuwe resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="58776-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="58776-168">Klik in het linkernavigatievenster onder **groepen** op de groep \*\* \<site name> bezoekers\*\* en gebruik stap 11-14 om de reeks gebruikersaccounts op te geven waarmee de bestanden in de submap kunnen worden weergegeven (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="58776-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="58776-169">Klik in het linkernavigatievenster onder **groepen** op de groep \*\* \<site name> eigenaren\*\* en gebruik stappen 11-14 om de set gebruikersaccounts op te geven waarmee de machtigingen in de submap kunnen worden beheerd (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="58776-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="58776-170">Sluit het tabblad **personen en groepen** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="58776-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="58776-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="58776-171">See Also</span></span>

[<span data-ttu-id="58776-172">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="58776-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="58776-173">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="58776-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="58776-174">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="58776-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



