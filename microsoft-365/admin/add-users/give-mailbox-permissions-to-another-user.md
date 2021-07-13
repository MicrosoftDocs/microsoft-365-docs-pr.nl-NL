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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Geef een gebruiker het recht om toegang te krijgen tot het postvak van een andere gebruiker, zodat de gebruiker e-mailberichten kan lezen en verzenden vanuit het postvak van de andere gebruiker.
ms.openlocfilehash: 1c1b591ff9053e20e8754df5b7c69288d198cc98
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394337"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="1e3d2-103">Postvakmachtigingen toewijzen aan een andere gebruiker - Help voor beheerders</span><span class="sxs-lookup"><span data-stu-id="1e3d2-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="1e3d2-p101">Als beheerder hebt u misschien te maken met bedrijfsvereisten waardoor bepaalde gebruikers toegang tot het postvak van andere gebruikers moeten krijgen. Mogelijk moet u een assistent toegang geven tot het postvak van een manager om e-mail te laten verzenden of lezen, of moet u een van uw gebruikers e-mail laten verzenden namens een andere gebruiker. In dit onderwerp leest u hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-p101">As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="1e3d2-107">Zie [Een gedeeld postvak maken](../email/create-a-shared-mailbox.md)voor informatie over het maken en beheren van gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="1e3d2-108">Wilt u machtigingen voor postvakken instellen?</span><span class="sxs-lookup"><span data-stu-id="1e3d2-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="1e3d2-p102">Met postvakmachtigingen kunt u lees-/schrijftoegang voor een postvak aan andere gebruikers verlenen. In de onderstaande artikelen vindt u wat u nodig hebt om deze functie in te stellen en te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1e3d2-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="1e3d2-111">**Machtigingen instellen:**</span><span class="sxs-lookup"><span data-stu-id="1e3d2-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="1e3d2-p103">De eerste stap bij het instellen van machtigingen bestaat uit het bepalen welke acties u een andere gebruiker wilt laten uitvoeren voor het betreffende postvak. U kunt toestaan dat een gebruiker e-mails in het postvak kan lezen, e-mails namens aan ander kan verzenden of e-mails kan verzenden alsof deze vanuit dat postvak zijn verzonden. Zie de volgende artikelen om de verschillende typen machtigingen in te stellen:</span><span class="sxs-lookup"><span data-stu-id="1e3d2-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="1e3d2-115">E-mail lezen vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="1e3d2-116">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="1e3d2-117">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="1e3d2-118">**Doorgifte wijzigen:**</span><span class="sxs-lookup"><span data-stu-id="1e3d2-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="1e3d2-119">Als u de machtigingen hebt ingesteld, kan het zestig minuten duren voordat de wijzigingen in het systeem zijn doorgevoerd en van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="1e3d2-120">**Gebruik van het postvak als de machtigingen zijn ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="1e3d2-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="1e3d2-p104">Een postvak kan op verschillende manieren worden geopend zodra u toegang hebt gekregen. Zie het volgende artikel voor hulp hierbij: [Het postvak van een andere gebruiker openen](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="1e3d2-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="1e3d2-123">De machtigingen kunnen alleen worden ingesteld binnen de huidige organisatie-tenant.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="1e3d2-124">Het is niet mogelijk om machtigingen voor het postvak in te stellen met niet-tenant gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="1e3d2-125">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e3d2-126">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="1e3d2-127">Selecteer de naam van de gebruiker (van wie u een verzendmachtiging wilt geven) om het deelvenster met eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1e3d2-128">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="1e3d2-129">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="1e3d2-130">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="1e3d2-131">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e3d2-132">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1e3d2-133">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1e3d2-134">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="1e3d2-135">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="1e3d2-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e3d2-137">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="1e3d2-138">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1e3d2-139">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="1e3d2-140">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="1e3d2-141">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="1e3d2-142">E-mail lezen in het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e3d2-143">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="1e3d2-144">Selecteer de naam van de gebruiker (met het postvak dat u wilt toelaten) om het eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1e3d2-145">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="1e3d2-146">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="1e3d2-147">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="1e3d2-148">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="1e3d2-149">**Lees-** en **Beheer-** machtigingen worden **Volledige toegangsmachtigingen** genoemd wanneer ze worden toegewezen in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="1e3d2-150">Volledige toegangsmachtiging staat niet gelijk aan **Versturen als-** of **Versturen namens-** machtigingen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e3d2-151">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="1e3d2-152">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="1e3d2-153">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="1e3d2-154">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="1e3d2-155">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e3d2-156">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="1e3d2-157">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="1e3d2-158">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="1e3d2-159">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="1e3d2-160">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="1e3d2-161">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="1e3d2-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e3d2-162">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1e3d2-163">Selecteer de naam van de gebruiker (van wie u **Verzenden namens**-machtiging wilt geven) om hun eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1e3d2-164">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="1e3d2-165">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="1e3d2-166">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="1e3d2-167">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e3d2-168">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1e3d2-169">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1e3d2-170">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="1e3d2-171">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="1e3d2-172">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e3d2-173">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="1e3d2-174">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen** uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1e3d2-175">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="1e3d2-176">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="1e3d2-177">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="1e3d2-178">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="1e3d2-178">Related content</span></span>
  
<span data-ttu-id="1e3d2-179">[E-mail- en agenda-items van een andere gebruiker beheren](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1e3d2-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>\   
<span data-ttu-id="1e3d2-180">[E-mail verzenden namens een andere persoon of groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1e3d2-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>\
<span data-ttu-id="1e3d2-181">[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (video)</span><span class="sxs-lookup"><span data-stu-id="1e3d2-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

