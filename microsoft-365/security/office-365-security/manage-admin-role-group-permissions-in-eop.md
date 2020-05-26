---
title: Rolgroepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen leren hoe u machtigingen toewijzen of verwijderen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.openlocfilehash: ba2d053e1e75bd8867ebb9eb7f426cde92abd3e8
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352333"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="e8ae0-103">Rollengroepen beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="e8ae0-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="e8ae0-104">In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rolgroepen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="e8ae0-105">Als u een gebruikers toevoegt aan een rolgroep, geeft de gebruiker machtigingen om specifieke beheertaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="e8ae0-106">U gebruikers ook verwijderen uit rolgroepen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="e8ae0-107">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen en rolgroepen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8ae0-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e8ae0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8ae0-109">Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum (EAC) wilt openen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e8ae0-110">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u zelfstandige EOP PowerShell wilt openen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e8ae0-111">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e8ae0-112">U hebt in het bijzonder de rolbeheerrol nodig, die standaard is toegewezen aan de rolgroep OrganizationManagement (globale beheerders).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="e8ae0-113">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="e8ae0-114">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e8ae0-115">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="e8ae0-115">Having problems?</span></span> <span data-ttu-id="e8ae0-116">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="e8ae0-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="e8ae0-117">De EAC gebruiken om rolgroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="e8ae0-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="e8ae0-118">De EAC gebruiken om rolgroepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e8ae0-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="e8ae0-119">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="e8ae0-120">Alle rolgroepen in uw organisatie worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="e8ae0-121">Selecteer een rolgroep.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-121">Select a role group.</span></span> <span data-ttu-id="e8ae0-122">In het deelvenster Details wordt de **naam**, **beschrijving**, **toegewezen rollen**en beheerd **door** van de rolgroep weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="e8ae0-123">U deze informatie ook bekijken door op pictogram Bewerken **bewerken** te klikken ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="e8ae0-124">De EAC gebruiken om rolgroepen te maken</span><span class="sxs-lookup"><span data-stu-id="e8ae0-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="e8ae0-125">Wanneer u een nieuwe rolgroep maakt, u alle instellingen zelf configureren (tijdens het maken van de groep of erna).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="e8ae0-126">U ook een bestaande rolgroep kopiëren en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="e8ae0-127">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**en voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="e8ae0-128">**Handmatig een nieuwe rolgroep maken:** **Klik** op ![ Pictogram Toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="e8ae0-129">**Een bestaande rolgroep kopiëren:** selecteer de rolgroep die u wilt kopiëren en **klik** op ![ Pictogram Kopiëren ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="e8ae0-130">Configureer in het venster **Nieuwe rolgroep** dat wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="e8ae0-131">**Naam:** Voer een unieke naam in voor de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="e8ae0-132">**Beschrijving**: Voer een optionele beschrijving in voor de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="e8ae0-133">**Rollen**: **Klik** op ![ Pictogram Toevoegen toevoegen of ](../../media/ITPro-EAC-AddIcon.png) **VERWIJDEREN** ![ VAN ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) om de rollen te selecteren of te wijzigen die aan de rolgroep zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="e8ae0-134">**Leden**: Klik op **Pictogram** ![ Toevoegen toevoegen of ](../../media/ITPro-EAC-AddIcon.png) **VERWIJDEREN** ![ ITPro-EAC-RemoveIcon.gif om het lidmaatschap van de ](../../media/ITPro-EAC-RemoveIcon.gif) rolgroep te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="e8ae0-135">Wanneer u klaar bent, klikt u op **Opslaan** om de rolgroep te maken.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="e8ae0-136">De EAC gebruiken om rolgroepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e8ae0-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="e8ae0-137">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder,** selecteer de rolgroep die u wilt wijzigen en klik vervolgens op Pictogram Bewerken **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="e8ae0-138">Dezelfde opties zijn beschikbaar wanneer u rolgroepen wijzigt als wanneer u rolgroepen maakt.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="e8ae0-139">U kunt:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-139">You can:</span></span>

- <span data-ttu-id="e8ae0-140">Wijzig de naam en beschrijving.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-140">Change the name and description.</span></span>

- <span data-ttu-id="e8ae0-141">Beheerrollen toevoegen en verwijderen (roltoewijzingen maken of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="e8ae0-142">Leden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-142">Add and remove members.</span></span>

<span data-ttu-id="e8ae0-143">**Opmerking:** Sommige rolgroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="e8ae0-144">De EAC wijzigen van de lijst met leden in rolgroepen</span><span class="sxs-lookup"><span data-stu-id="e8ae0-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="e8ae0-145">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder,** selecteer de rolgroep die u wilt wijzigen en klik vervolgens op Pictogram Bewerken **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="e8ae0-146">Ga in de pagina eigenschappen van de rolgroep die wordt geopend in de sectie **Memebers** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="e8ae0-147">Klik **op** Pictogram Toevoegen ![ toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="e8ae0-148">Zoek op de pagina die wordt weergegeven de gebruiker die wou wil toevoegen en klik vervolgens op **toevoegen ->**.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="e8ae0-149">Selecteer gebruikers en klik op **toevoegen ->** vele malen als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="e8ae0-150">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="e8ae0-151">Selecteer de gebruikers die u wilt **Remove** verwijderen en klik op ![ Pictogram Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="e8ae0-152">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e8ae0-153">Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toegevoegd of verwijderd uit de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="e8ae0-154">De EAC gebruiken om rolgroepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e8ae0-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="e8ae0-155">U ingebouwde rolgroepen niet verwijderen, maar u wel aangepaste rolgroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="e8ae0-156">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="e8ae0-157">Selecteer de rolgroep die u wilt verwijderen en **klik** op Pictogram ![ Verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="e8ae0-158">Klik **op Ja** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="e8ae0-159">PowerShell gebruiken om rolgroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="e8ae0-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="e8ae0-160">Zelfstandige EOP PowerShell gebruiken om rolgroepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e8ae0-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="e8ae0-161">Als u een rolgroep wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="e8ae0-162">In dit voorbeeld wordt een overzichtslijst met alle rolgroepen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="e8ae0-163">In dit voorbeeld worden gedetailleerde informatie geretourneerd voor de rolgroep met de naam Geadresseerde beheerders.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="e8ae0-164">In dit voorbeeld worden alle rolgroepen geretourneerd waarvan de gebruiker Julia lid is.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="e8ae0-165">U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="e8ae0-166">Zie Groep voor rollen [en](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)parameters voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="e8ae0-167">Zelfstandige EOP PowerShell gebruiken om rolgroepen te maken</span><span class="sxs-lookup"><span data-stu-id="e8ae0-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="e8ae0-168">Wanneer u een nieuwe rolgroep maakt, u alle instellingen handmatig configureren (tijdens het maken van de groep of erna).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="e8ae0-169">U ook een bestaande rolgroep kopiëren en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="e8ae0-170">Als u handmatig een nieuwe rolgroep wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="e8ae0-171">De parameter _Rollen_ geeft de beheerrollen op die aan de rolgroep moeten worden toegewezen met behulp van de volgende syntaxis `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="e8ae0-172">U de beschikbare rollen bekijken met de cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="e8ae0-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="e8ae0-173">De parameter _Leden_ geeft de leden van de rolgroep op met behulp van de volgende syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="e8ae0-174">U gebruikers, universele beveiligingsgroepen (USG's) met e-mail of andere rolgroepen (beveiligingsprincipals) opgeven.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="e8ae0-175">In dit voorbeeld wordt een nieuwe rolgroep gemaakt met de naam 'Beheer van beperkte geadresseerden' met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="e8ae0-176">De rol E-mailgeadresseerden is toegewezen aan de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="e8ae0-177">De gebruikers Kim en Martin worden toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="e8ae0-178">Ga als volgt te werk om een bestaande rolgroep te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="e8ae0-179">Sla de rolgroep op die u wilt kopiëren in een variabele met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="e8ae0-180">Maak de nieuwe rolgroep met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="e8ae0-181">De parameter _Leden_ geeft de leden van de rolgroep op met behulp van de volgende syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="e8ae0-182">U gebruikers, universele beveiligingsgroepen (USG's) met e-mail of andere rolgroepen (beveiligingsprincipals) opgeven.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="e8ae0-183">In dit voorbeeld wordt de rolgroep Organisatiebeheer overgemaakt naar de nieuwe rolgroep met de naam 'Limited Organization Management'.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="e8ae0-184">De leden van de rolgroep zijn Isabelle, Carter en Lukas.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="e8ae0-185">Voor gedetailleerde syntaxis- en parameterinformatie, [Nieuw-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="e8ae0-186">De lijst met leden in rolgroepen wijzigen door zelfstandige EOP PowerShell te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e8ae0-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="e8ae0-187">De cmdlets **Add-RoleGroupMember** en **Remove-RoleGroupMember** voegen afzonderlijke leden één voor één toe of verwijderen deze af.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="e8ae0-188">De cmdlet **Update-RoleGroupMember** kan de bestaande lijst met leden vervangen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="e8ae0-189">De leden van een rolgroep kunnen gebruikers, universele beveiligingsgroepen (USG's) of andere rolgroepen (beveiligingsprincipals) zijn.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="e8ae0-190">Als u de leden van een rolgroep wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="e8ae0-191">Als u de bestaande lijst met leden wilt _vervangen_ door de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="e8ae0-192">Als u de bestaande lijst met leden selectief wilt _wijzigen,_ gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="e8ae0-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="e8ae0-193">In dit voorbeeld worden alle huidige leden van de rolgroep Helpdesk vervangen door de opgegeven gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="e8ae0-194">In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd van de ledenlijst van de rolgroep Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="e8ae0-195">Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="e8ae0-196">Zelfstandige EOP PowerShell gebruiken om rolgroepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e8ae0-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="e8ae0-197">U ingebouwde rolgroepen niet verwijderen, maar u wel aangepaste rolgroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="e8ae0-198">Als u een aangepaste rolgroep wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="e8ae0-199">In dit voorbeeld wordt de rolgroep Trainingsbeheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="e8ae0-200">Zie Groep verwijderen en [parameteren](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e8ae0-201">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="e8ae0-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="e8ae0-202">Ga op een van de volgende stappen te werk om te controleren of u een rolgroep hebt gekopieerd:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="e8ae0-203">Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**en controleer of de rolgroep wordt weergegeven (of niet wordt vermeld).</span><span class="sxs-lookup"><span data-stu-id="e8ae0-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="e8ae0-204">Selecteer de rolgroep en controleer de instellingen **Edit** in het deelvenster Details of klik op ![ Pictogram Bewerken bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.</span><span class="sxs-lookup"><span data-stu-id="e8ae0-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="e8ae0-205">Vervang in Exchange Online PowerShell \< de naam van de rolgroep door de naam van de \> rolgroep en voer de volgende opdracht uit om te controleren of de rolgroep bestaat (of bestaat niet) en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="e8ae0-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
