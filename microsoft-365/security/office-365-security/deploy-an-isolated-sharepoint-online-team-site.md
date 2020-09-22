---
title: Een geïsoleerde SharePoint Online-teamsite implementeren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Gebruik deze stapsgewijze instructies voor het maken en configureren van een geïsoleerde SharePoint Online-team site in Microsoft Office 365.
ms.openlocfilehash: f2800e74149e79e5c3f0444799f454ab8b3caf69
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203129"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="0d106-103">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="0d106-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="0d106-104">**Overzicht:** Implementeer een nieuwe, geïsoleerde SharePoint Online-team site met deze stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="0d106-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="0d106-105">Dit artikel bevat stapsgewijze instructies voor het maken en configureren van een geïsoleerde SharePoint Online-team site in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d106-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="0d106-106">Bij deze stappen wordt uitgegaan van de drie standaardgroepen met SharePoint en de bijbehorende machtigingsniveaus, met één Azure Active Directory-toepassing op basis van Azure Active Directory (AD) voor elk toegangsniveau.</span><span class="sxs-lookup"><span data-stu-id="0d106-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="0d106-107">Fase 1: de toegangsgroepen voor de team site maken en vullen</span><span class="sxs-lookup"><span data-stu-id="0d106-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="0d106-108">In deze fase maakt u de drie groepen Azure AD-based Access voor de drie standaardgroepen in SharePoint en vult u ze met de juiste gebruikersaccounts in.</span><span class="sxs-lookup"><span data-stu-id="0d106-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d106-109">Bij de volgende stappen wordt ervan uitgegaan dat alle benodigde gebruikersaccounts al bestaan en de juiste licenties zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0d106-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="0d106-110">Als dat niet zo is, kunt u ze toevoegen en licenties toewijzen voordat u verder gaat met stap 1.</span><span class="sxs-lookup"><span data-stu-id="0d106-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="0d106-111">Stap 1: de SharePoint Online-beheerders voor de site weergeven</span><span class="sxs-lookup"><span data-stu-id="0d106-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="0d106-112">De set gebruikersaccounts bepalen die overeenkomen met de SharePoint Online-beheerders voor de geïsoleerde team site.</span><span class="sxs-lookup"><span data-stu-id="0d106-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="0d106-113">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u Windows PowerShell wilt gebruiken, maakt u een lijst met de gebruikers-principal-namen (Upn's) (belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0d106-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="0d106-114">Stap 2: de leden voor de site weergeven</span><span class="sxs-lookup"><span data-stu-id="0d106-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="0d106-115">Het bepalen van de gebruikersaccounts die overeenkomen met de leden van de geïsoleerde team site, degene die samenwerken aan resources die zijn opgeslagen in de site.</span><span class="sxs-lookup"><span data-stu-id="0d106-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="0d106-116">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u PowerShell wilt gebruiken, moet u een lijst maken van de Upn's.</span><span class="sxs-lookup"><span data-stu-id="0d106-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="0d106-117">Als er veel siteleden zijn, kunt u de lijst met Upn's opslaan in een tekstbestand en ze allemaal met één PowerShell-opdracht toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0d106-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="0d106-118">Stap 3: de kijkers voor de site weergeven</span><span class="sxs-lookup"><span data-stu-id="0d106-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="0d106-119">Bepalen welke gebruikersaccounts overeenkomen met de gebruikers van de geïsoleerde team site, met welke gebruikers de bronnen die op de site zijn opgeslagen, niet kunnen wijzigen of rechtstreeks samenwerken aan hun inhoud.</span><span class="sxs-lookup"><span data-stu-id="0d106-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="0d106-120">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u PowerShell wilt gebruiken, moet u een lijst maken van de Upn's.</span><span class="sxs-lookup"><span data-stu-id="0d106-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="0d106-121">Als er veel siteleden zijn, kunt u de lijst met Upn's opslaan in een tekstbestand en ze allemaal met één PowerShell-opdracht toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0d106-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="0d106-122">Kijkers voor de site kunnen directeuren, juridische adviseur of belanghebbenden van de afdeling zijn.</span><span class="sxs-lookup"><span data-stu-id="0d106-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="0d106-123">Stap 4: de drie toegangsgroepen maken voor de site in azure AD</span><span class="sxs-lookup"><span data-stu-id="0d106-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="0d106-124">U moet de volgende toegangsgroepen maken in azure AD:</span><span class="sxs-lookup"><span data-stu-id="0d106-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="0d106-125">Site beheerders (die de lijst uit stap 1) hebben</span><span class="sxs-lookup"><span data-stu-id="0d106-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="0d106-126">Site leden (die de lijst uit stap 2 bevatten)</span><span class="sxs-lookup"><span data-stu-id="0d106-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="0d106-127">Site bezoekers (die de lijst uit stap 3 bevatten)</span><span class="sxs-lookup"><span data-stu-id="0d106-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="0d106-128">Ga in uw browser naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) en meld u aan met de referenties van een account dat is toegewezen aan de beheerder van het Gebruikersbeheer of de beheerder van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0d106-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="0d106-129">Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="0d106-130">Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="0d106-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="0d106-131">Op de **nieuwe groeps** Blade:</span><span class="sxs-lookup"><span data-stu-id="0d106-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="0d106-132">Selecteer **Beveiliging** bij **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="0d106-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="0d106-133">Typ een **naam**voor de groep.</span><span class="sxs-lookup"><span data-stu-id="0d106-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="0d106-134">Typ een beschrijving van de groep in de **groepsbeschrijving**.</span><span class="sxs-lookup"><span data-stu-id="0d106-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="0d106-135">Selecteer **Toegewezen** bij **Lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="0d106-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="0d106-136">Klik op **Maken** en sluit vervolgens de blade**Groep**.</span><span class="sxs-lookup"><span data-stu-id="0d106-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="0d106-137">Herhaal stappen 3-5 voor uw extra groepen.</span><span class="sxs-lookup"><span data-stu-id="0d106-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0d106-138">U moet de Azure-Portal gebruiken om de groepen te maken, zodat de Office-functies beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="0d106-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="0d106-139">Als een geïsoleerde SharePoint Online-site later is geconfigureerd als een zeer vertrouwelijke site met een Azure Information Protection-label om bestanden te versleutelen en machtigingen toe te wijzen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met de Office-functies ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0d106-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="0d106-140">U kunt de instelling Office-functies van een Azure AD-groep niet wijzigen nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0d106-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="0d106-141">Hier ziet u de resultaten van de configuratie met de drie groepen site toegang.</span><span class="sxs-lookup"><span data-stu-id="0d106-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![De drie toegangsgroepen voor de implementatie van een geïsoleerde SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="0d106-143">Stap 5.</span><span class="sxs-lookup"><span data-stu-id="0d106-143">Step 5.</span></span> <span data-ttu-id="0d106-144">De gebruikersaccounts toevoegen aan de Access-groepen</span><span class="sxs-lookup"><span data-stu-id="0d106-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="0d106-145">In deze stap doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="0d106-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="0d106-146">De lijst met gebruikers uit stap 1 toevoegen aan de groep sitebeheerders toegang</span><span class="sxs-lookup"><span data-stu-id="0d106-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="0d106-147">Voeg de lijst met gebruikers uit stap 2 toe aan de groep toegang tot siteleden</span><span class="sxs-lookup"><span data-stu-id="0d106-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="0d106-148">De lijst met gebruikers uit stap 3 toevoegen aan de groep toegang tot sitebezoekers</span><span class="sxs-lookup"><span data-stu-id="0d106-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="0d106-149">Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d106-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="0d106-150">Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0d106-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="0d106-151">Als u een groepsnaam hebt voor een van de toegangsgroepen, dient u het Microsoft 365-Beheercentrum te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0d106-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="0d106-152">Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste gebruikersaccounts en groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="0d106-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="0d106-153">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0d106-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="0d106-154">Gebruik vervolgens de volgende opdracht blokkering om een afzonderlijk gebruikersaccount toe te voegen aan een Access-groep:</span><span class="sxs-lookup"><span data-stu-id="0d106-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="0d106-155">Als u de Upn's van gebruikersaccounts voor een van de toegangsgroepen in een tekstbestand hebt opgeslagen, kunt u deze met het volgende PowerShell-opdracht blok allemaal tegelijk toevoegen:</span><span class="sxs-lookup"><span data-stu-id="0d106-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="0d106-156">Gebruik voor PowerShell de volgende opdracht blokkering om een groep toe te voegen aan een Access-groep:</span><span class="sxs-lookup"><span data-stu-id="0d106-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="0d106-157">U moet het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="0d106-157">The results should be the following:</span></span>
  
- <span data-ttu-id="0d106-158">De groep sitebeheerders Azure AD bevat de gebruikersaccounts of groepen van de sitebeheerder</span><span class="sxs-lookup"><span data-stu-id="0d106-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="0d106-159">De groep Siteleden Azure AD bevat de gebruikersaccounts of groepen van de siteleden</span><span class="sxs-lookup"><span data-stu-id="0d106-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="0d106-160">De groep site viewers Azure AD bevat de gebruikersaccounts of groepen waarmee de site-inhoud kan worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d106-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="0d106-161">Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-Beheercentrum of met het volgende PowerShell-opdracht blok:</span><span class="sxs-lookup"><span data-stu-id="0d106-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="0d106-162">Hier ziet u de resultaten van de drie groepen toegang krijgen tot de sitegroepen, met gebruikersaccounts of groepen.</span><span class="sxs-lookup"><span data-stu-id="0d106-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![De drie toegangsgroepen die zijn gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="0d106-164">Fase 2: de geïsoleerde team site maken en configureren</span><span class="sxs-lookup"><span data-stu-id="0d106-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="0d106-165">In deze fase maakt u de geïsoleerde SharePoint Online-site en configureert u de machtigingen voor de standaard-SharePoint Online-machtigingsniveaus voor het gebruik van uw nieuwe Azure AD-toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="0d106-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="0d106-166">Nieuwe team sites bevatten standaard een Microsoft 365-groep en andere verwante bronnen, maar in dit geval maken we een team site zonder een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="0d106-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="0d106-167">Hiermee kunt u machtigingen volledig beheren via SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d106-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="0d106-168">Maak eerst de SharePoint Online-team site met deze stappen.</span><span class="sxs-lookup"><span data-stu-id="0d106-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="0d106-169">Meld u aan bij het Microsoft 365-Beheercentrum met een account dat ook wordt gebruikt voor het beheren van de SharePoint Online-team site (een beheerder van SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="0d106-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="0d106-170">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="0d106-170">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0d106-171">Klik in het Microsoft 365-Beheercentrum onder **beheer centra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0d106-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="0d106-172">In het SharePoint-Beheercentrum, vouwt u **sites** uit en klikt u op **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="0d106-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="0d106-173">Klik op **maken**en kies **andere opties**.</span><span class="sxs-lookup"><span data-stu-id="0d106-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="0d106-174">Kies in de lijst **een sjabloon kiezen** de optie **team site**.</span><span class="sxs-lookup"><span data-stu-id="0d106-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="0d106-175">Typ in **site naam**een naam voor de team site.</span><span class="sxs-lookup"><span data-stu-id="0d106-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="0d106-176">Typ bij **primaire beheerder**het account waarmee u bent aangemeld.</span><span class="sxs-lookup"><span data-stu-id="0d106-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="0d106-177">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="0d106-177">Click **Finish**.</span></span>
    
<span data-ttu-id="0d106-178">Vervolgens configureert u op de nieuwe SharePoint Online-team site machtigingen.</span><span class="sxs-lookup"><span data-stu-id="0d106-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="0d106-179">Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="0d106-180">Klik onder **site delen**op **wijzigen hoe leden kunnen delen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="0d106-181">Kies de **enige site-eigenaren kunnen bestanden, mappen en de site delen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="0d106-182">Stel **toegangsaanvragen toestaan** in op **uit**.</span><span class="sxs-lookup"><span data-stu-id="0d106-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="0d106-183">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0d106-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="0d106-184">Klik in het deelvenster **machtigingen** op **Geavanceerde instellingen voor machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="0d106-185">Klik op het tabblad **machtigingen** van uw browser op \*\* \<site name> leden\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0d106-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="0d106-186">Klik in **personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0d106-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="0d106-187">Typ in het dialoogvenster **delen** de naam van de groep toegang tot siteleden, Selecteer deze en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="0d106-188">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0d106-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="0d106-189">Klik op \*\* \<site name> eigenaren\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0d106-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="0d106-190">Klik in **personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0d106-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="0d106-191">Typ in het dialoogvenster **delen** de naam van de groep sitebeheerders toegang, Selecteer deze en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="0d106-192">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0d106-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="0d106-193">Klik op \*\* \<site name> bezoekers\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0d106-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="0d106-194">Klik in **personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="0d106-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="0d106-195">Typ in het dialoogvenster **delen** de naam van de groep toegang tot site kijkers, Selecteer deze en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="0d106-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="0d106-196">Sluit het tabblad **machtigingen** van uw browser.</span><span class="sxs-lookup"><span data-stu-id="0d106-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="0d106-197">De resultaten van deze machtigingsinstellingen zijn:</span><span class="sxs-lookup"><span data-stu-id="0d106-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="0d106-198">De SharePoint-groep \*\* \<site name> eigenaren\*\* bevat de groep sitebeheerders toegang, waarbij alle leden het machtigingsniveau **volledig beheer** hebben.</span><span class="sxs-lookup"><span data-stu-id="0d106-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="0d106-199">De SharePoint-groep \*\* \<site name> leden\*\* bevat de groep toegang tot siteleden, waarbij alle leden het machtigingsniveau voor **bewerken** hebben.</span><span class="sxs-lookup"><span data-stu-id="0d106-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="0d106-200">De SharePoint-groep \*\* \<site name> bezoekers\*\* bevat de groep gebruikers van de site met de machtiging voor het **lezen** van de site.</span><span class="sxs-lookup"><span data-stu-id="0d106-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="0d106-201">De mogelijkheid om leden te uitnodigen andere leden uit te nodigen of voor niet-leden om toegang aan te vragen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0d106-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="0d106-202">Hier ziet u de resultaten van de SharePoint-groepen waarmee de site is geconfigureerd voor het gebruik van de drie toegangsgroepen, die zijn gevuld met gebruikersaccounts of Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="0d106-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![De laatste configuratie van de geïsoleerde SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="0d106-204">U en de leden van de site, via groepslidmaatschap in een van de toegangsgroepen, kunnen nu samenwerken via de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="0d106-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="0d106-205">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0d106-205">Next step</span></span>

<span data-ttu-id="0d106-206">Zie [een geïsoleerde SharePoint Online-team site beheren](manage-an-isolated-sharepoint-online-team-site.md)als u lidmaatschap van een site toegangsgroep wilt wijzigen of een map wilt maken met aangepaste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="0d106-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d106-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0d106-207">See Also</span></span>

[<span data-ttu-id="0d106-208">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="0d106-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="0d106-209">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="0d106-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="0d106-210">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="0d106-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



