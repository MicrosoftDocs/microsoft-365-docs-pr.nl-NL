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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Leer een beveiligingsgroep maken, bewerken of verwijderen.
ms.openlocfilehash: 689adb46bdec4d4f669482af6b5467fdcf63482c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628877"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="efcca-103">Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="efcca-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="efcca-104">Op de pagina Microsoft **365-groepen** u groepen gebruikersaccounts maken waaraan u dezelfde machtigingen toewijzen in SharePoint Online en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="efcca-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="efcca-105">Een beheerder kan bijvoorbeeld een beveiligingsgroep maken om een bepaalde groep mensen toegang te verlenen tot een SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="efcca-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="efcca-106">Alleen beheerders van globale en gebruikersbeheer hebben machtigingen om beveiligingsgroepen te maken, te bewerken of te verwijderen. Zie [Beheerdersrollen toewijzen](../add-users/assign-admin-roles.md)voor meer informatie over beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="efcca-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="efcca-107">Er zijn ook [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) die u kunt gebruiken om e-mail te verzenden of machtigingen toe te wijzen aan een groep gebruikers, en [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) waarmee u gebruikers rechten en toegang kunt geven tot sites en siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="efcca-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="efcca-108">Bent u van plan sitepostvakken te gebruiken?</span><span class="sxs-lookup"><span data-stu-id="efcca-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="efcca-109">Alle gebruikers die zijn toegevoegd aan een SharePoint-site via een beveiligingsgroep in plaats van individueel, kunnen het sitepostvak alleen gebruiken vanuit SharePoint.</span><span class="sxs-lookup"><span data-stu-id="efcca-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="efcca-110">Deze gebruikers hebben geen toegang tot het sitepostvak vanuit Outlook.</span><span class="sxs-lookup"><span data-stu-id="efcca-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="efcca-111">Zie [Microsoft 365-groepen gebruiken in plaats van Site-postvakken](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="efcca-111">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="efcca-112">Beveiligingsgroepen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="efcca-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="efcca-113">Een beveiligingsgroep toevoegen</span><span class="sxs-lookup"><span data-stu-id="efcca-113">Add a security group</span></span>

1. <span data-ttu-id="efcca-114">Ga in het Microsoft 365-beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="efcca-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="efcca-115">Selecteer **op** de pagina Groepen de optie **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="efcca-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="efcca-116">Kies **beveiliging**op de pagina **Een groepstype** kiezen .</span><span class="sxs-lookup"><span data-stu-id="efcca-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="efcca-117">Volg de stappen om de creatie van de groep te voltooien.</span><span class="sxs-lookup"><span data-stu-id="efcca-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="efcca-118">Leden toevoegen aan een beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="efcca-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="efcca-119">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="efcca-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="efcca-120">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer op het tabblad **Leden** **alle objecten weergeven en leden beheren.**</span><span class="sxs-lookup"><span data-stu-id="efcca-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="efcca-121">Selecteer in het groepsvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="efcca-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="efcca-122">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="efcca-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efcca-123">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **Bewerken** naast **Leden**.</span><span class="sxs-lookup"><span data-stu-id="efcca-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="efcca-124">Selecteer in het groepsvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="efcca-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="efcca-125">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="efcca-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="efcca-126">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **Bewerken** naast **Leden**.</span><span class="sxs-lookup"><span data-stu-id="efcca-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="efcca-127">Selecteer in het groepsvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="efcca-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="efcca-128">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="efcca-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="efcca-129">Een beveiligingsgroep bewerken</span><span class="sxs-lookup"><span data-stu-id="efcca-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="efcca-130">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="efcca-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="efcca-131">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="efcca-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="efcca-132">Selecteer **op** de pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="efcca-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="efcca-133">Selecteer in het instellingenvenster het tabblad **Algemeen** of het tabblad **Leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="efcca-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efcca-134">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="efcca-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="efcca-135">Selecteer **op** de pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="efcca-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="efcca-136">Selecteer in het deelvenster Beveiligingsgroep de optie **Bewerken** naast het tabblad **Naam** of **leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="efcca-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="efcca-137">Nadat u wijzigingen hebt aangebracht, selecteert u **Sluiten** \> **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="efcca-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="efcca-138">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="efcca-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="efcca-139">Selecteer **op** de pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="efcca-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="efcca-140">Selecteer in het deelvenster Beveiligingsgroep de optie **Bewerken** naast het tabblad **Naam** of **leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="efcca-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="efcca-141">Nadat u wijzigingen hebt aangebracht, selecteert u **Sluiten** > **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="efcca-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="efcca-142">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="efcca-142">Delete a security group</span></span>

1. <span data-ttu-id="efcca-143">Ga in het beheercentrum naar de pagina **Groepen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="efcca-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="efcca-144">Selecteer **op** de pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="efcca-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="efcca-145">Selecteer **Groep verwijderen** (pictogram wastbin) en bevestig vervolgens door Verwijderen **te**selecteren.</span><span class="sxs-lookup"><span data-stu-id="efcca-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="efcca-146">Selecteer **Sluiten** zodra de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="efcca-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="efcca-147">Groepen in Exchange Online en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="efcca-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="efcca-148">Als u groepen gebruikers wilt maken zodat u ze allemaal tegelijk e-mail verzenden, u dat doen in het Exchange-beheercentrum door naar **Exchange** \> **ontvangersgroepen voor** \> **beheerdersuitwisseling** \> te gaan. **Groups**</span><span class="sxs-lookup"><span data-stu-id="efcca-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="efcca-149">Selecteer vervolgens **New**![Nieuwe](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)toevoegen en selecteer het type groep dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="efcca-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="efcca-150">**Distributiegroep**: deze groep wordt gebruikt om berichten te verzenden naar een groep gebruikers.</span><span class="sxs-lookup"><span data-stu-id="efcca-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="efcca-151">Het wordt ook wel een *distributiegroep met e-mail*of een *distributielijst genoemd.*</span><span class="sxs-lookup"><span data-stu-id="efcca-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="efcca-152">Zie [Distributiegroepen beheren](https://technet.microsoft.com/library/bb124513.aspx)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="efcca-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="efcca-153">**Beveiligingsgroep**: deze groep kan worden gebruikt om berichten te verzenden naar een groep gebruikers of om toegangsrechten te verlenen aan resources.</span><span class="sxs-lookup"><span data-stu-id="efcca-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="efcca-154">Deze groep wordt ook wel een *beveiligingsgroep met e-mail*genoemd.</span><span class="sxs-lookup"><span data-stu-id="efcca-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="efcca-155">Zie [Beveiligingsgroepen beheren voor](https://technet.microsoft.com/library/bb123521.aspx)meer informatie .</span><span class="sxs-lookup"><span data-stu-id="efcca-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="efcca-156">**Dynamische distributiegroep**: dit is een type distributiegroep waarbij de lijst met geadresseerden telkens opnieuw berekend wanneer u een bericht verzendt op basis van filters en voorwaarden die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="efcca-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="efcca-157">Zie [Dynamische distributiegroepen beheren](https://technet.microsoft.com/library/bb123722.aspx)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="efcca-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="efcca-158">Nadat u distributiegroepen en beveiligingsgroepen met e-mail hebt gemaakt in het Exchange-beheercentrum, worden hun namen en gebruikerslijsten weergegeven op de pagina **Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="efcca-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="efcca-159">U kunt deze groepen op beide locaties verwijderen, maar u kunt ze alleen bewerken in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="efcca-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="efcca-160">Dynamische distributiegroepen worden niet weergegeven op de pagina **Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="efcca-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="efcca-161">SharePoint-groepen worden automatisch gemaakt wanneer u een siteverzameling maakt.</span><span class="sxs-lookup"><span data-stu-id="efcca-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="efcca-162">De standaardgroepen gebruiken de standaardmachtigingsniveaus in SharePoint (soms ook wel SharePoint-rollen genaamd) om gebruikers rechten en toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="efcca-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="efcca-163">Zie [StandaardSharePoint-groepen in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="efcca-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="efcca-164">Waarin verschilt een beveiligingsgroep van beveiligingsgroepen die ik in SharePoint maak?</span><span class="sxs-lookup"><span data-stu-id="efcca-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="efcca-165">Beveiligingsgroepen kunnen worden gebruikt met SharePoint, Exchange, MDM, Windows en meer.</span><span class="sxs-lookup"><span data-stu-id="efcca-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="efcca-166">Een beveiligingsgroep die u in SharePoint maakt, wordt alleen erkend door die SharePoint-siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="efcca-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="efcca-167">Moet ik beveiligingsgroepen gebruiken om veilig te zijn voor mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="efcca-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="efcca-p110">Nee, dit is slechts een extra manier waarop u de beveiliging voor uw organisatie kunt beheren. U kunt altijd gebruikersmachtigingen en toegang tot sites op individuele basis verlenen. Met beveiligingsgroepen kunt u echter gemakkelijk grotere groepen gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="efcca-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="efcca-172">Kan ik e-mail sturen naar een beveiligingsgroep?</span><span class="sxs-lookup"><span data-stu-id="efcca-172">Can I send email to a security group?</span></span>

<span data-ttu-id="efcca-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="efcca-173">Yes.</span></span> <span data-ttu-id="efcca-174">Maar als u groepen wilt gebruiken voor e-mail en samenwerking, raden we u aan in plaats daarvan [een Microsoft 365-groep te maken.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="efcca-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
