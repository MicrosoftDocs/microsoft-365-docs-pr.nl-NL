---
title: Een team configureren met beveiligingsisolatie in een ontwikkel-/testomgeving
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Configureer de beveiliging en infrastructuur waardoor uw werknemers altijd en overal op afstand kunnen werken.
ms.openlocfilehash: 62361126ad0b843fd909b98807eeb186f13e75bb
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778335"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="661da-103">Een team configureren met beveiligingsisolatie in een ontwikkel-/testomgeving</span><span class="sxs-lookup"><span data-stu-id="661da-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="661da-104">Dit artikel bevat stapsgewijze instructies voor het maken van een [team met beveiligingsisolatie](secure-teams-security-isolation.md) in een ontwikkel-/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="661da-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![Configuratie voor het geïsoleerde bedrijfsstrategieteam.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="661da-106">Gebruik deze ontwikkel-/testomgeving om te experimenteren en instellingen af te stemmen op uw specifieke behoeften voordat u dit soort team in productie neemt.</span><span class="sxs-lookup"><span data-stu-id="661da-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="661da-107">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="661da-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="661da-108">Als u alleen gevoelige en zeer vertrouwelijke teams op een eenvoudige manier wilt testen met de minimale vereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="661da-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="661da-109">Als u gevoelige en zeer vertrouwelijke teams in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Wachtwoord-hash-synchronisatie](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="661da-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

>[!Note]
><span data-ttu-id="661da-110">Voor het testen van een team met beveiligingsisolatie is de testomgeving van een gesimuleerde onderneming niet nodig. Deze omgeving bevat een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="661da-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="661da-111">Dit wordt hier als optie gegeven, zodat u een team met beveiligingsisolatie kunt testen en ermee kunt experimenteren in een omgeving die een standaardorganisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="661da-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="661da-112">Fase 2: uw Microsoft Azure AD-groep (Active Directory) en -gebruikers maken en configureren</span><span class="sxs-lookup"><span data-stu-id="661da-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="661da-113">In deze fase maakt en configureert u de Microsoft Azure AD-groep en -gebruikers voor uw fictieve organisatie.</span><span class="sxs-lookup"><span data-stu-id="661da-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>
  
<span data-ttu-id="661da-114">Maak eerst een beveiligingsgroep met de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="661da-114">First, create a security group with the Azure portal.</span></span>
  
1. <span data-ttu-id="661da-115">Open een afzonderlijk tabblad in uw browser en ga naar de Microsoft Azure Portal op [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="661da-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="661da-116">Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement of uw betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="661da-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="661da-117">Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.</span><span class="sxs-lookup"><span data-stu-id="661da-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="661da-118">Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="661da-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="661da-119">In de blade **Groep**:</span><span class="sxs-lookup"><span data-stu-id="661da-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="661da-120">Selecteer **Beveiliging** bij **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="661da-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="661da-121">Typ **C-Suite** bij **Naam**.</span><span class="sxs-lookup"><span data-stu-id="661da-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="661da-122">Selecteer **Toegewezen** bij **Lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="661da-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="661da-123">Klik op **Maken** en sluit vervolgens de blade**Groep**.</span><span class="sxs-lookup"><span data-stu-id="661da-123">Click **Create**, and then close the **Group** blade.</span></span>
    
<span data-ttu-id="661da-124">Configureer vervolgens automatische licentieverlening, zodat leden van de nieuwe **C-Suite** automatisch een Microsoft 365 E5-licentie krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="661da-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>
  
1. <span data-ttu-id="661da-125">Klik in de Microsoft Azure-portal op **licenties voor Azure Active Directory > alle producten**.</span><span class="sxs-lookup"><span data-stu-id="661da-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="661da-126">Selecteer in de lijst **Microsoft 365 Enterprise E5** en klik vervolgens op **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="661da-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="661da-127">Klik in de blade **Licentie toewijzen** op \*\* Gebruikers en groepen\*\*.</span><span class="sxs-lookup"><span data-stu-id="661da-127">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="661da-128">Selecteer in de lijst met groepen de groep **C-Suite**.</span><span class="sxs-lookup"><span data-stu-id="661da-128">In the list of groups, select the **C-Suite** group.</span></span>
    
5. <span data-ttu-id="661da-129">Klik op **Selecteren** en klik vervolgens op **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="661da-129">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="661da-130">Sluit het tabblad Microsoft Azure-portal in uw browser.</span><span class="sxs-lookup"><span data-stu-id="661da-130">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="661da-131">Maak nu [verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="661da-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="661da-132">Vul de naam van uw organisatie, uw locatie en een gemeenschappelijk wachtwoord in en voer vervolgens deze opdrachten uit in de opdrachtprompt van Windows PowerShell of de Integrated Scripting Environment (ISE) om nieuwe gebruikersaccounts te maken en toe te voegen aan de groep C-Suite:</span><span class="sxs-lookup"><span data-stu-id="661da-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
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
```

> [!NOTE]
> <span data-ttu-id="661da-133">U gebruikt hier een gemeenschappelijk wachtwoord voor automatisering en configuratiegemak in een ontwikkel-/testomgeving.</span><span class="sxs-lookup"><span data-stu-id="661da-133">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="661da-134">Uiteraard wordt dit sterk afgeraden voor productieabonnementen.</span><span class="sxs-lookup"><span data-stu-id="661da-134">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="661da-135">Volg deze stappen om te controleren of de licentieverlening op groepsbasis correct werkt.</span><span class="sxs-lookup"><span data-stu-id="661da-135">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="661da-136">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="661da-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="661da-137">Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="661da-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="661da-138">Klik in de lijst met gebruikers op **CEO**.</span><span class="sxs-lookup"><span data-stu-id="661da-138">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="661da-139">In het deelvenster met de eigenschappen van het gebruikersaccount van de **CEO** controleert u dat dit account de licentie **Microsoft 365 Enterprise E5** heeft toegewezen gekregen bij **Productlicenties**.</span><span class="sxs-lookup"><span data-stu-id="661da-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>
    
## <a name="phase-3-create-your-team"></a><span data-ttu-id="661da-140">Fase 3: uw team maken</span><span class="sxs-lookup"><span data-stu-id="661da-140">Phase 3: Create your team</span></span>

<span data-ttu-id="661da-141">In deze fase maakt en configureert u een team met beveiligingsisolatie voor leden van het senior management voor het samenwerken aan de bedrijfsstrategie.</span><span class="sxs-lookup"><span data-stu-id="661da-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="661da-142">Schakel eerst gevoeligheidslabels in om de inhoud van Microsoft Teams, Office 365-groepen en SharePoint-sites te beveiligen voordat u verder gaat met de stappen in [dit artikel](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="661da-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="661da-143">Maak nu het team:</span><span class="sxs-lookup"><span data-stu-id="661da-143">Next, create the team:</span></span>

1. <span data-ttu-id="661da-144">Klik links in Teams op **Teams** en klik onderaan de lijst met teams op **Deelnemen aan een team of een team maken**.</span><span class="sxs-lookup"><span data-stu-id="661da-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="661da-145">Klik op **Team maken** (eerste kaart, linkerbovenhoek).</span><span class="sxs-lookup"><span data-stu-id="661da-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="661da-146">Kies **Een volledig nieuw team maken**.</span><span class="sxs-lookup"><span data-stu-id="661da-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="661da-147">Behoudt in de lijst **gevoeligheid** de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="661da-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="661da-148">Klik onder **privacy** op **persoonlijk**.</span><span class="sxs-lookup"><span data-stu-id="661da-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="661da-149">Typ **Bedrijfsstrategie** en klik op **Maken** > **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="661da-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="661da-150">Beperk vervolgens het creëren van privékanalen tot eigenaren van de Bedrijfsstrategiegroep.</span><span class="sxs-lookup"><span data-stu-id="661da-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="661da-151">In het team klikt u op **Meer opties**en klikt u vervolgens op **Team beheren**.</span><span class="sxs-lookup"><span data-stu-id="661da-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="661da-152">Vouw op het tabblad **Instellingen** de optie **Machtigingen voor leden** uit.</span><span class="sxs-lookup"><span data-stu-id="661da-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="661da-153">Schakel het selectievakje **Leden toestaan privékanalen te maken** uit.</span><span class="sxs-lookup"><span data-stu-id="661da-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="661da-154">U moet nu een gevoeligheidslabel configureren met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="661da-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="661da-155">De naam is Bedrijfsstrategie</span><span class="sxs-lookup"><span data-stu-id="661da-155">The name is Company Strategy</span></span>
- <span data-ttu-id="661da-156">Versleuteling is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="661da-156">Encryption is enabled</span></span>
- <span data-ttu-id="661da-157">De groep Bedrijfsstrategie heeft cocreatie-machtigingen</span><span class="sxs-lookup"><span data-stu-id="661da-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="661da-158">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="661da-158">Follow these steps:</span></span>

1. <span data-ttu-id="661da-159">Open het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="661da-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="661da-160">Klik onder **Oplossingen**op **Informatiebeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="661da-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="661da-161">Klik op **een label maken**.</span><span class="sxs-lookup"><span data-stu-id="661da-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="661da-162">Typ **Bedrijfsstrategie** als labelnaam.</span><span class="sxs-lookup"><span data-stu-id="661da-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="661da-163">Typ **Documenten bedrijfsstrategie voor senior management** als knopinfo en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="661da-164">Kies op de pagina **Versleuteling** in de vervolgkeuzelijst **Versleuteling** de optie **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="661da-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="661da-165">Teammachtigingen toevoegen:</span><span class="sxs-lookup"><span data-stu-id="661da-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="661da-166">a.</span><span class="sxs-lookup"><span data-stu-id="661da-166">a.</span></span> <span data-ttu-id="661da-167">Klik op **Machtigingen toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="661da-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="661da-168">b.</span><span class="sxs-lookup"><span data-stu-id="661da-168">b.</span></span> <span data-ttu-id="661da-169">Klik op **Gebruikers of groepen toevoegen**, selecteer **Bedrijfsstrategie** en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="661da-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="661da-170">c.</span><span class="sxs-lookup"><span data-stu-id="661da-170">c.</span></span> <span data-ttu-id="661da-171">Klik op **Machtigingen kiezen**.</span><span class="sxs-lookup"><span data-stu-id="661da-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="661da-172">d.</span><span class="sxs-lookup"><span data-stu-id="661da-172">d.</span></span> <span data-ttu-id="661da-173">Kies **Co-auteurs** in de vervolgkeuzelijst en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="661da-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="661da-174">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-174">Click **Next**.</span></span>
9. <span data-ttu-id="661da-175">Klik op de pagina **inhoudsmarkering** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="661da-176">Stel op de pagina **Site- en groepsinstellingen** de **Site- en groepsinstellingen** in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="661da-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="661da-177">Klik in de vervolgkeuzelijst **Privacy van Office 365 met de groep verbonden teamsites** op **Privé - alleen leden hebben toegang tot de site**.</span><span class="sxs-lookup"><span data-stu-id="661da-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="661da-178">Kies onder **Niet-beheerde apparaten** de optie **Toegang blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="661da-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="661da-179">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-179">Click **Next**.</span></span>
14. <span data-ttu-id="661da-180">Klik op de pagina **Automatische labeling voor Office-apps** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="661da-181">Klik op **Verzenden** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="661da-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="661da-182">Publiceer nu het nieuwe label aan de hand van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="661da-182">Next, publish the new label with these steps:</span></span> 

1. <span data-ttu-id="661da-183">Kies in het Microsoft 365-compliancecentrum op de pagina **Informatiebeveiliging** het tabblad **Labelbeleid**.</span><span class="sxs-lookup"><span data-stu-id="661da-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="661da-184">Klik op **Labels publiceren**.</span><span class="sxs-lookup"><span data-stu-id="661da-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="661da-185">Klik op de pagina **Kies gevoeligheidslabels om te publiceren** op **Kies gevoeligheidslabels om te publiceren**.</span><span class="sxs-lookup"><span data-stu-id="661da-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="661da-186">Typ **Bedrijfsstrategie** en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="661da-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="661da-187">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-187">Click **Next**.</span></span>
6. <span data-ttu-id="661da-188">Klik op de pagina **Publiceren voor gebruikers en groepen** op **Gebruikers en groepen kiezen**.</span><span class="sxs-lookup"><span data-stu-id="661da-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="661da-189">Klik op **Toevoegen** en selecteer **Bedrijfsstrategie**.</span><span class="sxs-lookup"><span data-stu-id="661da-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="661da-190">Klik op **Toevoegen** en klik op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="661da-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="661da-191">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-191">Click **Next**.</span></span>
10. <span data-ttu-id="661da-192">Schakel op de pagina beleidsinstellingen het selectievakje **Gebruikers moeten redenen geven om een label of lagere classificatielabel te verwijderen** in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="661da-193">Typ **Bedrijfsstrategie** als beleidsnaam en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="661da-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="661da-194">Klik op **Verzenden** en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="661da-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="661da-195">Het kan even duren voordat het label **Bedrijfsstrategie** beschikbaar is nadat het is gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="661da-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="661da-196">Pas vervolgens het nieuwe label toe op het team **Bedrijfsstrategie** en werk het standaard koppelingstype voor delen bij om het risico te verkleinen dat bestanden en mappen per ongeluk worden gedeeld met een breder publiek dan bedoeld.</span><span class="sxs-lookup"><span data-stu-id="661da-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span> 

1. <span data-ttu-id="661da-197">Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="661da-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="661da-198">Klik onder **Sites**op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="661da-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="661da-199">Klik op de site **Bedrijfsstrategie**.</span><span class="sxs-lookup"><span data-stu-id="661da-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="661da-200">Klik op het tabblad **Beleid** onder **Gevoeligheid**op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="661da-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="661da-201">Selecteer het label **Bedrijfsstrategie** en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="661da-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="661da-202">Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="661da-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="661da-203">Kies **Alleen personen binnen uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="661da-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="661da-204">Schakel onder **Standaard koppelingstype voor delen** het selectievakje **Hetzelfde als instelling op organisatieniveau** uit en selecteer **Personen met bestaande toegang**.</span><span class="sxs-lookup"><span data-stu-id="661da-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="661da-205">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="661da-205">Click **Save**.</span></span>

<span data-ttu-id="661da-206">Configureer het delen van sites voor alleen-eigenaren voor het team **Bedrijfsstrategie**.</span><span class="sxs-lookup"><span data-stu-id="661da-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="661da-207">Ga in Teams naar het tabblad **Algemeen** van het team **Bedrijfsstrategie**.</span><span class="sxs-lookup"><span data-stu-id="661da-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="661da-208">Klik op de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="661da-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="661da-209">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="661da-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="661da-210">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="661da-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="661da-211">Klik in het deelvenster Site-machtigingen onder **Delen van een site** op **Wijzigen hoe leden kunnen delen**.</span><span class="sxs-lookup"><span data-stu-id="661da-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="661da-212">Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="661da-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="661da-213">Sluit de deelvensters **Machtigingen** en **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="661da-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="661da-214">Als u zich aanmeldt als lid van de groep Bedrijfsstrategie ziet u **Bedrijfsstrategie** in de optie **Gevoeligheid** op de werkbalk Start van Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="661da-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="661da-215">Selecteer het label **Bedrijfsstrategie** bij de optie **Gevoeligheid** om het label aan een bestand toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="661da-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="661da-216">Hier is de resulterende configuratie voor het bedrijfsstrategieteam.</span><span class="sxs-lookup"><span data-stu-id="661da-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![Configuratie voor het geïsoleerde bedrijfsstrategieteam.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="661da-218">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="661da-218">Next step</span></span>

<span data-ttu-id="661da-219">Als u klaar bent voor de productie-implementatie, raadpleegt u deze [configuratie-instructies](secure-teams-security-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="661da-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
