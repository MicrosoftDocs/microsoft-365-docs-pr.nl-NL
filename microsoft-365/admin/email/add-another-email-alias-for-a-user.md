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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Lees hoe u meer dan één e-mailadres, de zogenaamde e-mailalias, hebben gekoppeld aan uw Microsoft 365 voor zakelijke account. '
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048805"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="2bb31-103">Een ander e-mailalias toevoegen voor een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2bb31-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="2bb31-104">Dit artikel is voor Microsoft 365-beheerders die zakelijke abonnementen hebben.</span><span class="sxs-lookup"><span data-stu-id="2bb31-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="2bb31-105">Het is niet bedoeld voor thuisgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2bb31-105">It's not for home users.</span></span>
  
<span data-ttu-id="2bb31-106">Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat een gebruiker is toegewezen toen zijn/haar account werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2bb31-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="2bb31-107">Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="2bb31-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="2bb31-108">Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor zakelijke account.</span><span class="sxs-lookup"><span data-stu-id="2bb31-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="2bb31-109">Deze extra adressen worden aliassen genoemd.</span><span class="sxs-lookup"><span data-stu-id="2bb31-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="2bb31-110">Stel dat Jenna het e-mailadres heeft jenna@contosoco.com, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam.</span><span class="sxs-lookup"><span data-stu-id="2bb31-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="2bb31-111">Je aliassen voor haar maken, zodat beide e-mailadressen naar Jenna's inbox gaan.</span><span class="sxs-lookup"><span data-stu-id="2bb31-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="2bb31-112">U kunt maximaal 400 aliassen maken voor een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2bb31-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="2bb31-113">Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="2bb31-114">Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres worden verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="2bb31-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="2bb31-115">Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2bb31-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="2bb31-116">E-mailaliassen toevoegen aan een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2bb31-116">Add email aliases to a user</span></span>
<span data-ttu-id="2bb31-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="2bb31-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="2bb31-118">U moet [beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="2bb31-119">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2bb31-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="2bb31-120">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="2bb31-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2bb31-121">Selecteer op de pagina **Actieve gebruikers** de gebruiker > **E-mailaliassen beheren.**</span><span class="sxs-lookup"><span data-stu-id="2bb31-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="2bb31-122">U ziet deze optie niet als de persoon geen licentie aan hem of haar heeft toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="2bb31-123">Selecteer **+ Voeg een alias toe** en voer een nieuwe alias in voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2bb31-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="2bb31-124">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2bb31-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2bb31-125">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="2bb31-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2bb31-126">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2bb31-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2bb31-127">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="2bb31-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="2bb31-128">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2bb31-129">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="2bb31-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2bb31-130">Zie Een domein toevoegen aan [Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="2bb31-131">Wanneer u klaar bent, kiest **u Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="2bb31-132">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bb31-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="2bb31-133">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="2bb31-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2bb31-134">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="2bb31-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2bb31-135">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="2bb31-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2bb31-136">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2bb31-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2bb31-137">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="2bb31-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="2bb31-138">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="2bb31-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="2bb31-139">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2bb31-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="2bb31-140">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="2bb31-141">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2bb31-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2bb31-142">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="2bb31-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2bb31-143">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2bb31-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2bb31-144">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="2bb31-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="2bb31-145">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="2bb31-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="2bb31-146">Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="2bb31-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="2bb31-147">Selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2bb31-148">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2bb31-149">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="2bb31-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2bb31-150">Zie Een domein toevoegen aan [Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="2bb31-151">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="2bb31-152">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bb31-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="2bb31-153">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="2bb31-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2bb31-154">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="2bb31-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2bb31-155">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="2bb31-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2bb31-156">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2bb31-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2bb31-157">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="2bb31-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2bb31-158">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="2bb31-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="2bb31-159">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2bb31-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="2bb31-160">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="2bb31-161">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2bb31-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2bb31-162">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="2bb31-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2bb31-163">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2bb31-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2bb31-164">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="2bb31-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="2bb31-165">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="2bb31-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="2bb31-166">Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="2bb31-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="2bb31-167">Selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2bb31-168">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2bb31-169">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="2bb31-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2bb31-170">Zie Een domein toevoegen aan [Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="2bb31-171">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2bb31-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="2bb31-172">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bb31-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="2bb31-173">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="2bb31-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2bb31-174">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="2bb31-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2bb31-175">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="2bb31-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2bb31-176">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2bb31-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2bb31-177">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="2bb31-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="2bb31-178">Heb je "Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="2bb31-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="2bb31-179">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses**" betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2bb31-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2bb31-180">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="2bb31-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2bb31-181">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2bb31-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2bb31-182">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="2bb31-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="2bb31-183">Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?</span><span class="sxs-lookup"><span data-stu-id="2bb31-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="2bb31-184">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2bb31-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="2bb31-185">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2bb31-185">Related articles</span></span>

[<span data-ttu-id="2bb31-186">E-mail verzenden via een ander adres</span><span class="sxs-lookup"><span data-stu-id="2bb31-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="2bb31-187">Een gebruikersnaam en e-mailadres wijzigen</span><span class="sxs-lookup"><span data-stu-id="2bb31-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

