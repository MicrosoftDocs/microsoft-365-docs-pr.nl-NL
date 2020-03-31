---
title: Veilige teams voor bestanden in een ontwikkel- en testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Samenvatting: maak gevoelige en zeer vertrouwelijke teams in Microsoft Teams voor bestanden in een ontwikkel-/testomgeving.'
ms.openlocfilehash: 7af36e5a3af94297124c6f03cdead514ac941e5b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811672"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a><span data-ttu-id="d3551-103">Veilige teams voor bestanden in een ontwikkel-/testomgeving</span><span class="sxs-lookup"><span data-stu-id="d3551-103">Secure Teams for files in a dev/test environment</span></span>

<span data-ttu-id="d3551-104">Dit artikel bevat stapsgewijze instructies om een ontwikkel-/testomgeving te creëren met gevoelige en zeer vertrouwelijke teams voor de [beveiligde bestanden in Microsoft Teams](secure-files-in-teams.md)-oplossing.</span><span class="sxs-lookup"><span data-stu-id="d3551-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential teams for the [Secure files in Microsoft Teams](secure-files-in-teams.md) solution.</span></span>
  
![Gevoelige en zeer vertrouwelijke teams in Microsoft Teams voor bestanden.](../../media/sensitive-highly-confidential-teams-dev-test.png)
  
<span data-ttu-id="d3551-106">Gebruik deze ontwikkel-/testomgeving om te experimenteren en instellingen af te stemmen op uw specifieke behoeften voordat u dit soort teams in productie neemt.</span><span class="sxs-lookup"><span data-stu-id="d3551-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying these types of teams in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d3551-107">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="d3551-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d3551-108">Als u alleen gevoelige en zeer vertrouwelijke teams op een eenvoudige manier wilt testen met de minimale vereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="d3551-108">If you just want to test sensitive and highly confidential teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="d3551-109">Als u gevoelige en zeer vertrouwelijke teams in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Wachtwoord-hash-synchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="d3551-109">If you want to test sensitive and highly confidential teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="d3551-110">Voor het testen van gevoelige en zeer vertrouwelijke teams is de testomgeving van een gesimuleerde onderneming niet nodig. Deze omgeving bevat een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d3551-110">Testing sensitive and highly confidential teams does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d3551-111">Dit wordt hier als optie gegeven, zodat u gevoelige en zeer vertrouwelijke teams kunt testen en er mee kunt experimenteren in een omgeving die een standaardorganisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="d3551-111">It is provided here as an option so that you can test sensitive and highly confidential teams and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="d3551-112">Fase 2: uw Azure AD-groepen (Active Directory) en -gebruikers maken en configureren</span><span class="sxs-lookup"><span data-stu-id="d3551-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="d3551-113">In deze fase maakt en configureert u de Azure AD-groepen en -gebruikers voor uw fictieve organisatie.</span><span class="sxs-lookup"><span data-stu-id="d3551-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="d3551-114">Maak eerst twee groepen voor een standaardorganisatie met de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="d3551-114">First, create two groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="d3551-115">Open een afzonderlijk tabblad in uw browser en ga naar de Azure Portal op [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d3551-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="d3551-116">Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement of uw betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d3551-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="d3551-117">Klik in de Azure-portal op **Azure Active Directory > Groepen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="d3551-118">Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="d3551-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="d3551-119">Op de blade **Groep**:</span><span class="sxs-lookup"><span data-stu-id="d3551-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="d3551-120">Selecteer **Beveiliging** bij **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="d3551-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="d3551-121">Typ **C-Suite** bij **Naam**.</span><span class="sxs-lookup"><span data-stu-id="d3551-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="d3551-122">Selecteer **Toegewezen** bij **Lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="d3551-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="d3551-123">Klik op **Maken** en sluit vervolgens de blade**Groep**.</span><span class="sxs-lookup"><span data-stu-id="d3551-123">Click **Create**, and then close the **Group** blade.</span></span>
    
6.  <span data-ttu-id="d3551-124">Herhaal stappen 3-5 voor een nieuwe groep met de naam **marketingpersoneel**.</span><span class="sxs-lookup"><span data-stu-id="d3551-124">Repeat steps 3-5 for a new group named **Marketing staff**.</span></span>
    
<span data-ttu-id="d3551-125">Vervolgens configureert u automatische licentieverlening, zodat de leden van uw groepen automatisch licenties krijgen toegewezen voor uw Office 365- en EMS-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="d3551-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="d3551-126">Klik in de Azure-portal op **Azure Active Directory > Licenties > Alle producten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="d3551-127">Selecteer in de lijst **Microsoft 365 Enterprise E5** en klik vervolgens op **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-127">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="d3551-128">Klik in de blade **Licentie toewijzen** op \*\* Gebruikers en groepen\*\*.</span><span class="sxs-lookup"><span data-stu-id="d3551-128">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="d3551-129">In de lijst met groepen selecteert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="d3551-129">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="d3551-130">C-Suite</span><span class="sxs-lookup"><span data-stu-id="d3551-130">C-Suite</span></span>
    
  - <span data-ttu-id="d3551-131">Marketingpersoneel</span><span class="sxs-lookup"><span data-stu-id="d3551-131">Marketing staff</span></span>
    
5. <span data-ttu-id="d3551-132">Klik op **Selecteren** en klik vervolgens op **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-132">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="d3551-133">Sluit het tabblad Azure Portal in uw browser.</span><span class="sxs-lookup"><span data-stu-id="d3551-133">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="d3551-134">Vervolgens maakt u [verbinding met de module Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d3551-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="d3551-135">Vul de naam van uw organisatie, uw locatie en een gemeenschappelijk wachtwoord in en voer vervolgens deze opdrachten uit in de opdrachtprompt van PowerShell of de Integrated Scripting Environment (ISE) om gebruikersaccounts te maken en toe te voegen aan hun groepen:</span><span class="sxs-lookup"><span data-stu-id="d3551-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="d3551-136">U gebruikt hier een gemeenschappelijk wachtwoord voor automatisering en configuratiegemak in een ontwikkel-/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d3551-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="d3551-137">Uiteraard wordt dit sterk afgeraden voor productieabonnementen.</span><span class="sxs-lookup"><span data-stu-id="d3551-137">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="d3551-138">Volg deze stappen om te controleren of de licentieverlening op groepsbasis correct werkt.</span><span class="sxs-lookup"><span data-stu-id="d3551-138">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="d3551-139">Klik in het tabblad **Microsoft Office voor Thuisgebruik** van uw browser op de tegel **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="d3551-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="d3551-140">Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d3551-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="d3551-141">Klik in de lijst met gebruikers op **CEO**.</span><span class="sxs-lookup"><span data-stu-id="d3551-141">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="d3551-142">In het deelvenster met de eigenschappen van het gebruikersaccount van de **CEO** controleert u dat dit account de licentie **Microsoft 365 Enterprise E5** heeft toegewezen gekregen (bij **Productlicenties**).</span><span class="sxs-lookup"><span data-stu-id="d3551-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="d3551-143">Fase 3: retentielabels voor Office 365 maken</span><span class="sxs-lookup"><span data-stu-id="d3551-143">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="d3551-144">In deze fase maakt u de retentielabels voor de verschillende beveiligingsniveaus voor onderliggende documentenmappen van de SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="d3551-144">In this phase, you create the retention labels for the different levels of security for underlying SharePoint site documents folders.</span></span>

1. <span data-ttu-id="d3551-145">Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com) met uw algemeen beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d3551-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="d3551-146">Klik op het tabblad van uw browser \*\*Start: compliance in Microsoft 365 \*\* op **Classificaties > Labels**.</span><span class="sxs-lookup"><span data-stu-id="d3551-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="d3551-147">Klik op **Retentielabels > een label maken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-147">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="d3551-148">Typ in het deelvenster **Uw label een naam geven** **Vertrouwelijk** in **Uw label een naam geven** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-148">On the **Name your label** pane, type **Sensitive** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="d3551-149">Klik in het deelvenster **Bestandsplandescriptors** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-149">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="d3551-150">Indien nodig kunt u in het deelvenster **Labelinstellingen** De **Retentie** instellen op **Aan** en vervolgens klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d3551-151">Klik in het deelvenster **Uw instellingen controleren** op **Label maken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-151">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="d3551-152">Herhaal stappen 3-7 voor een extra retentielabel met de naam **Zeer vertrouwelijk**.</span><span class="sxs-lookup"><span data-stu-id="d3551-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>
    
9. <span data-ttu-id="d3551-153">Klik in het deelvenster **Start > Labels** op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="d3551-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="d3551-154">Klik in het deelvenster **Labels kiezen om te publiceren** op **Labels kiezen om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="d3551-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="d3551-155">Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.</span><span class="sxs-lookup"><span data-stu-id="d3551-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="d3551-156">Klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="d3551-156">Click **Done**.</span></span>
    
13. <span data-ttu-id="d3551-157">Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-157">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="d3551-158">Klik in het deelvenster **Locaties kiezen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-158">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="d3551-159">Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="d3551-160">Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-teams"></a><span data-ttu-id="d3551-161">Fase 4: uw teams maken</span><span class="sxs-lookup"><span data-stu-id="d3551-161">Phase 4: Create your teams</span></span>

<span data-ttu-id="d3551-162">In deze fase maakt en configureert u gevoelige en zeer vertrouwelijke teamsites voor uw voorbeeldorganisatie.</span><span class="sxs-lookup"><span data-stu-id="d3551-162">In this phase, you create and configure sensitive and highly confidential teams for your example organization.</span></span>

### <a name="sensitive-team-for-marketing-campaigns"></a><span data-ttu-id="d3551-163">Gevoelig team voor marketingcampagnes</span><span class="sxs-lookup"><span data-stu-id="d3551-163">Sensitive team for marketing campaigns</span></span>

<span data-ttu-id="d3551-164">Ga als volgt te werk om een team te maken met een gevoeligheidsniveau voor leden van de marketinggroep waarin zij kunnen samenwerken aan lopende marketingcampagnes:</span><span class="sxs-lookup"><span data-stu-id="d3551-164">To create a sensitive-level team for members of the marketing group to collaborate on ongoing marketing campaigns:</span></span>

1. <span data-ttu-id="d3551-165">[Maak een nieuwe privéteamsite](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) met de naam **Marketingcampagnes**.</span><span class="sxs-lookup"><span data-stu-id="d3551-165">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Marketing Campaigns**.</span></span>
2. <span data-ttu-id="d3551-166">Open het team **marketingcampagnes**.</span><span class="sxs-lookup"><span data-stu-id="d3551-166">Open the **Marketing Campaigns** team.</span></span>
3.  <span data-ttu-id="d3551-167">Klik in de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="d3551-167">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="d3551-168">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d3551-168">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="d3551-169">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-169">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="d3551-170">Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-170">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="d3551-171">Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-171">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="d3551-172">Configureer vervolgens de documentenmap van de onderliggende SharePoint-site Marketingcampagnes voor het label Gevoelig.</span><span class="sxs-lookup"><span data-stu-id="d3551-172">Next, configure the documents folder of the underlying Marketing Campaigns SharePoint site for the Sensitive label.</span></span>

1.  <span data-ttu-id="d3551-173">Klik op het tabblad **Start Marketingcampagnes** van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-173">In the **Marketing Campaigns-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="d3551-174">Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-174">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="d3551-175">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-175">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="d3551-176">Selecteer in **Instellingen: Label toepassen** de optie **Gevoelig**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-176">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span> 

<span data-ttu-id="d3551-177">Configureer vervolgens een beleid voor de preventie van gegevensverlies (DLP) waardoor gebruikers worden gewaarschuwd wanneer ze een document met het label Gevoelig op de onderliggende SharePoint-site en buiten de organisatie delen, waaronder op de site Marketingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="d3551-177">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on the underlying SharePoint site with the Sensitive label, which includes the Marketing Campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="d3551-178">Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d3551-178">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="d3551-179">Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.</span><span class="sxs-lookup"><span data-stu-id="d3551-179">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="d3551-180">Klik in het deelvenster **Start > Preventie van gegevensverlies** op **Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-180">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="d3551-181">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-181">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="d3551-182">Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint-sites** in **Naam**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-182">In the **Name your policy** pane, type **Sensitive label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d3551-183">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-183">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d3551-184">Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-184">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d3551-185">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-185">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="d3551-186">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Retentielabels**.</span><span class="sxs-lookup"><span data-stu-id="d3551-186">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="d3551-187">Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen**en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="d3551-187">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="d3551-188">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-188">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="d3551-189">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-189">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="d3551-190">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-190">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="d3551-191">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-191">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="d3551-192">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="d3551-192">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="d3551-193">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="d3551-193">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="d3551-194">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="d3551-194">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="d3551-195">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="d3551-195">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="d3551-196">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3551-196">Click **OK**.</span></span>
    
17. <span data-ttu-id="d3551-197">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-197">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="d3551-198">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-198">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="d3551-199">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-199">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="d3551-200">Hier is de resulterende configuratie voor het bedrijfsstrategieteam.</span><span class="sxs-lookup"><span data-stu-id="d3551-200">Here is the resulting configuration for the Marketing Campaigns team.</span></span>

![Configuratie voor het bedrijfsstrategieteam.](../../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="d3551-202">Teamsite bedrijfsstrategie</span><span class="sxs-lookup"><span data-stu-id="d3551-202">Company strategy team site</span></span>

<span data-ttu-id="d3551-203">Zo maakt u een zeer vertrouwelijk team voor leden van het senior leiderschapsteam zodat zij kunnen samenwerken aan de bedrijfsstrategie:</span><span class="sxs-lookup"><span data-stu-id="d3551-203">To create a highly confidential-level team for members of the senior leadership team to collaborate on company strategy:</span></span>

1. <span data-ttu-id="d3551-204">[Maak een nieuw persoonlijk team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) met de naam **Bedrijfsstrategie**.</span><span class="sxs-lookup"><span data-stu-id="d3551-204">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="d3551-205">Open het **bedrijfsstrategie**-team.</span><span class="sxs-lookup"><span data-stu-id="d3551-205">Open the **Company Strategy** team.</span></span>
3.  <span data-ttu-id="d3551-206">Klik in de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="d3551-206">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="d3551-207">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d3551-207">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="d3551-208">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-208">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="d3551-209">Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-209">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="d3551-210">Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-210">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
8.  <span data-ttu-id="d3551-211">Schakel **Toegangsaanvragen toestaan** uit en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-211">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="d3551-212">Configureer vervolgens de documentenmap van de onderliggende Company Strategy SharePoint-site voor het label Gevoelig.</span><span class="sxs-lookup"><span data-stu-id="d3551-212">Next, configure the documents folder of the underlying Company Strategy SharePoint site for the Highly Confidential label.</span></span>

1.  <span data-ttu-id="d3551-213">Klik op het tabblad **Start bedrijfsstrategie** van uw browser op **Documenten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-213">In the **Company Strategy-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="d3551-214">Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-214">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="d3551-215">Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-215">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="d3551-216">Selecteer in **Instellingen: label toepassen** de optie **Gevoelig**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-216">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span> 

<span data-ttu-id="d3551-217">Configureer vervolgens een DLP-beleid dat gebruikers blokkeert wanneer ze een document op een onderliggende SharePoint-site met het label Gevoelig, waaronder de bedrijfsstrategiesite, buiten de organisatie delen.</span><span class="sxs-lookup"><span data-stu-id="d3551-217">Next, configure a DLP policy that blocks users when they share a document on an underlying SharePoint site with the Highly Confidential label, which includes the Company Strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="d3551-218">Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d3551-218">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="d3551-219">Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.</span><span class="sxs-lookup"><span data-stu-id="d3551-219">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="d3551-220">Klik in het deelvenster **Start > Preventie van gegevensverlies** op **Een beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-220">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="d3551-221">Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-221">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="d3551-222">Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint-sites** in **Naam**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-222">In the **Name your policy** pane, type **Highly Confidential label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d3551-223">Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-223">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d3551-224">Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-224">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d3551-225">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d3551-225">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="d3551-226">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Retentielabels**.</span><span class="sxs-lookup"><span data-stu-id="d3551-226">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="d3551-227">Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen**en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="d3551-227">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="d3551-228">Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3551-228">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="d3551-229">Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-229">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="d3551-230">Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-230">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="d3551-231">Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="d3551-231">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="d3551-232">Typ of plak in het tekstvak de volgende tekst:</span><span class="sxs-lookup"><span data-stu-id="d3551-232">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="d3551-233">Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand.</span><span class="sxs-lookup"><span data-stu-id="d3551-233">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="d3551-234">Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="d3551-234">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="d3551-235">Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.</span><span class="sxs-lookup"><span data-stu-id="d3551-235">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="d3551-236">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3551-236">Click **OK**.</span></span>
    
17. <span data-ttu-id="d3551-237">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-237">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="d3551-238">Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d3551-238">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="d3551-239">Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d3551-239">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="d3551-240">Gebruik [deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een gevoeligheids label met de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="d3551-240">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="d3551-241">De naam van het label is Bedrijfsstrategie</span><span class="sxs-lookup"><span data-stu-id="d3551-241">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="d3551-242">Versleuteling is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d3551-242">Encryption is enabled</span></span>
- <span data-ttu-id="d3551-243">De bedrijfsstrategiegroep heeft cocreatie-machtigingen</span><span class="sxs-lookup"><span data-stu-id="d3551-243">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="d3551-244">Publiceer na het maken het nieuwe label.</span><span class="sxs-lookup"><span data-stu-id="d3551-244">After creating, publish the new label.</span></span> <span data-ttu-id="d3551-245">Als u zich aanmeldt als lid van de bedrijfsstrategiegroep, ziet u het nieuwe label in de optie Gevoeligheid op de werkbalk Start van Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d3551-245">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="d3551-246">Selecteer het label Bedrijfsstrategie bij de optie Gevoeligheid om het label aan een bestand toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="d3551-246">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="d3551-247">Hier is de resulterende configuratie voor het bedrijfsstrategieteam.</span><span class="sxs-lookup"><span data-stu-id="d3551-247">Here is the resulting configuration for the Company Strategy team.</span></span>

![Configuratie voor het bedrijfsstrategieteam.](../../media/highlyconfidential-team-config-dev-test.png) 

<span data-ttu-id="d3551-249">Bestanden in het documentgedeelte van de onderliggende SharePoint-site voor bedrijfsstrategie krijgen het retentielabel Zeer gevoelig toegewezen en zijn onderworpen aan het geconfigureerde DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="d3551-249">Files in the documents section of the underlying Company Strategy SharePoint site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="d3551-250">Aan bestanden kan ook het gevoeligheidslabel Bedrijfsstrategie worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d3551-250">Files can also have the Company Strategy sensitivity label assigned.</span></span>    
  
## <a name="next-step"></a><span data-ttu-id="d3551-251">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d3551-251">Next step</span></span>

<span data-ttu-id="d3551-252">Wanneer u klaar bent voor productie-implementatie, raadpleegt u [beveiligde bestanden in Microsoft Teams](secure-files-in-teams.md) voor meer informatie en koppelingen naar artikelen met stapsgewijze implementatie.</span><span class="sxs-lookup"><span data-stu-id="d3551-252">When you are ready for production deployment, see [Secure files in Microsoft Teams](secure-files-in-teams.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3551-253">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d3551-253">See Also</span></span>

[<span data-ttu-id="d3551-254">Cloud acceptatie en hybride oplossingen</span><span class="sxs-lookup"><span data-stu-id="d3551-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
