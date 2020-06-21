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
description: Gebruik deze stapsgewijze implementatiehandleiding om een geïsoleerde SharePoint Online-teamsite te maken en te configureren in Microsoft Office 365.
ms.openlocfilehash: 05fdbcfff792805708bfe0b8027e955d54a1ec6f
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755222"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="a964c-103">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="a964c-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="a964c-104">**Samenvatting:** Implementeer een nieuwe geïsoleerde SharePoint Online-teamsite met deze stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="a964c-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="a964c-105">Dit artikel is een stapsgewijze implementatiehandleiding voor het maken en configureren van een geïsoleerde SharePoint Online-teamsite in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="a964c-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="a964c-106">In deze stappen wordt uitgegaan van het gebruik van de drie standaardSharePoint-groepen en de bijbehorende machtigingsniveaus, met één toegangsgroep (Azure Active Directory) voor elk toegangsniveau.</span><span class="sxs-lookup"><span data-stu-id="a964c-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="a964c-107">Fase 1: de toegangsgroepen van de teamsite maken en vullen</span><span class="sxs-lookup"><span data-stu-id="a964c-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="a964c-108">In deze fase maakt u de drie Azure AD-gebaseerde toegangsgroepen voor de drie standaardSharePoint-groepen en vult u deze met de juiste gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="a964c-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a964c-109">Bij de volgende stappen wordt ervan uitgegaan dat alle benodigde gebruikersaccounts al bestaan en de juiste licenties worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a964c-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="a964c-110">Zo niet, voeg ze dan toe en wijs licenties toe voordat u doorgaat naar stap 1.</span><span class="sxs-lookup"><span data-stu-id="a964c-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="a964c-111">Stap 1: De SharePoint Online-beheerders voor de site aanbieden</span><span class="sxs-lookup"><span data-stu-id="a964c-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="a964c-112">Bepaal de set gebruikersaccounts die overeenkomen met de SharePoint Online-beheerders voor de geïsoleerde teamsite.</span><span class="sxs-lookup"><span data-stu-id="a964c-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="a964c-113">Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en Windows PowerShell wilt gebruiken, maakt u een lijst met de belangrijkste namen van de gebruiker (UPN) (voorbeeld UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a964c-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="a964c-114">Stap 2: Lijst van de leden voor de site</span><span class="sxs-lookup"><span data-stu-id="a964c-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="a964c-115">Bepaal de set gebruikersaccounts die overeenkomen met de leden voor de geïsoleerde teamsite, degenen die samenwerken aan bronnen die zijn opgeslagen op de site.</span><span class="sxs-lookup"><span data-stu-id="a964c-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="a964c-116">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPNs.</span><span class="sxs-lookup"><span data-stu-id="a964c-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="a964c-117">Als er veel siteleden zijn, u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="a964c-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="a964c-118">Stap 3: De kijkers voor de site aanbieden</span><span class="sxs-lookup"><span data-stu-id="a964c-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="a964c-119">Bepaal de set gebruikersaccounts die overeenkomen met de kijkers van de geïsoleerde teamsite, degenen die de bronnen kunnen bekijken die op de site zijn opgeslagen, maar deze niet kunnen wijzigen of rechtstreeks samenwerken aan de inhoud ervan.</span><span class="sxs-lookup"><span data-stu-id="a964c-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="a964c-120">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPNs.</span><span class="sxs-lookup"><span data-stu-id="a964c-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="a964c-121">Als er veel siteleden zijn, u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="a964c-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="a964c-122">Kijkers voor de site kunnen bestaan uit uitvoerend management, juridisch advies of interdepartementale belanghebbenden.</span><span class="sxs-lookup"><span data-stu-id="a964c-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="a964c-123">Stap 4: De drie toegangsgroepen voor de site maken in Azure AD</span><span class="sxs-lookup"><span data-stu-id="a964c-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="a964c-124">U moet de volgende toegangsgroepen maken in Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a964c-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="a964c-125">Sitebeheerders (die de lijst van stap 1 bevatten)</span><span class="sxs-lookup"><span data-stu-id="a964c-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="a964c-126">Siteleden (die de lijst van stap 2 bevatten)</span><span class="sxs-lookup"><span data-stu-id="a964c-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="a964c-127">Sitekijkers (die de lijst van stap 3 bevatten)</span><span class="sxs-lookup"><span data-stu-id="a964c-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="a964c-128">Ga in uw browser naar de Azure-portal [https://portal.azure.com](https://portal.azure.com) en meld u aan met de referenties van een account dat is toegewezen aan de rol Gebruikersbeheerbeheerder of bedrijfsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="a964c-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a964c-129">Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="a964c-130">Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="a964c-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="a964c-131">Op het **nieuwe groepsblad:**</span><span class="sxs-lookup"><span data-stu-id="a964c-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="a964c-132">Selecteer **Beveiliging** bij **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="a964c-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="a964c-133">Typ de groepsnaam in **Naam**.</span><span class="sxs-lookup"><span data-stu-id="a964c-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="a964c-134">Typ een beschrijving van de groep in **groepsbeschrijving**.</span><span class="sxs-lookup"><span data-stu-id="a964c-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="a964c-135">Selecteer **Toegewezen** bij **Lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="a964c-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="a964c-136">Klik op **Maken** en sluit vervolgens de blade**Groep**.</span><span class="sxs-lookup"><span data-stu-id="a964c-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="a964c-137">Herhaal stap 3-5 voor uw extra groepen.</span><span class="sxs-lookup"><span data-stu-id="a964c-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a964c-138">U moet de Azure-portal gebruiken om de groepen zo te maken dat Office-functies zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a964c-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="a964c-139">Als een geïsoleerde SharePoint Online-site later is geconfigureerd als een zeer vertrouwelijke site met een Azure Information Protection-label om bestanden te versleutelen en toestemming toe te wijzen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met Office-functies ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a964c-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="a964c-140">U de instelling voor Office-functies van een Azure AD-groep niet wijzigen nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a964c-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="a964c-141">Hier is uw resulterende configuratie met de drie sitetoegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="a964c-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![De drie toegangsgroepen voor uw implementatie van een geïsoleerde SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="a964c-143">Stap 5.</span><span class="sxs-lookup"><span data-stu-id="a964c-143">Step 5.</span></span> <span data-ttu-id="a964c-144">De gebruikersaccounts toevoegen aan de toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="a964c-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="a964c-145">Ga in deze stap als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="a964c-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="a964c-146">De lijst met gebruikers van stap 1 toevoegen aan de toegangsgroep voor sitebeheerders</span><span class="sxs-lookup"><span data-stu-id="a964c-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="a964c-147">De lijst met gebruikers van stap 2 toevoegen aan de toegangsgroep voor siteleden</span><span class="sxs-lookup"><span data-stu-id="a964c-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="a964c-148">De lijst met gebruikers van stap 3 toevoegen aan de toegangsgroep voor sitekijkers</span><span class="sxs-lookup"><span data-stu-id="a964c-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="a964c-149">Als u gebruikersaccounts en groepen beheert via Ad DS (Active Directory Domain Services), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="a964c-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="a964c-150">Als u gebruikersaccounts en groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a964c-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="a964c-151">Als u dubbele groepsnamen hebt voor een van de toegangsgroepen, moet u het Microsoft 365-beheercentrum gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a964c-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="a964c-152">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Gebruikersaccountbeheerder of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikersaccounts en groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="a964c-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="a964c-153">Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a964c-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="a964c-154">Gebruik vervolgens het volgende opdrachtblok om een individueel gebruikersaccount toe te voegen aan een toegangsgroep:</span><span class="sxs-lookup"><span data-stu-id="a964c-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="a964c-155">Als u de UPN's van gebruikersaccounts hebt opgeslagen voor een van de toegangsgroepen in een tekstbestand, u het volgende PowerShell-opdrachtblok gebruiken om ze allemaal tegelijk toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="a964c-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="a964c-156">Gebruik voor PowerShell het volgende opdrachtblok om een afzonderlijke groep toe te voegen aan een toegangsgroep:</span><span class="sxs-lookup"><span data-stu-id="a964c-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="a964c-157">De resultaten moeten als volgt worden vastgesteld:</span><span class="sxs-lookup"><span data-stu-id="a964c-157">The results should be the following:</span></span>
  
- <span data-ttu-id="a964c-158">De Azure AD-groep van de sitebeheerder bevat de gebruikersaccounts of groepen van de sitebeheerder</span><span class="sxs-lookup"><span data-stu-id="a964c-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="a964c-159">De Azure AD-groep van de siteleden bevat gebruikersaccounts of groepen van het sitelid</span><span class="sxs-lookup"><span data-stu-id="a964c-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="a964c-160">De Azure AD-groep van de sitekijkers bevat de gebruikersaccounts of groepen die alleen de site-inhoud kunnen bekijken</span><span class="sxs-lookup"><span data-stu-id="a964c-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="a964c-161">Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-beheercentrum of met het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="a964c-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="a964c-162">Hier is uw resulterende configuratie met de drie sitetoegangsgroepen gevuld met gebruikersaccounts of groepen.</span><span class="sxs-lookup"><span data-stu-id="a964c-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![De drie toegangsgroepen gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="a964c-164">Fase 2: De geïsoleerde teamsite maken en configureren</span><span class="sxs-lookup"><span data-stu-id="a964c-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="a964c-165">In deze fase maakt u de geïsoleerde SharePoint Online-site en configureert u de machtigingen voor de standaard machtigingsniveaus voor SharePoint Online om uw nieuwe Azure AD-gebaseerde toegangsgroepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a964c-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="a964c-166">Nieuwe teamsites bevatten standaard een Microsoft 365-groep en andere gerelateerde bronnen, maar in dit geval maken we een teamsite zonder Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="a964c-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="a964c-167">Hierdoor kunnen machtigingen volledig via SharePoint worden gehandhaafd.</span><span class="sxs-lookup"><span data-stu-id="a964c-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="a964c-168">Maak eerst de SharePoint Online-teamsite met deze stappen.</span><span class="sxs-lookup"><span data-stu-id="a964c-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="a964c-169">Meld u aan bij het Microsoft 365-beheercentrum met een account dat ook wordt gebruikt voor het beheer van de SharePoint Online-teamsite (een SharePoint Online-beheerder).</span><span class="sxs-lookup"><span data-stu-id="a964c-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="a964c-170">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="a964c-170">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="a964c-171">Klik in het Microsoft 365-beheercentrum onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a964c-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="a964c-172">Vouw **sites** uit in het SharePoint-beheercentrum en klik op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="a964c-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="a964c-173">Klik **op Maken**en kies andere **opties**.</span><span class="sxs-lookup"><span data-stu-id="a964c-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="a964c-174">Kies in de lijst **Een sjabloon** kiezen **de optie Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="a964c-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="a964c-175">Typ in **De naam van**de site een naam voor de teamsite.</span><span class="sxs-lookup"><span data-stu-id="a964c-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="a964c-176">Typ in **Primaire beheerder**het account waarmee u bent ingelogd.</span><span class="sxs-lookup"><span data-stu-id="a964c-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="a964c-177">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="a964c-177">Click **Finish**.</span></span>
    
<span data-ttu-id="a964c-178">Configureer vervolgens vanaf de nieuwe SharePoint Online-teamsite machtigingen.</span><span class="sxs-lookup"><span data-stu-id="a964c-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="a964c-179">Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="a964c-180">Klik onder **Sitedelen**op **Wijzigen hoe leden kunnen delen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="a964c-181">Kies de **enige site-eigenaren kunnen bestanden, mappen en de site delen.**</span><span class="sxs-lookup"><span data-stu-id="a964c-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="a964c-182">**Accessaanvragen toestaan** instellen op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="a964c-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="a964c-183">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a964c-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="a964c-184">Klik in het deelvenster **Machtigingen** op **Instellingen voor geavanceerde machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="a964c-185">Klik op het tabblad **Machtigingen** van uw browser op \*\* \<site name> Leden\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a964c-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="a964c-186">Klik **in Personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="a964c-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="a964c-187">Typ in het dialoogvenster **Delen** de naam van de toegangsgroep van siteleden, selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="a964c-188">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="a964c-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="a964c-189">Klik \*\* \<site name> op Eigenaren\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a964c-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="a964c-190">Klik **in Personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="a964c-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="a964c-191">Typ in het dialoogvenster **Delen** de naam van de toegangsgroep van sitebeheerders, selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="a964c-192">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="a964c-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="a964c-193">Klik \*\* \<site name> op Bezoekers\*\* in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a964c-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="a964c-194">Klik **in Personen en groepen**op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="a964c-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="a964c-195">Typ in het dialoogvenster **Delen** de naam van de toegangsgroep voor sitekijkers, selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="a964c-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="a964c-196">Sluit het tabblad **Machtigingen** van uw browser.</span><span class="sxs-lookup"><span data-stu-id="a964c-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="a964c-197">De resultaten van deze machtigingsinstellingen zijn:</span><span class="sxs-lookup"><span data-stu-id="a964c-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="a964c-198">De \*\* \<site name> SharePoint-groep Eigenaren\*\* bevat de toegangsgroep sitebeheerders, waarin alle leden het **machtigingsniveau Volledig beheer** hebben.</span><span class="sxs-lookup"><span data-stu-id="a964c-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="a964c-199">De \*\* \<site name> SharePoint-groep leden\*\* bevat de toegangsgroep voor siteleden, waarin alle leden het **machtigingsniveau Bewerken** hebben.</span><span class="sxs-lookup"><span data-stu-id="a964c-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="a964c-200">De **SharePoint-groep \<site name> Bezoekers** bevat de toegangsgroep voor sitekijkers, waarin alle leden het machtigingsniveau **Lezen** hebben.</span><span class="sxs-lookup"><span data-stu-id="a964c-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="a964c-201">De mogelijkheid voor leden om andere leden uit te nodigen of voor niet-leden om toegang aan te vragen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a964c-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="a964c-202">Hier volgt uw resulterende configuratie met de drie SharePoint-groepen voor de site die zijn geconfigureerd om de drie toegangsgroepen te gebruiken, die zijn gevuld met gebruikersaccounts of Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="a964c-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![De uiteindelijke configuratie van uw geïsoleerde SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="a964c-204">U en de leden van de site, door groepslidmaatschap in een van de toegangsgroepen, kunnen nu samenwerken met behulp van de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="a964c-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a964c-205">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a964c-205">Next step</span></span>

<span data-ttu-id="a964c-206">Zie Een [geïsoleerde SharePoint Online-teamsite](manage-an-isolated-sharepoint-online-team-site.md)beheren als u het lidmaatschap van de groep voor sitetoegang wilt wijzigen of een documentmap met aangepaste machtigingen moet maken.</span><span class="sxs-lookup"><span data-stu-id="a964c-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a964c-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a964c-207">See Also</span></span>

[<span data-ttu-id="a964c-208">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="a964c-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="a964c-209">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="a964c-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="a964c-210">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="a964c-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



