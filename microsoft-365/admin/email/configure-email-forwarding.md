---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: E-mail doorsturen naar een of meer e-mailaccounts instellen met Office365.
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780251"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="23c2b-103">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="23c2b-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="23c2b-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="23c2b-104">The admin center is changing.</span></span> <span data-ttu-id="23c2b-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="23c2b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="23c2b-106">Als beheerder van een organisatie u bedrijfsvereisten hebben om e-mail doorsturen in te stellen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="23c2b-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="23c2b-107">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="23c2b-108">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="23c2b-108">Configure email forwarding</span></span>

 <span data-ttu-id="23c2b-109">Noteer het volgende voordat u e-mail doorstuurt:</span><span class="sxs-lookup"><span data-stu-id="23c2b-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="23c2b-110">Zodra u e-mail doorsturen, alleen **nieuwe** e-mails verzonden naar de *van* mailbox zal worden fowarded.</span><span class="sxs-lookup"><span data-stu-id="23c2b-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="23c2b-111">E-mail doorsturen vereist dat de *van* account heeft een licentie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="23c2b-112">Als u e-mail doorstuurt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie om het postvak om te [zetten naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="23c2b-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="23c2b-113">Op deze manier hebben meerdere mensen er toegang toe.</span><span class="sxs-lookup"><span data-stu-id="23c2b-113">This way several people can access it.</span></span> <span data-ttu-id="23c2b-114">Een gedeeld postvak mag echter niet meer dan 50 GB bedragen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="23c2b-115">U moet een Exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="23c2b-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="23c2b-116">Zie het onderwerp [Over beheerdersrollen voor](../add-users/about-admin-roles.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23c2b-117">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="23c2b-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="23c2b-118">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="23c2b-119">Selecteer **e-mail doorsturen op**het tabblad **E-mail** beheren .</span><span class="sxs-lookup"><span data-stu-id="23c2b-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="23c2b-120">Selecteer op de pagina e-mail doorsturen de optie **Alle e-mails die naar dit postvak worden verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="23c2b-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="23c2b-121">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="23c2b-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="23c2b-122">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="23c2b-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="23c2b-123">Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="23c2b-124">Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="23c2b-125">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="23c2b-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="23c2b-126">Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!</span><span class="sxs-lookup"><span data-stu-id="23c2b-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="23c2b-127">Als u dat doet, stopt e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="23c2b-128">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="23c2b-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="23c2b-129">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="23c2b-130">Vouw **E-mailinstellingen**uit en selecteer vervolgens in de sectie **E-maildoorschakeling** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="23c2b-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="23c2b-131">Stel op de pagina e-mail doorsturen de schakelaar **in op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="23c2b-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="23c2b-132">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="23c2b-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="23c2b-133">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="23c2b-133">Select **Save**.</span></span>
    
    <span data-ttu-id="23c2b-134">Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="23c2b-135">Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="23c2b-136">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="23c2b-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="23c2b-137">Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!</span><span class="sxs-lookup"><span data-stu-id="23c2b-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="23c2b-138">Als u dat doet, stopt e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="23c2b-139">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="23c2b-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="23c2b-140">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="23c2b-141">Vouw **E-mailinstellingen**uit en selecteer vervolgens in de sectie **E-maildoorschakeling** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="23c2b-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="23c2b-142">Stel op de pagina e-mail doorsturen de schakelaar **in op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="23c2b-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="23c2b-143">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="23c2b-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="23c2b-144">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="23c2b-144">Select **Save**.</span></span>
    
    <span data-ttu-id="23c2b-145">Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="23c2b-146">Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23c2b-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="23c2b-147">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="23c2b-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="23c2b-148">Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!</span><span class="sxs-lookup"><span data-stu-id="23c2b-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="23c2b-149">Als u dat doet, stopt e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="23c2b-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
