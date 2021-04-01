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
description: 'Lees hoe u meerdere e-mailadressen, de zogenaamde e-mailalias, kunt toevoegen aan uw Microsoft 365 voor Bedrijven-account. '
ms.openlocfilehash: a44271cdbf52136e61702697a960cc3cbcd8119d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470999"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="db7b4-103">Een ander e-mailalias toevoegen voor een gebruiker</span><span class="sxs-lookup"><span data-stu-id="db7b4-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="db7b4-104">Dit artikel is bedoeld voor Microsoft 365-beheerders die een zakelijk abonnement hebben.</span><span class="sxs-lookup"><span data-stu-id="db7b4-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="db7b4-105">Het is niet bedoeld voor thuisgebruikers.</span><span class="sxs-lookup"><span data-stu-id="db7b4-105">It's not for home users.</span></span>
  
<span data-ttu-id="db7b4-106">Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen zijn account werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="db7b4-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="db7b4-107">Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="db7b4-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="db7b4-108">Ze kunnen ook meerdere e-mailadressen hebben die zijn gekoppeld aan hun Microsoft 365 voor Bedrijven-account.</span><span class="sxs-lookup"><span data-stu-id="db7b4-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="db7b4-109">Deze extra adressen worden aliassen genoemd.</span><span class="sxs-lookup"><span data-stu-id="db7b4-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="db7b4-110">Stel dat Jenna het e-mailadres jenna@contosoco.com, maar ze wil ook e-mail ontvangen bij jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam.</span><span class="sxs-lookup"><span data-stu-id="db7b4-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="db7b4-111">U kunt aliassen voor haar maken, zodat beide e-mailadressen naar het Postvak IN van Jenna gaan.</span><span class="sxs-lookup"><span data-stu-id="db7b4-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="db7b4-112">U kunt maximaal 400 aliassen maken voor een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db7b4-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="db7b4-113">Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="db7b4-114">Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres wordt verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="db7b4-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="db7b4-115">Zie Een gedeeld [postvak maken voor meer informatie.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="db7b4-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="db7b4-116">E-mailaliassen toevoegen aan een gebruiker</span><span class="sxs-lookup"><span data-stu-id="db7b4-116">Add email aliases to a user</span></span>
<span data-ttu-id="db7b4-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="db7b4-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="db7b4-118">Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="db7b4-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="db7b4-119">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db7b4-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="db7b4-120">Selecteer op **de pagina** Actieve gebruikers de gebruiker > **E-mailalias beheren.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="db7b4-121">U ziet deze optie niet als de persoon geen licentie aan hem of haar heeft toegewezen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="db7b4-122">Selecteer **+ Een alias toevoegen** en voer een nieuwe alias voor de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="db7b4-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="db7b4-123">Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="db7b4-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="db7b4-124">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="db7b4-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="db7b4-125">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db7b4-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="db7b4-126">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="db7b4-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="db7b4-127">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="db7b4-128">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="db7b4-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="db7b4-129">Zie Een domein toevoegen aan [Microsoft 365](../setup/add-domain.md)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="db7b4-130">Wanneer u klaar bent, kiest u **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="db7b4-131">Wacht 24 uur totdat de nieuwe aliassen worden ingevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db7b4-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="db7b4-132">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="db7b4-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="db7b4-133">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.</span><span class="sxs-lookup"><span data-stu-id="db7b4-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="db7b4-134">**Wanneer de gebruiker antwoordt, is *het Van-adres*  haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-134">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="db7b4-135">Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db7b4-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="db7b4-136">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="db7b4-136">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="db7b4-137">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db7b4-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="db7b4-138">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="db7b4-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="db7b4-139">Selecteer naast **Gebruikersnaam /E-mailalias** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="db7b4-140">Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="db7b4-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="db7b4-141">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="db7b4-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="db7b4-142">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db7b4-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="db7b4-143">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="db7b4-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="db7b4-144">Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="db7b4-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="db7b4-145">Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="db7b4-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="db7b4-146">Selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="db7b4-147">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="db7b4-148">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="db7b4-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="db7b4-149">Zie Een domein toevoegen aan [Microsoft 365](../setup/add-domain.md)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="db7b4-150">Wanneer u klaar bent, selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="db7b4-151">Wacht 24 uur totdat de nieuwe aliassen worden ingevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db7b4-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="db7b4-152">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="db7b4-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="db7b4-153">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.</span><span class="sxs-lookup"><span data-stu-id="db7b4-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="db7b4-154">**Wanneer de gebruiker antwoordt, is *het Van-adres*  haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-154">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="db7b4-155">Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db7b4-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="db7b4-156">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="db7b4-156">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="db7b4-157">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db7b4-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="db7b4-158">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="db7b4-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="db7b4-159">Selecteer naast **Gebruikersnaam /E-mailalias** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="db7b4-160">Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="db7b4-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="db7b4-161">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="db7b4-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="db7b4-162">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db7b4-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="db7b4-163">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="db7b4-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="db7b4-164">Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="db7b4-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="db7b4-165">Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="db7b4-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="db7b4-166">Selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="db7b4-167">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="db7b4-168">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="db7b4-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="db7b4-169">Zie Een domein toevoegen aan [Microsoft 365](../setup/add-domain.md)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="db7b4-170">Wanneer u klaar bent, selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="db7b4-171">Wacht 24 uur totdat de nieuwe aliassen worden ingevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db7b4-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="db7b4-172">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="db7b4-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="db7b4-173">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.</span><span class="sxs-lookup"><span data-stu-id="db7b4-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="db7b4-174">**Wanneer de gebruiker antwoordt, is *het Van-adres*  haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="db7b4-174">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="db7b4-175">Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db7b4-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="db7b4-176">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="db7b4-176">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="db7b4-177">Hebt u 'A parameter cannot be found that matches parameter name EmailAddresses' gekregen?</span><span class="sxs-lookup"><span data-stu-id="db7b4-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="db7b4-178">Als u het foutbericht ' Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam EmailAddresses'** wordt weergegeven, betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="db7b4-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="db7b4-179">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="db7b4-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="db7b4-180">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db7b4-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="db7b4-181">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="db7b4-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="db7b4-182">Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?</span><span class="sxs-lookup"><span data-stu-id="db7b4-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="db7b4-183">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="db7b4-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="db7b4-184">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="db7b4-184">Related articles</span></span>

[<span data-ttu-id="db7b4-185">E-mail verzenden via een ander adres</span><span class="sxs-lookup"><span data-stu-id="db7b4-185">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="db7b4-186">Een gebruikersnaam en e-mailadres wijzigen</span><span class="sxs-lookup"><span data-stu-id="db7b4-186">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
