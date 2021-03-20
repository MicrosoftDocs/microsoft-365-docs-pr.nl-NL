---
title: Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informatie over het maken, bewerken of verwijderen van een beveiligingsgroep.
ms.openlocfilehash: d2cc749acaf7b2e23674156f6ad9a200ec7b386d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915816"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="703d9-103">Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="703d9-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="703d9-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="703d9-104">The admin center is changing.</span></span> <span data-ttu-id="703d9-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="703d9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="703d9-106">Op de pagina Microsoft 365 **Groepen** kunt u groepen gebruikersaccounts maken die u kunt gebruiken om dezelfde machtigingen toe te wijzen in SharePoint Online en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="703d9-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="703d9-107">Een beheerder kan bijvoorbeeld een beveiligingsgroep maken om een bepaalde groep personen toegang te verlenen tot een SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="703d9-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="703d9-108">Alleen globale beheerders en beheerders van gebruikersbeheer hebben machtigingen voor het maken, bewerken of verwijderen van beveiligingsgroepen. Zie Beheerdersrollen toewijzen voor meer informatie over [beheerdersrollen.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="703d9-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="703d9-109">Er zijn ook [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) die u kunt gebruiken om e-mail te verzenden of machtigingen toe te wijzen aan een groep gebruikers, en [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) waarmee u gebruikers rechten en toegang kunt geven tot sites en siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="703d9-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="703d9-110">Bent u van plan sitepostvakken te gebruiken?</span><span class="sxs-lookup"><span data-stu-id="703d9-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="703d9-111">Alle gebruikers die zijn toegevoegd aan een SharePoint-site via een beveiligingsgroep in plaats van individueel, kunnen het sitepostvak alleen gebruiken vanuit SharePoint.</span><span class="sxs-lookup"><span data-stu-id="703d9-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="703d9-112">Deze gebruikers hebben geen toegang tot het sitepostvak vanuit Outlook.</span><span class="sxs-lookup"><span data-stu-id="703d9-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="703d9-113">Zie Microsoft [365 Groepen gebruiken](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)in plaats van Teampostvakken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="703d9-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="703d9-114">Beveiligingsgroepen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="703d9-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="703d9-115">Een beveiligingsgroep toevoegen</span><span class="sxs-lookup"><span data-stu-id="703d9-115">Add a security group</span></span>

1. <span data-ttu-id="703d9-116">Ga in het Microsoft 365-beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a></span><span class="sxs-lookup"><span data-stu-id="703d9-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="703d9-117">Selecteer op **de** pagina Groepen de optie **Een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="703d9-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="703d9-118">Kies op **de pagina Een groeptype** kiezen de optie **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="703d9-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="703d9-119">Volg de stappen om het maken van de groep te voltooien.</span><span class="sxs-lookup"><span data-stu-id="703d9-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="703d9-120">Leden toevoegen aan een beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="703d9-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="703d9-121">Selecteer de naam van de beveiligingsgroep op **de** pagina Groepen en selecteer op **het** tabblad Leden de optie Alle leden weergeven **en leden beheren.**</span><span class="sxs-lookup"><span data-stu-id="703d9-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="703d9-122">Selecteer in het groepsdeelvenster Leden **toevoegen** en kies de persoon in de lijst  of typ de naam van de persoon die u wilt toevoegen in het vak Zoeken en selecteer **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="703d9-123">Als u leden wilt verwijderen, selecteert u de X naast de naam.</span><span class="sxs-lookup"><span data-stu-id="703d9-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="703d9-124">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **vervolgens Bewerken** naast **Leden.**</span><span class="sxs-lookup"><span data-stu-id="703d9-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="703d9-125">Selecteer in het groepsdeelvenster Leden **toevoegen** en kies de persoon in de lijst  of typ de naam van de persoon die u wilt toevoegen in het vak Zoeken en selecteer **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="703d9-126">Als u leden wilt verwijderen, selecteert u de X naast de naam.</span><span class="sxs-lookup"><span data-stu-id="703d9-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="703d9-127">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **vervolgens Bewerken** naast **Leden.**</span><span class="sxs-lookup"><span data-stu-id="703d9-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="703d9-128">Selecteer in het groepsdeelvenster Leden **toevoegen** en kies de persoon in de lijst  of typ de naam van de persoon die u wilt toevoegen in het vak Zoeken en selecteer **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="703d9-129">Als u leden wilt verwijderen, selecteert u de X naast de naam.</span><span class="sxs-lookup"><span data-stu-id="703d9-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="703d9-130">Een beveiligingsgroep bewerken</span><span class="sxs-lookup"><span data-stu-id="703d9-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="703d9-131">Ga in het beheercentrum  naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a></span><span class="sxs-lookup"><span data-stu-id="703d9-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="703d9-132">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="703d9-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="703d9-133">Selecteer in het instellingenvenster **het** tabblad Algemeen of het tabblad **Leden** om groepsdetails of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="703d9-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="703d9-134">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de pagina  \> **Groepen groepen.**</span><span class="sxs-lookup"><span data-stu-id="703d9-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="703d9-135">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="703d9-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="703d9-136">Selecteer bewerken naast het tabblad Naam  of  Leden in het deelvenster Beveiligingsgroep om groepsdetails of leden te bewerken. </span><span class="sxs-lookup"><span data-stu-id="703d9-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="703d9-137">Nadat u wijzigingen hebt  aangebracht, selecteert u \> **Sluiten opslaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="703d9-138">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de pagina  \> **Groepen groepen.**</span><span class="sxs-lookup"><span data-stu-id="703d9-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="703d9-139">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="703d9-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="703d9-140">Selecteer bewerken naast het tabblad Naam  of  Leden in het deelvenster Beveiligingsgroep om groepsdetails of leden te bewerken. </span><span class="sxs-lookup"><span data-stu-id="703d9-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="703d9-141">Nadat u wijzigingen hebt  aangebracht, selecteert u > **Sluiten opslaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="703d9-142">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="703d9-142">Delete a security group</span></span>

1. <span data-ttu-id="703d9-143">Ga in het beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a></span><span class="sxs-lookup"><span data-stu-id="703d9-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="703d9-144">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="703d9-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="703d9-145">Selecteer **Groep verwijderen** (pictogram wasetbin) en bevestig vervolgens door Verwijderen te **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="703d9-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="703d9-146">Selecteer **Sluiten zodra** de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="703d9-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="703d9-147">Groepen in Exchange Online en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="703d9-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="703d9-148">Als u groepen gebruikers wilt maken, zodat u tegelijkertijd e-mail naar hen kunt verzenden, kunt  u dat doen in het Exchange-beheercentrum door naar \>  \> **Exchange-geadresseerdengroepen** voor beheerders te \> **gaan.**</span><span class="sxs-lookup"><span data-stu-id="703d9-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="703d9-149">Selecteer vervolgens **Nieuw** ![ toevoegen en selecteer het type groep dat u wilt ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) maken:</span><span class="sxs-lookup"><span data-stu-id="703d9-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="703d9-150">**Distributiegroep**: deze groep wordt gebruikt om berichten te verzenden naar een groep gebruikers.</span><span class="sxs-lookup"><span data-stu-id="703d9-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="703d9-151">Het wordt ook wel een *distributiegroep met e-mail* of een *distributielijst genoemd.*</span><span class="sxs-lookup"><span data-stu-id="703d9-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="703d9-152">Zie Distributiegroepen beheren voor [meer informatie.](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="703d9-152">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="703d9-153">**Beveiligingsgroep**: deze groep kan worden gebruikt om berichten te verzenden naar een groep gebruikers of om toegangsrechten te verlenen aan resources.</span><span class="sxs-lookup"><span data-stu-id="703d9-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="703d9-154">Deze groep wordt ook wel een *beveiligingsgroep met e-mail genoemd.*</span><span class="sxs-lookup"><span data-stu-id="703d9-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="703d9-155">Zie Beveiligingsgroepen met [e-mail beheren](/Exchange/recipients/mail-enabled-security-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="703d9-155">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="703d9-156">**Dynamische distributiegroep**: dit is een type distributiegroep waarbij de lijst met geadresseerden telkens opnieuw berekend wanneer u een bericht verzendt op basis van filters en voorwaarden die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="703d9-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="703d9-157">Zie Dynamische distributiegroepen beheren voor [meer informatie.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="703d9-157">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="703d9-158">Nadat u distributiegroepen en beveiligingsgroepen met e-mail hebt gemaakt in het Exchange-beheercentrum, worden hun namen en gebruikerslijsten weergegeven op de **pagina Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="703d9-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="703d9-159">U kunt deze groepen op beide locaties verwijderen, maar u kunt ze alleen bewerken in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="703d9-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="703d9-160">Dynamische distributiegroepen worden niet weergegeven op de pagina **Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="703d9-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="703d9-161">SharePoint-groepen worden automatisch gemaakt wanneer u een siteverzameling maakt.</span><span class="sxs-lookup"><span data-stu-id="703d9-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="703d9-162">De standaardgroepen gebruiken de standaardmachtigingsniveaus in SharePoint (soms ook wel SharePoint-rollen genaamd) om gebruikers rechten en toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="703d9-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="703d9-163">Zie Standaard [SharePoint-groepen in SharePoint Online](/sharepoint/default-sharepoint-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="703d9-163">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="703d9-164">Hoe verschilt een beveiligingsgroep van beveiligingsgroepen die ik in SharePoint maak?</span><span class="sxs-lookup"><span data-stu-id="703d9-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="703d9-165">Beveiligingsgroepen kunnen worden gebruikt met SharePoint, Exchange, MDM, Windows en meer.</span><span class="sxs-lookup"><span data-stu-id="703d9-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="703d9-166">Een beveiligingsgroep die u in SharePoint maakt, wordt alleen erkend door die SharePoint-siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="703d9-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="703d9-167">Moet ik beveiligingsgroepen gebruiken om mijn organisatie te beveiligen?</span><span class="sxs-lookup"><span data-stu-id="703d9-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="703d9-p111">Nee, dit is slechts een extra manier waarop u de beveiliging voor uw organisatie kunt beheren. U kunt altijd gebruikersmachtigingen en toegang tot sites op individuele basis verlenen. Met beveiligingsgroepen kunt u echter gemakkelijk grotere groepen gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="703d9-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="703d9-172">Kan ik e-mail verzenden naar een beveiligingsgroep?</span><span class="sxs-lookup"><span data-stu-id="703d9-172">Can I send email to a security group?</span></span>

<span data-ttu-id="703d9-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="703d9-173">Yes.</span></span> <span data-ttu-id="703d9-174">Maar als u groepen wilt gebruiken voor e-mail en samenwerking, raden we u aan in plaats daarvan een [Microsoft 365-groep te](../create-groups/create-groups.md) maken.</span><span class="sxs-lookup"><span data-stu-id="703d9-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
