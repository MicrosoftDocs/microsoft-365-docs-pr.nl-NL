---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: E-mail doorsturen naar een of meer e-mailaccounts via Office365.
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560790"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="1b6ae-103">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="1b6ae-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1b6ae-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-104">The admin center is changing.</span></span> <span data-ttu-id="1b6ae-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1b6ae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="1b6ae-106">Als beheerder van een organisatie hebt u mogelijk een bedrijf nodig om het doorsturen van e-mail in te stellen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="1b6ae-107">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b6ae-108">U kunt uitgaande spamfilter beleidsregels gebruiken om automatisch doorsturen naar externe geadresseerden te beheren.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="1b6ae-109">Zie voor meer informatie [het artikel automatisch doorsturen van externe e-mail in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="1b6ae-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="1b6ae-110">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="1b6ae-110">Configure email forwarding</span></span>

 <span data-ttu-id="1b6ae-111">Let op het volgende voordat u het doorsturen van e-mail instelt:</span><span class="sxs-lookup"><span data-stu-id="1b6ae-111">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="1b6ae-112">Wanneer u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mailberichten die zijn verzonden naar het Postvak  *van*  de e-mail doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="1b6ae-113">Voor het doorsturen van e-mail is vereist dat het  *van*  -account een licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="1b6ae-114">Als u het doorsturen van e-mail instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie [het postvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1b6ae-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="1b6ae-115">Op deze manier kunnen meerdere mensen er toegang toe krijgen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-115">This way several people can access it.</span></span> <span data-ttu-id="1b6ae-116">Een gedeeld postvak mag echter niet groter zijn dan 50 GB.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-116">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="1b6ae-117">U kunt deze stappen alleen uitvoeren als u een Exchange-beheerder of globale beheerder in Microsoft 365 bent.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="1b6ae-118">Voor meer informatie raadpleegt u het onderwerp [over beheerdersrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1b6ae-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1b6ae-119">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="1b6ae-120">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-120">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="1b6ae-121">Selecteer op het tabblad **e-mail** de optie **doorsturen van e-mail beheren**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-121">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="1b6ae-122">Selecteer op de pagina voor het doorsturen van e-mail **alle e-mail die naar dit postvak is verzonden**, voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1b6ae-123">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1b6ae-124">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-124">Select **Save changes**.</span></span>
    
    <span data-ttu-id="1b6ae-125">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1b6ae-126">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1b6ae-127">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1b6ae-128">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1b6ae-129">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-129">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="1b6ae-130">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1b6ae-131">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-131">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1b6ae-132">Vouw **e-mailinstellingen** uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1b6ae-133">Op de pagina voor het doorsturen van e-mail zet **u de** wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1b6ae-134">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1b6ae-135">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-135">Select **Save**.</span></span>
    
    <span data-ttu-id="1b6ae-136">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1b6ae-137">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1b6ae-138">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1b6ae-139">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1b6ae-140">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-140">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1b6ae-141">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1b6ae-142">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-142">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1b6ae-143">Vouw **e-mailinstellingen** uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1b6ae-144">Op de pagina voor het doorsturen van e-mail zet **u de** wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1b6ae-145">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1b6ae-146">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-146">Select **Save**.</span></span>
    
    <span data-ttu-id="1b6ae-147">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1b6ae-148">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1b6ae-149">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1b6ae-150">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1b6ae-151">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="1b6ae-151">If you do, email forwarding will stop.</span></span> 


::: moniker-end 
