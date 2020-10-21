---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
ms.openlocfilehash: d19e2c533be6fac927bdf2aa65d72acab9fad6f6
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645525"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="0e33c-103">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="0e33c-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0e33c-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0e33c-104">The admin center is changing.</span></span> <span data-ttu-id="0e33c-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0e33c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="0e33c-106">Als beheerder van een organisatie hebt u mogelijk een bedrijf nodig om het doorsturen van e-mail in te stellen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0e33c-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="0e33c-107">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0e33c-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="0e33c-108">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="0e33c-108">Configure email forwarding</span></span>

 <span data-ttu-id="0e33c-109">Let op het volgende voordat u het doorsturen van e-mail instelt:</span><span class="sxs-lookup"><span data-stu-id="0e33c-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="0e33c-110">Wanneer u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mailberichten die worden verzonden naar het Postvak  *in*  doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="0e33c-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="0e33c-111">Voor het doorsturen van e-mail is vereist dat het  *van*  -account een licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="0e33c-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="0e33c-112">Als u het doorsturen van e-mail instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie [het postvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="0e33c-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="0e33c-113">Op deze manier kunnen meerdere mensen er toegang toe krijgen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-113">This way several people can access it.</span></span> <span data-ttu-id="0e33c-114">Een gedeeld postvak mag echter niet groter zijn dan 50 GB.</span><span class="sxs-lookup"><span data-stu-id="0e33c-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="0e33c-115">U kunt deze stappen alleen uitvoeren als u een Exchange-beheerder of globale beheerder in Microsoft 365 bent.</span><span class="sxs-lookup"><span data-stu-id="0e33c-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="0e33c-116">Voor meer informatie raadpleegt u het onderwerp [over beheerdersrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0e33c-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0e33c-117">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0e33c-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="0e33c-118">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="0e33c-119">Selecteer op het tabblad **e-mail** de optie **doorsturen van e-mail beheren**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="0e33c-120">Selecteer op de pagina voor het doorsturen van e-mail **alle e-mail die naar dit postvak is verzonden**, voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="0e33c-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0e33c-121">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0e33c-122">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="0e33c-123">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0e33c-124">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e33c-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="0e33c-125">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="0e33c-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="0e33c-126">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0e33c-127">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="0e33c-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="0e33c-128">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0e33c-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="0e33c-129">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="0e33c-130">Vouw **e-mailinstellingen**uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0e33c-131">Op de pagina voor het doorsturen van e-mail zet **u de**wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="0e33c-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0e33c-132">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0e33c-133">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-133">Select **Save**.</span></span>
    
    <span data-ttu-id="0e33c-134">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0e33c-135">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e33c-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="0e33c-136">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="0e33c-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="0e33c-137">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0e33c-138">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="0e33c-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="0e33c-139">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0e33c-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="0e33c-140">Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="0e33c-141">Vouw **e-mailinstellingen**uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0e33c-142">Op de pagina voor het doorsturen van e-mail zet **u de**wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="0e33c-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0e33c-143">Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0e33c-144">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e33c-144">Select **Save**.</span></span>
    
    <span data-ttu-id="0e33c-145">**Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0e33c-146">Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e33c-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="0e33c-147">U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="0e33c-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="0e33c-148">Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0e33c-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0e33c-149">Als u dat doet, wordt het doorsturen van e-mail gestopt.</span><span class="sxs-lookup"><span data-stu-id="0e33c-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
