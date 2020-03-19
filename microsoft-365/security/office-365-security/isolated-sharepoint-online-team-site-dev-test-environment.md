---
title: Dev/testomgeving van de geïsoleerde SharePoint Online-teamsite
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Samenvatting: Configureer een SharePoint Online-teamsite die is geïsoleerd van de rest van de organisatie in uw Office 365-dev/testomgeving.'
ms.openlocfilehash: fc56a151d00eba3a6c0131ae1692febe69e76122
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812773"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="68262-103">Dev/testomgeving van de geïsoleerde SharePoint Online-teamsite</span><span class="sxs-lookup"><span data-stu-id="68262-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="68262-104">**Samenvatting:** Configureer een SharePoint Online-teamsite die is geïsoleerd van de rest van de organisatie in uw Office 365-dev/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="68262-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>

<span data-ttu-id="68262-105">SharePoint Online-teamsites in Office 365 zijn locaties voor samenwerking met behulp van een algemene documentbibliotheek, een OneNote-notitieblok en andere services.</span><span class="sxs-lookup"><span data-stu-id="68262-105">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="68262-106">In veel gevallen wilt u brede toegang en samenwerking tussen afdelingen of organisaties.</span><span class="sxs-lookup"><span data-stu-id="68262-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="68262-107">In sommige gevallen wilt u echter de toegang en machtigingen voor samenwerking tussen een kleine groep mensen streng beheren.</span><span class="sxs-lookup"><span data-stu-id="68262-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="68262-108">Toegang tot SharePoint Online-teamsites en wat gebruikers kunnen doen, wordt beheerd door SharePoint-groepen en machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="68262-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="68262-109">SharePoint Online-sites hebben standaard drie toegangsniveaus:</span><span class="sxs-lookup"><span data-stu-id="68262-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="68262-110">**Leden**, die bronnen op de site kunnen bekijken, maken en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="68262-110">**Members**, who can view, create, and modify resources on the site.</span></span>

- <span data-ttu-id="68262-111">**Eigenaren**, die volledige controle over de site hebben, inclusief de mogelijkheid om machtigingen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="68262-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>

- <span data-ttu-id="68262-112">**Bezoekers**, die alleen bronnen op de site kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="68262-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="68262-113">In dit artikel wordt u door de configuratie van een geïsoleerde SharePoint Online-teamsite geplaatst voor een geheim onderzoeksproject met de naam ProjectX.</span><span class="sxs-lookup"><span data-stu-id="68262-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="68262-114">De toegangsvereisten zijn:</span><span class="sxs-lookup"><span data-stu-id="68262-114">The access requirements are:</span></span>

- <span data-ttu-id="68262-115">Alleen leden van het project hebben toegang tot de site en de inhoud ervan (documenten, OneNote-notitieblok, pagina's), met sharepoint-machtigingsniveaus bewerken en bekijken die worden beheerd via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="68262-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="68262-116">Alleen de maker van de site en leden van een groep Beheerders voor de site kunnen sitebeheer uitvoeren, waaronder het wijzigen van machtigingen op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="68262-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="68262-117">Er zijn drie fasen voor het instellen van een geïsoleerde SharePoint Online-teamsite in uw Office 365-dev/testomgeving:</span><span class="sxs-lookup"><span data-stu-id="68262-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>

1. <span data-ttu-id="68262-118">Maak de Office 365-dev/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="68262-118">Create the Office 365 dev/test environment.</span></span>

2. <span data-ttu-id="68262-119">Maak de gebruikers en groepen voor ProjectX.</span><span class="sxs-lookup"><span data-stu-id="68262-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="68262-120">Maak een nieuwe ProjectX SharePoint Online-teamsite en isoleer deze.</span><span class="sxs-lookup"><span data-stu-id="68262-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="68262-121">Klik [hier](https://aka.ms/catlgstack) voor een visuele kaart voor alle artikelen in de One Microsoft Cloud Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="68262-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="68262-122">Fase 1: Bouw uw lichtgewicht of gesimuleerde bedrijfsoffice 365-dev/testomgeving uit</span><span class="sxs-lookup"><span data-stu-id="68262-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="68262-123">Als u gewoon een geïsoleerde SharePoint Online-teamsite op een lichtgewicht manier wilt maken met de minimale vereisten, volgt u de instructies in fase 2 en 3 van [de Office 365-dev/testomgeving.](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)</span><span class="sxs-lookup"><span data-stu-id="68262-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>

<span data-ttu-id="68262-124">Als u een geïsoleerde SharePoint Online-teamsite wilt maken in een gesimuleerde bedrijfsconfiguratie, volgt u de instructies in [DirSync voor uw Office 365-dev/testomgeving.](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment)</span><span class="sxs-lookup"><span data-stu-id="68262-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="68262-125">Voor het maken van een geïsoleerde SharePoint Online-site is de gesimuleerde bedrijfsdev/testomgeving niet vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="68262-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="68262-126">Het wordt hier als optie aangeboden, zodat u een geïsoleerde SharePoint Online-site testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="68262-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="68262-127">Fase 2: Gebruikersaccounts en toegangsgroepen maken</span><span class="sxs-lookup"><span data-stu-id="68262-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="68262-128">Gebruik de instructies in [Verbinding maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) om verbinding te maken met uw Office 365-trailabonnement met uw wereldwijde beheerdersaccount vanaf:</span><span class="sxs-lookup"><span data-stu-id="68262-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>

- <span data-ttu-id="68262-129">Uw computer (voor de lichtgewicht Office 365 dev/testomgeving).</span><span class="sxs-lookup"><span data-stu-id="68262-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>

- <span data-ttu-id="68262-130">De virtuele client1-machine (voor de gesimuleerde bedrijfsoffice 365-dev/testomgeving).</span><span class="sxs-lookup"><span data-stu-id="68262-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>

<span data-ttu-id="68262-131">Als u de nieuwe toegangsgroepen voor de ProjectX SharePoint Online-teamsite wilt maken, voert u deze opdrachten uit vanuit de prompt van Windows Azure Active Directory Module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68262-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="68262-132">Vul de naam van uw organisatie in (bijvoorbeeld: contosotoycompany), de landcode met twee tekens voor uw locatie en voer vervolgens de volgende opdrachten uit vanuit de prompt van Windows Azure Active Directory Module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68262-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="68262-133">Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Lead Designer-account en neem het op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="68262-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="68262-134">Voer de volgende opdrachten uit de Windows Azure Active Directory Module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="68262-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="68262-135">Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Lead Researcher-account en noteer het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="68262-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="68262-136">Voer de volgende opdrachten uit de Windows Azure Active Directory Module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="68262-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="68262-137">Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Development VP-account en neem het op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="68262-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="68262-138">Voer vervolgens de volgende PowerShell-opdrachten uit vanuit de Prompt van Windows Azure Active Directory Module voor Windows PowerShell om de nieuwe accounts toe te voegen aan de nieuwe toegangsgroepen:</span><span class="sxs-lookup"><span data-stu-id="68262-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="68262-139">Resultaten:</span><span class="sxs-lookup"><span data-stu-id="68262-139">Results:</span></span>

- <span data-ttu-id="68262-140">De toegangsgroep ProjectX-Leden bevat de gebruikersaccounts Lead Designer en Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="68262-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="68262-141">De toegangsgroep ProjectX-Administrators bevat het globale beheerdersaccount voor uw proefabonnement</span><span class="sxs-lookup"><span data-stu-id="68262-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="68262-142">De toegangsgroep ProjectX-Kijkers bevat het Gebruikersaccount Development VP</span><span class="sxs-lookup"><span data-stu-id="68262-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="68262-143">Figuur 1 toont de toegangsgroepen en hun lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="68262-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="68262-144">**Figuur 1**</span><span class="sxs-lookup"><span data-stu-id="68262-144">**Figure 1**</span></span>

![De Office 365-groepen en hun lidmaatschap voor een geïsoleerde SharePoint Online-groepsite](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="68262-146">Fase 3: Een nieuwe ProjectX SharePoint Online-teamsite maken en deze isoleren</span><span class="sxs-lookup"><span data-stu-id="68262-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="68262-147">Ga als volgt te werk om een SharePoint Online-teamsite voor ProjectX te maken:</span><span class="sxs-lookup"><span data-stu-id="68262-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="68262-148">Meld u aan bij de Office 365-portal ()[https://admin.microsoft.com](https://admin.microsoft.com)met uw globale beheerdersaccount met een browser op uw lokale computer (lichtgewicht configuratie) of client1 (gesimuleerde bedrijfsconfiguratie).</span><span class="sxs-lookup"><span data-stu-id="68262-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>

2. <span data-ttu-id="68262-149">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="68262-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="68262-150">Klik op het nieuwe tabblad SharePoint in uw browser op **Site maken**.</span><span class="sxs-lookup"><span data-stu-id="68262-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="68262-151">Typ **ProjectX**in **teamsitenaam**.</span><span class="sxs-lookup"><span data-stu-id="68262-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="68262-152">Selecteer **privé-** in **Privacy-instellingen**en selecteer deze site .</span><span class="sxs-lookup"><span data-stu-id="68262-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="68262-153">Typ **in Teamsitebeschrijving** **SharePoint-site voor ProjectX**en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="68262-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="68262-154">Op de **Wie wil je toevoegen?** op **Voltooien**klikken.</span><span class="sxs-lookup"><span data-stu-id="68262-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="68262-155">Klik op het nieuwe tabblad **ProjectX-Start** in uw browser op de **gereedschapsbalk**op het pictogram Instellingen en klik vervolgens op Sitemachtigingen .</span><span class="sxs-lookup"><span data-stu-id="68262-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="68262-156">Klik in het deelvenster **Sitemachtigingen** op **Instellingen voor geavanceerde machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="68262-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="68262-157">Klik in het nieuwe **tabblad Machtigingen: Project X** in uw browser op Instellingen voor **toegangsaanvragen**.</span><span class="sxs-lookup"><span data-stu-id="68262-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="68262-158">Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **schakel Instellingen voor toegang uit om de site en afzonderlijke bestanden en mappen te delen** en **toegangsaanvragen toestaan** (zodat alle drie de selectievakjes zijn gewist) en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="68262-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="68262-159">Klik op **ProjectX-leden** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="68262-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="68262-160">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="68262-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="68262-161">Typ **projectx-leden**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="68262-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="68262-162">Klik op de knop Terug in uw browser.</span><span class="sxs-lookup"><span data-stu-id="68262-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="68262-163">Klik op **ProjectX-eigenaren** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="68262-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="68262-164">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="68262-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="68262-165">Typ **projectx-beheerders**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="68262-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="68262-166">Klik op de knop Terug in uw browser.</span><span class="sxs-lookup"><span data-stu-id="68262-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="68262-167">Klik op **ProjectX-bezoekers** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="68262-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="68262-168">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="68262-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="68262-169">Typ **projectx-viewers**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="68262-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="68262-170">Sluit het tabblad **Personen en groepen** in uw browser, klik op het tabblad **ProjectX-Start** in uw browser en sluit het deelvenster **Sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="68262-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="68262-171">Hier zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="68262-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="68262-172">De SharePoint-groep ProjectX-leden bevat alleen de toegangsgroep ProjectX-Leden (die alleen de gebruikersaccounts leaddesigner en leadonderzoeker bevat) en de ProjectX-groep (die alleen het algemene beheerdersgebruikersaccount bevat).</span><span class="sxs-lookup"><span data-stu-id="68262-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="68262-173">De SharePoint-groep ProjectX-eigenaren bevat alleen de toegangsgroep projectx-beheerders (die alleen het gebruikersaccount van de globale beheerder bevat).</span><span class="sxs-lookup"><span data-stu-id="68262-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="68262-174">De SharePoint-groep ProjectX-bezoekers bevat alleen de toegangsgroep ProjectX-Kijkers (die alleen het gebruikersaccount Van De VP-gebruiker van Ontwikkeling bevat).</span><span class="sxs-lookup"><span data-stu-id="68262-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="68262-175">Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden gedaan door leden van de projectx-beheerdersgroep).</span><span class="sxs-lookup"><span data-stu-id="68262-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="68262-176">Andere gebruikersaccounts hebben geen toegang tot de site of de bronnen ervan of vragen geen toegang tot de site.</span><span class="sxs-lookup"><span data-stu-id="68262-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="68262-177">Figuur 2 toont de SharePoint-groepen en hun lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="68262-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="68262-178">**Figuur 2**</span><span class="sxs-lookup"><span data-stu-id="68262-178">**Figure 2**</span></span>

![De SharePoint Online-groepen en hun lidmaatschap voor een geïsoleerde SharePoint Online-groepssite](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="68262-180">Laten we nu de toegang demonstreren met het Lead Designer-gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="68262-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="68262-181">Sluit het tabblad **ProjectX-Start** in uw browser en klik op het tabblad **Microsoft Office Start** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="68262-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="68262-182">Klik op de naam van uw globale beheerder en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="68262-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="68262-183">Meld u aan bij de[https://admin.microsoft.com](https://admin.microsoft.com)Office 365-portal ( ) met de naam van het Lead Designer-account en het wachtwoord ervan.</span><span class="sxs-lookup"><span data-stu-id="68262-183">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="68262-184">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="68262-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="68262-185">Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **projectx-teamsite.**</span><span class="sxs-lookup"><span data-stu-id="68262-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="68262-186">U ziet een nieuw tabblad in uw browser voor de ProjectX-teamsite.</span><span class="sxs-lookup"><span data-stu-id="68262-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="68262-187">Klik op het pictogram Instellingen.</span><span class="sxs-lookup"><span data-stu-id="68262-187">Click the settings icon.</span></span> <span data-ttu-id="68262-188">Merk op dat er geen optie is voor **sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="68262-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="68262-189">Dit is juist omdat alleen de leden van de groep ProjectX-Administrators machtigingen op de site kunnen wijzigen</span><span class="sxs-lookup"><span data-stu-id="68262-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="68262-190">Open Kladblok of een teksteditor naar keuze.</span><span class="sxs-lookup"><span data-stu-id="68262-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="68262-191">Kopieer de URL van de ProjectX-teamsite en plak deze op een nieuwe regel in Kladblok of uw teksteditor.</span><span class="sxs-lookup"><span data-stu-id="68262-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="68262-192">Klik op het nieuwe tabblad **ProjectX-Start** in uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="68262-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="68262-193">Kopieer de URL van de map ProjectX-documenten en plak deze op een nieuwe regel in Kladblok of uw teksteditor.</span><span class="sxs-lookup"><span data-stu-id="68262-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="68262-194">Klik op het nieuwe tabblad **ProjectX-Documenten** in uw browser op **Nieuw > Word-document**.</span><span class="sxs-lookup"><span data-stu-id="68262-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="68262-195">Typ tekst op de pagina, wacht tot de status **is opgeslagen,** klik op de knop Vorige in uw browser en vernieuw de pagina.</span><span class="sxs-lookup"><span data-stu-id="68262-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="68262-196">U ziet een nieuwe **Document.docx** in de map **Documenten.**</span><span class="sxs-lookup"><span data-stu-id="68262-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="68262-197">Klik op de ellips voor het **document Document.docx** en klik vervolgens op **Een koppeling opvragen.**</span><span class="sxs-lookup"><span data-stu-id="68262-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="68262-198">Kopieer de URL in het dialoogvenster **'Document.docx' delen** en plak deze op een nieuwe regel in Kladblok of uw teksteditor en sluit het dialoogvenster **'Document.docx' delen.**</span><span class="sxs-lookup"><span data-stu-id="68262-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="68262-199">Sluit de **Tabbladen ProjectX-Documents** en **SharePoint** in uw browser en klik op het tabblad **Microsoft Office Start.**</span><span class="sxs-lookup"><span data-stu-id="68262-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="68262-200">Klik op de naam **Van hoofdontwerper** en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="68262-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="68262-201">Laten we nu de toegang demonstreren met het Gebruikersaccount Van Ontwikkeling VP:</span><span class="sxs-lookup"><span data-stu-id="68262-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="68262-202">Meld u aan bij de[https://admin.microsoft.com](https://admin.microsoft.com)Office 365-portal ( ) met de naam van het Development VP-account en het wachtwoord ervan.</span><span class="sxs-lookup"><span data-stu-id="68262-202">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="68262-203">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="68262-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="68262-204">Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **projectx-teamsite.**</span><span class="sxs-lookup"><span data-stu-id="68262-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="68262-205">U ziet een nieuw tabblad in uw browser voor de ProjectX-teamsite.</span><span class="sxs-lookup"><span data-stu-id="68262-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="68262-206">Klik **op Documenten**en klik vervolgens op het **document.docx-bestand.**</span><span class="sxs-lookup"><span data-stu-id="68262-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="68262-207">Probeer de tekst in het tabblad **Document.docx** in uw browser te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="68262-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="68262-208">U ziet een bericht met de vermelding **Dit document is alleen-lezen.**</span><span class="sxs-lookup"><span data-stu-id="68262-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="68262-209">Dit wordt verwacht omdat het gebruikersaccount van Development VP alleen weergavemachtigingen voor de site heeft.</span><span class="sxs-lookup"><span data-stu-id="68262-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="68262-210">Sluit de tabbladen **Document.docx,** **ProjectX-Documents**en **SharePoint** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="68262-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="68262-211">Klik op het tabblad **Microsoft Office Start,** klik op de naam **Development VP** en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="68262-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="68262-212">Laten we nu de toegang demonstreren met een gebruikersaccount dat geen machtigingen heeft:</span><span class="sxs-lookup"><span data-stu-id="68262-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="68262-213">Meld u aan bij de[https://admin.microsoft.com](https://admin.microsoft.com)Office 365-portal ( ) met de naam van het account Gebruiker 3 en het wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="68262-213">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="68262-214">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="68262-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="68262-215">Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak en activeer de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="68262-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="68262-216">U ziet het bericht **Niets hier komt overeen met uw zoekopdracht.**</span><span class="sxs-lookup"><span data-stu-id="68262-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="68262-217">Kopieer vanuit het geopende exemplaar van Kladblok of uw teksteditor de URL voor de ProjectX-site naar de adresbalk van uw browser en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="68262-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="68262-218">U ziet een pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="68262-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="68262-219">Kopieer vanuit Kladblok of uw teksteditor de URL voor de map ProjectX-documenten naar de adresbalk van uw browser en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="68262-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="68262-220">U ziet een pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="68262-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="68262-221">Kopieer vanuit Kladblok of uw teksteditor de URL voor het bestand Documents.docx naar de adresbalk van uw browser en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="68262-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="68262-222">U ziet een pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="68262-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="68262-223">Sluit het tabblad **SharePoint** in uw browser, klik op het tabblad **Microsoft Office Start,** klik op de naam **Gebruiker 3** en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="68262-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="68262-224">Uw geïsoleerde SharePoint Online-site is nu klaar voor uw aanvullende experimenten.</span><span class="sxs-lookup"><span data-stu-id="68262-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="68262-225">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="68262-225">Next Step</span></span>

<span data-ttu-id="68262-226">Wanneer u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze ontwerpoverwegingen in [Het ontwerpen van een geïsoleerde SharePoint Online-teamsite.](design-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="68262-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68262-227">Zie ook</span><span class="sxs-lookup"><span data-stu-id="68262-227">See Also</span></span>

[<span data-ttu-id="68262-228">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="68262-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="68262-229">Cloud adoptie Test Lab Guides (TLD's)</span><span class="sxs-lookup"><span data-stu-id="68262-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="68262-230">Basisconfiguratiedev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="68262-230">Base Configuration dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[<span data-ttu-id="68262-231">Office 365-dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="68262-231">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[<span data-ttu-id="68262-232">Cloudadoptie en hybride oplossingen</span><span class="sxs-lookup"><span data-stu-id="68262-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




