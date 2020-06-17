---
title: Een gedeeld postvak maken
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Maak gedeelde postvakken zodat meerdere personen binnen uw bedrijf de verantwoordelijkheid kunnen delen voor het lezen en beantwoorden van e-mails die naar hetzelfde adres zijn gestuurd.
ms.openlocfilehash: 331f5f320f9b57ee503734f57ed8d804e9ad04e3
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432287"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="c9e89-103">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="c9e89-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="c9e89-104">Als uw organisatie gebruikmaakt van een hybride Exchange-omgeving, moet u het on-premises Exchange-beheercentrum (EAC) gebruiken om gedeelde postvakken te maken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="c9e89-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="c9e89-105">[Gedeelde postvakken maken in het Exchange-beheercentrum](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="c9e89-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="c9e89-106">Zie [Groepen vergelijken](../create-groups/compare-groups.md) als u niet zeker weet of u een gedeeld postvak of een Microsoft 365-groep voor Outlook moet maken.</span><span class="sxs-lookup"><span data-stu-id="c9e89-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="c9e89-107">Momenteel is het niet mogelijk een gedeeld postvak te migreren naar een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="c9e89-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="c9e89-108">Als dit iets is dat u zou willen, laat ons dat dan weten door [hier te stemmen](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="c9e89-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="c9e89-109">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9e89-109">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com.</span></span> <span data-ttu-id="c9e89-110">When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span><span class="sxs-lookup"><span data-stu-id="c9e89-110">When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="c9e89-111">Gedeelde postvakken hebben een gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="c9e89-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="c9e89-112">Veel kleine bedrijven vinden de gedeelde agenda handig omdat iedereen hier zijn afspraken kan invoeren.</span><span class="sxs-lookup"><span data-stu-id="c9e89-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="c9e89-113">Als u bijvoorbeeld drie mensen hebt die klantbezoeken doen, kunnen zij allemaal de gedeelde agenda gebruiken om hun afspraken in te voeren.</span><span class="sxs-lookup"><span data-stu-id="c9e89-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="c9e89-114">Dit is een handige manier om iedereen op de hoogte te houden van waar mensen zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="c9e89-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="c9e89-115">Lees eerst [Meer informatie over gedeelde postvakken](about-shared-mailboxes.md) voordat u een gedeeld postvak maakt.</span><span class="sxs-lookup"><span data-stu-id="c9e89-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="c9e89-116">Een gedeeld postvak maken en leden toevoegen</span><span class="sxs-lookup"><span data-stu-id="c9e89-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="c9e89-117">Meld u aan met een globaal beheerdersaccount of Exchange-beheerder-account.</span><span class="sxs-lookup"><span data-stu-id="c9e89-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="c9e89-118">Als het u het bericht ‘**U bent niet gemachtigd om deze pagina weer te geven of deze handeling uit te voeren**’ krijgt, dan bent u geen beheerder.</span><span class="sxs-lookup"><span data-stu-id="c9e89-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="c9e89-119">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.</span><span class="sxs-lookup"><span data-stu-id="c9e89-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="c9e89-120">Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041) naar de pagina **Groepen** \> **Gedeelde postvakken**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="c9e89-121">Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627) naar de pagina **Groepen** \> **Gedeelde postvakken**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="c9e89-122">Selecteer op de pagina **Gedeelde postvakken**, **+Een postvak toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="c9e89-123">Voer een naam in voor het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="c9e89-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="c9e89-124">De wizard kiest vervolgens het e-mailadres, dat u echter kunt bewerken.</span><span class="sxs-lookup"><span data-stu-id="c9e89-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Geef het gedeelde Postvak een naam.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="c9e89-126">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-126">Select **Add**.</span></span> <span data-ttu-id="c9e89-127">Het kan enkele minuten duren voordat u leden kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c9e89-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="c9e89-128">Selecteer onder **Volgende stappen**, **Leden toevoegen aan dit postvak**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="c9e89-129">Leden zijn degenen die de inkomende e-mail voor dit gedeelde postvak en de uitgaande antwoorden kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="c9e89-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Leden toevoegen, selecteren](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="c9e89-131">Selecteer de knop **+Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-131">Select the **+Add members** button.</span></span> <span data-ttu-id="c9e89-132">Schakel het selectievakje in naast de personen die dit gedeelde postvak mogen gebruiken en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Leden toevoegen aan het gedeeld postvak](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="c9e89-134">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-134">Select **Close**.</span></span>

<span data-ttu-id="c9e89-135">U hebt een gedeeld postvak en een gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="c9e89-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="c9e89-136">Ga nu naar de volgende stap: Aanmelding voor het account van het gedeelde postvak blokkeren.</span><span class="sxs-lookup"><span data-stu-id="c9e89-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="c9e89-137">Aanmelding voor het account van het gedeelde postvak blokkeren</span><span class="sxs-lookup"><span data-stu-id="c9e89-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="c9e89-138">Elk gedeeld postvak heeft een bijbehorend gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="c9e89-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="c9e89-139">Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte?</span><span class="sxs-lookup"><span data-stu-id="c9e89-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="c9e89-140">Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend).</span><span class="sxs-lookup"><span data-stu-id="c9e89-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="c9e89-141">Het is niet de bedoeling het account te gebruiken om u aan te melden in het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="c9e89-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="c9e89-142">En als de beheerder het wachtwoord van het gebruikersaccount van het gedeelde postvak opnieuw instelt?</span><span class="sxs-lookup"><span data-stu-id="c9e89-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="c9e89-143">Of wat als een hacker zich toegang verschaft tot de referenties van het account van het gedeelde postvak?</span><span class="sxs-lookup"><span data-stu-id="c9e89-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="c9e89-144">Hiermee zou het gebruikersaccount zich aan kunnen melden bij het gedeelde postvak en e-mail verzenden.</span><span class="sxs-lookup"><span data-stu-id="c9e89-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="c9e89-145">Om dit te voorkomen, moet u de aanmelding voor het account die behoort bij het gedeelde postvak blokkeren.</span><span class="sxs-lookup"><span data-stu-id="c9e89-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9e89-146">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="c9e89-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c9e89-147">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander het filter bijvoorbeeld in **Gebruikers zonder licentie**).</span><span class="sxs-lookup"><span data-stu-id="c9e89-147">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="c9e89-148">Selecteer de gebruiker om het eigenschappenvenster te openen en selecteer dan het pictogram **Deze gebruiker blokkeren** ![Schermafbeelding van het pictogram Deze gebruiker blokkeren](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="c9e89-148">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="c9e89-149">**Opmerking**: Als het account al wordt geblokkeerd, wordt er bovenaan **Geblokkeerd** weergegeven en staat er in het pictogram **De blokkering van deze gebruiker opheffen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-149">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="c9e89-150">Selecteer in het venster **Deze gebruiker blokkeren?**, **Voorkomen dat de gebruiker zich aanmeldt** en selecteer dan **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-150">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c9e89-151">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="c9e89-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c9e89-152">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.</span><span class="sxs-lookup"><span data-stu-id="c9e89-152">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="c9e89-153">Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-153">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="c9e89-154">**Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-154">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="c9e89-155">Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-155">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9e89-156">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="c9e89-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c9e89-157">Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.</span><span class="sxs-lookup"><span data-stu-id="c9e89-157">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="c9e89-158">Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-158">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="c9e89-159">**Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-159">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="c9e89-160">Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c9e89-160">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="c9e89-161">Zie [Gebruikersaccounts blokkeren met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell) voor meer informatie over het blokkeren van accounts met Azure AD PowerShell (met inbegrip van meerdere accounts tegelijk).</span><span class="sxs-lookup"><span data-stu-id="c9e89-161">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="c9e89-162">Het gedeelde postvak toevoegen aan Outlook</span><span class="sxs-lookup"><span data-stu-id="c9e89-162">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="c9e89-163">Als u automatisch toewijzen voor uw bedrijf hebt ingeschakeld (iets wat de meeste mensen doen), wordt het gedeelde postvak automatisch weergegeven in de Outlook-app van uw gebruikers nadat ze Outlook hebben gesloten en opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="c9e89-163">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="c9e89-164">Automatisch toewijzen wordt ingesteld in het postvak van de gebruiker, niet het gedeelde postvak.  </span><span class="sxs-lookup"><span data-stu-id="c9e89-164">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="c9e89-165">Dit betekent dat als u probeert een beveiligingsgroep te gebruiken om te beheren wie toegang heeft tot het gedeelde postvak, automatisch toewijzen niet werkt.</span><span class="sxs-lookup"><span data-stu-id="c9e89-165">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="c9e89-166">Als u dus gebruik wilt maken van automatisch toewijzen, moet u de machtigingen expliciet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="c9e89-166">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="c9e89-167">Standaard is automatisch toewijzen ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c9e89-167">Automapping is on by default.</span></span> <span data-ttu-id="c9e89-168">Zie [Automatisch toewijzen verwijderen van een gedeeld postvak](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox) voor informatie over het uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="c9e89-168">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="c9e89-169">Zie voor meer informatie over gedeelde postvakken maken in Outlook:</span><span class="sxs-lookup"><span data-stu-id="c9e89-169">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="c9e89-170"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Een gedeeld postvak openen en gebruiken in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="c9e89-170"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="c9e89-171"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a></span><span class="sxs-lookup"><span data-stu-id="c9e89-171"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="c9e89-172"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="c9e89-172"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="c9e89-173"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Een gedeelde map of gedeeld postvak openen in Outlook voor Mac</a></span><span class="sxs-lookup"><span data-stu-id="c9e89-173"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="c9e89-174"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Regels toevoegen aan een gedeeld postvak</a></span><span class="sxs-lookup"><span data-stu-id="c9e89-174"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="c9e89-175">Een gedeeld postvak gebruiken op een mobiel apparaat (telefoon of tablet)</span><span class="sxs-lookup"><span data-stu-id="c9e89-175">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="c9e89-176">U kunt op twee manieren toegang krijgen tot een gedeeld postvak op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="c9e89-176">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="c9e89-177">Voeg het gedeelde postvak toe aan de <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook voor iOS</a> of de <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">mobiele app voor Outlook voor Android</a>.</span><span class="sxs-lookup"><span data-stu-id="c9e89-177">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="c9e89-178">Zie <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a> voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c9e89-178">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="c9e89-179">Open uw browser, meld u aan en ga dan naar de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9e89-179">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="c9e89-180">Vanuit de webversie van Outlook hebt u toegang tot het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="c9e89-180">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="c9e89-181">Zie <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a> voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c9e89-181">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="c9e89-182">De gedeelde agenda gebruiken</span><span class="sxs-lookup"><span data-stu-id="c9e89-182">Use the shared calendar</span></span>

<span data-ttu-id="c9e89-183">Wanneer u een gedeeld postvak maakt, maakt u automatisch een gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="c9e89-183">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="c9e89-184">We gebruiken liever de agenda van het gedeelde Postvak dan een SharePoint-agenda voor het bijhouden van afspraken en waar personen zijn.</span><span class="sxs-lookup"><span data-stu-id="c9e89-184">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="c9e89-185">Een gedeelde agenda is geïntegreerd met Outlook en is veel eenvoudiger te gebruiken dan een SharePoint-agenda.</span><span class="sxs-lookup"><span data-stu-id="c9e89-185">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="c9e89-186">In de Outlook-app gaat u naar de agendaweergave en selecteert u het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="c9e89-186">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="c9e89-187">Wanneer u afspraken invoert, zijn deze zichtbaar voor alle gebruikers die lid zijn van het gedeelde postvak. </span><span class="sxs-lookup"><span data-stu-id="c9e89-187">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="c9e89-188">Een lid van het gedeelde postvak kan afspraken in de agenda aanmaken, weergeven en beheren, net zoals ze dat doen voor persoonlijke afspraken.</span><span class="sxs-lookup"><span data-stu-id="c9e89-188">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="c9e89-189">Iedereen die lid is van het gedeelde postvak kan de wijzigingen zien in de gedeelde agenda.</span><span class="sxs-lookup"><span data-stu-id="c9e89-189">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c9e89-190">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c9e89-190">Related articles</span></span>

[<span data-ttu-id="c9e89-191">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="c9e89-191">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c9e89-192">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="c9e89-192">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="c9e89-193">Een gebruikerspostvak converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="c9e89-193">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="c9e89-194">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="c9e89-194">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="c9e89-195">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="c9e89-195">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





