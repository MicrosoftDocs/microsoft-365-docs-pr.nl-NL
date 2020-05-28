---
title: Postvakmachtigingen toewijzen aan een andere gebruiker - Help voor beheerders
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Lees hoe u een gebruiker toegang geeft tot het postvak van een andere gebruiker. Dat geeft de gebruiker het recht om e-mail te lezen en e-mails te verzenden vanuit het postvak van de andere gebruiker. '
ms.openlocfilehash: 51de5f4e2b134a503ec935b1f1d0ec6519d2c229
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387175"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="db3b5-104">Postvakmachtigingen toewijzen aan een andere gebruiker - Help voor beheerders</span><span class="sxs-lookup"><span data-stu-id="db3b5-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="db3b5-105">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="db3b5-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="db3b5-106">Als beheerder hebt u misschien te maken met bedrijfsvereisten waardoor bepaalde gebruikers toegang krijgen tot het postvak van een andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="db3b5-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="db3b5-107">Mogelijk moet u een assistent toegang geven tot het postvak van een manager om e-mail te laten verzenden of lezen, of moet u een van uw gebruikers e-mail laten verzenden namens een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db3b5-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="db3b5-108">In dit onderwerp leest u hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="db3b5-109">Zie [Een gedeeld postvak maken](../email/create-a-shared-mailbox.md)voor informatie over het maken en beheren van gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="db3b5-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="db3b5-110">Wilt u machtigingen voor postvakken instellen?</span><span class="sxs-lookup"><span data-stu-id="db3b5-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="db3b5-p103">Met postvakmachtigingen kunt u lees-/schrijftoegang voor een postvak aan andere gebruikers verlenen. In de onderstaande artikelen vindt u wat u nodig hebt om deze functie in te stellen en te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="db3b5-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="db3b5-113">**Machtigingen instellen:**</span><span class="sxs-lookup"><span data-stu-id="db3b5-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="db3b5-p104">De eerste stap bij het instellen van machtigingen bestaat uit het bepalen welke acties u een andere gebruiker wilt laten uitvoeren voor het betreffende postvak. U kunt toestaan dat een gebruiker e-mails in het postvak kan lezen, e-mails namens aan ander kan verzenden of e-mails kan verzenden alsof deze vanuit dat postvak zijn verzonden. Zie de volgende artikelen om de verschillende typen machtigingen in te stellen:</span><span class="sxs-lookup"><span data-stu-id="db3b5-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="db3b5-117">E-mail lezen vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="db3b5-118">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="db3b5-119">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="db3b5-120">**Doorgifte wijzigen:**</span><span class="sxs-lookup"><span data-stu-id="db3b5-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="db3b5-121">Als u de machtigingen hebt ingesteld, kan het zestig minuten duren voordat de wijzigingen in het systeem zijn doorgevoerd en van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="db3b5-122">**Gebruik van het postvak als de machtigingen zijn ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="db3b5-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="db3b5-p105">Een postvak kan op verschillende manieren worden geopend zodra u toegang hebt gekregen. Zie het volgende artikel voor hulp hierbij: [Het postvak van een andere gebruiker openen](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="db3b5-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="db3b5-125">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="db3b5-126">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="db3b5-127">Selecteer de naam van de gebruiker (van wie u een verzendmachtiging wilt geven) om het deelvenster met eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="db3b5-128">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="db3b5-129">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="db3b5-130">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="db3b5-131">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="db3b5-132">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="db3b5-133">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="db3b5-134">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="db3b5-135">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="db3b5-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="db3b5-137">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="db3b5-138">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="db3b5-139">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="db3b5-140">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="db3b5-141">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="db3b5-142">E-mail lezen in het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="db3b5-143">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="db3b5-144">Selecteer de naam van de gebruiker (met het postvak dat u wilt toelaten) om het eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="db3b5-145">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="db3b5-146">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="db3b5-147">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="db3b5-148">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="db3b5-149">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="db3b5-150">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="db3b5-151">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="db3b5-152">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="db3b5-153">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="db3b5-154">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="db3b5-155">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="db3b5-156">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="db3b5-157">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="db3b5-158">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="db3b5-159">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="db3b5-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="db3b5-160">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="db3b5-161">Selecteer de naam van de gebruiker (van wie u**Verzenden namens**-machtiging wilt geven) om hun eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="db3b5-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="db3b5-162">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="db3b5-163">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="db3b5-164">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="db3b5-165">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="db3b5-166">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="db3b5-167">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="db3b5-168">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="db3b5-169">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="db3b5-170">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="db3b5-171">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="db3b5-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="db3b5-172">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="db3b5-173">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="db3b5-174">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="db3b5-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="db3b5-175">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="db3b5-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="db3b5-176">Verzenden vanuit en lezen in Outlook en de webversie van Outlook voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="db3b5-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="db3b5-p106">Wilt u weten hoe u e-mail verzendt vanuit het postvak van een andere gebruiker? Raadpleeg de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="db3b5-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="db3b5-179">E-mail- en agenda-items van een andere gebruiker beheren</span><span class="sxs-lookup"><span data-stu-id="db3b5-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="db3b5-180">E-mail verzenden namens een andere persoon of groep</span><span class="sxs-lookup"><span data-stu-id="db3b5-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
