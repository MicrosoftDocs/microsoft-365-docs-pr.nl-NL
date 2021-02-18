---
title: Gescheiden dev/testomgeving van een SharePoint Online-teamsite
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Overzicht: Configureer een SharePoint Online-teamsite die geïsoleerd is van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286607"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="8892b-103">Gescheiden dev/testomgeving van een SharePoint Online-teamsite</span><span class="sxs-lookup"><span data-stu-id="8892b-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8892b-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8892b-104">**Applies to**</span></span>
- [<span data-ttu-id="8892b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8892b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8892b-106">Microsoft Defender voor Office 365-abonnement 1</span><span class="sxs-lookup"><span data-stu-id="8892b-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="8892b-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8892b-107">SharePoint Online</span></span> 


 <span data-ttu-id="8892b-108">**Overzicht:** Configureer een SharePoint Online-teamsite die geïsoleerd is van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="8892b-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="8892b-109">SharePoint Online-teamsites in Microsoft 365 zijn locaties voor samenwerking met behulp van een gemeenschappelijke documentbibliotheek, een OneNote-notitieblok en andere services.</span><span class="sxs-lookup"><span data-stu-id="8892b-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="8892b-110">In veel gevallen wilt u brede toegang en samenwerking tussen afdelingen of organisaties.</span><span class="sxs-lookup"><span data-stu-id="8892b-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="8892b-111">In sommige gevallen wilt u echter de toegang en machtigingen voor samenwerking tussen een kleine groep personen nauw bepalen.</span><span class="sxs-lookup"><span data-stu-id="8892b-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="8892b-112">Toegang tot teamsites van SharePoint Online en wat gebruikers kunnen doen, wordt bepaald door SharePoint-groepen en machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="8892b-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="8892b-113">SharePoint Online-sites hebben standaard drie toegangsniveaus:</span><span class="sxs-lookup"><span data-stu-id="8892b-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="8892b-114">**Leden** die resources op de site kunnen bekijken, maken en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8892b-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="8892b-115">**Eigenaren,** die volledige controle over de site hebben, inclusief de mogelijkheid om machtigingen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8892b-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="8892b-116">**Bezoekers,** die alleen resources op de site kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="8892b-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="8892b-117">In dit artikel wordt u stap voor stap door de configuratie van een geïsoleerd SharePoint Online-teamsite voor een geheim onderzoeksproject genaamd ProjectX beschreven.</span><span class="sxs-lookup"><span data-stu-id="8892b-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="8892b-118">De toegangsvereisten zijn:</span><span class="sxs-lookup"><span data-stu-id="8892b-118">The access requirements are:</span></span>

- <span data-ttu-id="8892b-119">Alleen leden van het project hebben toegang tot de site en de inhoud ervan (documenten, OneNote-notitieblok, pagina's), met sharePoint-machtigingsniveaus die worden beheerd via groepslidmaatschap, te bewerken en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8892b-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="8892b-120">Alleen de maker en leden van een beheerdersgroep voor de site kunnen sitebeheer uitvoeren, waaronder het wijzigen van machtigingen op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="8892b-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="8892b-121">Er zijn drie fasen voor het instellen van een afzonderlijke SharePoint Online-teamsite in uw Microsoft 365-dev/testomgeving:</span><span class="sxs-lookup"><span data-stu-id="8892b-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="8892b-122">Maak de Microsoft 365-dev/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="8892b-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="8892b-123">Maak de gebruikers en groepen voor ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8892b-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="8892b-124">Maak een nieuwe ProjectX SharePoint Online-teamsite en isoleert deze.</span><span class="sxs-lookup"><span data-stu-id="8892b-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="8892b-125">Klik [hier](https://aka.ms/catlgstack) voor een visuele plattegrond van alle artikelen in de One Microsoft Cloud Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="8892b-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="8892b-126">Fase 1: Uw lichtgewicht of gesimuleerde bedrijfsomgeving met Microsoft 365-dev/test bouwen</span><span class="sxs-lookup"><span data-stu-id="8892b-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="8892b-127">Als u alleen een afzonderlijke SharePoint Online-teamsite wilt maken met minimale vereisten, volgt u de instructies in fasen 2 en 3 van de [basisconfiguratie.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8892b-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="8892b-128">Als u een geïsoleerd SharePoint Online-teamsite wilt maken in een gesimuleerde bedrijfsconfiguratie, volgt u de instructies in Wachtwoord-hashsynchronisatie voor uw [Microsoft 365-testomgeving.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="8892b-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8892b-129">Als u een afzonderlijke SharePoint Online-site maakt, hebt u niet de gesimuleerde bedrijfsdev/testomgeving nodig, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="8892b-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8892b-130">U kunt hier een afzonderlijke SharePoint Online-site testen en daarmee experimenteren in een omgeving die een gewone organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="8892b-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="8892b-131">Fase 2: Gebruikersaccounts maken en groepen openen</span><span class="sxs-lookup"><span data-stu-id="8892b-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="8892b-132">Gebruik de instructies in [Verbinding maken met Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) om verbinding te maken met uw proefabonnement met uw globale beheerdersaccount vanuit:</span><span class="sxs-lookup"><span data-stu-id="8892b-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="8892b-133">Uw computer (voor de lichtgewicht Microsoft 365-dev/testomgeving).</span><span class="sxs-lookup"><span data-stu-id="8892b-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="8892b-134">De virtuele client1-machine (voor de gesimuleerde microsoft 365-dev/testomgeving voor enterprise Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="8892b-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="8892b-135">Als u de nieuwe toegangsgroepen wilt maken voor de teamsite van ProjectX SharePoint Online, voert u deze opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="8892b-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8892b-136">Vul de naam van uw organisatie in (bijvoorbeeld: contospartycompany), de landcode van twee tekens voor uw locatie en voer vervolgens de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8892b-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8892b-137">Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het Lead Designer-account en noteer het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="8892b-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="8892b-138">Voer de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="8892b-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8892b-139">Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het account Onderzoek voor leads en noteer het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="8892b-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="8892b-140">Voer de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="8892b-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8892b-141">Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het DEVELOPMENT VP-account en neem het op in een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="8892b-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="8892b-142">Als u vervolgens de nieuwe accounts wilt toevoegen aan de nieuwe toegangsgroepen, voert u deze PowerShell-opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="8892b-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8892b-143">Resultaten:</span><span class="sxs-lookup"><span data-stu-id="8892b-143">Results:</span></span>

- <span data-ttu-id="8892b-144">De ProjectX-Members groep Toegang bevat de gebruikersaccounts Lead Designer en Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="8892b-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="8892b-145">De ProjectX-Admins groep toegang bevat het globale beheerdersaccount voor uw proefabonnement</span><span class="sxs-lookup"><span data-stu-id="8892b-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="8892b-146">Het ProjectX-Viewers de groep Toegang bevat het gebruikersaccount Vicepresident ontwikkeling</span><span class="sxs-lookup"><span data-stu-id="8892b-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="8892b-147">Afbeelding 1 bevat de toegangsgroepen en hun lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="8892b-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="8892b-148">**Afbeelding 1:**</span><span class="sxs-lookup"><span data-stu-id="8892b-148">**Figure 1**:</span></span>

![De Microsoft 365-groepen en hun lidmaatschap voor een afzonderlijke SharePoint Online-groepssite](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="8892b-150">Fase 3: Een nieuwe ProjectX SharePoint Online-teamsite maken en isoleren</span><span class="sxs-lookup"><span data-stu-id="8892b-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="8892b-151">Ga als volgt te werk om een SharePoint Online-teamsite te maken voor ProjectX:</span><span class="sxs-lookup"><span data-stu-id="8892b-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="8892b-152">Meld u aan bij het Microsoft 365-beheercentrum met behulp van uw globale beheerdersaccount met behulp van een browser op uw lokale computer (basisconfiguratie) of client1 (gesimuleerde <https://admin.microsoft.com> bedrijfsconfiguratie).</span><span class="sxs-lookup"><span data-stu-id="8892b-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="8892b-153">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8892b-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8892b-154">Klik in het nieuwe SharePoint-tabblad in uw browser op **+ Site maken**.</span><span class="sxs-lookup"><span data-stu-id="8892b-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="8892b-155">Typ **ProjectX in de** naam van de **teamsite.**</span><span class="sxs-lookup"><span data-stu-id="8892b-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="8892b-156">Selecteer **Privé in** privacy-instellingen. Alleen leden hebben toegang tot deze **site.**</span><span class="sxs-lookup"><span data-stu-id="8892b-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="8892b-157">Typ **een** **SharePoint-site** voor ProjectX in de beschrijving van de teamsite en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8892b-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="8892b-158">Op de **wie wilt u toevoegen?** op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="8892b-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="8892b-159">Klik op het nieuwe tabblad **ProjectX-start** in uw browser op de werkbalk op het instellingenpictogram en klik vervolgens op **Sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="8892b-160">Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="8892b-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="8892b-161">Klik op het **nieuwe tabblad Machtigingen: Project X** in uw browser op Instellingen voor **toegangsaanvraag.**</span><span class="sxs-lookup"><span data-stu-id="8892b-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="8892b-162">In **het** dialoogvenster Instellingen voor toegangsaanvragen, selecteert u Leden toestaan om de site en afzonderlijke bestanden en mappen te delen en **Toegangsaanvragen** toestaan **(zodat** alle drie de selectievakjes zijn gewist) uit en klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="8892b-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="8892b-163">Klik **op ProjectX-leden** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="8892b-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="8892b-164">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="8892b-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="8892b-165">Typ  **ProjectX-leden** in het dialoogvenster Delen, selecteer het en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="8892b-166">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="8892b-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="8892b-167">Klik **in de lijst op ProjectX-eigenaren.**</span><span class="sxs-lookup"><span data-stu-id="8892b-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="8892b-168">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="8892b-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="8892b-169">Typ  **ProjectX-beheerders** in het dialoogvenster Delen, selecteer dit en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="8892b-170">Klik op de terugknop in uw browser.</span><span class="sxs-lookup"><span data-stu-id="8892b-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="8892b-171">Klik **in de lijst op ProjectX-bezoekers.**</span><span class="sxs-lookup"><span data-stu-id="8892b-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="8892b-172">Klik op de pagina **Personen en groepen** op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="8892b-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="8892b-173">Typ  **ProjectX-Viewers** in het dialoogvenster Delen, selecteer dit en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="8892b-174">Sluit het **tabblad Personen en** groepen in uw browser, klik op het tabblad **ProjectX-Start** in uw browser en sluit het deelvenster **Sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="8892b-175">Dit zijn de resultaten van het configureren van machtigingen:</span><span class="sxs-lookup"><span data-stu-id="8892b-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="8892b-176">De SharePoint-groep ProjectX-leden bevat alleen de toegangsgroep ProjectX-Members (die alleen de gebruikersaccounts Lead Designer en Lead Researcher bevat) en de ProjectX-groep (die alleen het globale beheerdersgebruikersaccount bevat).</span><span class="sxs-lookup"><span data-stu-id="8892b-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8892b-177">De SharePoint-groep ProjectX-eigenaren bevat alleen ProjectX-Admins toegangsgroep (die alleen het globale beheerdersaccount bevat).</span><span class="sxs-lookup"><span data-stu-id="8892b-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8892b-178">De SharePoint-groep ProjectX-bezoekers bevat alleen ProjectX-Viewers toegangsgroep (die alleen het gebruikersaccount van development vp bevat).</span><span class="sxs-lookup"><span data-stu-id="8892b-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="8892b-179">Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden gedaan door leden van de ProjectX-Admins groep).</span><span class="sxs-lookup"><span data-stu-id="8892b-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="8892b-180">Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="8892b-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="8892b-181">Afbeelding 2 bevat de SharePoint-groepen en hun lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="8892b-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="8892b-182">**Afbeelding 2**</span><span class="sxs-lookup"><span data-stu-id="8892b-182">**Figure 2**</span></span>

![De SharePoint Online-groepen en hun lidmaatschap voor een afzonderlijke SharePoint Online-groepssite](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="8892b-184">Laten we nu eens een demonstratie geven van de toegang met behulp van het lead designer-gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="8892b-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="8892b-185">Sluit het **tabblad ProjectX-start** in uw browser en klik in uw browser op het tabblad **Microsoft Office** Home.</span><span class="sxs-lookup"><span data-stu-id="8892b-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="8892b-186">Klik op de naam van uw globale beheerder en klik vervolgens **op Afloggen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="8892b-187">Meld u aan bij het Microsoft 365-beheercentrum () met de naam en het wachtwoord van het <https://admin.microsoft.com> Lead Designer-account.</span><span class="sxs-lookup"><span data-stu-id="8892b-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="8892b-188">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8892b-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="8892b-189">Typ op het nieuwe **SharePoint-tabblad** in uw browser **ProjectX** in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **ProjectX-teamsite.**</span><span class="sxs-lookup"><span data-stu-id="8892b-189">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8892b-190">U ziet nu een nieuw tabblad in uw browser voor de ProjectX-teamsite.</span><span class="sxs-lookup"><span data-stu-id="8892b-190">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="8892b-191">Klik op het instellingenpictogram.</span><span class="sxs-lookup"><span data-stu-id="8892b-191">Click the settings icon.</span></span> <span data-ttu-id="8892b-192">U ziet dat er geen optie is voor **Sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-192">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="8892b-193">Dit is juist omdat alleen de leden van ProjectX-Admins groep machtigingen voor de site kunnen wijzigen</span><span class="sxs-lookup"><span data-stu-id="8892b-193">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="8892b-194">Open Kladblok of een teksteditor van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="8892b-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="8892b-195">Kopieer de URL van de ProjectX-teamsite en plak deze op een nieuwe regel in Kladblok of de teksteditor.</span><span class="sxs-lookup"><span data-stu-id="8892b-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="8892b-196">Klik op het **nieuwe tabblad ProjectX-start** in uw browser op **Documenten.**</span><span class="sxs-lookup"><span data-stu-id="8892b-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="8892b-197">Kopieer de URL van de map ProjectX-documenten en plak deze op een nieuwe regel in Kladblok of de teksteditor.</span><span class="sxs-lookup"><span data-stu-id="8892b-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="8892b-198">Klik op het **nieuwe tabblad ProjectX-documenten** in uw browser op **> Word-document.**</span><span class="sxs-lookup"><span data-stu-id="8892b-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="8892b-199">Typ wat tekst op de pagina, wacht tot de status Opgeslagen wordt **weergegeven,** klik op de knop Terug in uw browser en vernieuw vervolgens de pagina.</span><span class="sxs-lookup"><span data-stu-id="8892b-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="8892b-200">U ziet nu een **nieuw** Document.docxin de **map** Documenten.</span><span class="sxs-lookup"><span data-stu-id="8892b-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="8892b-201">Klik op het beletselteken voor **Document.docx** document en klik vervolgens **op Koppeling maken.**</span><span class="sxs-lookup"><span data-stu-id="8892b-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="8892b-202">Kopieer de URL in het dialoogvenster **'Document.docx'** delen en plak deze op een nieuwe regel in Kladblok of de teksteditor. Sluit vervolgens het dialoogvenster **'Document.docx'** delen.</span><span class="sxs-lookup"><span data-stu-id="8892b-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="8892b-203">Sluit de **tabbladen ProjectX-documenten** en **SharePoint** in uw browser en klik vervolgens op het tabblad **Start van Microsoft Office.**</span><span class="sxs-lookup"><span data-stu-id="8892b-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="8892b-204">Klik op **de naam van de** leadontwerper en klik vervolgens op **Afloggen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8892b-205">Laten we nu de toegang laten zien met behulp van het gebruikersaccount Development VP:</span><span class="sxs-lookup"><span data-stu-id="8892b-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="8892b-206">Meld u aan bij het Microsoft 365-beheercentrum ( ) met de naam en het wachtwoord van de <https://admin.microsoft.com> VP-account voor ontwikkeling.</span><span class="sxs-lookup"><span data-stu-id="8892b-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="8892b-207">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8892b-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8892b-208">Typ op het nieuwe **SharePoint-tabblad** in uw browser **ProjectX** in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **ProjectX-teamsite.**</span><span class="sxs-lookup"><span data-stu-id="8892b-208">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8892b-209">U ziet nu een nieuw tabblad in uw browser voor de ProjectX-teamsite.</span><span class="sxs-lookup"><span data-stu-id="8892b-209">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="8892b-210">Klik **op Documenten** en klik vervolgens op **Document.docx** bestand.</span><span class="sxs-lookup"><span data-stu-id="8892b-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="8892b-211">Probeer de **Document.docx** te wijzigen op het tabbladDocument.docxin de browser.</span><span class="sxs-lookup"><span data-stu-id="8892b-211">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="8892b-212">Er wordt een bericht weergegeven met de mededeling **dat dit document alleen-lezen is.**</span><span class="sxs-lookup"><span data-stu-id="8892b-212">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="8892b-213">Dit is verwacht omdat het gebruikersaccount van de vicepresident van development alleen weergavemachtigingen voor de site heeft.</span><span class="sxs-lookup"><span data-stu-id="8892b-213">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="8892b-214">Sluit de **Document.docx** in uw browser, **ProjectX-documenten** en **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="8892b-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="8892b-215">Klik op het tabblad Start van **Microsoft Office,** klik op de naam van de **vicepresident** voor ontwikkelaars en klik vervolgens **op Afloggen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8892b-216">Laten we nu de toegang laten zien met een gebruikersaccount dat geen machtigingen heeft:</span><span class="sxs-lookup"><span data-stu-id="8892b-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="8892b-217">Meld u aan bij het Microsoft 365-beheercentrum () met de accountnaam en <https://admin.microsoft.com> het wachtwoord van Gebruiker 3.</span><span class="sxs-lookup"><span data-stu-id="8892b-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="8892b-218">Klik in de lijst met tegels op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8892b-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8892b-219">Typ **ProjectX** in het zoekvak op het nieuwe **tabblad SharePoint** in uw browser en activeer vervolgens de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="8892b-219">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="8892b-220">U ziet nu het bericht **Niets komt overeen met uw zoekopdracht.**</span><span class="sxs-lookup"><span data-stu-id="8892b-220">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="8892b-221">Kopieer vanuit het geopende exemplaar van Kladblok of uw teksteditor de URL voor de ProjectX-site naar de adresbalk van uw browser en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="8892b-221">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8892b-222">U ziet nu de pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="8892b-222">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="8892b-223">Kopieer in Kladblok of uw teksteditor de URL voor de map ProjectX-documenten naar de adresbalk van uw browser en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="8892b-223">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8892b-224">U ziet nu de pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="8892b-224">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="8892b-225">Kopieer vanuit Kladblok of de teksteditor de URL voor het Documents.docx-bestand naar de adresbalk van uw browser en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="8892b-225">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8892b-226">U ziet nu de pagina **Toegang geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="8892b-226">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="8892b-227">Sluit het **tabblad SharePoint** in uw browser, klik op het tabblad **Microsoft Office Voor** thuisgebruik, klik op de naam gebruiker **3** en klik vervolgens **op Afloggen.**</span><span class="sxs-lookup"><span data-stu-id="8892b-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8892b-228">Uw afzonderlijke SharePoint Online-site is nu klaar voor extra experiment.</span><span class="sxs-lookup"><span data-stu-id="8892b-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="8892b-229">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="8892b-229">Next Step</span></span>

<span data-ttu-id="8892b-230">Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="8892b-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8892b-231">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8892b-231">See Also</span></span>

[<span data-ttu-id="8892b-232">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="8892b-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="8892b-233">Cloud adoption Test Lab Guides (TLGs)</span><span class="sxs-lookup"><span data-stu-id="8892b-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="8892b-234">De basisconfiguratie voor een gesimuleerde Enterprise</span><span class="sxs-lookup"><span data-stu-id="8892b-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8892b-235">De lichtgewicht basisconfiguratie</span><span class="sxs-lookup"><span data-stu-id="8892b-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8892b-236">Microsoft 365-oplossingen- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="8892b-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)