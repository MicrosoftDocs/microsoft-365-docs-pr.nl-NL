---
title: Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 beheercentrum
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informatie over het maken, bewerken of verwijderen van een beveiligingsgroep.
ms.openlocfilehash: 7887a6371287ebef3a91cc1a37f2ed696df1948d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623999"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ce3bc-103">Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="ce3bc-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ce3bc-104">Op de Microsoft 365 **groepen** kunt u groepen gebruikersaccounts maken die u kunt gebruiken om dezelfde machtigingen toe te wijzen in SharePoint Online en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="ce3bc-105">Een beheerder kan bijvoorbeeld een beveiligingsgroep maken om een bepaalde groep personen toegang te verlenen tot een SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="ce3bc-106">Alleen globale beheerders en beheerders van gebruikersbeheer hebben machtigingen voor het maken, bewerken of verwijderen van beveiligingsgroepen. Zie Beheerdersrollen toewijzen voor meer informatie over [beheerdersrollen.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="ce3bc-107">Er zijn ook [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) die u kunt gebruiken om e-mail te verzenden of machtigingen toe te wijzen aan een groep gebruikers, en [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) waarmee u gebruikers rechten en toegang kunt geven tot sites en siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="ce3bc-108">Bent u van plan sitepostvakken te gebruiken?</span><span class="sxs-lookup"><span data-stu-id="ce3bc-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="ce3bc-109">Alle gebruikers die zijn toegevoegd aan een SharePoint-site via een beveiligingsgroep in plaats van individueel, kunnen het sitepostvak alleen gebruiken vanuit SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="ce3bc-110">Deze gebruikers hebben geen toegang tot het sitepostvak vanuit Outlook.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="ce3bc-111">Zie Groepen gebruiken Microsoft 365 in plaats van [teampostvakken](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="ce3bc-112">Beveiligingsgroepen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="ce3bc-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="ce3bc-113">Een beveiligingsgroep toevoegen</span><span class="sxs-lookup"><span data-stu-id="ce3bc-113">Add a security group</span></span>

1. <span data-ttu-id="ce3bc-114">Ga in Microsoft 365 beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a></span><span class="sxs-lookup"><span data-stu-id="ce3bc-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce3bc-115">Selecteer op **de** pagina Groepen de optie **Een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="ce3bc-116">Kies op **de pagina Een groeptype** kiezen de optie **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="ce3bc-117">Volg de stappen om het maken van de groep te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="ce3bc-118">Leden toevoegen aan een beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="ce3bc-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="ce3bc-119">Selecteer de naam van de beveiligingsgroep op **de** pagina Groepen en selecteer op **het** tabblad Leden de optie Alle leden weergeven **en leden beheren.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="ce3bc-120">Selecteer in het groepsdeelvenster Leden **toevoegen** en kies de persoon in de lijst  of typ de naam van de persoon die u wilt toevoegen in het vak Zoeken en selecteer **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="ce3bc-121">Als u leden wilt verwijderen, selecteert u de X naast de naam.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="ce3bc-122">Een beveiligingsgroep bewerken</span><span class="sxs-lookup"><span data-stu-id="ce3bc-122">Edit a security group</span></span>

1. <span data-ttu-id="ce3bc-123">Ga in het beheercentrum  naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a></span><span class="sxs-lookup"><span data-stu-id="ce3bc-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce3bc-124">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce3bc-125">Selecteer in het instellingenvenster **het** tabblad Algemeen of het tabblad **Leden** om groepsdetails of leden te bewerken.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="ce3bc-126">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="ce3bc-126">Delete a security group</span></span>

1. <span data-ttu-id="ce3bc-127">Ga in het beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a></span><span class="sxs-lookup"><span data-stu-id="ce3bc-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="ce3bc-128">Selecteer op **de** pagina Groepen de naam van de groep.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce3bc-129">Selecteer **Groep verwijderen** (pictogram wasetbin) en bevestig vervolgens door Verwijderen te **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="ce3bc-130">Selecteer **Sluiten zodra** de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="ce3bc-131">Groepen in Exchange Online en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce3bc-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="ce3bc-132">Als u groepen gebruikers wilt maken zodat u tegelijkertijd e-mail naar hen kunt verzenden, kunt u dat doen in het Exchange-beheercentrum door naar **Beheerders** Exchange Groepen geadresseerden te \>  \>  \> **gaan.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="ce3bc-133">Selecteer vervolgens **Nieuw** ![ toevoegen en selecteer het type groep dat u wilt ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) maken:</span><span class="sxs-lookup"><span data-stu-id="ce3bc-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="ce3bc-134">**Distributiegroep**: deze groep wordt gebruikt om berichten te verzenden naar een groep gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="ce3bc-135">Het wordt ook wel een *distributiegroep met e-mail* of een *distributielijst genoemd.*</span><span class="sxs-lookup"><span data-stu-id="ce3bc-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="ce3bc-136">Zie Distributiegroepen beheren voor [meer informatie.](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="ce3bc-137">**Beveiligingsgroep**: deze groep kan worden gebruikt om berichten te verzenden naar een groep gebruikers of om toegangsrechten te verlenen aan resources.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="ce3bc-138">Deze groep wordt ook wel een *beveiligingsgroep met e-mail genoemd.*</span><span class="sxs-lookup"><span data-stu-id="ce3bc-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="ce3bc-139">Zie Beveiligingsgroepen met [e-mail beheren](/Exchange/recipients/mail-enabled-security-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="ce3bc-140">**Dynamische distributiegroep**: dit is een type distributiegroep waarbij de lijst met geadresseerden telkens opnieuw berekend wanneer u een bericht verzendt op basis van filters en voorwaarden die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="ce3bc-141">Zie Dynamische distributiegroepen beheren voor [meer informatie.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="ce3bc-142">Nadat u distributiegroepen en beveiligingsgroepen met e-mail hebt gemaakt in het Exchange beheercentrum, worden hun namen en gebruikerslijsten weergegeven op de pagina **Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="ce3bc-143">U kunt deze groepen op beide locaties verwijderen, maar u kunt ze alleen bewerken in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="ce3bc-144">Dynamische distributiegroepen worden niet weergegeven op de pagina **Beveiligingsgroepen.**</span><span class="sxs-lookup"><span data-stu-id="ce3bc-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="ce3bc-145">SharePoint-groepen worden automatisch gemaakt wanneer u een siteverzameling maakt.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="ce3bc-146">De standaardgroepen gebruiken de standaardmachtigingsniveaus in SharePoint (soms ook wel SharePoint-rollen genaamd) om gebruikers rechten en toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="ce3bc-147">Zie Standaardgroepen in [SharePoint online SharePoint voor meer informatie.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="ce3bc-148">Hoe verschilt een beveiligingsgroep van beveiligingsgroepen die ik maak in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="ce3bc-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="ce3bc-149">Beveiligingsgroepen kunnen worden gebruikt met SharePoint, Exchange, MDM, Windows en meer.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="ce3bc-150">Een beveiligingsgroep die u in SharePoint maakt, wordt alleen erkend door die SharePoint-siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="ce3bc-151">Moet ik beveiligingsgroepen gebruiken om mijn organisatie te beveiligen?</span><span class="sxs-lookup"><span data-stu-id="ce3bc-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="ce3bc-p110">Nee, dit is slechts een extra manier waarop u de beveiliging voor uw organisatie kunt beheren. U kunt altijd gebruikersmachtigingen en toegang tot sites op individuele basis verlenen. Met beveiligingsgroepen kunt u echter gemakkelijk grotere groepen gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="ce3bc-156">Kan ik e-mail verzenden naar een beveiligingsgroep?</span><span class="sxs-lookup"><span data-stu-id="ce3bc-156">Can I send email to a security group?</span></span>

<span data-ttu-id="ce3bc-157">Ja.</span><span class="sxs-lookup"><span data-stu-id="ce3bc-157">Yes.</span></span> <span data-ttu-id="ce3bc-158">Maar als u groepen wilt gebruiken voor e-mail en samenwerking, raden we u aan in plaats daarvan een Microsoft 365 [maken.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="ce3bc-159">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ce3bc-159">Related content</span></span>

<span data-ttu-id="ce3bc-160">[Een groep maken in het Microsoft 365 beheercentrum](../create-groups/create-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="ce3bc-161">[Uitleg over Microsoft 365 groepen aan uw gebruikers](../create-groups/explain-groups-knowledge-worker.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="ce3bc-162">[Een groep beheren in het Microsoft 365 beheercentrum](../create-groups/manage-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce3bc-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>