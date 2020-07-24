---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Meer informatie over het converteren van een privépostvak naar een gedeeld postvak dat door meerdere gebruikers kan worden geopend. '
ms.openlocfilehash: 7ae00c1d9c901378798f063554a44a3e5b741442
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391528"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="0692f-103">Het postvak van een gebruiker converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="0692f-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="0692f-104">Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden.</span><span class="sxs-lookup"><span data-stu-id="0692f-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="0692f-105">Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon.</span><span class="sxs-lookup"><span data-stu-id="0692f-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="0692f-106">Op een later tijdstip u een gedeeld postvak converteren naar een privépostvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0692f-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="0692f-107">**Hier zijn een aantal echt belangrijke dingen die je moet weten:**</span><span class="sxs-lookup"><span data-stu-id="0692f-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="0692f-108">Het gebruikerspostvak dat u converteert, heeft een licentie nodig die eraan is toegewezen voordat u deze converteert naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="0692f-109">Anders wordt de optie om het postvak te converteren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0692f-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="0692f-110">Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren.</span><span class="sxs-lookup"><span data-stu-id="0692f-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="0692f-111">Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="0692f-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="0692f-p103">Gedeelde postvakken kunnen maximaal 50 GB aan gegevens bevatten zonder dat er een licentie aan is toegewezen. Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen. Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0692f-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="0692f-p104">Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="0692f-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="0692f-118">De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="0692f-119">Het Exchange-beheercentrum gebruiken om een postvak te converteren</span><span class="sxs-lookup"><span data-stu-id="0692f-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="0692f-120">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="0692f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="0692f-121">Postvakken **geadresseerden** \> **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="0692f-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="0692f-122">Selecteer het gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-122">Select the user mailbox.</span></span> <span data-ttu-id="0692f-123">Selecteer **Onder Converteren naar gedeeld postvak**de optie **Converteren**.</span><span class="sxs-lookup"><span data-stu-id="0692f-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0692f-124">Als het postvak kleiner is dan 50 GB, kunt u de [licentie van de gebruiker](../manage/remove-licenses-from-users.md) verwijderen zodat u er niet meer voor hoeft te betalen.</span><span class="sxs-lookup"><span data-stu-id="0692f-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="0692f-125">Verwijder het account van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="0692f-125">Don't delete the user's account.</span></span> <span data-ttu-id="0692f-126">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="0692f-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="0692f-127">Als u het postvak converteert van een werknemer die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen.</span><span class="sxs-lookup"><span data-stu-id="0692f-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="0692f-128">Zie [Een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="0692f-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="0692f-129">Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor alles wat u moet weten over gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="0692f-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="0692f-130">Het Microsoft 365-beheercentrum gebruiken om een postvak te converteren</span><span class="sxs-lookup"><span data-stu-id="0692f-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0692f-131">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0692f-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0692f-132">Selecteer de naam van de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="0692f-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="0692f-133">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="0692f-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="0692f-134">Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="0692f-135">Als het wachtwoord echter niet opnieuw wordt ingesteld, **blijven de oorspronkelijke gebruikersnaam en het wachtwoord werken** nadat de conversie van het postvak is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0692f-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="0692f-136">Selecteer op het tabblad **E-mail** onder **Meer acties**de optie **Converteren naar gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="0692f-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0692f-137">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0692f-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0692f-138">Selecteer de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="0692f-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="0692f-139">Vouw in het rechterdeelvenster **E-mailinstellingen uit**.</span><span class="sxs-lookup"><span data-stu-id="0692f-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="0692f-140">Selecteer naast **Meer instellingen**de optie **Converteren naar gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="0692f-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0692f-141">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0692f-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0692f-142">Selecteer de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="0692f-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="0692f-143">Vouw in het rechterdeelvenster **E-mailinstellingen uit**.</span><span class="sxs-lookup"><span data-stu-id="0692f-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="0692f-144">Selecteer naast **Meer instellingen**de optie **Converteren naar gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="0692f-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="0692f-145">Als het postvak kleiner is dan 50 GB, u [de licentie van de gebruiker verwijderen](../manage/remove-licenses-from-users.md)en er niet meer voor betalen.</span><span class="sxs-lookup"><span data-stu-id="0692f-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="0692f-146">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="0692f-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="0692f-147">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="0692f-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="0692f-148">Als u het postvak converteert van een werknemer die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen.</span><span class="sxs-lookup"><span data-stu-id="0692f-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="0692f-149">Zie [Een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="0692f-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="0692f-150">Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor alles wat u moet weten over gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="0692f-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0692f-151">Gedeelde postvakken vereisen geen aparte licentie.</span><span class="sxs-lookup"><span data-stu-id="0692f-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="0692f-152">Als u in-place archive wilt inschakelen of een in-place hold of een litigation hold op een gedeeld postvak wilt plaatsen, moet u een Exchange Online Plan 1 met Exchange Online Archiveing of Exchange Online Plan 2-licentie toewijzen aan het postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="0692f-153">Het postvak van een verwijderde gebruiker converteren</span><span class="sxs-lookup"><span data-stu-id="0692f-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="0692f-p112">Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:</span><span class="sxs-lookup"><span data-stu-id="0692f-p112">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="0692f-156">[Het account van de gebruiker herstellen](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="0692f-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="0692f-157">Zorg ervoor dat er een Microsoft 365-licentie aan is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0692f-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="0692f-158">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="0692f-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="0692f-159">Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0692f-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="0692f-160">Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="0692f-161">Nadat dat is gebeurd, u de licentie uit het postvak van de gebruiker verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0692f-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="0692f-162">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="0692f-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="0692f-163">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="0692f-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="0692f-164">Voeg leden toe aan het gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="0692f-165">Een gedeeld postvak converteren naar het (privé)postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="0692f-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="0692f-166">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="0692f-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="0692f-167">Selecteer **Gedeelde geadresseerden** \> **Shared**.</span><span class="sxs-lookup"><span data-stu-id="0692f-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="0692f-168">Selecteer het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-168">Select the shared mailbox.</span></span> <span data-ttu-id="0692f-169">Selecteer **Onder Converteren naar normaal postvak**de optie **Converteren**.</span><span class="sxs-lookup"><span data-stu-id="0692f-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0692f-170">Ga terug naar het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0692f-170">Go back to the admin center.</span></span> <span data-ttu-id="0692f-171">Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="0692f-172">Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="0692f-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="0692f-p116">Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.</span><span class="sxs-lookup"><span data-stu-id="0692f-p116">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="0692f-175">Het postvak van een gebruiker converteren in een hybride omgeving</span><span class="sxs-lookup"><span data-stu-id="0692f-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="0692f-176">Als dit gedeelde postvak zich in een hybride omgeving bevindt, raden we u **ten zeerste aan** (bijna nodig!) om het gebruikerspostvak terug te verplaatsen naar on-premises, het gebruikerspostvak om te zetten naar een gedeeld postvak en vervolgens het gedeelde postvak terug te verplaatsen naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="0692f-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="0692f-177">Hier is waarom: als u het postvak in de cloud converteert, kan het worden geconverteerd, maar on-premises denkt nog steeds dat het postvak het postvak van de gebruiker is, omdat de nieuwe realiteit niet wordt gesynchroniseerd met on-premises.</span><span class="sxs-lookup"><span data-stu-id="0692f-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="0692f-178">Meestal is dit geen probleem, maar er zijn enkele scenario's waarin de on-premises kenmerken (die denken dat het postvak het postvak van de gebruiker is) de nieuwe cloudversies van die kenmerken kunnen overschrijven en als gevolg daarvan het postvak kan worden omgeboekt.</span><span class="sxs-lookup"><span data-stu-id="0692f-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="0692f-179">Dit is een probleem omdat gebruikerspostvakken licenties vereisen **of ze zijn zacht verwijderd na 30 dagen!**</span><span class="sxs-lookup"><span data-stu-id="0692f-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="0692f-180">We hebben de meeste redenen aangepakt waarom dit gebeurt, maar het kan nog steeds gebeuren, hoewel zelden.</span><span class="sxs-lookup"><span data-stu-id="0692f-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="0692f-181">Het is het beste om veilig te zijn en de brievenbus terug te verplaatsen naar on-premises.</span><span class="sxs-lookup"><span data-stu-id="0692f-181">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="0692f-182">Als u deel uitmaakt van Organisatiebeheer of Ontvangstbeheer, u de shell Exchange Management gebruiken om een gebruikerspostvak on-premises te wijzigen in een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="0692f-182">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="0692f-183">Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="0692f-183">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="0692f-184">Bekijk de tijdelijke oplossing in deze ondersteuningsoplossing voor voorbeelden waarin [gedeelde postvakken onverwacht worden geconverteerd naar postvakken van gebruikers](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="0692f-184">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="0692f-185">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0692f-185">Related articles</span></span>

[<span data-ttu-id="0692f-186">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="0692f-186">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0692f-187">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="0692f-187">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0692f-188">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="0692f-188">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0692f-189">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="0692f-189">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="0692f-190">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="0692f-190">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
