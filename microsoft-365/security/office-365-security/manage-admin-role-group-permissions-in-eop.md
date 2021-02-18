---
title: Rollengroepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen informatie krijgen over het toewijzen of verwijderen van machtigingen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289923"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="b7c6e-103">Rollengroepen beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="b7c6e-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b7c6e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-104">**Applies to**</span></span>
-  [<span data-ttu-id="b7c6e-105">Zelfstandige versie van Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b7c6e-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="b7c6e-106">In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rollengroepen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="b7c6e-107">Als u een gebruiker toevoegt aan een rollengroep, krijgt de gebruiker machtigingen om specifieke beheertaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="b7c6e-108">U kunt gebruikers ook verwijderen uit rollengroepen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="b7c6e-109">Zie Machtigingen in de zelfstandige EOP voor meer informatie over rollen en [rollengroepen.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7c6e-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b7c6e-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b7c6e-111">Als u het Exchange-beheercentrum (EAC) wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b7c6e-112">Zie Connect to Exchange Online Protection PowerShell (Verbinding [maken met Exchange Online Protection PowerShell)](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)als u de zelfstandige EOP PowerShell wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b7c6e-113">U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="b7c6e-114">U hebt met name de **rol Rollenbeheer**  nodig, die standaard is toegewezen aan de rollengroep Organisatiebeheer.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="b7c6e-115">Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="b7c6e-116">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b7c6e-117">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="b7c6e-117">Having problems?</span></span> <span data-ttu-id="b7c6e-118">Vraag om hulp op het forum [van Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="b7c6e-119">Het EAC gebruiken om rollengroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="b7c6e-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="b7c6e-120">Het EAC gebruiken om rollengroepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="b7c6e-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="b7c6e-121">Ga in het Exchange-beheercentrum naar **Beheerdersrollen** \> **voor machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="b7c6e-122">Alle rollengroepen in uw organisatie worden hier vermeld.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="b7c6e-123">Selecteer een rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-123">Select a role group.</span></span> <span data-ttu-id="b7c6e-124">Het deelvenster Details bevat **de naam,** **beschrijving,** **toegewezen rollen** en beheerd **door** de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="b7c6e-125">U kunt deze informatie ook zien door op het **pictogram** Bewerken ![ te ](../../media/ITPro-EAC-EditIcon.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="b7c6e-126">Het EAC gebruiken om rollengroepen te maken</span><span class="sxs-lookup"><span data-stu-id="b7c6e-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="b7c6e-127">Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen zelf configureren (tijdens het maken van de groep of er daarna).</span><span class="sxs-lookup"><span data-stu-id="b7c6e-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="b7c6e-128">U kunt ook een bestaande rollengroep kopiëren en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="b7c6e-129">Ga in het Exchange-beheercentrum naar de rollen **van Machtigingenbeheerder** \> en ga vervolgens op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="b7c6e-130">**Maak handmatig een nieuwe rollengroep:** klik op **het pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="b7c6e-131">**Een bestaande rollengroep kopiëren:** Selecteer de rollengroep die u wilt kopiëren en klik op **het pictogram** ![ ](../../media/ITPro-EAC-CopyIcon.png) Kopiëren.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="b7c6e-132">Configureer **de volgende instellingen** in het venster Nieuwe rollengroep dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="b7c6e-133">**Naam:** voer een unieke naam in voor de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="b7c6e-134">**Beschrijving:** voer een optionele beschrijving in voor de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="b7c6e-135">**Rollen:** klik op **het pictogram** Toevoegen of verwijderen om de rollen te selecteren of te wijzigen die aan de ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="b7c6e-136">**Leden:** klik op **het pictogram** Toevoegen of ![ het ](../../media/ITPro-EAC-AddIcon.png) **pictogram** Verwijderen om het lidmaatschap van ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="b7c6e-137">Wanneer u klaar bent, klikt u op **Opslaan om** de rollengroep te maken.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="b7c6e-138">Het EAC gebruiken om rollengroepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b7c6e-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="b7c6e-139">Ga in het Exchange-beheercentrum naar Rollen **van machtigingenbeheerder,** selecteer de rollengroep die u wilt wijzigen en klik vervolgens op \>  **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="b7c6e-140">Dezelfde opties zijn beschikbaar wanneer u rollengroepen wijzigt als wanneer u rollengroepen maakt.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="b7c6e-141">U kunt:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-141">You can:</span></span>

- <span data-ttu-id="b7c6e-142">Wijzig de naam en beschrijving.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-142">Change the name and description.</span></span>

- <span data-ttu-id="b7c6e-143">Beheerrollen toevoegen en verwijderen (roltoewijzingen maken of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="b7c6e-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="b7c6e-144">Leden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-144">Add and remove members.</span></span>

<span data-ttu-id="b7c6e-145">**Opmerking:** sommige rollengroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="b7c6e-146">De lijst met leden in rollengroepen wijzigen met het EAC</span><span class="sxs-lookup"><span data-stu-id="b7c6e-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="b7c6e-147">Ga in het Exchange-beheercentrum naar Rollen **van machtigingenbeheerder,** selecteer de rollengroep die u wilt wijzigen en klik vervolgens op \>  **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="b7c6e-148">Ga op een van de volgende  stappen te werk op de pagina eigenschappen van rollengroep die wordt geopend in de sectie Leden:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="b7c6e-149">Klik **op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b7c6e-150">Zoek op de pagina die wordt weergegeven de gebruiker die u wilt toevoegen en klik op **->.**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="b7c6e-151">Selecteer gebruikers en klik **zo vaak** als nodig >toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="b7c6e-152">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="b7c6e-153">Selecteer de gebruikers die u wilt verwijderen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b7c6e-154">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7c6e-155">Gebruikers moeten zich mogelijk afloggen en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toevoegt aan of verwijderd uit de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="b7c6e-156">Het EAC gebruiken om rollengroepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b7c6e-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="b7c6e-157">U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt wel aangepaste rollengroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="b7c6e-158">Ga in het Exchange-beheercentrum naar **Beheerdersrollen** \> **voor machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="b7c6e-159">Selecteer de rollengroep die u wilt verwijderen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="b7c6e-160">Klik **op Ja** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="b7c6e-161">PowerShell gebruiken om rollengroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="b7c6e-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="b7c6e-162">Zelfstandige EOP PowerShell gebruiken om rollengroepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="b7c6e-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="b7c6e-163">Gebruik de volgende syntaxis om een rollengroep weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="b7c6e-164">In dit voorbeeld wordt een overzichtslijst van alle rollengroepen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="b7c6e-165">In dit voorbeeld wordt gedetailleerde informatie gegeven over de rollengroep met de naam Ontvangersbeheerders.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="b7c6e-166">In dit voorbeeld worden alle rollengroepen als retourneert waar de gebruiker Julia lid van is.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="b7c6e-167">U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u kunt vinden door de opdracht uit te `Get-User -Identity Julia | Format-List DistinguishedName` voeren:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="b7c6e-168">Zie [Get-RoleGroup voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="b7c6e-169">Zelfstandige EOP PowerShell gebruiken om rollengroepen te maken</span><span class="sxs-lookup"><span data-stu-id="b7c6e-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="b7c6e-170">Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen handmatig configureren (tijdens het maken van de groep of er waarna).</span><span class="sxs-lookup"><span data-stu-id="b7c6e-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="b7c6e-171">U kunt ook een bestaande rollengroep kopiëren en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="b7c6e-172">Gebruik de volgende syntaxis om handmatig een nieuwe rollengroep te maken:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="b7c6e-173">Met de parameter _Rollen_ worden de beheerrollen opgegeven die moeten worden toegewezen aan de rollengroep met behulp van de volgende `"Role1","Role1",..."RoleN"` syntaxis.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="b7c6e-174">U kunt de beschikbare rollen zien met behulp van de cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="b7c6e-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="b7c6e-175">De parameter _Leden_ geeft de leden van de rollengroep aan met behulp van de volgende `"Member1","Member2",..."MemberN"` syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="b7c6e-176">U kunt gebruikers, usgs (mail-enabled universal security groups) of andere rollengroepen (security principals) opgeven.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="b7c6e-177">In dit voorbeeld wordt een nieuwe rollengroep met de naam Beperkt beheer van geadresseerden gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="b7c6e-178">De rol E-mailontvangers wordt toegewezen aan de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="b7c6e-179">De gebruikers Kim en Martin worden toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="b7c6e-180">Ga als volgt te werk om een bestaande rollengroep te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="b7c6e-181">Sla de rollengroep die u wilt kopiëren op in een variabele met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="b7c6e-182">Maak de nieuwe rollengroep met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="b7c6e-183">De parameter _Leden_ geeft de leden van de rollengroep aan met behulp van de volgende `"Member1","Member2",..."MemberN"` syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="b7c6e-184">U kunt gebruikers, usgs (mail-enabled universal security groups) of andere rollengroepen (security principals) opgeven.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="b7c6e-185">In dit voorbeeld wordt de rollengroep Organisatiebeheer gekopieerd naar de nieuwe rollengroep genaamd Beperkt organisatiebeheer.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="b7c6e-186">De leden van de rollengroep zijn Aek, Deze en Lukas.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="b7c6e-187">Voor gedetailleerde syntaxis- en parameterinformatie, [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="b7c6e-188">De lijst met leden in rollengroepen wijzigen met zelfstandige EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c6e-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="b7c6e-189">Met de cmdlets **Add-RoleGroupMember** en **Remove-RoleGroupMember** kunt u afzonderlijke leden een voor een toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="b7c6e-190">De **cmdlet Update-RoleGroupMember** kan de bestaande lijst met leden vervangen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="b7c6e-191">De leden van een rollengroep kunnen gebruikers, USG's (Universal Security Groups) met e-mail of andere rollengroepen (beveiligings-principals) zijn.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="b7c6e-192">Gebruik de volgende syntaxis om de leden van een rollengroep te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="b7c6e-193">Gebruik _de_ volgende syntaxis om de bestaande lijst met leden te vervangen door de waarden die u opgeeft: `"Member1","Member2",..."MemberN"`</span><span class="sxs-lookup"><span data-stu-id="b7c6e-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="b7c6e-194">Gebruik _de volgende_ syntaxis om de bestaande lijst met leden selectief te wijzigen: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`</span><span class="sxs-lookup"><span data-stu-id="b7c6e-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="b7c6e-195">In dit voorbeeld worden alle huidige leden van de rollengroep Helpdesk vervangen door de opgegeven gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="b7c6e-196">In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Wordt Erdodo verwijderd uit de lijst met leden van de rollengroep Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="b7c6e-197">Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="b7c6e-198">Zelfstandige EOP PowerShell gebruiken om rollengroepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b7c6e-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="b7c6e-199">U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt wel aangepaste rollengroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="b7c6e-200">Gebruik de volgende syntaxis om een aangepaste rollengroep te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="b7c6e-201">In dit voorbeeld wordt de rollengroep Trainingsbeheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="b7c6e-202">Zie [Remove-RoleGroup voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="b7c6e-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b7c6e-203">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="b7c6e-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="b7c6e-204">Ga op een van de volgende stappen te werk om te controleren of u een rollengroep hebt gekopieerd:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="b7c6e-205">Ga in het Exchange-beheercentrum naar Beheerdersrollen voor machtigingen en controleer of de rollengroep wordt vermeld  \> (of niet wordt weergegeven).</span><span class="sxs-lookup"><span data-stu-id="b7c6e-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="b7c6e-206">Selecteer de rollengroep en controleer de instellingen  in het deelvenster Details of klik op het ![ pictogram Bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) controleren.</span><span class="sxs-lookup"><span data-stu-id="b7c6e-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="b7c6e-207">Vervang in Exchange Online PowerShell door de naam van de rollengroep en voer de volgende opdracht uit om te controleren of de rollengroep bestaat (of bestaat niet) en controleer de \<Role Group Name\> instellingen:</span><span class="sxs-lookup"><span data-stu-id="b7c6e-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
