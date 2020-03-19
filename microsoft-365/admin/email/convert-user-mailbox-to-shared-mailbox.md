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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Leer een privépostvak converteren naar een gedeeld postvak dat door meerdere gebruikers kan worden geopend. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811753"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="5ac47-103">Het postvak van een gebruiker converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="5ac47-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="5ac47-104">Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden.</span><span class="sxs-lookup"><span data-stu-id="5ac47-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="5ac47-105">Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon.</span><span class="sxs-lookup"><span data-stu-id="5ac47-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="5ac47-106">Op een later tijdstip u een gedeeld postvak weer converteren naar een (privé)postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5ac47-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="5ac47-107">**Hier zijn een aantal echt belangrijke dingen die je moet weten:**</span><span class="sxs-lookup"><span data-stu-id="5ac47-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="5ac47-108">Het gebruikerspostvak dat u converteert, heeft een licentie nodig die eraan is toegewezen voordat u het converteert naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="5ac47-109">Anders wordt de optie om het postvak te converteren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5ac47-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="5ac47-110">Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren.</span><span class="sxs-lookup"><span data-stu-id="5ac47-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="5ac47-111">Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="5ac47-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="5ac47-p103">Gedeelde postvakken kunnen maximaal 50 GB aan gegevens bevatten zonder dat er een licentie aan is toegewezen. Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen. Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="5ac47-p104">Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="5ac47-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="5ac47-118">De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="5ac47-119">Het Exchange-beheercentrum gebruiken om een postvak om te zetten</span><span class="sxs-lookup"><span data-stu-id="5ac47-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="5ac47-120">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="5ac47-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="5ac47-121">Selecteer **Postvakken voor** \> **geadresseerden**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="5ac47-122">Selecteer het gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-122">Select the user mailbox.</span></span> <span data-ttu-id="5ac47-123">Selecteer Onder **Converteren naar gedeeld postvak**de optie **Converteren**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="5ac47-124">Als het postvak kleiner is dan 50 GB, kunt u de [licentie van de gebruiker](../manage/remove-licenses-from-users.md) verwijderen zodat u er niet meer voor hoeft te betalen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="5ac47-125">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="5ac47-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="5ac47-126">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="5ac47-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="5ac47-127">Als u het postvak van een werknemer converteert die uw organisatie verlaat, moet u aanvullende stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="5ac47-128">Zie [Een voormalig werknemer verwijderen uit Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="5ac47-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="5ac47-129">Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak](create-a-shared-mailbox.md)maken voor alles wat u moet weten over gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="5ac47-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="5ac47-130">Het Microsoft 365-beheercentrum gebruiken om een postvak te converteren</span><span class="sxs-lookup"><span data-stu-id="5ac47-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5ac47-131">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5ac47-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="5ac47-132">Selecteer de naam van de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="5ac47-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="5ac47-133">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac47-134">Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="5ac47-135">Als het wachtwoord echter niet wordt gereset, **blijven de oorspronkelijke gebruikersnaam en het wachtwoord werken** nadat de conversie van het postvak is voltooid.</span><span class="sxs-lookup"><span data-stu-id="5ac47-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="5ac47-136">Selecteer op het tabblad **E-mail** onder **Meer acties**de optie Converteren naar **gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5ac47-137">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5ac47-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="5ac47-138">Selecteer de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="5ac47-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="5ac47-139">Vouw in het rechterdeelvenster **e-mailinstellingen**uit .</span><span class="sxs-lookup"><span data-stu-id="5ac47-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="5ac47-140">Selecteer Naast **Meer instellingen**de optie Converteren naar **gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5ac47-141">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5ac47-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="5ac47-142">Selecteer de gebruiker wiens postvak u wilt converteren.</span><span class="sxs-lookup"><span data-stu-id="5ac47-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="5ac47-143">Vouw in het rechterdeelvenster **e-mailinstellingen**uit .</span><span class="sxs-lookup"><span data-stu-id="5ac47-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="5ac47-144">Selecteer Naast **Meer instellingen**de optie Converteren naar **gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="5ac47-145">Als het postvak kleiner is dan 50 GB, u [de licentie van de gebruiker verwijderen](../manage/remove-licenses-from-users.md)en stoppen met betalen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="5ac47-146">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="5ac47-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="5ac47-147">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="5ac47-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="5ac47-148">Als u het postvak van een werknemer converteert die uw organisatie verlaat, moet u aanvullende stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="5ac47-149">Zie [Een voormalig werknemer verwijderen uit Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="5ac47-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="5ac47-150">Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak](create-a-shared-mailbox.md)maken voor alles wat u moet weten over gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="5ac47-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="5ac47-151">Het postvak van een verwijderde gebruiker converteren</span><span class="sxs-lookup"><span data-stu-id="5ac47-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="5ac47-p111">Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:</span><span class="sxs-lookup"><span data-stu-id="5ac47-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="5ac47-154">[Herstel het account van de gebruiker](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="5ac47-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="5ac47-155">Zorg dat er een Office 365-licentie aan het account is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="5ac47-156">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="5ac47-157">Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5ac47-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="5ac47-158">Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="5ac47-159">Nadat dat is gebeurd, u de licentie uit het postvak van de gebruiker verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="5ac47-160">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="5ac47-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="5ac47-161">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="5ac47-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="5ac47-162">Voeg leden toe aan het gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="5ac47-163">Een gedeeld postvak terugconverteren naar het (privé)postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="5ac47-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="5ac47-164">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="5ac47-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="5ac47-165">Selecteer **Gedeelde** **geadresseerden** \> .</span><span class="sxs-lookup"><span data-stu-id="5ac47-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="5ac47-166">Selecteer het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-166">Select the shared mailbox.</span></span> <span data-ttu-id="5ac47-167">Selecteer Onder **Converteren naar regulier postvak**de optie **Converteren**.</span><span class="sxs-lookup"><span data-stu-id="5ac47-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="5ac47-168">Ga terug naar het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5ac47-168">Go back to the admin center.</span></span> <span data-ttu-id="5ac47-169">Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5ac47-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="5ac47-170">Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="5ac47-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="5ac47-p115">Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.</span><span class="sxs-lookup"><span data-stu-id="5ac47-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="5ac47-173">Het postvak van een gebruiker converteren in een hybride omgeving</span><span class="sxs-lookup"><span data-stu-id="5ac47-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="5ac47-174">Als dit gedeelde postvak zich in een hybride omgeving bevindt, raden we u **ten zeerste aan** (bijna nodig" te zijn om het gebruikerspostvak weer on-premises te verplaatsen naar on-premises, het gebruikerspostvak om te zetten naar een gedeeld postvak en vervolgens het gedeelde postvak terug te verplaatsen naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="5ac47-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="5ac47-175">Dit is waarom: als u het postvak in de cloud converteert, kan deze worden geconverteerd, maar on-premises denkt nog steeds dat het postvak het gebruikerspostvak is, omdat de nieuwe werkelijkheid niet wordt gesynchroniseerd met on-premises.</span><span class="sxs-lookup"><span data-stu-id="5ac47-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="5ac47-176">Meestal is dit geen probleem, maar er zijn enkele scenario's waarin de on-premises kenmerken (die denken dat het postvak het gebruikerspostvak is) de nieuwe cloudversies van die kenmerken kunnen overschrijven en als gevolg hiervan kan het postvak worden geconverteerd.</span><span class="sxs-lookup"><span data-stu-id="5ac47-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="5ac47-177">Dit is een probleem omdat gebruikerspostvakken licenties vereisen **of ze zacht verwijderd zijn na 30 dagen**!</span><span class="sxs-lookup"><span data-stu-id="5ac47-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="5ac47-178">We hebben de meeste redenen waarom dit gebeurt aangepakt, maar het kan nog steeds gebeuren, hoewel zelden.</span><span class="sxs-lookup"><span data-stu-id="5ac47-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="5ac47-179">Het is het beste om veilig te zijn en de brievenbus terug te verplaatsen naar on-premises.</span><span class="sxs-lookup"><span data-stu-id="5ac47-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac47-180">Als u deel uitmaakt van Organisatiebeheer of Ontvangerbeheer, u de shell Exchange Management gebruiken om een gebruikerspostvak on-premises in een gedeeld postvak te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5ac47-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="5ac47-181">Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="5ac47-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="5ac47-182">Bekijk de tijdelijke oplossing in deze ondersteuningsoplossing voor gevallen waarin [gedeelde postvakken onverwacht worden geconverteerd naar gebruikerspostvakken](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="5ac47-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5ac47-183">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5ac47-183">Related articles</span></span>

[<span data-ttu-id="5ac47-184">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="5ac47-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="5ac47-185">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="5ac47-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="5ac47-186">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="5ac47-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="5ac47-187">Een licentie verwijderen uit een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="5ac47-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="5ac47-188">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="5ac47-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
