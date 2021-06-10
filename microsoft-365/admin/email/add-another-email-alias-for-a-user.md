---
title: Een ander e-mailalias toevoegen voor een gebruiker
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
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Lees hoe u meerdere e-mailadressen, een e-mailalias, kunt toevoegen aan uw Microsoft 365 voor zakelijke account. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572103"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="8f7e2-103">Een ander e-mailalias toevoegen voor een gebruiker</span><span class="sxs-lookup"><span data-stu-id="8f7e2-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="8f7e2-104">Dit artikel is bedoeld Microsoft 365 beheerders die een zakelijk abonnement hebben.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="8f7e2-105">Het is niet bedoeld voor thuisgebruikers.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-105">It's not for home users.</span></span>
  
<span data-ttu-id="8f7e2-106">Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen zijn account werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="8f7e2-107">Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="8f7e2-108">Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan Microsoft 365 account voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="8f7e2-109">Deze extra adressen worden aliassen genoemd.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="8f7e2-110">Stel dat Jenna het e-mailadres jenna@contosoco.com, maar ze wil ook e-mail ontvangen bij jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="8f7e2-111">U kunt aliassen voor haar maken, zodat beide e-mailadressen naar het Postvak IN van Jenna gaan.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="8f7e2-p104">U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="8f7e2-114">Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres wordt verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="8f7e2-115">Zie Een gedeeld [postvak maken voor meer informatie.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="8f7e2-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="8f7e2-116">E-mailaliassen toevoegen aan een gebruiker</span><span class="sxs-lookup"><span data-stu-id="8f7e2-116">Add email aliases to a user</span></span>

<span data-ttu-id="8f7e2-117">Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="8f7e2-118">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="8f7e2-119">Selecteer op **de pagina** Actieve gebruikers de gebruiker > Gebruikersnaam en e-mail **beheren.**</span><span class="sxs-lookup"><span data-stu-id="8f7e2-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="8f7e2-120">U ziet deze optie niet als de persoon geen licentie aan hem of haar heeft toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="8f7e2-121">Selecteer **+ Een alias toevoegen** en voer een nieuwe alias voor de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="8f7e2-122">Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8f7e2-123">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8f7e2-124">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8f7e2-125">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="8f7e2-126">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8f7e2-127">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8f7e2-128">Zie Een domein toevoegen aan [Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="8f7e2-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="8f7e2-129">Wanneer u klaar bent, kiest u **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8f7e2-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="8f7e2-130">Wacht 24 uur totdat de nieuwe aliassen in de hele Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="8f7e2-131">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8f7e2-132">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8f7e2-133">**Wanneer de gebruiker antwoordt, is *het Van-adres* afhankelijk van Outlook client. Outlook op internet gebruikt u de alias waarmee de e-mail is ontvangen (we noemen dit het ping-pong-principe). Outlook bureaublad gebruikt haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="8f7e2-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="8f7e2-134">Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8f7e2-135">Wanneer Eliza het bericht beantwoordt met Outlook bureaublad, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet als Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="8f7e2-136">Hebt u 'A parameter cannot be found that matches parameter name EmailAddresses' gekregen?</span><span class="sxs-lookup"><span data-stu-id="8f7e2-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="8f7e2-137">Als u het foutbericht ' Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam EmailAddresses'** wordt weergegeven, betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8f7e2-138">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8f7e2-139">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8f7e2-140">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="8f7e2-141">Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?</span><span class="sxs-lookup"><span data-stu-id="8f7e2-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="8f7e2-142">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="8f7e2-143">Eenvoudig e-mail verzenden vanaf het proxyadres</span><span class="sxs-lookup"><span data-stu-id="8f7e2-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="8f7e2-144">In april 2021 wordt een nieuwe functie uitgerold waarmee gebruikers eenvoudig vanuit hun aliassen kunnen verzenden wanneer ze Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="8f7e2-145">Wanneer de functie wordt uitrolt naar een tenancy waarbij de tenantbeheerder de cmdlet gebruikt, krijgen gebruikers binnen de huurperiode toegang tot een lijst met selectievakjes waarin elke vermelding overeenkomt met een alias in de Outlook `Set-OrganizationConfig -SendFromAliasEnabled $true` instellingen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="8f7e2-146">Als u een alias selecteert, wordt deze weergegeven in de vervolgkeuzekeuze in het formulier Opstellen.</span><span class="sxs-lookup"><span data-stu-id="8f7e2-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="8f7e2-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8f7e2-147">Related content</span></span>

<span data-ttu-id="8f7e2-148">[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8f7e2-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="8f7e2-149">[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8f7e2-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="8f7e2-150">[Doorsturen van e‑mail configureren in Microsoft 365](configure-email-forwarding.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8f7e2-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
