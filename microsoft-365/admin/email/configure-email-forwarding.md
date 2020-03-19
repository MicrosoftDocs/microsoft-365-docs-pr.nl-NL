---
title: Doorsturen van e-mail configureren in Office 365
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
description: Stel e-maildoorsturen in naar een of meer e-mailaccounts met Office365.
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806389"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="e6563-103">Doorsturen van e-mail configureren in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6563-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="e6563-p101">Als beheerder van een Office 365-organisatie hebt u wellicht bedrijfsmatige verplichtingen om het doorsturen van e-mail naar het postvak van een gebruiker in te stellen. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6563-p101">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="e6563-106">Doorsturen van e-mail configureren</span><span class="sxs-lookup"><span data-stu-id="e6563-106">Configure email forwarding</span></span>

 <span data-ttu-id="e6563-107">Noteer het volgende voordat u e-maildoorstuur instelt:</span><span class="sxs-lookup"><span data-stu-id="e6563-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="e6563-108">Zodra u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mails die vanuit *postvak* worden verzonden, opgedrongen.</span><span class="sxs-lookup"><span data-stu-id="e6563-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="e6563-109">E-mail doorsturen vereist dat het *account van* een account een licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="e6563-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="e6563-110">Als u e-maildoorstuur instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie het [converteren van zijn postvak naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="e6563-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="e6563-111">Op deze manier hebben meerdere mensen er toegang toe.</span><span class="sxs-lookup"><span data-stu-id="e6563-111">This way several people can access it.</span></span> <span data-ttu-id="e6563-112">Een gedeeld postvak mag echter niet meer dan 50 GB bedragen.</span><span class="sxs-lookup"><span data-stu-id="e6563-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="e6563-113">U moet een Exchange-beheerder of Globale beheerder in Office 365 zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e6563-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="e6563-114">Zie voor meer informatie het onderwerp [Over beheerdersrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e6563-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e6563-115">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e6563-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e6563-116">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="e6563-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="e6563-117">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="e6563-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="e6563-118">Selecteer op het tabblad **E-mail** de optie **E-mail doorsturen beheren**.</span><span class="sxs-lookup"><span data-stu-id="e6563-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="e6563-119">Selecteer op de pagina e-mail doorsturen de optie **Alle e-mails doorsturen die naar dit postvak zijn verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="e6563-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e6563-120">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="e6563-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e6563-121">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e6563-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="e6563-122">Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="e6563-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e6563-123">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6563-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e6563-124">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6563-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e6563-125">Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!</span><span class="sxs-lookup"><span data-stu-id="e6563-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e6563-126">Als u dat doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="e6563-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="e6563-127">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="e6563-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="e6563-128">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="e6563-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="e6563-129">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e6563-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e6563-130">Stel op de pagina e-mail doorsturen de schakelaar in op **Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="e6563-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e6563-131">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="e6563-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e6563-132">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e6563-132">Select **Save**.</span></span>
    
    <span data-ttu-id="e6563-133">Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="e6563-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e6563-134">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6563-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e6563-135">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6563-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e6563-136">Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!</span><span class="sxs-lookup"><span data-stu-id="e6563-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e6563-137">Als u dat doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="e6563-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="e6563-138">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="e6563-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="e6563-139">Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="e6563-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="e6563-140">Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e6563-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e6563-141">Stel op de pagina e-mail doorsturen de schakelaar in op **Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="e6563-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e6563-142">Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="e6563-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e6563-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e6563-143">Select **Save**.</span></span>
    
    <span data-ttu-id="e6563-144">Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen.</span><span class="sxs-lookup"><span data-stu-id="e6563-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e6563-145">Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6563-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e6563-146">Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6563-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e6563-147">Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!</span><span class="sxs-lookup"><span data-stu-id="e6563-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e6563-148">Als u dat doet, stopt het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="e6563-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
