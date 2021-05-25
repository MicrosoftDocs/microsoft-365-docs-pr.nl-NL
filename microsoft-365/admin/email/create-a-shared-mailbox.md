---
title: Een gedeeld postvak maken
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Maak gedeelde postvakken zodat meerdere personen binnen uw bedrijf de verantwoordelijkheid kunnen delen voor het lezen en beantwoorden van e-mails die naar hetzelfde adres zijn gestuurd.
ms.openlocfilehash: e628d72482ed7ff32a204eaf9503fdd9a271844a
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635496"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="fc77f-103">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="fc77f-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="fc77f-104">Als uw organisatie gebruikmaakt van een hybride Exchange-omgeving, moet u het on-premises Exchange-beheercentrum (EAC) gebruiken om gedeelde postvakken te maken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="fc77f-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="fc77f-105">[Gedeelde postvakken maken in het Exchange-beheercentrum](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="fc77f-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="fc77f-106">Zie [Groepen vergelijken](../create-groups/compare-groups.md) als u niet zeker weet of u een gedeeld postvak of een Microsoft 365-groep voor Outlook moet maken.</span><span class="sxs-lookup"><span data-stu-id="fc77f-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="fc77f-107">Momenteel is het niet mogelijk een gedeeld postvak te migreren naar een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="fc77f-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="fc77f-108">Als dit iets is dat u zou willen, laat ons dat dan weten door [hier te stemmen](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="fc77f-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="fc77f-p103">Het is eenvoudig om gedeelde postvakken te maken zodat een groep e-mail kan controleren en verzenden vanaf een gemeenschappelijk e-mailadres zoals info@contoso.com. Wanneer een persoon in de groep een bericht beantwoordt dat naar het gedeelde postvak is verzonden, lijkt het e-mailbericht afkomstig te zijn van het gedeelde postvak, niet van de afzonderlijke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fc77f-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="fc77f-p104">In gedeelde postvakken is een gedeelde agenda opgenomen. Veel kleine bedrijven vinden de gedeelde agenda handig omdat iedereen hier zijn afspraken kan invoeren. Als u bijvoorbeeld drie mensen hebt die klantbezoeken doen, kunnen zij allemaal de gedeelde agenda gebruiken om hun afspraken in te voeren. Dit is een handige manier om iedereen op de hoogte te houden van waar mensen zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="fc77f-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="fc77f-115">Lees eerst [Meer informatie over gedeelde postvakken](about-shared-mailboxes.md) voordat u een gedeeld postvak maakt.</span><span class="sxs-lookup"><span data-stu-id="fc77f-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="fc77f-116">Een gedeeld postvak maken en leden toevoegen</span><span class="sxs-lookup"><span data-stu-id="fc77f-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="fc77f-117">Meld u aan met een globaal beheerdersaccount of Exchange-beheerder-account.</span><span class="sxs-lookup"><span data-stu-id="fc77f-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="fc77f-118">Als het u het bericht ‘**U bent niet gemachtigd om deze pagina weer te geven of deze handeling uit te voeren**’ krijgt, dan bent u geen beheerder.</span><span class="sxs-lookup"><span data-stu-id="fc77f-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="fc77f-119">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.</span><span class="sxs-lookup"><span data-stu-id="fc77f-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="fc77f-120">Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041) naar de pagina **Groepen** \> **Gedeelde postvakken**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="fc77f-121">Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627) naar de pagina **Groepen** \> **Gedeelde postvakken**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="fc77f-122">Selecteer op de pagina **Gedeelde postvakken**, **+Een postvak toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="fc77f-123">Voer een naam in voor het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="fc77f-124">De wizard kiest vervolgens het e-mailadres, dat u echter kunt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc77f-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Geef het gedeelde Postvak een naam.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="fc77f-126">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-126">Select **Add**.</span></span> <span data-ttu-id="fc77f-127">Het kan enkele minuten duren voordat u leden kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="fc77f-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="fc77f-128">Selecteer onder **Volgende stappen**, **Leden toevoegen aan dit postvak**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="fc77f-129">Leden zijn degenen die de inkomende e-mail voor dit gedeelde postvak en de uitgaande antwoorden kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="fc77f-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Leden toevoegen, selecteren](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="fc77f-131">Selecteer de knop **+Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-131">Select the **+Add members** button.</span></span> <span data-ttu-id="fc77f-132">Schakel het selectievakje in naast de personen die dit gedeelde postvak mogen gebruiken en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Leden toevoegen aan het gedeeld postvak](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="fc77f-134">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-134">Select **Close**.</span></span>

<span data-ttu-id="fc77f-135">U hebt een gedeeld postvak en een gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="fc77f-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="fc77f-136">Ga nu naar de volgende stap: Aanmelding voor het account van het gedeelde postvak blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fc77f-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="fc77f-137">Welke machtiging moet je gebruiken?</span><span class="sxs-lookup"><span data-stu-id="fc77f-137">Which permissions should you use?</span></span>

<span data-ttu-id="fc77f-138">Je kunt de volgende machtigingen gebruiken met een gedeeld postvak:</span><span class="sxs-lookup"><span data-stu-id="fc77f-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="fc77f-139">**Volledige toegang**: Met de machtiging Volledige toegang kan een gebruiker zich aanmelden bij het gedeelde postvak en optreden als de eigenaar van dat postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="fc77f-140">Nadat een gebruiker het gedeelde postvak heeft geopend, kan hij agenda-items maken, taken en contactpersonen voor de agenda maken en e-mailberichten lezen, weergeven, verwijderen en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fc77f-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="fc77f-141">Gebruikers met de machtiging Volledige toegang kunnen echter geen e-mail verzenden vanuit het gedeelde postvak tenzij ze ook de machtiging Verzenden als of Verzenden namens hebben.</span><span class="sxs-lookup"><span data-stu-id="fc77f-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="fc77f-142">**Verzenden als**: Met de machtiging Verzenden als kan een gebruiker e-mailberichten vanuit het gedeelde postvak onder een andere naam verzenden.</span><span class="sxs-lookup"><span data-stu-id="fc77f-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="fc77f-143">Als bijvoorbeeld Flip Schoonen zich aanmeldt bij het gedeelde postvak Afdeling Marketing en een e-mailbericht verzendt, ziet dit eruit alsof de Afdeling Marketing het e-mailbericht heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="fc77f-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="fc77f-144">**Verzenden namens**: Met de machtiging Verzenden namens kan een gebruiker e-mailberichten verzenden namens het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="fc77f-145">Als bijvoorbeeld Ger zich aanmeldt bij het gedeelde postvak Ontvangstgebouw 32 en een e-mailbericht verzendt, ziet dit eruit alsof het e-mailbericht is verzonden door 'Ger namens Ontvangstgebouw 32'.</span><span class="sxs-lookup"><span data-stu-id="fc77f-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="fc77f-146">Je kunt het Exchange-beheercentrum niet gebruiken om de machtiging Verzenden namens te verlenen. Daarvoor moet je de **Set-Mailbox**-cmdlet met de parameter _GrantSendonBehalf_ gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fc77f-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="fc77f-147">Het Exchange-beheercentrum gebruiken om het delegeren voor het gedeelde postvak te bewerken</span><span class="sxs-lookup"><span data-stu-id="fc77f-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="fc77f-148">Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Gedeeld**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="fc77f-149">Selecteer het gedeelde postvak en vervolgens **Bewerken** ![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="fc77f-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="fc77f-150">Klik op **Postvakdelegering**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="fc77f-151">Als je de machtiging Volledige toegang of Verzenden als wilt instellen of verwijderen, klik je op **Toevoegen** ![Pictogram Toevoegen](../../media/ITPro-EAC-AddIcon.png) of **Verwijderen** ![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif) en selecteer je de gewenste gebruikers.</span><span class="sxs-lookup"><span data-stu-id="fc77f-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fc77f-p115">Met de machtiging Volledige toegang kan een gebruiker het postvak openen en daarin items maken en wijzigen. Met de machtiging Verzenden als kan ieder andere gebruiker dan de eigenaar van het postvak e-mail vanuit dit gedeelde postvak verzenden. Beide machtigingen zijn vereist om het gedeelde postvak goed te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fc77f-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="fc77f-155">Selecteer **Opslaan** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="fc77f-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="fc77f-156">Aanmelding voor het account van het gedeelde postvak blokkeren</span><span class="sxs-lookup"><span data-stu-id="fc77f-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="fc77f-157">Elk gedeeld postvak heeft een bijbehorend gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="fc77f-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="fc77f-158">Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte?</span><span class="sxs-lookup"><span data-stu-id="fc77f-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="fc77f-159">Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend).</span><span class="sxs-lookup"><span data-stu-id="fc77f-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="fc77f-160">Het is niet de bedoeling het account te gebruiken om u aan te melden in het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="fc77f-161">En als de beheerder het wachtwoord van het gebruikersaccount van het gedeelde postvak opnieuw instelt?</span><span class="sxs-lookup"><span data-stu-id="fc77f-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="fc77f-162">Of wat als een hacker zich toegang verschaft tot de referenties van het account van het gedeelde postvak?</span><span class="sxs-lookup"><span data-stu-id="fc77f-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="fc77f-163">Hiermee zou het gebruikersaccount zich aan kunnen melden bij het gedeelde postvak en e-mail verzenden.</span><span class="sxs-lookup"><span data-stu-id="fc77f-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="fc77f-164">Om dit te voorkomen, moet u de aanmelding voor het account die behoort bij het gedeelde postvak blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fc77f-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fc77f-165">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="fc77f-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="fc77f-166">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander het filter bijvoorbeeld in **Gebruikers zonder licentie**).</span><span class="sxs-lookup"><span data-stu-id="fc77f-166">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="fc77f-167">Selecteer de gebruiker om het eigenschappenvenster te openen en selecteer dan het pictogram **Deze gebruiker blokkeren** ![Schermafbeelding van het pictogram Deze gebruiker blokkeren](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="fc77f-167">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="fc77f-168">**Opmerking**: Als het account al wordt geblokkeerd, wordt er bovenaan **Geblokkeerd** weergegeven en staat er in het pictogram **De blokkering van deze gebruiker opheffen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-168">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="fc77f-169">Selecteer in het venster **Deze gebruiker blokkeren?**, **Voorkomen dat de gebruiker zich aanmeldt** en selecteer dan **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-169">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fc77f-170">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="fc77f-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="fc77f-171">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.</span><span class="sxs-lookup"><span data-stu-id="fc77f-171">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="fc77f-172">Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-172">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="fc77f-173">**Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-173">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="fc77f-174">Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-174">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fc77f-175">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="fc77f-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="fc77f-176">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.</span><span class="sxs-lookup"><span data-stu-id="fc77f-176">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="fc77f-177">Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-177">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="fc77f-178">**Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-178">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="fc77f-179">Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="fc77f-179">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="fc77f-180">Zie [Gebruikersaccounts blokkeren met Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md) voor meer informatie over het blokkeren van accounts met Azure AD PowerShell (met inbegrip van meerdere accounts tegelijk).</span><span class="sxs-lookup"><span data-stu-id="fc77f-180">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="fc77f-181">Het gedeelde postvak toevoegen aan Outlook</span><span class="sxs-lookup"><span data-stu-id="fc77f-181">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="fc77f-182">Als u automatisch toewijzen voor uw bedrijf hebt ingeschakeld (iets wat de meeste mensen doen), wordt het gedeelde postvak automatisch weergegeven in de Outlook-app van uw gebruikers nadat ze Outlook hebben gesloten en opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="fc77f-182">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="fc77f-183">Automatisch toewijzen wordt ingesteld in het postvak van de gebruiker, niet het gedeelde postvak.  </span><span class="sxs-lookup"><span data-stu-id="fc77f-183">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="fc77f-184">Dit betekent dat als u probeert een beveiligingsgroep te gebruiken om te beheren wie toegang heeft tot het gedeelde postvak, automatisch toewijzen niet werkt.</span><span class="sxs-lookup"><span data-stu-id="fc77f-184">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="fc77f-185">Als u dus gebruik wilt maken van automatisch toewijzen, moet u de machtigingen expliciet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="fc77f-185">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="fc77f-186">Standaard is automatisch toewijzen ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc77f-186">Automapping is on by default.</span></span> <span data-ttu-id="fc77f-187">Zie [Automatisch toewijzen verwijderen van een gedeeld postvak](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox) voor informatie over het uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="fc77f-187">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="fc77f-188">Zie voor meer informatie over gedeelde postvakken maken in Outlook:</span><span class="sxs-lookup"><span data-stu-id="fc77f-188">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="fc77f-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Een gedeeld postvak openen en gebruiken in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="fc77f-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="fc77f-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a></span><span class="sxs-lookup"><span data-stu-id="fc77f-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="fc77f-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="fc77f-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="fc77f-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Een gedeelde map of gedeeld postvak openen in Outlook voor Mac</a></span><span class="sxs-lookup"><span data-stu-id="fc77f-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="fc77f-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Regels toevoegen aan een gedeeld postvak</a></span><span class="sxs-lookup"><span data-stu-id="fc77f-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="fc77f-194">Een gedeeld postvak gebruiken op een mobiel apparaat (telefoon of tablet)</span><span class="sxs-lookup"><span data-stu-id="fc77f-194">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="fc77f-195">U kunt op twee manieren toegang krijgen tot een gedeeld postvak op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="fc77f-195">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="fc77f-196">Voeg het gedeelde postvak toe aan de <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook voor iOS</a> of de <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">mobiele app voor Outlook voor Android</a>.</span><span class="sxs-lookup"><span data-stu-id="fc77f-196">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="fc77f-197">Zie <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a> voor instructies.</span><span class="sxs-lookup"><span data-stu-id="fc77f-197">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="fc77f-198">Open uw browser, meld u aan en ga dan naar de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="fc77f-198">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="fc77f-199">Vanuit de webversie van Outlook hebt u toegang tot het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-199">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="fc77f-200">Zie <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a> voor instructies.</span><span class="sxs-lookup"><span data-stu-id="fc77f-200">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fc77f-201">Het gedeelde postvak kan alleen worden toegevoegd aan de app Outlook voor iOS of de mobiele Outlook voor Android-app.</span><span class="sxs-lookup"><span data-stu-id="fc77f-201">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="fc77f-202">De gedeelde agenda gebruiken</span><span class="sxs-lookup"><span data-stu-id="fc77f-202">Use the shared calendar</span></span>

<span data-ttu-id="fc77f-p120">We gebruiken liever de agenda van het gedeelde Postvak dan een SharePoint-agenda voor het bijhouden van afspraken en waar personen zijn. Een gedeelde agenda is geïntegreerd met Outlook, u ontvangt herinneringen en de gedeelde agenda is veel eenvoudiger te maken en te gebruiken dan een SharePoint-agenda.</span><span class="sxs-lookup"><span data-stu-id="fc77f-p120">When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="fc77f-206">In de Outlook-app gaat u naar de agendaweergave en selecteert u het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="fc77f-206">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="fc77f-207">Wanneer u afspraken invoert, zijn deze zichtbaar voor alle gebruikers die lid zijn van het gedeelde postvak. </span><span class="sxs-lookup"><span data-stu-id="fc77f-207">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="fc77f-208">Een lid van het gedeelde postvak kan afspraken in de agenda aanmaken, weergeven en beheren, net zoals ze dat doen voor persoonlijke afspraken.</span><span class="sxs-lookup"><span data-stu-id="fc77f-208">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="fc77f-209">Iedereen die lid is van het gedeelde postvak kan de wijzigingen zien in de gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="fc77f-209">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="fc77f-210">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="fc77f-210">Related content</span></span>

<span data-ttu-id="fc77f-211">[Info over gedeelde postvakken](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fc77f-211">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="fc77f-212">[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fc77f-212">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="fc77f-213">[Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fc77f-213">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="fc77f-214">[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fc77f-214">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="fc77f-215">[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fc77f-215">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>