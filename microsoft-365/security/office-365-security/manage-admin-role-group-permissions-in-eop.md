---
title: Rollen groepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen informatie lezen over het toewijzen of verwijderen van machtigingen in het Exchange-Beheercentrum in Exchange Online Protection.
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659295"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="56b2d-103">Rollengroepen beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="56b2d-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="56b2d-104">In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u het Exchange-Beheercentrum (SBV) gebruiken om gebruikers toe te voegen aan rollen groepen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="56b2d-105">Door een gebruiker toe te voegen aan een rollen groep, krijgt u de gebruikersmachtigingen om specifieke beheertaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="56b2d-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="56b2d-106">U kunt gebruikers ook verwijderen uit rollen groepen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="56b2d-107">Zie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen en rollen groepen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="56b2d-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="56b2d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="56b2d-109">U opent het Exchange-Beheercentrum door het Exchange- [Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="56b2d-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="56b2d-110">U opent zelfstandige EOP PowerShell via [verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="56b2d-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="56b2d-111">U moet machtigingen zijn toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="56b2d-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="56b2d-112">Specifiek hebt u de rol van **rollenbeheer** nodig die standaard aan de rollen groep **Organisatiebeheer** is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-112">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="56b2d-113">Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="56b2d-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="56b2d-114">Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="56b2d-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="56b2d-115">Problemen?</span><span class="sxs-lookup"><span data-stu-id="56b2d-115">Having problems?</span></span> <span data-ttu-id="56b2d-116">Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="56b2d-117">Het Beheercentrum gebruiken om rollen groepen te beheren</span><span class="sxs-lookup"><span data-stu-id="56b2d-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="56b2d-118">Het Exchange-Beheercentrum gebruiken om rollen groepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="56b2d-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="56b2d-119">Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**.</span><span class="sxs-lookup"><span data-stu-id="56b2d-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="56b2d-120">Alle rollen groepen in uw organisatie worden hier vermeld.</span><span class="sxs-lookup"><span data-stu-id="56b2d-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="56b2d-121">Selecteer een rollen groep.</span><span class="sxs-lookup"><span data-stu-id="56b2d-121">Select a role group.</span></span> <span data-ttu-id="56b2d-122">In het deelvenster Details worden de **naam**, de **Beschrijving**, de **toegewezen rollen** en de **beheerde** rollen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="56b2d-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="56b2d-123">U kunt deze informatie ook zien door te  klikken op het ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="56b2d-124">Gebruik de functie SBV om rollen groepen te maken</span><span class="sxs-lookup"><span data-stu-id="56b2d-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="56b2d-125">Wanneer u een nieuwe rollen groep maakt, kunt u alle instellingen zelf configureren (tijdens het maken van de groep of na).</span><span class="sxs-lookup"><span data-stu-id="56b2d-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="56b2d-126">U kunt ook een bestaande rollen groep kopiëren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="56b2d-127">Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerders** en voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="56b2d-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="56b2d-128">**Handmatig een nieuwe rollen groep maken**:  Klik op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="56b2d-129">**Een bestaande rolgroep kopiëren**: Selecteer de rollen groep die u wilt kopiëren en klik op het pictogram kopiëren **kopiëren** ![ ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="56b2d-130">Configureer de volgende instellingen in het venster **nieuwe rollen groep** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="56b2d-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="56b2d-131">**Naam**: Voer een unieke naam in voor de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="56b2d-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="56b2d-132">**Beschrijving**: Typ een optionele beschrijving voor de rollen groep.</span><span class="sxs-lookup"><span data-stu-id="56b2d-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="56b2d-133">**Rollen** **: Klik op** het ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) of **verwijderen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Als u de rollen wilt selecteren of wijzigen die zijn toegewezen aan de rollen groep.</span><span class="sxs-lookup"><span data-stu-id="56b2d-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="56b2d-134">**Leden** **: Klik op** ![ het pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) of **verwijderen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) om het lidmaatschap van de rollen groep te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="56b2d-135">Wanneer u klaar bent, klikt u op **Opslaan** om de rollen groep te maken.</span><span class="sxs-lookup"><span data-stu-id="56b2d-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="56b2d-136">Het Exchange-rollencentrum gebruiken om rollen groepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="56b2d-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="56b2d-137">Ga in het Exchange-Beheercentrum naar **machtigingen voor machtigingen** \> **beheerders**, selecteer de groep rollen die u wilt wijzigen en  klik vervolgens op ![ bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="56b2d-138">De opties zijn alleen beschikbaar wanneer u Rolgroepen aanpast wanneer u rollen groepen maakt.</span><span class="sxs-lookup"><span data-stu-id="56b2d-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="56b2d-139">U kunt:</span><span class="sxs-lookup"><span data-stu-id="56b2d-139">You can:</span></span>

- <span data-ttu-id="56b2d-140">Wijzig de naam en beschrijving.</span><span class="sxs-lookup"><span data-stu-id="56b2d-140">Change the name and description.</span></span>

- <span data-ttu-id="56b2d-141">Beheerrollen toevoegen en verwijderen (rollen toewijzingen maken of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="56b2d-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="56b2d-142">Leden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-142">Add and remove members.</span></span>

<span data-ttu-id="56b2d-143">**Opmerking**: Sommige rollen groepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="56b2d-144">Werken met de lijst met wijzigingen in de lijst met leden van rollen groepen</span><span class="sxs-lookup"><span data-stu-id="56b2d-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="56b2d-145">Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**, selecteer de rolgroep die u wilt wijzigen en klik vervolgens op  ![ bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="56b2d-146">Ga op een van de volgende manieren te werk in de sectie **leden** op de pagina eigenschappen van rollen groep:</span><span class="sxs-lookup"><span data-stu-id="56b2d-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="56b2d-147">Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="56b2d-148">Zoek op de pagina die wordt weergegeven de gebruiker die wou wilt toevoegen en klik vervolgens op **add->**.</span><span class="sxs-lookup"><span data-stu-id="56b2d-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="56b2d-149">Selecteer gebruikers en klik zo nodig op **>** vaak.</span><span class="sxs-lookup"><span data-stu-id="56b2d-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="56b2d-150">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b2d-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="56b2d-151">Selecteer de gebruikers die u **wilt verwijderen en klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="56b2d-152">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="56b2d-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="56b2d-153">Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in de beheerdersbevoegdheid te zien nadat u leden toevoegt of verwijdert uit de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="56b2d-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="56b2d-154">De rollen groepen verwijderen via het Exchange-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="56b2d-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="56b2d-155">U kunt ingebouwde rollen groepen niet verwijderen, maar u kunt wel aangepaste Rolgroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="56b2d-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="56b2d-156">Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**.</span><span class="sxs-lookup"><span data-stu-id="56b2d-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="56b2d-157">Selecteer de rollen groep die u wilt verwijderen en **Klik op** ![ verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="56b2d-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="56b2d-158">Klik op **Ja** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="56b2d-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="56b2d-159">PowerShell gebruiken om rollen groepen te beheren</span><span class="sxs-lookup"><span data-stu-id="56b2d-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="56b2d-160">Standalone EOP PowerShell gebruiken om rollen groepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="56b2d-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="56b2d-161">Gebruik de volgende syntaxis om een rollen groep weer te geven:</span><span class="sxs-lookup"><span data-stu-id="56b2d-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="56b2d-162">In dit voorbeeld wordt een overzichtslijst met alle rollen groepen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="56b2d-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="56b2d-163">In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de rollen groep met de naam beheerders van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="56b2d-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="56b2d-164">In het volgende voorbeeld worden alle rollen groepen opgevraagd waarvan de gebruiker Julia lid is.</span><span class="sxs-lookup"><span data-stu-id="56b2d-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="56b2d-165">U moet de DN-waarde (Distinguished Name) gebruiken voor Julia, die u kunt vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="56b2d-166">Zie [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="56b2d-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="56b2d-167">Standalone EOP PowerShell gebruiken om rollen groepen te maken</span><span class="sxs-lookup"><span data-stu-id="56b2d-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="56b2d-168">Wanneer u een nieuwe rollen groep maakt, kunt u alle instellingen handmatig configureren (tijdens het maken van de groep of na).</span><span class="sxs-lookup"><span data-stu-id="56b2d-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="56b2d-169">U kunt ook een bestaande rollen groep kopiëren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="56b2d-170">Als u handmatig een nieuwe rollen groep wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="56b2d-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="56b2d-171">Met de parameter _roles_ worden de management rollen opgegeven die aan de rollen groep moeten worden toegewezen met behulp van de volgende syntaxis `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="56b2d-172">U kunt de beschikbare rollen zien met behulp van de cmdlet **Get-ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="56b2d-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="56b2d-173">Met de parameter parameters worden de leden van de rollen groep opgegeven met behulp _van de volgende_ syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="56b2d-174">U kunt gebruikers opgeven, universele beveiligingsgroepen voor e-mail (USGs) of andere Rolgroepen (beveiligings-principals).</span><span class="sxs-lookup"><span data-stu-id="56b2d-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="56b2d-175">In dit voorbeeld wordt een nieuwe rollen groep met de naam ' beperkte ontvanger beheer ' gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="56b2d-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="56b2d-176">De rol van e-mail geadresseerden is toegewezen aan de groep rollen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="56b2d-177">De gebruikers Kim en Martin worden toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="56b2d-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="56b2d-178">Voer de volgende stappen uit om een bestaande rollen groep te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="56b2d-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="56b2d-179">Sla de rollen groep op die u in een variabele wilt kopiëren met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="56b2d-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="56b2d-180">Maak als volgt de nieuwe rollen groep met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="56b2d-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="56b2d-181">Met de parameter parameters worden de leden van de rollen groep opgegeven met behulp _van de volgende_ syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="56b2d-182">U kunt gebruikers opgeven, universele beveiligingsgroepen voor e-mail (USGs) of andere Rolgroepen (beveiligings-principals).</span><span class="sxs-lookup"><span data-stu-id="56b2d-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="56b2d-183">In dit voorbeeld wordt de rollen groep Organisatiebeheer naar de nieuwe rollen groep met de naam ' beperkte Organisatiebeheer ' gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="56b2d-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="56b2d-184">De leden van de rollen groep zijn Isabelle, Carter en Lukas.</span><span class="sxs-lookup"><span data-stu-id="56b2d-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="56b2d-185">Voor gedetailleerde syntaxis-en parameterinformatie, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="56b2d-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="56b2d-186">Standalone EOP PowerShell gebruiken de lijst met leden in rollen groepen wijzigen</span><span class="sxs-lookup"><span data-stu-id="56b2d-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="56b2d-187">Met de cmdlet **add-RoleGroupMember** en **Remove-RoleGroupMember** worden afzonderlijke leden één voor één toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="56b2d-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="56b2d-188">Met de cmdlet **Update-RoleGroupMember** kunt u de bestaande lijst met leden vervangen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="56b2d-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="56b2d-189">De leden van een rollen groep kunnen gebruikers zijn, universele beveiligingsgroepen voor e-mail (USGs) of andere rollen groepen (beveiligings-principals).</span><span class="sxs-lookup"><span data-stu-id="56b2d-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="56b2d-190">Gebruik de volgende syntaxis om de leden van een rollen groep te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="56b2d-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="56b2d-191">Als u de bestaande lijst met leden wilt _vervangen_ door de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="56b2d-192">Als u de bestaande lijst met leden _selectief wilt wijzigen_ , gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="56b2d-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="56b2d-193">In dit voorbeeld worden alle huidige leden van de rollen groep Help Desk vervangen door de opgegeven gebruikers.</span><span class="sxs-lookup"><span data-stu-id="56b2d-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="56b2d-194">In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd uit de lijst met leden van de rollen groep van de Help Desk.</span><span class="sxs-lookup"><span data-stu-id="56b2d-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="56b2d-195">Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="56b2d-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="56b2d-196">Standalone EOP PowerShell gebruiken om rollen groepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="56b2d-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="56b2d-197">U kunt ingebouwde rollen groepen niet verwijderen, maar u kunt wel aangepaste Rolgroepen verwijderen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="56b2d-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="56b2d-198">Als u een aangepaste rollen groep wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="56b2d-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="56b2d-199">In dit voorbeeld wordt de rollen groep training beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="56b2d-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="56b2d-200">Zie [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="56b2d-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="56b2d-201">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="56b2d-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="56b2d-202">Voer een van de volgende stappen uit om te controleren of u een rollen groep hebt gekopieerd:</span><span class="sxs-lookup"><span data-stu-id="56b2d-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="56b2d-203">Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerders** en controleer of de rollen groep wel of niet wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="56b2d-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="56b2d-204">Selecteer de groep rollen, Controleer de instellingen in het detailvenster of klik op  ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-EditIcon.png) om de instellingen te controleren.</span><span class="sxs-lookup"><span data-stu-id="56b2d-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="56b2d-205">In Exchange Online PowerShell vervangt u \<Role Group Name\> de naam van de rolgroep en voert u de volgende opdracht uit om te controleren of de rollen groep bestaat (of niet bestaat) en controleert u de instellingen:</span><span class="sxs-lookup"><span data-stu-id="56b2d-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
