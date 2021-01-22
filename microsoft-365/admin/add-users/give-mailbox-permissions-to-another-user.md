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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Lees hoe u een gebruiker toegang geeft tot het postvak van een andere gebruiker. Dat geeft de gebruiker het recht om e-mail te lezen en e-mails te verzenden vanuit het postvak van de andere gebruiker. '
ms.openlocfilehash: e6b94d4e24b0ff1d5dc397ccbcfba98929a303f2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925540"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="92b6d-104">Postvakmachtigingen toewijzen aan een andere gebruiker - Help voor beheerders</span><span class="sxs-lookup"><span data-stu-id="92b6d-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="92b6d-105">Als beheerder hebt u misschien te maken met bedrijfsvereisten waardoor bepaalde gebruikers toegang krijgen tot het postvak van een andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="92b6d-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="92b6d-106">Mogelijk moet u een assistent toegang geven tot het postvak van een manager om e-mail te laten verzenden of lezen, of moet u een van uw gebruikers e-mail laten verzenden namens een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="92b6d-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="92b6d-107">In dit onderwerp leest u hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="92b6d-108">Zie [Een gedeeld postvak maken](../email/create-a-shared-mailbox.md)voor informatie over het maken en beheren van gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="92b6d-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="92b6d-109">Wilt u machtigingen voor postvakken instellen?</span><span class="sxs-lookup"><span data-stu-id="92b6d-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="92b6d-p103">Met postvakmachtigingen kunt u lees-/schrijftoegang voor een postvak aan andere gebruikers verlenen. In de onderstaande artikelen vindt u wat u nodig hebt om deze functie in te stellen en te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="92b6d-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="92b6d-112">**Machtigingen instellen:**</span><span class="sxs-lookup"><span data-stu-id="92b6d-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="92b6d-p104">De eerste stap bij het instellen van machtigingen bestaat uit het bepalen welke acties u een andere gebruiker wilt laten uitvoeren voor het betreffende postvak. U kunt toestaan dat een gebruiker e-mails in het postvak kan lezen, e-mails namens aan ander kan verzenden of e-mails kan verzenden alsof deze vanuit dat postvak zijn verzonden. Zie de volgende artikelen om de verschillende typen machtigingen in te stellen:</span><span class="sxs-lookup"><span data-stu-id="92b6d-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="92b6d-116">E-mail lezen vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="92b6d-117">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="92b6d-118">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="92b6d-119">**Doorgifte wijzigen:**</span><span class="sxs-lookup"><span data-stu-id="92b6d-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="92b6d-120">Als u de machtigingen hebt ingesteld, kan het zestig minuten duren voordat de wijzigingen in het systeem zijn doorgevoerd en van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="92b6d-121">**Gebruik van het postvak als de machtigingen zijn ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="92b6d-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="92b6d-p105">Een postvak kan op verschillende manieren worden geopend zodra u toegang hebt gekregen. Zie het volgende artikel voor hulp hierbij: [Het postvak van een andere gebruiker openen](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="92b6d-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="92b6d-124">De machtigingen kunnen alleen worden ingesteld binnen de huidige organisatie-tenant.</span><span class="sxs-lookup"><span data-stu-id="92b6d-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="92b6d-125">Het is niet mogelijk om machtigingen voor het postvak in te stellen met niet-tenant gebruikers.</span><span class="sxs-lookup"><span data-stu-id="92b6d-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="92b6d-126">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="92b6d-127">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="92b6d-128">Selecteer de naam van de gebruiker (van wie u een verzendmachtiging wilt geven) om het deelvenster met eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="92b6d-129">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="92b6d-130">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="92b6d-131">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="92b6d-132">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="92b6d-133">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="92b6d-134">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="92b6d-135">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="92b6d-136">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="92b6d-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="92b6d-138">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="92b6d-139">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="92b6d-140">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="92b6d-141">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="92b6d-142">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="92b6d-143">E-mail lezen in het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="92b6d-144">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="92b6d-145">Selecteer de naam van de gebruiker (met het postvak dat u wilt toelaten) om het eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="92b6d-146">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="92b6d-147">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="92b6d-148">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="92b6d-149">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="92b6d-150">**Lees-** en **Beheer-** machtigingen worden **Volledige toegangsmachtigingen** genoemd wanneer ze worden toegewezen in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="92b6d-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="92b6d-151">Volledige toegangsmachtiging staat niet gelijk aan **Versturen als-** of **Versturen namens-** machtigingen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="92b6d-152">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="92b6d-153">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="92b6d-154">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="92b6d-155">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="92b6d-156">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="92b6d-157">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="92b6d-158">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="92b6d-159">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="92b6d-160">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="92b6d-161">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="92b6d-162">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="92b6d-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="92b6d-163">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="92b6d-164">Selecteer de naam van de gebruiker (van wie u **Verzenden namens**-machtiging wilt geven) om hun eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="92b6d-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="92b6d-165">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="92b6d-166">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="92b6d-167">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="92b6d-168">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="92b6d-169">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="92b6d-170">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="92b6d-171">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="92b6d-172">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="92b6d-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="92b6d-174">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="92b6d-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="92b6d-175">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="92b6d-176">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="92b6d-177">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="92b6d-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="92b6d-178">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92b6d-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="92b6d-179">Verzenden vanuit en lezen in Outlook en de webversie van Outlook voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="92b6d-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="92b6d-p108">Wilt u weten hoe u e-mail verzendt vanuit het postvak van een andere gebruiker? Raadpleeg de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="92b6d-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="92b6d-182">E-mail- en agenda-items van een andere gebruiker beheren</span><span class="sxs-lookup"><span data-stu-id="92b6d-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="92b6d-183">E-mail verzenden namens een andere persoon of groep</span><span class="sxs-lookup"><span data-stu-id="92b6d-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
