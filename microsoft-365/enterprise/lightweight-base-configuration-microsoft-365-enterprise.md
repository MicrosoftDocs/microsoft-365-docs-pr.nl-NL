---
title: Lichtgewicht basisconfiguratie
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Gebruik deze test lab-gids voor het maken van een lichte test omgeving voor het testen van Microsoft 365 for Enterprise.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487386"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="9a766-103">De lichtgewicht basisconfiguratie</span><span class="sxs-lookup"><span data-stu-id="9a766-103">The lightweight base configuration</span></span>

<span data-ttu-id="9a766-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="9a766-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9a766-105">In dit artikel wordt uitgelegd hoe u een eenvoudige omgeving maakt met een Microsoft 365 E5-abonnement en een computer met Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9a766-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![De lichtgewicht Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="9a766-107">Het maken van een lichtgewicht testomgeving omvat vijf fasen:</span><span class="sxs-lookup"><span data-stu-id="9a766-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="9a766-108">Fase 1: uw abonnement op Microsoft 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="9a766-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="9a766-109">Fase 2: uw proefabonnement voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="9a766-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="9a766-110">Fase 3: een Microsoft 365 E5-proefabonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="9a766-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="9a766-111">Fase 4: een Windows 10 Enterprise-computer maken</span><span class="sxs-lookup"><span data-stu-id="9a766-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="9a766-112">Fase 5: uw Windows 10-computer verbinden met Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9a766-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="9a766-113">U kunt de functies en functionaliteit van [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)testen met behulp van de geresulteerde omgeving.</span><span class="sxs-lookup"><span data-stu-id="9a766-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="9a766-115">Zie [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)voor een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="9a766-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="9a766-116">Mogelijk wilt u dit artikel afdrukken voor het vastleggen van de specifieke informatie die u nodig hebt voor deze omgeving gedurende de 30 dagen van het proefabonnement voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a766-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="9a766-117">U kunt het proefabonnement eenvoudig verlengen met nog eens 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="9a766-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="9a766-118">Voor een permanente testomgeving kunt u een nieuw betaald abonnement maken met een afzonderlijke Azure Active Directory-tenant en een klein aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="9a766-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="9a766-119">Fase 1: uw abonnement op Microsoft 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="9a766-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="9a766-120">We beginnen met een proefabonnement voor Microsoft 365 E5 en vervolgens het Microsoft 365 E5-abonnement hieraan toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9a766-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="9a766-121">We raden u aan een proefabonnement te maken van Office 365, zodat de testomgeving een afzonderlijke Azure AD-Tenant heeft van alle betaalde abonnementen die u momenteel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9a766-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="9a766-122">Met deze scheiding kunt u gebruikers en groepen toevoegen aan of verwijderen uit de Tenant testen, zonder dat dit invloed heeft op de productie abonnementen.</span><span class="sxs-lookup"><span data-stu-id="9a766-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="9a766-123">Als u uw Microsoft 365 E5-proefabonnement wilt starten, hebt u eerst een fictieve bedrijfsnaam en een nieuw Microsoft-account nodig.</span><span class="sxs-lookup"><span data-stu-id="9a766-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="9a766-124">Het is raadzaam dat u een variant op de bedrijfsnaam Contoso gebruikt voor uw bedrijfsnaam. Dit is een fictief bedrijf dat wordt gebruikt in de voorbeeldinhoud van Microsoft, maar dit is niet vereist.</span><span class="sxs-lookup"><span data-stu-id="9a766-124">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span></span> <span data-ttu-id="9a766-125">Noteer hier uw fictieve bedrijfsnaam:</span><span class="sxs-lookup"><span data-stu-id="9a766-125">Record your fictitious company name here:</span></span> ![Lijn](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="9a766-127">Als u zich wilt registreren voor een nieuw Microsoft-account, gaat u naar [https://outlook.com](https://outlook.com) en maakt u een account aan met een nieuw e-mailaccount en adres.</span><span class="sxs-lookup"><span data-stu-id="9a766-127">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span></span> <span data-ttu-id="9a766-128">U gebruikt dit account om u aan te melden bij Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a766-128">You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="9a766-129">Noteer hier de voor- en achternaam van uw nieuwe account:</span><span class="sxs-lookup"><span data-stu-id="9a766-129">Record the first and last name of your new account here:</span></span> ![Lijn](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="9a766-131">Noteer hier het adres van het nieuwe e-mailaccount:</span><span class="sxs-lookup"><span data-stu-id="9a766-131">Record the new email account address here:</span></span> ![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="9a766-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="9a766-134">Registreer u voor een proefabonnement op Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="9a766-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="9a766-135">Ga in uw browser naar [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="9a766-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="9a766-136">Voer in stap 1 van de pagina **Bedankt voor het kiezen van Office 365 E5** uw nieuwe e-mailaccount adres in.</span><span class="sxs-lookup"><span data-stu-id="9a766-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="9a766-137">Voer in stap 2 van het proces voor het volgen van de volgen de gevraagde gegevens in en voer de verificatie uit.</span><span class="sxs-lookup"><span data-stu-id="9a766-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="9a766-138">Voer in stap 3 de naam van een organisatie in en klik vervolgens op de naam van een account die de globale beheerder voor het abonnement wordt.</span><span class="sxs-lookup"><span data-stu-id="9a766-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="9a766-139">In stap 4, leg hier de aanmeldingspagina vast (selecteren en kopiëren):</span><span class="sxs-lookup"><span data-stu-id="9a766-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Lijn](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="9a766-141">Noteer hier de gebruikers-ID: ![Lijn](../media/Common-Images/TableLine.png). onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a766-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="9a766-142">Noteer het wachtwoord dat u hebt ingevoerd op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="9a766-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="9a766-143">Deze waarde wordt beschouwd als de **naam van de globale beheerder**.</span><span class="sxs-lookup"><span data-stu-id="9a766-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="9a766-144">Selecteer **Ga naar Setup**.</span><span class="sxs-lookup"><span data-stu-id="9a766-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="9a766-145">Selecteer in Office 365 E5 instellen **de optie doorgaan met *uw organisatie*. onmicrosoft.com voor e-mail en aanmelden**, en selecteer vervolgens **afsluiten en later doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9a766-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="9a766-146">Nu ziet u het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9a766-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="9a766-147">Fase 2: uw proefabonnement voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="9a766-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="9a766-148">In deze fase configureert u uw abonnement met aanvullende gebruikers en wijst u Office 365 E5-licenties aan ze toe.</span><span class="sxs-lookup"><span data-stu-id="9a766-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="9a766-149">Als u vanuit uw computer verbinding wilt maken met uw abonnement met de Azure Active Directory PowerShell voor Graph module, volgt u de instructies in [verbinding maken met Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="9a766-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="9a766-150">Voer in het dialoogvenster **referentie aanvraag voor Windows PowerShell** de naam van de globale beheerder in (bijvoorbeeld *jdoe@contosotoycompany.onmicrosoft.com*) en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="9a766-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="9a766-151">Vul de naam van uw organisatie in (bijvoorbeeld *contosotoycompany*), het landnummer van twee tekens voor uw locatie, een veelvoorkomend accountwachtwoord en voer de volgende opdrachten uit op de PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="9a766-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="9a766-152">U gebruikt hier een algemeen wachtwoord voor automatisering en configuratiegemak in een testomgeving.</span><span class="sxs-lookup"><span data-stu-id="9a766-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="9a766-153">Uiteraard wordt dit sterk afgeraden voor productieabonnementen.</span><span class="sxs-lookup"><span data-stu-id="9a766-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="9a766-154">Noteer belangrijke informatie voor toekomstig gebruik</span><span class="sxs-lookup"><span data-stu-id="9a766-154">Record key information for future reference</span></span>

<span data-ttu-id="9a766-155">Als u deze waarden nog niet hebt opgenomen, kunt u deze nu opnemen:</span><span class="sxs-lookup"><span data-stu-id="9a766-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="9a766-156">Naam van globale beheerder:</span><span class="sxs-lookup"><span data-stu-id="9a766-156">Global administrator name:</span></span> ![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-158">.onmicrosoft.com (uit stap 6 van fase 1)</span><span class="sxs-lookup"><span data-stu-id="9a766-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="9a766-159">Noteer ook het wachtwoord voor dit account op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="9a766-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="9a766-160">De naam van de organisatie voor uw proefabonnement:</span><span class="sxs-lookup"><span data-stu-id="9a766-160">Your trial subscription organization name:</span></span> ![Lijn](../media/Common-Images/TableLine.png) <span data-ttu-id="9a766-162">(uit stap 4 van fase 1)</span><span class="sxs-lookup"><span data-stu-id="9a766-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="9a766-163">Voer de volgende opdracht uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt om de accounts weer te geven voor gebruiker 2, gebruiker 3, gebruiker 4 en gebruiker 5:</span><span class="sxs-lookup"><span data-stu-id="9a766-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="9a766-164">Noteer hier de accountnamen:</span><span class="sxs-lookup"><span data-stu-id="9a766-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="9a766-165">Naam van gebruiker 2-account: gebruiker2@</span><span class="sxs-lookup"><span data-stu-id="9a766-165">User 2 account name: user2@</span></span>![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a766-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="9a766-168">Naam van gebruiker 3-account: gebruiker3@</span><span class="sxs-lookup"><span data-stu-id="9a766-168">User 3 account name: user3@</span></span>![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a766-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="9a766-171">Naam van gebruiker 4-account: gebruiker4@</span><span class="sxs-lookup"><span data-stu-id="9a766-171">User 4 account name: user4@</span></span>![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a766-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="9a766-174">Naam van gebruiker 5-account: gebruiker5@</span><span class="sxs-lookup"><span data-stu-id="9a766-174">User 5 account name: user5@</span></span>![Lijn](../media/Common-Images/TableLine.png)<span data-ttu-id="9a766-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a766-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="9a766-177">Noteer ook het algemene wachtwoord voor dit account op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="9a766-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="9a766-178">Een Office 365 E5-testomgeving gebruiken</span><span class="sxs-lookup"><span data-stu-id="9a766-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="9a766-179">Als u alleen een Office 365-testomgeving nodig hebt, hoeft u de rest van dit artikel niet te lezen.</span><span class="sxs-lookup"><span data-stu-id="9a766-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="9a766-180">Zie [Microsoft 365 voor Enterprise test lab-handleidingen](m365-enterprise-test-lab-guides.md)voor extra test lab-gidsen die van toepassing zijn op zowel Office 365 als microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a766-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="9a766-181">Fase 3: een Microsoft 365 E5-proefabonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="9a766-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="9a766-182">In deze fase meld u zich aan voor het Microsoft 365 E5-proefabonnement en voegt het toe aan dezelfde organisatie als uw Office 365 E5-proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9a766-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="9a766-183">Voeg eerst het Microsoft 365 E5-proefabonnement toe en wijs de nieuwe Microsoft 365-licentie toe aan uw globale-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a766-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="9a766-184">Gebruik in een privé venster van internetbrowser uw globale beheerdersaccount referenties om u aan te melden bij het Microsoft 365-Beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="9a766-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="9a766-185">Selecteer op de pagina **Microsoft 365-Beheercentrum** in het linker navigatievenster **facturering > Services aanschaffen**.</span><span class="sxs-lookup"><span data-stu-id="9a766-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="9a766-186">Selecteer op de pagina **Services aanschaffen** de optie **Microsoft 365 E5**en selecteer vervolgens **gratis proefversie downloaden**.</span><span class="sxs-lookup"><span data-stu-id="9a766-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="9a766-187">Selecteer op de pagina **Microsoft 365 E5-proefversie** voor het ontvangen van een SMS-bericht of een telefoongesprek, voer uw telefoonnummer in en selecteer vervolgens **SMS** **bellen of mij bellen**.</span><span class="sxs-lookup"><span data-stu-id="9a766-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="9a766-188">Voer de verificatie uit.</span><span class="sxs-lookup"><span data-stu-id="9a766-188">Perform the verification.</span></span>

5. <span data-ttu-id="9a766-189">Selecteer op de pagina **uw bestelling bevestigen** de optie **nu proberen**.</span><span class="sxs-lookup"><span data-stu-id="9a766-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="9a766-190">Selecteer op de pagina **ontvangst van bestelling** de optie **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9a766-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="9a766-191">Selecteer **gebruikers > actieve gebruikers**in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9a766-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="9a766-192">Selecteer in **actieve gebruikers**uw beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a766-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="9a766-193">Selecteer **licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="9a766-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="9a766-194">Schakel de licentie voor Office 365 Enterprise E5 uit en activeer de licentie voor Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9a766-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="9a766-195">Selecteer **Save Changes**en sluit vervolgens het deelvenster met de gegevens van het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a766-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="9a766-196">Herhaal vervolgens stap 8 tot en met 11 van de vorige procedure voor al uw andere accounts (gebruiker 2, gebruiker 3, gebruiker 4 en gebruiker 5).</span><span class="sxs-lookup"><span data-stu-id="9a766-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a766-197">De lengte van het proefabonnement van Microsoft 365 E5 is 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="9a766-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="9a766-198">Voor een permanente testomgeving kunt u het omzetten naar een betaald abonnement met een klein aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="9a766-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="9a766-199">Uw testomgeving heeft nu:</span><span class="sxs-lookup"><span data-stu-id="9a766-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="9a766-200">Een Microsoft 365 E5-proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9a766-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="9a766-201">Al uw toepasselijke gebruikersaccounts (alleen de globale beheerder of alle vijf gebruikersaccounts) zijn geschikt voor het gebruik van Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9a766-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="9a766-202">De nieuwe configuratie, waarmee Microsoft 365 E5 wordt toegevoegd, ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9a766-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Fase 3 van de Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="9a766-204">Fase 4: een Windows 10 Enterprise-computer maken</span><span class="sxs-lookup"><span data-stu-id="9a766-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="9a766-205">In deze fase maakt u een zelfstandige computer met Windows 10 Enterprise als een fysieke computer, een virtuele machine of een virtuele machine van Azure.</span><span class="sxs-lookup"><span data-stu-id="9a766-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="9a766-206">Fysieke computer</span><span class="sxs-lookup"><span data-stu-id="9a766-206">Physical computer</span></span>

<span data-ttu-id="9a766-207">Installeer Windows 10 Enterprise op een personal computer.</span><span class="sxs-lookup"><span data-stu-id="9a766-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="9a766-208">U kunt de proefversie voor Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)downloaden.</span><span class="sxs-lookup"><span data-stu-id="9a766-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="9a766-209">Virtuele machine</span><span class="sxs-lookup"><span data-stu-id="9a766-209">Virtual machine</span></span>

<span data-ttu-id="9a766-210">Gebruik de hypervisor van uw keuze om een virtuele machine te maken en vervolgens Windows 10 Enterprise te installeren.</span><span class="sxs-lookup"><span data-stu-id="9a766-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="9a766-211">U kunt de proefversie voor Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)downloaden.</span><span class="sxs-lookup"><span data-stu-id="9a766-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="9a766-212">Virtuele machine in Azure</span><span class="sxs-lookup"><span data-stu-id="9a766-212">Virtual machine in Azure</span></span>

<span data-ttu-id="9a766-213">Als u een virtuele Windows 10-machine in Microsoft Azure wilt maken, ***heeft u een abonnement nodig dat is gebaseerd op Visual Studio***, dat toegang biedt tot de afbeelding voor Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9a766-213">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span></span> <span data-ttu-id="9a766-214">Andere typen Azure-abonnementen, zoals proefabonnementen en betaalde abonnementen, hebben geen toegang tot deze afbeelding.</span><span class="sxs-lookup"><span data-stu-id="9a766-214">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span></span> <span data-ttu-id="9a766-215">Zie [Windows-client in Azure gebruiken voor dev/test-scenario's](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)voor de meest recente informatie.</span><span class="sxs-lookup"><span data-stu-id="9a766-215">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a766-216">De volgende opdrachtsets gebruiken de nieuwste versie van Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a766-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="9a766-217">Zie [Aan de slag met Azure PowerShell-cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="9a766-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="9a766-218">Met deze opdracht bouwt u een virtuele machine voor Windows 10 Enterprise genaamd WIN10 en alle benodigde infrastructuur, inclusief een resourcegroep, een opslagaccount en een virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="9a766-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="9a766-219">Als u al bekend bent met de Azure-infrastructuurservices, past u deze instructies aan bij uw momenteel geïmplementeerde infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="9a766-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="9a766-220">Start eerst een Microsoft PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="9a766-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="9a766-221">Meld u aan bij uw Azure-account met behulp van de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="9a766-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="9a766-222">Neem de naam van uw abonnement op met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="9a766-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="9a766-223">Stel uw Azure-abonnement in.</span><span class="sxs-lookup"><span data-stu-id="9a766-223">Set your Azure subscription.</span></span> <span data-ttu-id="9a766-224">Vervang alles tussen de aanhalingstekens, inclusief de \< and > tekens, met de juiste naam.</span><span class="sxs-lookup"><span data-stu-id="9a766-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="9a766-225">Vervolgens maakt u een nieuwe resourcegroep aan.</span><span class="sxs-lookup"><span data-stu-id="9a766-225">Next, create a new resource group.</span></span> <span data-ttu-id="9a766-226">Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9a766-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="9a766-227">Maak uw nieuwe resourcegroep aan met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="9a766-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="9a766-228">Vervang alles tussen de aanhalingstekens, inclusief de \< and > tekens, met de juiste namen.</span><span class="sxs-lookup"><span data-stu-id="9a766-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="9a766-229">Vervolgens maakt u een nieuw virtueel netwerk en de virtuele machine WIN10 met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="9a766-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="9a766-230">Geef desgevraagd de naam en het wachtwoord op van het lokale beheerdersaccount voor WIN10 en bewaar deze op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="9a766-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="9a766-231">Fase 5: uw Windows 10-computer verbinden met Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9a766-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="9a766-232">Zodra de fysieke of virtuele computer met Windows 10 Enterprise is gemaakt, meldt u zich aan met een lokaal beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a766-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a766-233">Voor een virtuele machine in azure gebruikt u  [deze instructies](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) om verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="9a766-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="9a766-234">Vervolgens verbindt u de WIN10-computer met de Azure Active Directory-tenant van uw Microsoft 365 E5-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a766-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="9a766-235">Selecteer op de desktopcomputer van de WIN10-computer de optie **> instellingen > Accounts > toegang tot het werk of school > verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="9a766-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="9a766-236">Selecteer in het dialoogvenster **een werk-of schoolaccount instellen** de optie **Dit apparaat toevoegen aan Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9a766-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="9a766-237">Voer in het **werk-of schoolaccount**de naam van het globale beheerdersaccount van uw microsoft 365 E5-abonnement in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="9a766-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="9a766-238">Voer bij **wachtwoord invoeren**het wachtwoord voor uw globale beheerdersaccount in en selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="9a766-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="9a766-239">Wanneer u wordt gevraagd of u zeker weet dat dit uw organisatie is, selecteert u **deelnemen**en selecteert u **gereed**.</span><span class="sxs-lookup"><span data-stu-id="9a766-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="9a766-240">Sluit het Instellingenvenster.</span><span class="sxs-lookup"><span data-stu-id="9a766-240">Close the settings window.</span></span>
    
<span data-ttu-id="9a766-241">Vervolgens installeert u Microsoft 365-apps voor Enterprise op de WIN10-computer:</span><span class="sxs-lookup"><span data-stu-id="9a766-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="9a766-242">Open de Microsoft Edge-browser en meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a766-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="9a766-243">Selecteer op het tabblad **Start van Microsoft Office** de optie **Office installeren**.</span><span class="sxs-lookup"><span data-stu-id="9a766-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="9a766-244">Wanneer u wordt gevraagd wat u wilt doen, selecteert u **uitvoeren**en selecteert u **Ja** voor **Gebruikersaccountbeheer**.</span><span class="sxs-lookup"><span data-stu-id="9a766-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="9a766-245">Wacht totdat de installatie van Office is voltooid.</span><span class="sxs-lookup"><span data-stu-id="9a766-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="9a766-246">Selecteer twee keer **sluiten** wanneer u **klaar bent**.</span><span class="sxs-lookup"><span data-stu-id="9a766-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="9a766-247">Uw nieuwe omgeving ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9a766-247">Your resulting environment looks like this:</span></span>

![Fase 5 van de Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="9a766-249">Dit geldt ook voor de WIN10-computer die:</span><span class="sxs-lookup"><span data-stu-id="9a766-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="9a766-250">Verbonden is met de Azure Active Directory-tenant van uw Microsoft 365 E5-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a766-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="9a766-251">Geregistreerd is als een Azure Active Directory-apparaat in Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="9a766-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="9a766-252">Microsoft 365-apps voor Enterprise geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="9a766-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="9a766-253">U bent nu klaar om te experimenteren met de extra functies van [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="9a766-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="9a766-254">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="9a766-254">Next steps</span></span>

<span data-ttu-id="9a766-255">Verken de volgende extra sets testlabrichtlijnen:</span><span class="sxs-lookup"><span data-stu-id="9a766-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="9a766-256">Identiteit</span><span class="sxs-lookup"><span data-stu-id="9a766-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="9a766-257">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="9a766-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="9a766-258">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9a766-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="9a766-259">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9a766-259">See also</span></span>

[<span data-ttu-id="9a766-260">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="9a766-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9a766-261">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="9a766-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9a766-262">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9a766-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
