---
title: Het voorbereiden van een niet-routeerbaar domein voor adreslijstsynchronisatie
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Meer informatie over wat u moet doen als u een niet-routeerbaar domein hebt dat is gekoppeld aan uw on-premises gebruikersaccounts voordat u ze synchroniseert met uw Microsoft 365-Tenant.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780330"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="6c165-103">Het voorbereiden van een niet-routeerbaar domein voor adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="6c165-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="6c165-104">Wanneer u uw on-premises adreslijst synchroniseert met Microsoft 365, moet u een geverifieerd domein hebben in azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6c165-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6c165-105">Alleen de UPN (User Principal Names) die zijn gekoppeld aan het on-premises AD DS-domein (Active Directory Domain Services) worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="6c165-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="6c165-106">Elke UPN met een niet-routeerbaar domein (billa@contoso bijvoorbeeld '. lokaal ') wordt echter gesynchroniseerd met een. onmicrosoft.com-domein (voorbeeld: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="6c165-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="6c165-107">Als u momenteel een '. lokaal '-domein gebruikt voor uw gebruikersaccounts in AD DS, wordt u aangeraden ze te wijzigen voor gebruik van een geverifieerd domein, zoals billa@contoso.com, zodat u correct kunt synchroniseren met uw Microsoft 365-domein.</span><span class="sxs-lookup"><span data-stu-id="6c165-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="6c165-108">Wat moet ik doen als ik alleen het on-premises domein '. lokaal ' heb?</span><span class="sxs-lookup"><span data-stu-id="6c165-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="6c165-109">U gebruikt Azure AD Connect voor het synchroniseren van uw AD DS met de Azure AD-Tenant van uw Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="6c165-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="6c165-110">Zie voor meer informatie [uw on-premises Id's integreren met Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="6c165-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="6c165-111">Azure AD Connect synchroniseert de UPN en het wachtwoord van uw gebruikers, zodat gebruikers zich kunnen aanmelden met dezelfde referenties als ze on-premises worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6c165-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="6c165-112">Met Azure AD Connect worden echter alleen gebruikers gesynchroniseerd met domeinen die zijn geverifieerd door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c165-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="6c165-113">Dit betekent dat het domein ook is geverifieerd door Azure AD omdat Microsoft 365-identiteiten worden beheerd door Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6c165-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="6c165-114">Het domein moet dus een geldig Internet domein zijn (bijvoorbeeld. com,. org, .net,. us).</span><span class="sxs-lookup"><span data-stu-id="6c165-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="6c165-115">Als alleen een niet-routeerbaar domein (een niet-routeerbaar domein) wordt gebruikt in uw interne AD DS, kan dit niet overeenkomen met het geverifieerde domein dat u hebt voor uw Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="6c165-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="6c165-116">U kunt dit probleem oplossen door uw primaire domein te wijzigen in uw on-premises AD DS, of door een of meer UPN-achtervoegsels toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="6c165-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="6c165-117">Uw primaire domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="6c165-117">Change your primary domain</span></span>

<span data-ttu-id="6c165-118">Uw primaire domein wijzigen in een domein dat u hebt geverifieerd in Microsoft 365, bijvoorbeeld contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c165-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="6c165-119">Elke gebruiker met het domein contoso. local wordt vervolgens bijgewerkt naar contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c165-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="6c165-120">Dit is een zeer dicht proces en een eenvoudiger oplossing wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="6c165-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="6c165-121">UPN-achtervoegsels toevoegen en de gebruikers hieraan bijwerken</span><span class="sxs-lookup"><span data-stu-id="6c165-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="6c165-122">U kunt het probleem '. lokaal ' oplossen door nieuwe UPN-achtervoegsels of achtervoegsels in AD DS te registreren, zodat deze overeenkomen met de domeinen die u hebt geverifieerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c165-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="6c165-123">Nadat u het nieuwe achtervoegsel hebt geregistreerd, moet u de gebruikers-Upn's bijwerken om de ". local" te vervangen door de nieuwe domeinnaam, bijvoorbeeld zodat een gebruikersaccount eruit ziet zoals billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c165-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="6c165-124">Nadat u de Upn's hebt bijgewerkt voor gebruik met het geverifieerde domein, kunt u uw on-premises AD DS synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c165-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="6c165-125">Stap 1: het nieuwe UPN-achtervoegsel toevoegen \* \*</span><span class="sxs-lookup"><span data-stu-id="6c165-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="6c165-126">Kies op de AD DS-domeincontroller in Server beheer de optie **hulpmiddelen** voor \> **Active Directory-domeinen en vertrouwensrelaties**.</span><span class="sxs-lookup"><span data-stu-id="6c165-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="6c165-127">**Of, als u niet over Windows Server 2012 beschikt**</span><span class="sxs-lookup"><span data-stu-id="6c165-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="6c165-128">Druk op de **Windows-toets + R** om het dialoogvenster **uitvoeren** te openen, typ vervolgens Domain. msc en kies vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c165-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Kies Active Directory-domeinen en vertrouwensrelaties.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="6c165-130">Klik in het venster **Active Directory-domeinen en vertrouwensrelaties** met de rechtermuisknop op **Active Directory-domeinen en vertrouwensrelaties** en kies **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="6c165-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Klik met de rechtermuisknop op Active Directory-domeinen en-vertrouwensrelaties en kies Eigenschappen](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="6c165-132">Op het tabblad **UPN-achtervoegsels** , in het vak **andere UPN-achtervoegsels** , typt u het nieuwe UPN-achtervoegsel of achtervoegsels **en kiest u** vervolgens \> **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="6c165-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Een nieuw UPN-achtervoegsel toevoegen](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="6c165-134">Kies **OK** wanneer u klaar bent met het toevoegen van achtervoegsels.</span><span class="sxs-lookup"><span data-stu-id="6c165-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="6c165-135">Stap 2: het UPN-achtervoegsel voor bestaande gebruikers wijzigen</span><span class="sxs-lookup"><span data-stu-id="6c165-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="6c165-136">Kies op de AD DS-domeincontroller in Server beheer de optie **hulpprogramma's** \> **Active Directory: gebruikers en computers**.</span><span class="sxs-lookup"><span data-stu-id="6c165-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="6c165-137">**Of, als u niet over Windows Server 2012 beschikt**</span><span class="sxs-lookup"><span data-stu-id="6c165-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="6c165-138">Druk op de **Windows-toets + R** om het dialoogvenster **uitvoeren** te openen, typ vervolgens in dsa. msc en klik vervolgens op **OK** .</span><span class="sxs-lookup"><span data-stu-id="6c165-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="6c165-139">Selecteer een gebruiker, klik hierop met de rechtermuisknop en kies **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="6c165-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="6c165-140">Op het tabblad **account** , in de vervolgkeuzelijst met UPN-achtervoegsels, kiest u het nieuwe UPN-achtervoegsel en kiest u vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c165-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Nieuw UPN-achtervoegsel voor een gebruiker toevoegen](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="6c165-142">Voer deze stappen voor elke gebruiker uit.</span><span class="sxs-lookup"><span data-stu-id="6c165-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="6c165-143">PowerShell gebruiken om het UPN-achtervoegsel voor alle gebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="6c165-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="6c165-144">Als u veel gebruikersaccounts hebt om bij te werken, is het eenvoudiger PowerShell te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6c165-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="6c165-145">In het volgende voorbeeld worden de cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) en [set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) gebruikt om alle contoso. lokaal achtervoegsels te wijzigen in contoso.com in AD DS.</span><span class="sxs-lookup"><span data-stu-id="6c165-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="6c165-146">U kunt bijvoorbeeld de volgende PowerShell-opdrachten uitvoeren om alle contoso. lokaal achtervoegsels bij te werken in contoso.com:</span><span class="sxs-lookup"><span data-stu-id="6c165-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="6c165-147">Zie [Active Directory Windows PowerShell-module](https://go.microsoft.com/fwlink/p/?LinkId=624314) voor meer informatie over het gebruik van Windows PowerShell in AD DS.</span><span class="sxs-lookup"><span data-stu-id="6c165-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

