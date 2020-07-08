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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Ontdek hoe u meer dan één e-mailadres, e-mailalias genaamd, hebben gekoppeld aan uw Microsoft 365 voor bedrijven-account. '
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080013"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="6bb03-103">Een ander e-mailalias toevoegen voor een gebruiker</span><span class="sxs-lookup"><span data-stu-id="6bb03-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6bb03-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-104">The admin center is changing.</span></span> <span data-ttu-id="6bb03-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6bb03-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="6bb03-106">Dit artikel is voor Microsoft 365-beheerders met zakelijke abonnementen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="6bb03-107">Het is niet bedoeld voor thuisgebruikers.</span><span class="sxs-lookup"><span data-stu-id="6bb03-107">It's not for home users.</span></span>
  
<span data-ttu-id="6bb03-108">Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat een gebruiker heeft toegewezen toen zijn account werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="6bb03-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="6bb03-109">Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="6bb03-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="6bb03-110">Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor bedrijven-account.</span><span class="sxs-lookup"><span data-stu-id="6bb03-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="6bb03-111">Deze extra adressen worden aliassen genoemd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="6bb03-112">Stel dat Jenna het e-mailadres heeft jenna@contosoco.com, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam.</span><span class="sxs-lookup"><span data-stu-id="6bb03-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="6bb03-113">U aliassen voor haar maken, zodat beide e-mailadressen naar jenna's inbox gaan.</span><span class="sxs-lookup"><span data-stu-id="6bb03-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="6bb03-114">U kunt maximaal 400 aliassen maken voor een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6bb03-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="6bb03-115">Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="6bb03-116">Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres worden verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="6bb03-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="6bb03-117">Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6bb03-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="6bb03-118">E-mailaliassen toevoegen aan een gebruiker</span><span class="sxs-lookup"><span data-stu-id="6bb03-118">Add email aliases to a user</span></span>
<span data-ttu-id="6bb03-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="6bb03-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="6bb03-120">Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="6bb03-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="6bb03-121">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="6bb03-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6bb03-122">Selecteer op de pagina **Actieve gebruikers** de gebruiker > **E-mailaliassen beheren**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="6bb03-123">U ziet deze optie niet als de persoon geen licentie aan deze persoon heeft toegewezen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="6bb03-124">Selecteer **+ Voeg een alias toe** en voer een nieuwe alias voor de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="6bb03-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="6bb03-125">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6bb03-126">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="6bb03-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6bb03-127">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="6bb03-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6bb03-128">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="6bb03-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="6bb03-129">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6bb03-130">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="6bb03-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6bb03-131">Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="6bb03-132">Als u klaar bent, kiest u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="6bb03-133">Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bb03-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="6bb03-134">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="6bb03-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6bb03-135">Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="6bb03-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6bb03-136">**Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="6bb03-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6bb03-137">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6bb03-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6bb03-138">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6bb03-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="6bb03-139">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="6bb03-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="6bb03-140">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6bb03-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6bb03-141">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6bb03-142">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6bb03-143">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="6bb03-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6bb03-144">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="6bb03-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6bb03-145">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="6bb03-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6bb03-146">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="6bb03-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6bb03-147">Als u uw eigen domein hebt toegevoegd aan Microsoft 365, u het domein voor de nieuwe e-mailalias kiezen met de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="6bb03-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6bb03-148">Selecteer Vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6bb03-149">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6bb03-150">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="6bb03-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6bb03-151">Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="6bb03-152">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6bb03-153">Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bb03-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="6bb03-154">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="6bb03-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6bb03-155">Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="6bb03-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6bb03-156">**Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="6bb03-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6bb03-157">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6bb03-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6bb03-158">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6bb03-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6bb03-159">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="6bb03-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="6bb03-160">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6bb03-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6bb03-161">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6bb03-162">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6bb03-163">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="6bb03-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6bb03-164">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="6bb03-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6bb03-165">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="6bb03-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6bb03-166">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="6bb03-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6bb03-167">Als u uw eigen domein hebt toegevoegd aan Microsoft 365, u het domein voor de nieuwe e-mailalias kiezen met de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="6bb03-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6bb03-168">Selecteer Vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6bb03-169">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6bb03-170">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="6bb03-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6bb03-171">Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="6bb03-172">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6bb03-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6bb03-173">Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bb03-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="6bb03-174">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="6bb03-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6bb03-175">Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="6bb03-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6bb03-176">**Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="6bb03-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6bb03-177">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6bb03-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6bb03-178">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6bb03-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="6bb03-179">Heb je 'Een parameter kan niet worden gevonden die overeenkomt met de parameternaam EmailAddresses'?</span><span class="sxs-lookup"><span data-stu-id="6bb03-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="6bb03-180">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses**" betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6bb03-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6bb03-181">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="6bb03-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6bb03-182">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="6bb03-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6bb03-183">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="6bb03-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="6bb03-184">Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?</span><span class="sxs-lookup"><span data-stu-id="6bb03-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="6bb03-185">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6bb03-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6bb03-186">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="6bb03-186">Related articles</span></span>

[<span data-ttu-id="6bb03-187">E-mail verzenden via een ander adres</span><span class="sxs-lookup"><span data-stu-id="6bb03-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="6bb03-188">Een gebruikersnaam en e-mailadres wijzigen</span><span class="sxs-lookup"><span data-stu-id="6bb03-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

