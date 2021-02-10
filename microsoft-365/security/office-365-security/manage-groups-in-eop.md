---
title: Groepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Beheerders in zelfstandige Exchange Online Protection-organisaties (EOP) kunnen informatie krijgen over het maken, wijzigen en verwijderen van distributiegroepen en beveiligingsgroepen met e-mail in het Exchange-beheercentrum (EAC) en in zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166961"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="51b7d-103">Groepen beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="51b7d-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="51b7d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="51b7d-104">**Applies to**</span></span>
-  [<span data-ttu-id="51b7d-105">Zelfstandige versie van Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="51b7d-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="51b7d-106">In zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken kunt u de volgende typen groepen maken, wijzigen en verwijderen:</span><span class="sxs-lookup"><span data-stu-id="51b7d-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="51b7d-107">**Distributiegroepen:** een verzameling e-mailgebruikers of andere distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="51b7d-108">Bijvoorbeeld teams of andere ad-hocgroepen die e-mail moeten ontvangen of verzenden in een gemeenschappelijk interessegebied.</span><span class="sxs-lookup"><span data-stu-id="51b7d-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="51b7d-109">Distributiegroepen zijn uitsluitend voor het distribueren van e-mailberichten en zijn geen beveiligings-principals (aan deze groepen zijn geen machtigingen toegewezen).</span><span class="sxs-lookup"><span data-stu-id="51b7d-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="51b7d-110">**Beveiligingsgroepen met e-mail:** een verzameling e-mailgebruikers en andere beveiligingsgroepen die toegangsrechten nodig hebben voor beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="51b7d-111">U wilt bijvoorbeeld een specifieke groep gebruikers beheerdersmachtigingen geven zodat ze antispam- en antimalware-instellingen kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="51b7d-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="51b7d-112">Standaard weigeren nieuwe beveiligingsgroepen met e-mail berichten van externe (niet-geauteerde) afzenders.</span><span class="sxs-lookup"><span data-stu-id="51b7d-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="51b7d-113">Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="51b7d-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="51b7d-114">U kunt groepen beheren in het Exchange-beheercentrum (EAC) en in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51b7d-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51b7d-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="51b7d-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51b7d-116">Als u het Exchange-beheercentrum wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="51b7d-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="51b7d-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51b7d-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="51b7d-118">Wanneer u groepen beheert in zelfstandige EOP PowerShell, kan er beperkingen worden aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="51b7d-119">In de PowerShell-procedures in dit artikel wordt een batchverwerkingsmethode gebruikt die resulteert in een doorloopvertraging van een paar minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="51b7d-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="51b7d-120">U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="51b7d-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="51b7d-121">U hebt met name de rol **Distributiegroepen**  nodig, die standaard is toegewezen aan de rollengroepen Organisatiebeheer en **Geadresseerdenbeheer.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="51b7d-122">Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="51b7d-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="51b7d-123">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="51b7d-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="51b7d-124">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="51b7d-124">Having problems?</span></span> <span data-ttu-id="51b7d-125">Vraag om hulp op het forum [van Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="51b7d-125">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="51b7d-126">Het Exchange-beheercentrum gebruiken om distributiegroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="51b7d-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="51b7d-127">Het EAC gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="51b7d-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="51b7d-128">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="51b7d-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="51b7d-129">Klik **op** ![ het pictogram Nieuw en selecteer een van de volgende ](../../media/ITPro-EAC-AddIcon.png) opties:</span><span class="sxs-lookup"><span data-stu-id="51b7d-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="51b7d-130">**Distributiegroep**</span><span class="sxs-lookup"><span data-stu-id="51b7d-130">**Distribution group**</span></span>

   - <span data-ttu-id="51b7d-131">**Beveiligingsgroep met e-mail**</span><span class="sxs-lookup"><span data-stu-id="51b7d-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="51b7d-132">Configureer de volgende instellingen op de nieuwe groepspagina die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="51b7d-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="51b7d-133">Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="51b7d-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="51b7d-134"><sup>\*</sup>**Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de Regel  Aan: wanneer e-mail naar deze groep wordt verzonden en in de lijst Groepen in het EAC.</span><span class="sxs-lookup"><span data-stu-id="51b7d-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="51b7d-135">De weergavenaam is vereist, moet uniek zijn en moet herkenbaar zijn, zodat gebruikers weten wat de naam is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="51b7d-136"><sup>\*</sup>**Alias:** gebruik dit vak om de naam van de alias voor de groep te typen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="51b7d-137">De alias mag niet meer dan 64 tekens bevatten en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="51b7d-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="51b7d-138">Wanneer een gebruiker de alias in de regel Aan van een e-mailbericht typen, wordt de weergavenaam van de groep weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51b7d-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="51b7d-139"><sup>\*</sup>**E-mailadres:** het e-mailadres bestaat uit de alias aan de linkerkant van het at-symbool (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="51b7d-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="51b7d-140">Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="51b7d-141">Voor de domeinwaarde klikt u op de vervolgkeuzekeuze en selecteert en geaccepteerd domein in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="51b7d-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="51b7d-142">**Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het EAC.</span><span class="sxs-lookup"><span data-stu-id="51b7d-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="51b7d-143"><sup>\*</sup>**Eigenaren:** een groepseigenaar kan groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="51b7d-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="51b7d-144">De persoon die een groep maakt, is standaard de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="51b7d-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="51b7d-145">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="51b7d-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="51b7d-146">Als u eigenaars wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="51b7d-147">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="51b7d-148">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51b7d-149">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="51b7d-150">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="51b7d-151">**Leden:** groepsleden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="51b7d-152">Als u leden wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="51b7d-153">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="51b7d-154">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51b7d-155">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="51b7d-156">Als u een lid wilt verwijderen, selecteert u het lid en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="51b7d-157">Wanneer u klaar bent, klikt u op **Opslaan om** de distributiegroep te maken.</span><span class="sxs-lookup"><span data-stu-id="51b7d-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="51b7d-158">Het EAC gebruiken om distributiegroepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="51b7d-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="51b7d-159">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="51b7d-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="51b7d-160">Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="51b7d-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="51b7d-161">Klik op de pagina met eigenschappen van de distributiegroep die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="51b7d-162">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="51b7d-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="51b7d-163">Algemeen</span><span class="sxs-lookup"><span data-stu-id="51b7d-163">General</span></span>

<span data-ttu-id="51b7d-164">Gebruik dit tabblad om basisinformatie over de groep weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="51b7d-165">**Weergavenaam:** deze naam wordt weergegeven in het adresboek, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de **lijst Groepen.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="51b7d-166">De weergavenaam is verplicht en moet herkenbaar zijn, zodat gebruikers weten wat deze is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="51b7d-167">Het moet ook uniek zijn in uw domein.</span><span class="sxs-lookup"><span data-stu-id="51b7d-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="51b7d-168">Als u een groepsnaambeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die is gedefinieerd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="51b7d-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="51b7d-169">**Alias:** dit is het gedeelte van het e-mailadres dat links van het @-symbool wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51b7d-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="51b7d-170">Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep ook gewijzigd en bevat de nieuwe alias.</span><span class="sxs-lookup"><span data-stu-id="51b7d-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="51b7d-171">Het e-mailadres met de vorige alias wordt ook bewaard als een proxyadres voor de groep.</span><span class="sxs-lookup"><span data-stu-id="51b7d-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="51b7d-172">**E-mailadres:** het e-mailadres bestaat uit de alias aan de linkerkant van het at-symbool (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="51b7d-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="51b7d-173">Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="51b7d-174">Voor de domeinwaarde klikt u op de vervolgkeuzekeuze en selecteert en geaccepteerd domein in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="51b7d-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="51b7d-175">**Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het EAC.</span><span class="sxs-lookup"><span data-stu-id="51b7d-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="51b7d-176">Eigendom</span><span class="sxs-lookup"><span data-stu-id="51b7d-176">Ownership</span></span>

<span data-ttu-id="51b7d-177">Gebruik dit tabblad om groepseigenaars toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="51b7d-178">Een groepseigenaar kan het groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="51b7d-178">A group owner can manage group membership.</span></span> <span data-ttu-id="51b7d-179">De persoon die een groep maakt, is standaard de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="51b7d-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="51b7d-180">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="51b7d-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="51b7d-181">Als u eigenaars wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="51b7d-182">Zoek en selecteer een geadresseerde in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Invoeg**>.</span><span class="sxs-lookup"><span data-stu-id="51b7d-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="51b7d-183">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51b7d-184">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="51b7d-185">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="51b7d-186">Lidmaatschap</span><span class="sxs-lookup"><span data-stu-id="51b7d-186">Membership</span></span>

<span data-ttu-id="51b7d-187">Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="51b7d-188">Groepseigenaren hoeven geen lid te zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="51b7d-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="51b7d-189">Als u leden wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="51b7d-190">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="51b7d-191">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="51b7d-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51b7d-192">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="51b7d-193">Als u een lid wilt verwijderen, selecteert u het lid en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="51b7d-194">Het EAC gebruiken om groepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="51b7d-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="51b7d-195">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="51b7d-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="51b7d-196">Selecteer in de lijst met groepen de distributiegroep die u wilt verwijderen en klik op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="51b7d-197">PowerShell gebruiken om groepen te beheren</span><span class="sxs-lookup"><span data-stu-id="51b7d-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="51b7d-198">Zelfstandige EOP PowerShell gebruiken om groepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="51b7d-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="51b7d-199">Voer de volgende opdracht uit om een overzichtslijst met alle distributiegroepen en beveiligingsgroepen met e-mail in zelfstandige EOP PowerShell te retourneren:</span><span class="sxs-lookup"><span data-stu-id="51b7d-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="51b7d-200">Als u de lijst met groepsleden wilt retourneren, vervangt u door de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="51b7d-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="51b7d-201">Zie Get-Recipient en [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie. [](https://docs.microsoft.com/powershell/module/exchange/get-recipient)</span><span class="sxs-lookup"><span data-stu-id="51b7d-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="51b7d-202">Zelfstandige EOP PowerShell gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="51b7d-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="51b7d-203">Gebruik de volgende syntaxis om distributiegroepen of beveiligingsgroepen met e-mail te maken in zelfstandige EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="51b7d-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="51b7d-204">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="51b7d-204">**Notes**:</span></span>

- <span data-ttu-id="51b7d-205">De  parameter Name is vereist, heeft een maximumlengte van 64 tekens en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="51b7d-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="51b7d-206">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="51b7d-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="51b7d-207">Als u de _aliasparameter_ niet gebruikt, wordt de parameter _Name_ gebruikt voor de aliaswaarde.</span><span class="sxs-lookup"><span data-stu-id="51b7d-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="51b7d-208">Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).</span><span class="sxs-lookup"><span data-stu-id="51b7d-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="51b7d-209">Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de aliaswaarde gebruikt in de _primarySmtpAddress-parameter._</span><span class="sxs-lookup"><span data-stu-id="51b7d-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="51b7d-210">Als u de parameter Type niet _gebruikt,_ is de standaardwaarde Verdeling.</span><span class="sxs-lookup"><span data-stu-id="51b7d-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="51b7d-211">In dit voorbeeld wordt een distributiegroep gemaakt met de naam IT-beheerders met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="51b7d-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="51b7d-212">Zie [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="51b7d-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="51b7d-213">Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="51b7d-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="51b7d-214">Gebruik de volgende syntaxis om groepen in zelfstandige EOP PowerShell te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="51b7d-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="51b7d-215">In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) gewijzigd, dat de groep Werknemers van Seattle moet sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="51b7d-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="51b7d-216">In dit voorbeeld worden de huidige leden van de groep Beveiligingsteam vervangen door Petersen En Wordt Fawcett.</span><span class="sxs-lookup"><span data-stu-id="51b7d-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="51b7d-217">In dit voorbeeld wordt een nieuwe gebruiker met de naam Wordt Fawcett toegevoegd aan de groep genaamd Beveiligingsteam met behoud van de huidige leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="51b7d-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="51b7d-218">Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="51b7d-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="51b7d-219">Een groep verwijderen met behulp van externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51b7d-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="51b7d-220">In dit voorbeeld wordt de distributiegroep IT-beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="51b7d-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="51b7d-221">Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="51b7d-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="51b7d-222">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="51b7d-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="51b7d-223">Ga op een van de volgende stappen te werk om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="51b7d-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="51b7d-224">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="51b7d-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="51b7d-225">Controleer of de groep wel of niet wordt weergegeven en controleer de **waarde van het groepstype.**</span><span class="sxs-lookup"><span data-stu-id="51b7d-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="51b7d-226">Selecteer de groep en bekijk de informatie  in het detailvenster of klik op het pictogram ![ Bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.</span><span class="sxs-lookup"><span data-stu-id="51b7d-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="51b7d-227">Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt weergegeven (of niet wordt weergegeven):</span><span class="sxs-lookup"><span data-stu-id="51b7d-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="51b7d-228">Vervang door de naam, alias of het e-mailadres van de groep en voer de volgende opdracht \<GroupIdentity\> uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="51b7d-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="51b7d-229">Als u de groepsleden wilt weergeven, vervangt u door de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="51b7d-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
