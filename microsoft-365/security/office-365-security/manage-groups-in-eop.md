---
title: Groepen beheren in EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u groepen met e-mail voor een Exchange-organisatie maken en beheren in Exchange Online Protection (EOP).
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034400"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="b65fe-103">Groepen beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="b65fe-103">Manage groups in EOP</span></span>

 <span data-ttu-id="b65fe-104">U Exchange Online Protection (EOP) gebruiken om groepen met e-mail voor een Exchange-organisatie te maken.</span><span class="sxs-lookup"><span data-stu-id="b65fe-104">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="b65fe-105">U EOP ook gebruiken om groepseigenschappen te definiëren of bij te werken die lidmaatschap, e-mailadressen en andere aspecten van groepen opgeven.</span><span class="sxs-lookup"><span data-stu-id="b65fe-105">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="b65fe-106">U distributiegroepen en beveiligingsgroepen maken, afhankelijk van uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="b65fe-106">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="b65fe-107">Deze groepen kunnen worden gemaakt met behulp van het Exchange-beheercentrum (EAC) of via externe Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b65fe-107">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="b65fe-108">Typen e-mailgroepen</span><span class="sxs-lookup"><span data-stu-id="b65fe-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="b65fe-109">U twee typen groepen maken voor uw Exchange-organisatie:</span><span class="sxs-lookup"><span data-stu-id="b65fe-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="b65fe-110">Distributiegroepen zijn verzamelingen van e-mailgebruikers, zoals een team of een andere ad-hocgroep, die e-mail moeten ontvangen of verzenden met betrekking tot een gemeenschappelijk interessegebied.</span><span class="sxs-lookup"><span data-stu-id="b65fe-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="b65fe-111">Distributiegroepen zijn uitsluitend voor het verspreiden van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b65fe-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="b65fe-112">In EOP verwijst een distributiegroep naar een groep met e-mailingeschakelde groepen, ongeacht of deze al dan niet een beveiligingscontext heeft.</span><span class="sxs-lookup"><span data-stu-id="b65fe-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="b65fe-113">Beveiligingsgroepen zijn verzamelingen van e-mailgebruikers die toegangsmachtigingen nodig hebben voor beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="b65fe-114">U bijvoorbeeld specifieke machtigingen voor beheerdersvan gebruikers opgeven, zodat ze instellingen voor antispam en anti-malware kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="b65fe-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b65fe-115">Standaard vereisen alle nieuwe beveiligingsgroepen met e-mail dat alle afzenders worden geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="b65fe-115">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="b65fe-116">Dit voorkomt dat externe afzenders berichten verzenden naar beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="b65fe-116">This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b65fe-117">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b65fe-117">Before you begin</span></span>

- <span data-ttu-id="b65fe-118">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b65fe-118">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b65fe-119">Zie het item 'Distributiegroepen en beveiligingsgroepen' in het onderwerp [Functiemachtigingen in het onderwerp EOP](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b65fe-119">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="b65fe-120">Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b65fe-121">Houd er rekening mee dat bij het maken en beheren van groepen met Behulp van Exchange Online Protection PowerShell-cmdlets u mogelijk throttling tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="b65fe-122">De PowerShell-procedures in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="b65fe-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b65fe-123">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b65fe-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b65fe-124">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b65fe-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b65fe-125">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="b65fe-125">Having problems?</span></span> <span data-ttu-id="b65fe-126">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="b65fe-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="b65fe-127">Een groep maken in de EAC</span><span class="sxs-lookup"><span data-stu-id="b65fe-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="b65fe-128">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="b65fe-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b65fe-129">Klik **New** ![op](../../media/ITPro-EAC-AddIcon.gif)Nieuw pictogram toevoegen en klik vervolgens op **Distributiegroep** of **Beveiligingsgroep,** afhankelijk van uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="b65fe-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="b65fe-130">Configureer de volgende instellingen op de pagina **Nieuwe distributiegroep** of **Nieuwe beveiligingsgroep:**</span><span class="sxs-lookup"><span data-stu-id="b65fe-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="b65fe-131">**Weergavenaam:** typ een weergavenaam die uniek is voor uw organisatie en betekenisvol is voor EOP-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b65fe-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="b65fe-132">De weergavenaam is vereist.</span><span class="sxs-lookup"><span data-stu-id="b65fe-132">The display name is required.</span></span>

   - <span data-ttu-id="b65fe-133">**Alias:** Typ een groepsalias van maximaal 64 tekens die uniek is voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b65fe-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="b65fe-134">EOP-gebruikers typen de alias in de regel Aan: e-mailberichten en de alias wordt opgelost voor de weergavenaam van de groep.</span><span class="sxs-lookup"><span data-stu-id="b65fe-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="b65fe-135">Als u de alias wijzigt, wordt ook het primaire SMTP-adres voor de groep gewijzigd en bevat het de nieuwe alias.</span><span class="sxs-lookup"><span data-stu-id="b65fe-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="b65fe-136">De alias is vereist.</span><span class="sxs-lookup"><span data-stu-id="b65fe-136">The alias is required.</span></span>

   - <span data-ttu-id="b65fe-137">**Beschrijving**: Typ een beschrijving van de groep, zodat mensen het doel van de groep weten.</span><span class="sxs-lookup"><span data-stu-id="b65fe-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="b65fe-138">**Eigenaren**: Standaard is de persoon die de groep maakt de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="b65fe-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="b65fe-139">U een eigenaar **Add** ![toevoegen door](../../media/ITPro-EAC-AddIcon.gif)Pictogram Toevoegen te kiezen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="b65fe-140">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="b65fe-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b65fe-141">Eigenaren hoeven geen lid te zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="b65fe-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="b65fe-142">**Leden**: Gebruik deze sectie om groepsleden toe te voegen en om aan te geven of er goedkeuring nodig is voor mensen om lid te worden of de groep te verlaten.</span><span class="sxs-lookup"><span data-stu-id="b65fe-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="b65fe-143">Als u leden aan de groep](../../media/ITPro-EAC-AddIcon.gif)wilt toevoegen, **klikt** ![u op Pictogram toevoegen .</span><span class="sxs-lookup"><span data-stu-id="b65fe-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="b65fe-144">Klik op **OK** om terug te keren naar de oorspronkelijke pagina.</span><span class="sxs-lookup"><span data-stu-id="b65fe-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="b65fe-145">Wanneer u klaar bent, klikt u op **Opslaan** om de groep te maken.</span><span class="sxs-lookup"><span data-stu-id="b65fe-145">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="b65fe-146">De nieuwe groep moet worden weergegeven in de lijst met groepen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-146">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="b65fe-147">Een groep in de EAC bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="b65fe-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="b65fe-148">Navigeer in de EAC naar \> **ontvangersgroepen**. **Recipients**</span><span class="sxs-lookup"><span data-stu-id="b65fe-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b65fe-149">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b65fe-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="b65fe-150">Een groep bewerken: klik in de lijst met groepen op de groep die **Edit** ![u wilt](../../media/ITPro-EAC-EditIcon.gif)weergeven of wijzigen en klik vervolgens op Pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="b65fe-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="b65fe-151">U algemene instellingen bijwerken, groepseigenaren toevoegen of verwijderen en groepsleden toevoegen of verwijderen als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="b65fe-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="b65fe-152">Een groep verwijderen: selecteer de **Remove** ![groep](../../media/ITPro-EAC-RemoveIcon.gif)en klik op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="b65fe-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b65fe-153">Klik op **Opslaan**als u klaar bent met het aanbrengen van wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b65fe-154">Een groep maken, bewerken of verwijderen met behulp van externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b65fe-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b65fe-155">In deze sectie vindt u informatie over het maken van groepen en het wijzigen van hun eigenschappen in Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b65fe-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="b65fe-156">Het laat ook zien hoe je een bestaande groep verwijdert.</span><span class="sxs-lookup"><span data-stu-id="b65fe-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b65fe-157">Een groep maken met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b65fe-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b65fe-158">In dit voorbeeld wordt de cmdlet [Nieuw-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) gebruikt om een distributiegroep te maken met een alias van itadmin en de naam IT-beheerders.</span><span class="sxs-lookup"><span data-stu-id="b65fe-158">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="b65fe-159">Het voegt ook gebruikers toe als leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="b65fe-159">It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="b65fe-160">**Opmerking:** Als u een beveiligingsgroep wilt maken `Security` in plaats van een distributiegroep, gebruikt u de waarde voor de parameter *Type.*</span><span class="sxs-lookup"><span data-stu-id="b65fe-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="b65fe-161">Als u wilt controleren of u de groep IT-beheerders hebt gemaakt, voert u de volgende opdracht uit om informatie over de nieuwe groep weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b65fe-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="b65fe-162">Zie [Ontvanger opdoen](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b65fe-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="b65fe-163">Voer de volgende opdracht uit om een lijst met leden in de groep te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b65fe-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="b65fe-164">Zie [Groeplid get-distributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b65fe-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="b65fe-165">Voer de volgende opdracht uit om een volledige lijst met al uw groepen te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b65fe-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b65fe-166">De eigenschappen van een groep wijzigen met behulp van externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b65fe-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b65fe-167">Een voordeel van het gebruik van PowerShell in plaats van de EAC is de mogelijkheid om eigenschappen voor meerdere groepen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="b65fe-168">Hier volgen enkele voorbeelden van het gebruik van Exchange Online Protection PowerShell om groepseigenschappen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b65fe-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="b65fe-169">In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) gewijzigd voor de groep Werknemers in Seattle in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b65fe-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="b65fe-170">Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b65fe-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="b65fe-171">Als u wilt controleren of u de eigenschappen voor de groep hebt gewijzigd, voert u de volgende opdracht uit om de nieuwe waarde te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b65fe-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="b65fe-172">In dit voorbeeld worden alle leden van de groep Werknemers in Seattle bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b65fe-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="b65fe-173">Gebruik een komma om alle leden te scheiden.</span><span class="sxs-lookup"><span data-stu-id="b65fe-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="b65fe-174">Zie [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b65fe-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="b65fe-175">Voer de volgende opdracht uit om de lijst met alle leden in de groep Werknemers van Seattle te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b65fe-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b65fe-176">Een groep verwijderen met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b65fe-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b65fe-177">In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b65fe-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="b65fe-178">Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b65fe-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="b65fe-179">Als u wilt controleren of de groep is verwijderd, voert u de volgende opdracht uit en bevestigt u dat de groep (in dit geval 'It-beheerders') is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b65fe-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
