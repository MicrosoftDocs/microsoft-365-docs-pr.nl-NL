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
description: U Exchange Online Protection (EOP) gebruiken om groepen met e-mail te maken voor een Exchange-organisatie. U EOP ook gebruiken om groepseigenschappen te definiëren of bij te werken die lidmaatschap, e-mailadressen en andere aspecten van groepen opgeven.
ms.openlocfilehash: ad07066906f78703c568850afbfa5dfa8d8cc3c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806114"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="b631d-104">Groepen beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="b631d-104">Manage groups in EOP</span></span>

 <span data-ttu-id="b631d-105">U Exchange Online Protection (EOP) gebruiken om groepen met e-mail te maken voor een Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="b631d-105">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="b631d-106">U EOP ook gebruiken om groepseigenschappen te definiëren of bij te werken die lidmaatschap, e-mailadressen en andere aspecten van groepen opgeven.</span><span class="sxs-lookup"><span data-stu-id="b631d-106">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="b631d-107">U distributiegroepen en beveiligingsgroepen maken, afhankelijk van uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="b631d-107">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="b631d-108">Deze groepen kunnen worden gemaakt met behulp van het Exchange-beheercentrum (EAC) of via externe Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b631d-108">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="b631d-109">Typen groepen met e-mail</span><span class="sxs-lookup"><span data-stu-id="b631d-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="b631d-110">U twee typen groepen maken voor uw Exchange-organisatie:</span><span class="sxs-lookup"><span data-stu-id="b631d-110">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="b631d-111">Distributiegroepen zijn verzamelingen van e-mailgebruikers, zoals een team of andere ad hoc-groep, die e-mail moeten ontvangen of verzenden met betrekking tot een gemeenschappelijk interessegebied.</span><span class="sxs-lookup"><span data-stu-id="b631d-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="b631d-112">Distributiegroepen zijn uitsluitend voor het verspreiden van e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b631d-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="b631d-113">In EOP verwijst een distributiegroep naar een groep met e-mail, ongeacht of deze een beveiligingscontext heeft.</span><span class="sxs-lookup"><span data-stu-id="b631d-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="b631d-114">Beveiligingsgroepen zijn verzamelingen van e-mailgebruikers die toegangsmachtigingen nodig hebben voor beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="b631d-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="b631d-115">U bijvoorbeeld specifieke gebruikersbeheerdersrolmachtigingen geven, zodat ze anti-spam- en anti-malware-instellingen kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="b631d-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b631d-116">Standaard vereisen alle nieuwe beveiligingsgroepen met e-mail dat alle afzenders worden geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="b631d-116">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="b631d-117">Dit voorkomt dat externe afzenders berichten verzenden naar beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="b631d-117">This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b631d-118">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b631d-118">Before you begin</span></span>

- <span data-ttu-id="b631d-119">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b631d-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b631d-120">Zie de vermelding 'Distributiegroepen en beveiligingsgroepen' in het onderwerp [Functiemachtigingen in het eOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b631d-120">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="b631d-121">Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b631d-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b631d-122">Houd er rekening mee dat u bij het maken en beheren van groepen met Exchange Online Protection PowerShell-cmdlets throttling tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="b631d-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="b631d-123">De PowerShell-procedures in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een vertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="b631d-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b631d-124">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b631d-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b631d-125">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b631d-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b631d-126">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="b631d-126">Having problems?</span></span> <span data-ttu-id="b631d-127">Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="b631d-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="b631d-128">Een groep maken in de EAC</span><span class="sxs-lookup"><span data-stu-id="b631d-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="b631d-129">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="b631d-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b631d-130">Klik **New** ![op](../../media/ITPro-EAC-AddIcon.gif)Pictogram Nieuw toevoegen en klik vervolgens op **De groep Distributie** of **Beveiligingsgroep,** afhankelijk van uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="b631d-130">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="b631d-131">Configureer op de pagina **Nieuwe distributiegroep** of **Nieuwe beveiligingsgroep** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b631d-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="b631d-132">**Weergavenaam:** typ een weergavenaam die uniek is voor uw organisatie en zinvol is voor EOP-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b631d-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="b631d-133">De weergavenaam is vereist.</span><span class="sxs-lookup"><span data-stu-id="b631d-133">The display name is required.</span></span>

   - <span data-ttu-id="b631d-134">**Alias:** Typ een groepsalias van maximaal 64 tekens die uniek zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b631d-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="b631d-135">EOP-gebruikers typen de alias in de regel van e-mailberichten en de alias wordt opgelost in de weergavenaam van de groep.</span><span class="sxs-lookup"><span data-stu-id="b631d-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="b631d-136">Als u de alias wijzigt, wordt ook het primaire SMTP-adres voor de groep gewijzigd en bevat het de nieuwe alias.</span><span class="sxs-lookup"><span data-stu-id="b631d-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="b631d-137">De alias is vereist.</span><span class="sxs-lookup"><span data-stu-id="b631d-137">The alias is required.</span></span>

   - <span data-ttu-id="b631d-138">**Beschrijving**: Typ een beschrijving van de groep, zodat mensen het doel van de groep kennen.</span><span class="sxs-lookup"><span data-stu-id="b631d-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="b631d-139">**Eigenaren**: De persoon die de groep maakt, is standaard de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="b631d-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="b631d-140">U een eigenaar toevoegen door](../../media/ITPro-EAC-AddIcon.gif)Pictogram **Add** ![Toevoegen te kiezen.</span><span class="sxs-lookup"><span data-stu-id="b631d-140">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="b631d-141">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="b631d-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b631d-142">Eigenaren hoeven geen lid te zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="b631d-142">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="b631d-143">**Leden**: Gebruik deze sectie om groepsleden toe te voegen en om aan te geven of goedkeuring vereist is voor mensen om lid te worden of de groep te verlaten.</span><span class="sxs-lookup"><span data-stu-id="b631d-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="b631d-144">Als u leden aan de groep](../../media/ITPro-EAC-AddIcon.gif)wilt toevoegen, **klikt** ![u op Pictogram toevoegen toevoegen .</span><span class="sxs-lookup"><span data-stu-id="b631d-144">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="b631d-145">Klik op **OK** om terug te keren naar de oorspronkelijke pagina.</span><span class="sxs-lookup"><span data-stu-id="b631d-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="b631d-146">Als u klaar bent, klikt u op **Opslaan** om de groep te maken.</span><span class="sxs-lookup"><span data-stu-id="b631d-146">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="b631d-147">De nieuwe groep moet worden weergegeven in de lijst met groepen.</span><span class="sxs-lookup"><span data-stu-id="b631d-147">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="b631d-148">Een groep in de EAC bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="b631d-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="b631d-149">Navigeer in de EAC naar \> **ontvangersgroepen**. **Recipients**</span><span class="sxs-lookup"><span data-stu-id="b631d-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b631d-150">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b631d-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="b631d-151">Een groep bewerken: klik in de lijst met groepen op de groep die u wilt](../../media/ITPro-EAC-EditIcon.gif)weergeven of wijzigen en **klik** ![vervolgens op Pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="b631d-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="b631d-152">U algemene instellingen bijwerken, groepseigenaren toevoegen of verwijderen en groepsleden toevoegen of verwijderen als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="b631d-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="b631d-153">Een groep verwijderen: selecteer de groep](../../media/ITPro-EAC-RemoveIcon.gif)en **klik** ![op Pictogram Verwijderen verwijderen .</span><span class="sxs-lookup"><span data-stu-id="b631d-153">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b631d-154">Wanneer u klaar bent met het aanbrengen van wijzigingen, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b631d-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b631d-155">Een groep maken, bewerken of verwijderen met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b631d-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b631d-156">In deze sectie vindt u informatie over het maken van groepen en het wijzigen van hun eigenschappen in Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b631d-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="b631d-157">Het laat ook zien hoe u een bestaande groep verwijdert.</span><span class="sxs-lookup"><span data-stu-id="b631d-157">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b631d-158">Een groep maken met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b631d-158">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b631d-159">In dit voorbeeld wordt de cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) gebruikt om een distributiegroep te maken met een alias itadmin en de naam IT-beheerders.</span><span class="sxs-lookup"><span data-stu-id="b631d-159">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="b631d-160">Het voegt ook gebruikers toe als leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="b631d-160">It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="b631d-161">**Opmerking**: Als u een beveiligingsgroep wilt maken `Security` in plaats van een distributiegroep, gebruikt u de waarde voor de parameter *Type.*</span><span class="sxs-lookup"><span data-stu-id="b631d-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="b631d-162">Voer de volgende opdracht uit om informatie over de nieuwe groep weer te geven om te controleren of u de groep IT-beheerders hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="b631d-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="b631d-163">Zie [Ontvanger ontvangen](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b631d-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="b631d-164">Voer de volgende opdracht uit om een lijst met leden in de groep te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b631d-164">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="b631d-165">Zie [Groepslid voor](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)u voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="b631d-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="b631d-166">Voer de volgende opdracht uit om een volledige lijst met al uw groepen te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b631d-166">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b631d-167">De eigenschappen van een groep wijzigen met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b631d-167">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b631d-168">Een voordeel van het gebruik van PowerShell in plaats van de EAC is de mogelijkheid om eigenschappen voor meerdere groepen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b631d-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="b631d-169">Hier volgen enkele voorbeelden van het gebruik van Exchange Online Protection PowerShell om groepseigenschappen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b631d-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="b631d-170">In dit voorbeeld worden wijzigingen gebruikt van het primaire SMTP-adres (ook wel het antwoordadres genoemd) voor de groep Werknemers in Seattle sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b631d-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="b631d-171">Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="b631d-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="b631d-172">Voer de volgende opdracht uit om de nieuwe waarde te verifiëren om te controleren of u de eigenschappen voor de groep hebt gewijzigd:</span><span class="sxs-lookup"><span data-stu-id="b631d-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="b631d-173">In dit voorbeeld worden alle leden van de groep Werknemers van Seattle bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b631d-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="b631d-174">Gebruik een komma om alle leden te scheiden.</span><span class="sxs-lookup"><span data-stu-id="b631d-174">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="b631d-175">Zie [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="b631d-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="b631d-176">Voer de volgende opdracht uit om de lijst van alle leden in de werknemers van Seattle van de groep Seattle te krijgen:</span><span class="sxs-lookup"><span data-stu-id="b631d-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b631d-177">Een groep verwijderen met externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b631d-177">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b631d-178">In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b631d-178">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="b631d-179">Zie [Groep verwijderen-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="b631d-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="b631d-180">Voer de volgende opdracht uit om te controleren of de groep is verwijderd en bevestigt dat de groep (in dit geval 'It Administrators') is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b631d-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
