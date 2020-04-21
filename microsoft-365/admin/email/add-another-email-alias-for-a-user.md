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
ms.openlocfilehash: 66ff2441c95ed28b2072792fd0a63b16eea85c04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629081"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="5c902-103">Een ander e-mailalias toevoegen voor een gebruiker</span><span class="sxs-lookup"><span data-stu-id="5c902-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="5c902-104">Dit artikel is voor Microsoft 365-beheerders die zakelijke abonnementen hebben.</span><span class="sxs-lookup"><span data-stu-id="5c902-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="5c902-105">Het is niet bedoeld voor thuisgebruikers.</span><span class="sxs-lookup"><span data-stu-id="5c902-105">It's not for home users.</span></span>
  
<span data-ttu-id="5c902-106">Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat een gebruiker is toegewezen toen zijn/haar account werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5c902-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="5c902-107">Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="5c902-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="5c902-108">Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor zakelijke account.</span><span class="sxs-lookup"><span data-stu-id="5c902-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="5c902-109">Deze extra adressen worden aliassen genoemd.</span><span class="sxs-lookup"><span data-stu-id="5c902-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="5c902-110">Stel dat Jenna het e-mailadres heeft jenna@contosoco.com, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam.</span><span class="sxs-lookup"><span data-stu-id="5c902-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="5c902-111">Je aliassen voor haar maken, zodat beide e-mailadressen naar Jenna's inbox gaan.</span><span class="sxs-lookup"><span data-stu-id="5c902-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="5c902-112">U kunt maximaal 400 aliassen maken voor een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5c902-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="5c902-113">Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.</span><span class="sxs-lookup"><span data-stu-id="5c902-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="5c902-114">Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres worden verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="5c902-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="5c902-115">Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5c902-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="5c902-116">E-mailaliassen toevoegen aan een gebruiker</span><span class="sxs-lookup"><span data-stu-id="5c902-116">Add email aliases to a user</span></span>
<span data-ttu-id="5c902-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="5c902-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="5c902-118">U moet [beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="5c902-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5c902-119">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5c902-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="5c902-120">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5c902-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="5c902-121">Selecteer op de pagina **Actieve gebruikers** de gebruiker > **E-mailaliassen beheren.**</span><span class="sxs-lookup"><span data-stu-id="5c902-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="5c902-122">U ziet deze optie niet als de persoon geen licentie aan hem of haar heeft toegewezen.</span><span class="sxs-lookup"><span data-stu-id="5c902-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="5c902-123">Selecteer **+ Voeg een alias toe** en voer een nieuwe alias in voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5c902-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="5c902-124">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="5c902-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5c902-125">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="5c902-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5c902-126">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="5c902-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5c902-127">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="5c902-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="5c902-128">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5c902-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5c902-129">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c902-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5c902-130">Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5c902-130">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 
  
     
5. <span data-ttu-id="5c902-131">Wanneer u klaar bent, kiest **u Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5c902-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="5c902-132">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c902-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="5c902-133">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="5c902-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5c902-134">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="5c902-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5c902-135">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="5c902-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="5c902-136">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5c902-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5c902-137">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="5c902-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="5c902-138">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5c902-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="5c902-139">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5c902-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="5c902-140">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="5c902-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="5c902-141">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="5c902-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5c902-142">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="5c902-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5c902-143">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="5c902-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5c902-144">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="5c902-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="5c902-145">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="5c902-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="5c902-146">Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c902-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="5c902-147">Selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5c902-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5c902-148">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5c902-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5c902-149">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c902-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5c902-150">Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5c902-150">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="5c902-151">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5c902-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="5c902-152">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c902-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="5c902-153">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="5c902-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5c902-154">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="5c902-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5c902-155">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="5c902-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="5c902-156">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5c902-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5c902-157">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="5c902-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5c902-158">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="5c902-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="5c902-159">Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5c902-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="5c902-160">Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="5c902-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="5c902-161">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses",** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="5c902-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5c902-162">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="5c902-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5c902-163">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="5c902-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5c902-164">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="5c902-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="5c902-165">Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias.</span><span class="sxs-lookup"><span data-stu-id="5c902-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="5c902-166">Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c902-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="5c902-167">Selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5c902-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5c902-168">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5c902-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5c902-169">De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c902-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5c902-170">Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5c902-170">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="5c902-171">Wanneer u klaar bent, selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5c902-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="5c902-172">Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c902-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="5c902-173">De gebruiker heeft nu een primair adres en een alias.</span><span class="sxs-lookup"><span data-stu-id="5c902-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5c902-174">Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.</span><span class="sxs-lookup"><span data-stu-id="5c902-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5c902-175">**Wanneer de gebruiker antwoordt, is het *Van-adres* haar primaire e-mailalias.**</span><span class="sxs-lookup"><span data-stu-id="5c902-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="5c902-176">Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's inbox wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5c902-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5c902-177">Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="5c902-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="5c902-178">Heb je "Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="5c902-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="5c902-179">Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses**" betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="5c902-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5c902-180">Het instellen kan 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="5c902-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5c902-181">Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="5c902-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5c902-182">Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.</span><span class="sxs-lookup"><span data-stu-id="5c902-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="5c902-183">Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?</span><span class="sxs-lookup"><span data-stu-id="5c902-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="5c902-184">Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5c902-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5c902-185">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5c902-185">Related articles</span></span>

[<span data-ttu-id="5c902-186">E-mail verzenden via een ander adres</span><span class="sxs-lookup"><span data-stu-id="5c902-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="5c902-187">Een gebruikersnaam en e-mailadres wijzigen</span><span class="sxs-lookup"><span data-stu-id="5c902-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

