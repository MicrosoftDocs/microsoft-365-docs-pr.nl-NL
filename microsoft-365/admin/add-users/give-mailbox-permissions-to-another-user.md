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
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780599"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="9df12-104">Postvakmachtigingen toewijzen aan een andere gebruiker - Help voor beheerders</span><span class="sxs-lookup"><span data-stu-id="9df12-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="9df12-105">Als beheerder hebt u misschien te maken met bedrijfsvereisten waardoor bepaalde gebruikers toegang krijgen tot het postvak van een andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9df12-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="9df12-106">Mogelijk moet u een assistent toegang geven tot het postvak van een manager om e-mail te laten verzenden of lezen, of moet u een van uw gebruikers e-mail laten verzenden namens een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="9df12-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="9df12-107">In dit onderwerp leest u hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="9df12-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="9df12-108">Zie [Een gedeeld postvak maken](../email/create-a-shared-mailbox.md)voor informatie over het maken en beheren van gedeelde postvakken.</span><span class="sxs-lookup"><span data-stu-id="9df12-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="9df12-109">Wilt u machtigingen voor postvakken instellen?</span><span class="sxs-lookup"><span data-stu-id="9df12-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="9df12-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span><span class="sxs-lookup"><span data-stu-id="9df12-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span></span> <span data-ttu-id="9df12-111">The articles below might give you the help you need to set up and use this feature:</span><span class="sxs-lookup"><span data-stu-id="9df12-111">The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="9df12-112">**Machtigingen instellen:**</span><span class="sxs-lookup"><span data-stu-id="9df12-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="9df12-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span><span class="sxs-lookup"><span data-stu-id="9df12-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span></span> <span data-ttu-id="9df12-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span><span class="sxs-lookup"><span data-stu-id="9df12-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span></span> <span data-ttu-id="9df12-115">Refer to the following articles on how to set up each type of permissions:</span><span class="sxs-lookup"><span data-stu-id="9df12-115">Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="9df12-116">E-mail lezen vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="9df12-117">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="9df12-118">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="9df12-119">**Doorgifte wijzigen:**</span><span class="sxs-lookup"><span data-stu-id="9df12-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="9df12-120">Als u de machtigingen hebt ingesteld, kan het zestig minuten duren voordat de wijzigingen in het systeem zijn doorgevoerd en van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="9df12-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="9df12-121">**Gebruik van het postvak als de machtigingen zijn ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="9df12-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="9df12-122">There are a few different ways you can access a mailbox once you've been given access.</span><span class="sxs-lookup"><span data-stu-id="9df12-122">There are a few different ways you can access a mailbox once you've been given access.</span></span> <span data-ttu-id="9df12-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="9df12-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="9df12-124">E-mail verzenden vanuit het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9df12-125">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="9df12-126">Selecteer de naam van de gebruiker (van wie u een verzendmachtiging wilt geven) om het deelvenster met eigenschappen te openen.</span><span class="sxs-lookup"><span data-stu-id="9df12-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="9df12-127">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="9df12-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="9df12-128">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="9df12-129">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="9df12-130">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9df12-131">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9df12-132">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="9df12-133">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="9df12-134">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="9df12-135">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9df12-136">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="9df12-137">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="9df12-138">Selecteer naast **Verzenden als**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="9df12-139">Selecteer **Machtigingen toevoegen**en kies vervolgens de naam van de persoon vanuit waar deze gebruiker kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="9df12-140">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="9df12-141">E-mail lezen in het postvak van een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9df12-142">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="9df12-143">Selecteer de naam van de gebruiker (met het postvak dat u wilt toelaten) om het eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="9df12-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="9df12-144">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="9df12-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="9df12-145">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="9df12-146">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="9df12-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="9df12-147">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9df12-148">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="9df12-149">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="9df12-150">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="9df12-151">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="9df12-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="9df12-152">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9df12-153">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="9df12-154">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="9df12-155">Selecteer naast **Lezen en beheren**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="9df12-156">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers die e-mail in dit postvak mogen lezen.</span><span class="sxs-lookup"><span data-stu-id="9df12-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="9df12-157">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="9df12-158">E-mail verzenden namens een andere gebruiker</span><span class="sxs-lookup"><span data-stu-id="9df12-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9df12-159">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9df12-160">Selecteer de naam van de gebruiker (van wie u**Verzenden namens**-machtiging wilt geven) om hun eigenschappenvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="9df12-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="9df12-161">Selecteer op het tabblad **E-mail** **Postvakmachtigingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="9df12-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="9df12-162">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="9df12-163">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="9df12-164">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9df12-165">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9df12-166">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="9df12-167">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="9df12-168">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="9df12-169">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9df12-170">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="9df12-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="9df12-171">Selecteer de gebruiker die u wilt, vouw **E-mail instellingen**uit en selecteer vervolgens **Bewerken** naast **Postvakmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="9df12-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="9df12-172">Selecteer naast **Verzenden namens**, de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9df12-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="9df12-173">Selecteer **Machtigingen toevoegen** en kies vervolgens de naam van de gebruiker of gebruikers vanuit dit postvak e-mails mogen verzenden.</span><span class="sxs-lookup"><span data-stu-id="9df12-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="9df12-174">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9df12-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="9df12-175">Verzenden vanuit en lezen in Outlook en de webversie van Outlook voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9df12-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="9df12-176">Want to know how to send email from another user's mailbox?</span><span class="sxs-lookup"><span data-stu-id="9df12-176">Want to know how to send email from another user's mailbox?</span></span> <span data-ttu-id="9df12-177">Check out the following topics:</span><span class="sxs-lookup"><span data-stu-id="9df12-177">Check out the following topics:</span></span>
  
- [<span data-ttu-id="9df12-178">E-mail- en agenda-items van een andere gebruiker beheren</span><span class="sxs-lookup"><span data-stu-id="9df12-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="9df12-179">E-mail verzenden namens een andere persoon of groep</span><span class="sxs-lookup"><span data-stu-id="9df12-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
