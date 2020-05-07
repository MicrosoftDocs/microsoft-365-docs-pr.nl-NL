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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: E-mail doorsturen instellen voor een of meer e-mailaccounts met Office365.
ms.openlocfilehash: 8cd86bcab4d73719e527f9942cd41a3174966c2d
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140451"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="3031b-103">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="3031b-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3031b-104">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="3031b-104">The admin center is changing.</span></span> <span data-ttu-id="3031b-105">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3031b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="3031b-106">Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten om e-maildoorsturen in te stellen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3031b-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="3031b-107">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="3031b-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="3031b-108">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="3031b-108">Configure email forwarding</span></span>

 <span data-ttu-id="3031b-109">Voordat u e-mail doorstuur instelt, moet u het volgende noteren:</span><span class="sxs-lookup"><span data-stu-id="3031b-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="3031b-110">Zodra u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mails die naar het *postvak worden* verzonden, verzonden.</span><span class="sxs-lookup"><span data-stu-id="3031b-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="3031b-111">E-mail doorsturen vereist dat het *van* account een licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="3031b-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="3031b-112">Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie om zijn postvak om te [zetten naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="3031b-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="3031b-113">Op deze manier kunnen meerdere mensen er toegang toe krijgen.</span><span class="sxs-lookup"><span data-stu-id="3031b-113">This way several people can access it.</span></span> <span data-ttu-id="3031b-114">Een gedeeld postvak mag echter niet meer dan 50 GB bedragen.</span><span class="sxs-lookup"><span data-stu-id="3031b-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="3031b-115">U moet exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3031b-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="3031b-116">Zie het onderwerp [Over beheerdersrollen](../add-users/about-admin-roles.md)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="3031b-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3031b-117">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3031b-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="3031b-118">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3031b-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="3031b-119">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="3031b-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="3031b-120">Selecteer op het tabblad **E-mail** de optie **E-mail doorsturen beheren**.</span><span class="sxs-lookup"><span data-stu-id="3031b-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="3031b-121">Selecteer op de pagina e-mail doorsturen **alle e-mails die naar dit postvak zijn verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="3031b-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="3031b-122">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3031b-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="3031b-123">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3031b-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="3031b-124">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="3031b-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="3031b-125">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3031b-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="3031b-126">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3031b-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="3031b-127">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="3031b-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="3031b-128">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="3031b-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="3031b-129">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3031b-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="3031b-130">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="3031b-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="3031b-131">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3031b-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="3031b-132">Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="3031b-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="3031b-133">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3031b-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="3031b-134">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3031b-134">Select **Save**.</span></span>
    
    <span data-ttu-id="3031b-135">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="3031b-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="3031b-136">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3031b-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="3031b-137">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3031b-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="3031b-138">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="3031b-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="3031b-139">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="3031b-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3031b-140">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3031b-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="3031b-141">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="3031b-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="3031b-142">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3031b-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="3031b-143">Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="3031b-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="3031b-144">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3031b-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="3031b-145">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3031b-145">Select **Save**.</span></span>
    
    <span data-ttu-id="3031b-146">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="3031b-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="3031b-147">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3031b-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="3031b-148">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3031b-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="3031b-149">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="3031b-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="3031b-150">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="3031b-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
