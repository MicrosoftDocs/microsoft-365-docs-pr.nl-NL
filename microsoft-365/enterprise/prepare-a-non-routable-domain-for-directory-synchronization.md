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
description: Lees wat u moet doen als u een niet-routable domein hebt dat is gekoppeld aan uw on-premises gebruikersaccounts voordat u deze synchroniseert met uw Microsoft 365-tenant.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927394"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="a6366-103">Het voorbereiden van een niet-routeerbaar domein voor adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="a6366-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="a6366-104">Wanneer u uw on-premises adreslijst synchroniseert met Microsoft 365, moet u een geverifieerd domein hebben in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a6366-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a6366-105">Alleen de UPN's (User Principal Names) die zijn gekoppeld aan het on-premises Ad DS-domein (Active Directory Domain Services) worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="a6366-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="a6366-106">Elke UPN die een niet-routable domein bevat, zoals '.lokaal' (bijvoorbeeld: billa@contoso.local), wordt echter gesynchroniseerd met een .onmicrosoft.com-domein (bijvoorbeeld: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="a6366-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="a6366-107">Als u momenteel een '.lokaal' domein gebruikt voor uw gebruikersaccounts in AD DS, wordt u aangeraden deze te wijzigen in een geverifieerd domein, zoals billa@contoso.com, om op de juiste manier te synchroniseren met uw Microsoft 365-domein.</span><span class="sxs-lookup"><span data-stu-id="a6366-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="a6366-108">Wat gebeurt er als ik alleen een on-premises domein '.lokaal' heb?</span><span class="sxs-lookup"><span data-stu-id="a6366-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="a6366-109">U gebruikt Azure AD Connect om uw AD DS te synchroniseren met de Azure AD-tenant van uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="a6366-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="a6366-110">Zie Uw [on-premises](/azure/architecture/reference-architectures/identity/azure-ad)identiteiten integreren met Azure AD voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a6366-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="a6366-111">Met Azure AD Connect worden de UPN en het wachtwoord van uw gebruikers gesynchroniseerd, zodat gebruikers zich kunnen aanmelden met dezelfde referenties die ze on-premises gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a6366-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="a6366-112">Azure AD Connect synchroniseert echter alleen gebruikers met domeinen die worden geverifieerd door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6366-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="a6366-113">Dit betekent dat het domein ook wordt geverifieerd door Azure AD omdat Microsoft 365-identiteiten worden beheerd door Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a6366-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="a6366-114">Met andere woorden, het domein moet een geldig internetdomein zijn (zoals .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="a6366-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="a6366-115">Als uw interne AD DS alleen een niet-routable-domein gebruikt (bijvoorbeeld '.lokaal'), kan dit mogelijk niet overeenkomen met het geverifieerde domein dat u hebt voor uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="a6366-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="a6366-116">U kunt dit probleem oplossen door uw primaire domein in uw on-premises AD DS te wijzigen of door een of meer UPN-achtervoegsels toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="a6366-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="a6366-117">Uw primaire domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="a6366-117">Change your primary domain</span></span>

<span data-ttu-id="a6366-118">Wijzig uw primaire domein in een domein dat u hebt geverifieerd in Microsoft 365, bijvoorbeeld contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a6366-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="a6366-119">Elke gebruiker met het domein contoso.local wordt vervolgens bijgewerkt naar contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a6366-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="a6366-120">Dit is echter een zeer betrokken proces en een eenvoudigere oplossing wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="a6366-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="a6366-121">UPN-achtervoegsels toevoegen en uw gebruikers hieraan bijwerken</span><span class="sxs-lookup"><span data-stu-id="a6366-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="a6366-122">U kunt het probleem '.lokaal' oplossen door nieuwe UPN-achtervoegsels of achtervoegsels in AD DS te registreren die overeenkomen met het domein (of domeinen) dat u hebt geverifieerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6366-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="a6366-123">Nadat u het nieuwe achtervoegsel hebt geregistreerd, kunt u de UPN's van de gebruiker bijwerken om bijvoorbeeld de '.local' te vervangen door de nieuwe domeinnaam, zodat een gebruikersaccount eruitziet als billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a6366-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="a6366-124">Nadat u de UPN's hebt bijgewerkt om het geverifieerde domein te gebruiken, kunt u uw on-premises AD DS synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6366-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="a6366-125">Stap 1: Het nieuwe UPN-achtervoegsel toevoegen\*\*</span><span class="sxs-lookup"><span data-stu-id="a6366-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="a6366-126">Kies op de AD DS-domeincontroller in Serverbeheer **de optie Extra** Active \> **Directory-domeinen en -vertrouwensinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="a6366-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="a6366-127">**Of als u geen Windows Server 2012 hebt**</span><span class="sxs-lookup"><span data-stu-id="a6366-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="a6366-128">Druk **op Windows-toets + R** om het dialoogvenster Uitvoeren te openen en typ domein.msc en kies  **OK.**</span><span class="sxs-lookup"><span data-stu-id="a6366-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Kies Active Directory-domeinen en -vertrouwensrelatie.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="a6366-130">Klik in **het venster Active Directory Domains and Trusts** met de rechtermuisknop op Active Directory **Domains and Trusts** en kies **vervolgens Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="a6366-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Klik met de rechtermuisknop op Active Directory-domeinen en -vertrouwensrelatie en kies Eigenschappen](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="a6366-132">Typ op **het tabblad UPN-achtervoegsels** in het vak Alternatieve **UPN-achtervoegsels** uw nieuwe UPN-achtervoegsel of achtervoegsels en kies vervolgens **Toepassen** \> **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a6366-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Een nieuw UPN-achtervoegsel toevoegen](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="a6366-134">Kies **OK** wanneer u klaar bent met het toevoegen van achtervoegsels.</span><span class="sxs-lookup"><span data-stu-id="a6366-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="a6366-135">Stap 2: het UPN-achtervoegsel voor bestaande gebruikers wijzigen</span><span class="sxs-lookup"><span data-stu-id="a6366-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="a6366-136">Kies op de AD DS-domeincontroller in Serverbeheer **de optie Extra** Active \> **Directory-gebruikers en -computers.**</span><span class="sxs-lookup"><span data-stu-id="a6366-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="a6366-137">**Of als u geen Windows Server 2012 hebt**</span><span class="sxs-lookup"><span data-stu-id="a6366-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="a6366-138">Druk **op Windows-toets + R** om het dialoogvenster Uitvoeren te openen en typ Dsa.msc en klik vervolgens op  **OK**</span><span class="sxs-lookup"><span data-stu-id="a6366-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="a6366-139">Selecteer een gebruiker, klik met de rechtermuisknop en kies vervolgens **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="a6366-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="a6366-140">Kies op **het** tabblad Account in de vervolgkeuzelijst UPN-achtervoegsel het nieuwe UPN-achtervoegsel en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="a6366-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Nieuw UPN-achtervoegsel toevoegen voor een gebruiker](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="a6366-142">Voltooi deze stappen voor elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a6366-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="a6366-143">PowerShell gebruiken om het UPN-achtervoegsel voor al uw gebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a6366-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="a6366-144">Als u veel gebruikersaccounts wilt bijwerken, kunt u PowerShell gemakkelijker gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a6366-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="a6366-145">In het volgende voorbeeld worden de cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) en [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) gebruikt om alle contoso.local-achtervoegsels te wijzigen in contoso.com in AD DS.</span><span class="sxs-lookup"><span data-stu-id="a6366-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="a6366-146">U kunt bijvoorbeeld de volgende PowerShell-opdrachten uitvoeren om alle contoso.local-achtervoegsels bij te werken naar contoso.com:</span><span class="sxs-lookup"><span data-stu-id="a6366-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="a6366-147">Zie [Active Directory Windows PowerShell-module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) voor meer informatie over het gebruik van Windows PowerShell in AD DS.</span><span class="sxs-lookup"><span data-stu-id="a6366-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>