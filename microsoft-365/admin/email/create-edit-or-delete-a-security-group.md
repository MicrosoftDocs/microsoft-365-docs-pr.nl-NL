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
description: Meer informatie over het maken, bewerken of verwijderen van een beveiligingsgroep.
ms.openlocfilehash: f51c21261a83e1a0034a67f9f1580dd297a3d583
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811752"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4127c-103">Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="4127c-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="4127c-p101">Op de pagina Office 365 **Groepen** kunt u groepen gebruikersaccounts maken waarmee u dezelfde machtigingen kunt toewijzen aan gebruikers in SharePoint Online en CRM Online. Een beheerder kan bijvoorbeeld een beveiligingsgroep maken om bepaalde gebruikers toegang te geven tot een SharePoint-site. Alleen globale beheerders en beheerders met de rol Gebruikersbeheer kunnen beveiligingsgroepen maken, wijzigen of verwijderen. Zie [Beheerdersrollen toewijzen](../add-users/assign-admin-roles.md) voor meer informatie over beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="4127c-p101">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online. For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site. Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="4127c-107">Er zijn ook [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) die u kunt gebruiken om e-mail te verzenden of machtigingen toe te wijzen aan een groep gebruikers, en [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) waarmee u gebruikers rechten en toegang kunt geven tot sites en siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="4127c-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4127c-108">Bent u van plan sitepostvakken te gebruiken?</span><span class="sxs-lookup"><span data-stu-id="4127c-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="4127c-109">Alle gebruikers die zijn toegevoegd aan een SharePoint-site via een beveiligingsgroep in plaats van individueel, kunnen het sitepostvak alleen gebruiken vanuit SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4127c-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="4127c-110">Deze gebruikers hebben geen toegang tot het sitepostvak vanuit Outlook.</span><span class="sxs-lookup"><span data-stu-id="4127c-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="4127c-111">Zie [Office 365-groepen gebruiken in plaats van Teampostvakken](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4127c-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="4127c-112">Beveiligingsgroepen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="4127c-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="4127c-113">Een beveiligingsgroep toevoegen</span><span class="sxs-lookup"><span data-stu-id="4127c-113">Add a security group</span></span>

1. <span data-ttu-id="4127c-114">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="4127c-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4127c-115">Selecteer op de pagina **Groepen** de optie **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4127c-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="4127c-116">Kies op de pagina **Een groepstype kiezen** voor **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="4127c-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="4127c-117">Volg de stappen om de creatie van de groep te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4127c-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="4127c-118">Leden toevoegen aan een beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="4127c-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4127c-119">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4127c-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="4127c-120">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer op het tabblad **Leden** alle weergave en **beheer leden**.</span><span class="sxs-lookup"><span data-stu-id="4127c-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="4127c-121">Selecteer in het groepsdeelvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4127c-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4127c-122">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="4127c-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4127c-123">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **Bewerken** naast **leden**.</span><span class="sxs-lookup"><span data-stu-id="4127c-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="4127c-124">Selecteer in het groepsdeelvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4127c-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4127c-125">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="4127c-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="4127c-126">Selecteer de naam van de beveiligingsgroep op de pagina **Groepen** en selecteer **Bewerken** naast **leden**.</span><span class="sxs-lookup"><span data-stu-id="4127c-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="4127c-127">Selecteer in het groepsdeelvenster **Leden toevoegen** en kies de persoon in de lijst of typ de naam van de persoon die u wilt toevoegen in het vak **Zoeken** en selecteer **Vervolgens Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4127c-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4127c-128">Als u leden wilt verwijderen, selecteert u de X naast hun naam.</span><span class="sxs-lookup"><span data-stu-id="4127c-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="4127c-129">Een beveiligingsgroep bewerken</span><span class="sxs-lookup"><span data-stu-id="4127c-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4127c-130">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4127c-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4127c-131">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="4127c-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4127c-132">Selecteer op de pagina **Groepen** de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="4127c-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4127c-133">Selecteer in het instellingenvenster het tabblad **Algemeen** of het tabblad **Leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="4127c-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4127c-134">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="4127c-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4127c-135">Selecteer op de pagina **Groepen** de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="4127c-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4127c-136">Selecteer in het deelvenster beveiligingsgroep de optie **Bewerken** naast het tabblad **Naam** of **Leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="4127c-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="4127c-137">Nadat u wijzigingen hebt aangebracht, selecteert u **Sluiten** \> **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4127c-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4127c-138">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="4127c-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4127c-139">Selecteer op de pagina **Groepen** de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="4127c-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4127c-140">Selecteer in het deelvenster beveiligingsgroep de optie **Bewerken** naast het tabblad **Naam** of **Leden** om groepsgegevens of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="4127c-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="4127c-141">Nadat u wijzigingen hebt aangebracht, selecteert u **Sluiten** \> **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4127c-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="4127c-142">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="4127c-142">Delete a security group</span></span>

1. <span data-ttu-id="4127c-143">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="4127c-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="4127c-144">Selecteer op de pagina **Groepen** de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="4127c-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4127c-145">Selecteer **Groep Verwijderen** (wasetbin-pictogram) en bevestig vervolgens door **Verwijderen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4127c-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="4127c-146">Selecteer **Sluiten** zodra de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="4127c-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="4127c-147">Groepen in Exchange Online en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4127c-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="4127c-148">Als u groepen gebruikers wilt maken, zodat u ze allemaal tegelijk verzenden, u dat doen in het Exchange-beheercentrum door naar \> **Ontvangersgroepen** **voor beheerdersuitwisseling** \> **Exchange** \> **Recipients** te gaan.</span><span class="sxs-lookup"><span data-stu-id="4127c-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="4127c-149">Selecteer vervolgens **New**![Nieuwe](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)toevoegen en selecteer het soort groep dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="4127c-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="4127c-150">**Distributiegroep**: deze groep wordt gebruikt om berichten te verzenden naar een groep gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4127c-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="4127c-151">Het wordt ook wel een distributiegroep met *e-mail*genoemd of, in Office 365, een *distributielijst.*</span><span class="sxs-lookup"><span data-stu-id="4127c-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="4127c-152">Zie [Distributiegroepen beheren](https://technet.microsoft.com/library/bb124513.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4127c-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="4127c-153">**Beveiligingsgroep**: deze groep kan worden gebruikt om berichten te verzenden naar een groep gebruikers of om toegangsrechten te verlenen aan resources.</span><span class="sxs-lookup"><span data-stu-id="4127c-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="4127c-154">Deze groep wordt ook wel een *e-mailbeveiligingsgroep*genoemd.</span><span class="sxs-lookup"><span data-stu-id="4127c-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="4127c-155">Zie [Beveiligingsgroepen met e-mail beheren](https://technet.microsoft.com/library/bb123521.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4127c-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="4127c-156">**Dynamische distributiegroep**: dit is een type distributiegroep waarbij de lijst met geadresseerden telkens opnieuw berekend wanneer u een bericht verzendt op basis van filters en voorwaarden die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="4127c-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="4127c-157">Zie [Dynamische distributiegroepen beheren](https://technet.microsoft.com/library/bb123722.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4127c-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="4127c-p107">Nadat u distributiegroepen en beveiligingsgroepen met e-mail hebt gemaakt in het Exchange-beheercentrum, worden de namen en gebruikerslijsten ervan weergegeven op de pagina **Beveiligingsgroepen** in Office 365. U kunt deze groepen op beide locaties verwijderen, maar u kunt ze alleen bewerken in het Exchange-beheercentrum. Dynamische distributiegroepen worden niet weergegeven op de pagina **Beveiligingsgroepen** in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4127c-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="4127c-161">SharePoint-groepen worden automatisch gemaakt wanneer u een siteverzameling maakt.</span><span class="sxs-lookup"><span data-stu-id="4127c-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="4127c-162">De standaardgroepen gebruiken de standaardmachtigingsniveaus in SharePoint (soms ook wel SharePoint-rollen genaamd) om gebruikers rechten en toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="4127c-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="4127c-163">Zie [StandaardSharePoint-groepen in SharePoint Online voor](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4127c-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="4127c-164">Hoe verschilt een beveiligingsgroep van beveiligingsgroepen die ik maak in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="4127c-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="4127c-165">Beveiligingsgroepen kunnen worden gebruikt met SharePoint, Exchange, MDM, Windows en meer.</span><span class="sxs-lookup"><span data-stu-id="4127c-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="4127c-166">Een beveiligingsgroep die u in SharePoint maakt, wordt alleen erkend door die SharePoint-siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="4127c-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="4127c-167">Moet ik beveiligingsgroepen gebruiken om mijn organisatie veilig te maken?</span><span class="sxs-lookup"><span data-stu-id="4127c-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="4127c-p110">Nee, dit is slechts een extra manier waarop u de beveiliging voor uw organisatie kunt beheren. U kunt altijd gebruikersmachtigingen en toegang tot sites op individuele basis verlenen. Met beveiligingsgroepen kunt u echter gemakkelijk grotere groepen gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="4127c-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="4127c-172">Kan ik e-mail sturen naar een beveiligingsgroep?</span><span class="sxs-lookup"><span data-stu-id="4127c-172">Can I send email to a security group?</span></span>

<span data-ttu-id="4127c-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="4127c-173">Yes.</span></span> <span data-ttu-id="4127c-174">Maar als u groepen wilt gebruiken voor e-mail en samenwerking, raden we u aan in plaats daarvan [een Office 365-groep te maken.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4127c-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
