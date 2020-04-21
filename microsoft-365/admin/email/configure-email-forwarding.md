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
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628913"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="eb343-103">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="eb343-103">Configure email forwarding</span></span>
  
<span data-ttu-id="eb343-104">Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten om e-maildoorsturen in te stellen voor het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="eb343-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="eb343-105">Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="eb343-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="eb343-106">Doorsturen van e‑mail configureren</span><span class="sxs-lookup"><span data-stu-id="eb343-106">Configure email forwarding</span></span>

 <span data-ttu-id="eb343-107">Voordat u e-mail doorstuur instelt, moet u het volgende noteren:</span><span class="sxs-lookup"><span data-stu-id="eb343-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="eb343-108">Zodra u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mails die naar het *postvak worden* verzonden, verzonden.</span><span class="sxs-lookup"><span data-stu-id="eb343-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="eb343-109">E-mail doorsturen vereist dat het *van* account een licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="eb343-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="eb343-110">Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie om zijn postvak om te [zetten naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="eb343-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="eb343-111">Op deze manier kunnen meerdere mensen er toegang toe krijgen.</span><span class="sxs-lookup"><span data-stu-id="eb343-111">This way several people can access it.</span></span> <span data-ttu-id="eb343-112">Een gedeeld postvak mag echter niet meer dan 50 GB bedragen.</span><span class="sxs-lookup"><span data-stu-id="eb343-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="eb343-113">U moet exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="eb343-113">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="eb343-114">Zie het onderwerp [Over beheerdersrollen](../add-users/about-admin-roles.md)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="eb343-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="eb343-115">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="eb343-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="eb343-116">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="eb343-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="eb343-117">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="eb343-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="eb343-118">Selecteer op het tabblad **E-mail** de optie **E-mail doorsturen beheren**.</span><span class="sxs-lookup"><span data-stu-id="eb343-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="eb343-119">Selecteer op de pagina e-mail doorsturen **alle e-mails die naar dit postvak zijn verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="eb343-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="eb343-120">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="eb343-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="eb343-121">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="eb343-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="eb343-122">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="eb343-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="eb343-123">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb343-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="eb343-124">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="eb343-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="eb343-125">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="eb343-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="eb343-126">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="eb343-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="eb343-127">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="eb343-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="eb343-128">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="eb343-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="eb343-129">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="eb343-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="eb343-130">Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="eb343-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="eb343-131">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="eb343-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="eb343-132">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="eb343-132">Select **Save**.</span></span>
    
    <span data-ttu-id="eb343-133">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="eb343-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="eb343-134">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb343-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="eb343-135">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="eb343-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="eb343-136">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="eb343-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="eb343-137">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="eb343-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="eb343-138">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="eb343-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="eb343-139">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen.</span><span class="sxs-lookup"><span data-stu-id="eb343-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="eb343-140">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="eb343-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="eb343-141">Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="eb343-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="eb343-142">Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="eb343-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="eb343-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="eb343-143">Select **Save**.</span></span>
    
    <span data-ttu-id="eb343-144">**Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="eb343-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="eb343-145">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb343-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="eb343-146">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="eb343-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="eb343-147">Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!</span><span class="sxs-lookup"><span data-stu-id="eb343-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="eb343-148">Als u dit doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="eb343-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
