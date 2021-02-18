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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Gebruik deze stapsgewijse implementatiehandleiding voor het maken en configureren van een geïsoleerd SharePoint Online-teamsite in Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288345"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ff613-103">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="ff613-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff613-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ff613-104">**Applies to**</span></span>
- [<span data-ttu-id="ff613-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ff613-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ff613-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff613-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="ff613-107">**Overzicht:** Implementeer een nieuwe afzonderlijke SharePoint Online-teamsite met deze stapsgewijs instructies.</span><span class="sxs-lookup"><span data-stu-id="ff613-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="ff613-108">Dit artikel is een stapsgewijse implementatiehandleiding voor het maken en configureren van een geïsoleerd SharePoint Online-teamsite in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff613-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="ff613-109">Bij deze stappen wordt ervan uitgenomen dat de drie standaardGroepen van SharePoint en de bijbehorende machtigingsniveaus worden gebruikt, met één op Azure Active Directory (AD) gebaseerde toegangsgroep voor elk toegangsniveau.</span><span class="sxs-lookup"><span data-stu-id="ff613-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="ff613-110">Fase 1: Toegangsgroepen voor de teamsite maken en in vullen</span><span class="sxs-lookup"><span data-stu-id="ff613-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="ff613-111">In deze fase maakt u de drie op Azure AD gebaseerde toegangsgroepen voor de drie standaard SharePoint-groepen en vult u deze met de juiste gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="ff613-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="ff613-112">In de volgende stappen wordt ervan uitgenomen dat alle benodigde gebruikersaccounts al bestaan en dat ze de juiste licenties toegewezen krijgen.</span><span class="sxs-lookup"><span data-stu-id="ff613-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="ff613-113">Als dat niet zo is, voegt u deze toe en wijst u licenties toe voordat u verdergaat met stap 1.</span><span class="sxs-lookup"><span data-stu-id="ff613-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="ff613-114">Stap 1: De SharePoint Online-beheerders voor de site in een lijst plaatsen</span><span class="sxs-lookup"><span data-stu-id="ff613-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="ff613-115">Bepaal welke set gebruikersaccounts overeenkomt met de SharePoint Online-beheerders voor de geïsoleerde teamsite.</span><span class="sxs-lookup"><span data-stu-id="ff613-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="ff613-116">Als u gebruikersaccounts en groepen beheert via Microsoft 365 en Windows PowerShell wilt gebruiken, maakt u een lijst met upn's (User Principal Names) (voorbeeld UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ff613-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="ff613-117">Stap 2: Een lijst maken met de leden voor de site</span><span class="sxs-lookup"><span data-stu-id="ff613-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="ff613-118">Bepaal de set gebruikersaccounts die betrekking hebben op de leden van de geïsoleerde teamsite, de gebruikers die zullen samenwerken aan resources die op de site zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="ff613-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="ff613-119">Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's.</span><span class="sxs-lookup"><span data-stu-id="ff613-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="ff613-120">Als er veel siteleden zijn, kunt u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="ff613-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="ff613-121">Stap 3: De viewers voor de site in een lijst plaatsen</span><span class="sxs-lookup"><span data-stu-id="ff613-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="ff613-122">Bepaal de set gebruikersaccounts die overeenkomen met de gebruikers van de geïsoleerde teamsite, personen die de resources kunnen bekijken die op de site zijn opgeslagen, maar niet kunnen wijzigen of rechtstreeks kunnen samenwerken aan de inhoud.</span><span class="sxs-lookup"><span data-stu-id="ff613-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="ff613-123">Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's.</span><span class="sxs-lookup"><span data-stu-id="ff613-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="ff613-124">Als er veel siteleden zijn, kunt u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="ff613-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="ff613-125">Gebruikers van de site kunnen bijvoorbeeld leidinggevenden, juridische vertegenwoordigers of belanghebbenden tussen afdelingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="ff613-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="ff613-126">Stap 4: De drie toegangsgroepen voor de site maken in Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff613-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="ff613-127">U moet de volgende toegangsgroepen maken in Azure AD:</span><span class="sxs-lookup"><span data-stu-id="ff613-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="ff613-128">Sitebeheerders (die de lijst van stap 1 bevatten)</span><span class="sxs-lookup"><span data-stu-id="ff613-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="ff613-129">Siteleden (die de lijst van stap 2 bevatten)</span><span class="sxs-lookup"><span data-stu-id="ff613-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="ff613-130">Sitekijkers (die de lijst uit stap 3 bevatten)</span><span class="sxs-lookup"><span data-stu-id="ff613-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="ff613-131">Ga in uw browser naar azure portal en meld u aan met de referenties van een account dat is toegewezen met de rol <https://portal.azure.com> User Management Admin of Company Administrator.</span><span class="sxs-lookup"><span data-stu-id="ff613-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="ff613-132">Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.</span><span class="sxs-lookup"><span data-stu-id="ff613-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="ff613-133">Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="ff613-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="ff613-134">Op de **nieuwe groeps blade:**</span><span class="sxs-lookup"><span data-stu-id="ff613-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="ff613-135">Selecteer **Beveiliging** bij **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="ff613-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="ff613-136">Typ de groepsnaam in **Naam.**</span><span class="sxs-lookup"><span data-stu-id="ff613-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="ff613-137">Typ een beschrijving van de groep in **de groepsbeschrijving.**</span><span class="sxs-lookup"><span data-stu-id="ff613-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="ff613-138">Selecteer **Toegewezen** bij **Lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="ff613-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="ff613-139">Klik op **Maken** en sluit vervolgens de blade **Groep**.</span><span class="sxs-lookup"><span data-stu-id="ff613-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="ff613-140">Herhaal stap 3 tot en met 5 voor uw extra groepen.</span><span class="sxs-lookup"><span data-stu-id="ff613-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="ff613-141">U moet de Azure Portal gebruiken om de groepen te maken, zodat ze Office-functies hebben ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff613-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="ff613-142">Als een afzonderlijke SharePoint Online-site later wordt geconfigureerd als zeer vertrouwelijke site met een Azure Information Protection-label voor het versleutelen van bestanden en het toewijzen van machtigingen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met Office-functies ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff613-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="ff613-143">U kunt de instelling voor Office-functies van een Azure AD-groep niet meer wijzigen nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ff613-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="ff613-144">Hier is uw resulterende configuratie met de drie toegangsgroepen voor de site.</span><span class="sxs-lookup"><span data-stu-id="ff613-144">Here is your resulting configuration with the three site access groups.</span></span>

![De drie toegangsgroepen voor uw implementatie van een afzonderlijke SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="ff613-146">Stap 5.</span><span class="sxs-lookup"><span data-stu-id="ff613-146">Step 5.</span></span> <span data-ttu-id="ff613-147">Gebruikersaccounts toevoegen aan de toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="ff613-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="ff613-148">Ga in deze stap als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="ff613-148">In this step, do the following:</span></span>

1. <span data-ttu-id="ff613-149">Voeg de lijst met gebruikers uit stap 1 toe aan de toegangsgroep voor sitebeheerders.</span><span class="sxs-lookup"><span data-stu-id="ff613-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="ff613-150">Voeg de lijst met gebruikers uit stap 2 toe aan de groep met siteleden.</span><span class="sxs-lookup"><span data-stu-id="ff613-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="ff613-151">Voeg de lijst met gebruikers uit stap 3 toe aan de groep voor sitegebruikers.</span><span class="sxs-lookup"><span data-stu-id="ff613-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="ff613-152">Als u gebruikersaccounts en -groepen beheert via Active Directory Domain Services (AD DS), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en -groepsbeheerprocedures en wacht u op synchronisatie met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="ff613-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="ff613-153">Als u gebruikersaccounts en -groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ff613-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="ff613-154">Als u dubbele groepsnamen hebt voor een van de toegangsgroepen, gebruikt u het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ff613-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="ff613-155">Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikersaccounts en -groepen toe te voegen aan de juiste toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="ff613-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="ff613-156">Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ff613-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="ff613-157">Gebruik vervolgens het volgende opdrachtblok om een afzonderlijk gebruikersaccount toe te voegen aan een toegangsgroep:</span><span class="sxs-lookup"><span data-stu-id="ff613-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ff613-158">Als u de UPN's van gebruikersaccounts hebt opgeslagen voor een van de toegangsgroepen in een tekstbestand, kunt u deze allemaal tegelijk toevoegen met het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="ff613-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="ff613-159">Gebruik voor PowerShell het volgende opdrachtblok om een afzonderlijke groep toe te voegen aan een toegangsgroep:</span><span class="sxs-lookup"><span data-stu-id="ff613-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ff613-160">Het resultaat moet als volgt zijn:</span><span class="sxs-lookup"><span data-stu-id="ff613-160">The results should be the following:</span></span>

- <span data-ttu-id="ff613-161">De Azure AD-groep sitebeheerders bevat de gebruikersaccounts of groepen van de sitebeheerder</span><span class="sxs-lookup"><span data-stu-id="ff613-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="ff613-162">De siteleden van de Azure AD-groep bevatten de gebruikersaccounts of groepen van de siteleden</span><span class="sxs-lookup"><span data-stu-id="ff613-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="ff613-163">De Azure AD-groep voor sitegebruikers bevat de gebruikersaccounts of groepen die alleen de inhoud van de site kunnen bekijken</span><span class="sxs-lookup"><span data-stu-id="ff613-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="ff613-164">Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-beheercentrum of met het volgende PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="ff613-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="ff613-165">Hier is uw resulterende configuratie met de drie toegangsgroepen voor de site die worden gevuld met gebruikersaccounts of -groepen.</span><span class="sxs-lookup"><span data-stu-id="ff613-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![De drie toegangsgroepen worden gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="ff613-167">Fase 2: De geïsoleerde teamsite maken en configureren</span><span class="sxs-lookup"><span data-stu-id="ff613-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="ff613-168">In deze fase maakt u de afzonderlijke SharePoint Online-site en configureert u de machtigingen voor de standaardmachtigingsniveaus van SharePoint Online voor het gebruik van uw nieuwe toegangsgroepen op basis van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff613-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="ff613-169">Nieuwe teamsites bevatten standaard een Microsoft 365-groep en andere verwante informatiebronnen, maar in dit geval maken we een teamsite zonder een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="ff613-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="ff613-170">Hierdoor kunnen machtigingen volledig via SharePoint worden onderhouden.</span><span class="sxs-lookup"><span data-stu-id="ff613-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="ff613-171">Maak eerst de SharePoint Online-teamsite met deze stappen.</span><span class="sxs-lookup"><span data-stu-id="ff613-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="ff613-172">Meld u aan bij het Microsoft 365-beheercentrum met een account dat ook wordt gebruikt voor het beheren van de SharePoint Online-teamsite (een beheerder van SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="ff613-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="ff613-173">Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="ff613-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ff613-174">Klik in het Microsoft 365-beheercentrum onder **Beheercentra** op **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="ff613-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="ff613-175">Vouw in het SharePoint-beheercentrum **Sites uit en** klik op Actieve **sites.**</span><span class="sxs-lookup"><span data-stu-id="ff613-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="ff613-176">Klik **op** Maken en kies **Andere opties.**</span><span class="sxs-lookup"><span data-stu-id="ff613-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="ff613-177">Kies **Teamsite in** de lijst Een sjabloon **kiezen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="ff613-178">Typ **in De** naam van de site een naam voor de teamsite.</span><span class="sxs-lookup"><span data-stu-id="ff613-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="ff613-179">Typ **bij Primaire** beheerder het account met wie u bent aangemeld.</span><span class="sxs-lookup"><span data-stu-id="ff613-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="ff613-180">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="ff613-180">Click **Finish**.</span></span>

<span data-ttu-id="ff613-181">Configureer vervolgens vanaf de nieuwe SharePoint Online-teamsite machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ff613-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="ff613-182">Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="ff613-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="ff613-183">Klik **onder Site delen** op Wijzigen hoe leden kunnen **delen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="ff613-184">Kies de **optie Alleen site-eigenaren kunnen bestanden, mappen en de site delen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="ff613-185">Stel **Toegangsaanvragen toestaan in** op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="ff613-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="ff613-186">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff613-186">Click **Save**.</span></span>

6. <span data-ttu-id="ff613-187">Klik in **het deelvenster Machtigingen** op **Geavanceerde machtigingsinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="ff613-188">Klik op **het tabblad** Machtigingen van uw browser op **\<site name> Leden** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ff613-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="ff613-189">Klik **in Personen en groepen** op **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="ff613-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="ff613-190">Typ in **het** dialoogvenster Delen de naam van de toegangsgroep voor siteleden, selecteer deze en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="ff613-191">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="ff613-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="ff613-192">Klik **\<site name> in de** lijst op Eigenaren.</span><span class="sxs-lookup"><span data-stu-id="ff613-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="ff613-193">Klik **in Personen en groepen** op **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="ff613-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="ff613-194">Typ in **het** dialoogvenster Delen de naam van de toegangsgroep voor sitebeheerders, selecteer deze en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="ff613-195">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="ff613-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="ff613-196">Klik **\<site name> op Bezoekers** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ff613-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="ff613-197">Klik **in Personen en groepen** op **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="ff613-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="ff613-198">Typ in **het** dialoogvenster Delen de naam van de groep voor sitekijkers, selecteer deze en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="ff613-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="ff613-199">Sluit het **tabblad Machtigingen** van uw browser.</span><span class="sxs-lookup"><span data-stu-id="ff613-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="ff613-200">De resultaten van deze machtigingsinstellingen zijn:</span><span class="sxs-lookup"><span data-stu-id="ff613-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="ff613-201">De **\<site name> SharePoint-groep** Eigenaren bevat de toegangsgroep voor sitebeheerders, waarin alle leden het machtigingsniveau Volledig **beheer** hebben.</span><span class="sxs-lookup"><span data-stu-id="ff613-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="ff613-202">De **\<site name>** SharePoint-groep Leden bevat de toegangsgroep voor siteleden, waarin alle leden het **machtigingsniveau Bewerken** hebben.</span><span class="sxs-lookup"><span data-stu-id="ff613-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="ff613-203">De **\<site name>** SharePoint-groep Bezoekers bevat de groep Bezoekers van de site, waarin alle leden het **machtigingsniveau** Lezen hebben.</span><span class="sxs-lookup"><span data-stu-id="ff613-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="ff613-204">De mogelijkheid voor leden om andere leden of niet-leden uit te nodigen om toegang aan te vragen, is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff613-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="ff613-205">Hier is uw resulterende configuratie met de drie SharePoint-groepen voor de site geconfigureerd voor het gebruik van de drie toegangsgroepen, die worden gevuld met gebruikersaccounts of Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="ff613-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![De uiteindelijke configuratie van uw afzonderlijke SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="ff613-207">U en de leden van de site kunnen nu via groepslidmaatschap in een van de toegangsgroepen samenwerken met behulp van de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="ff613-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="ff613-208">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ff613-208">Next step</span></span>

<span data-ttu-id="ff613-209">Zie Een afzonderlijke [SharePoint Online-teamsite](manage-an-isolated-sharepoint-online-team-site.md)beheren wanneer u het groepslidmaatschap van een site wilt wijzigen of een documentmap met aangepaste machtigingen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="ff613-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff613-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ff613-210">See Also</span></span>

[<span data-ttu-id="ff613-211">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="ff613-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="ff613-212">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="ff613-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ff613-213">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="ff613-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
