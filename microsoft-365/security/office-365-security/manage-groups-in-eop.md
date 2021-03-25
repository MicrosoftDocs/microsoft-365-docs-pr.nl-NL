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
description: Beheerders in zelfstandige EOP-organisaties (Exchange Online Protection) kunnen informatie krijgen over het maken, wijzigen en verwijderen van distributiegroepen en beveiligingsgroepen met e-mail in het Exchange-beheercentrum (EAC) en in zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203991"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="5147c-103">Groepen beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="5147c-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5147c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="5147c-104">**Applies to**</span></span>
-  [<span data-ttu-id="5147c-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5147c-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="5147c-106">In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u de volgende typen groepen maken, wijzigen en verwijderen:</span><span class="sxs-lookup"><span data-stu-id="5147c-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="5147c-107">**Distributiegroepen:** een verzameling e-mailgebruikers of andere distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="5147c-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="5147c-108">Bijvoorbeeld teams of andere ad-hocgroepen die e-mail moeten ontvangen of verzenden in een gemeenschappelijk interessegebied.</span><span class="sxs-lookup"><span data-stu-id="5147c-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="5147c-109">Distributiegroepen zijn uitsluitend voor het distribueren van e-mailberichten en zijn geen beveiligingsprincipen (ze kunnen geen machtigingen aan hen hebben toegewezen).</span><span class="sxs-lookup"><span data-stu-id="5147c-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="5147c-110">**Beveiligingsgroepen met e-mail:** een verzameling e-mailgebruikers en andere beveiligingsgroepen die toegangsmachtigingen nodig hebben voor beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="5147c-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="5147c-111">U kunt bijvoorbeeld een bepaalde groep gebruikers beheerdersmachtigingen geven, zodat ze antispam- en anti-malware-instellingen kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="5147c-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="5147c-112">Nieuwe beveiligingsgroepen met e-mail weigeren standaard berichten van externe (niet-nauthenticated) afzenders.</span><span class="sxs-lookup"><span data-stu-id="5147c-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="5147c-113">Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="5147c-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="5147c-114">U kunt groepen beheren in het Exchange-beheercentrum (EAC) en in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5147c-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5147c-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5147c-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5147c-116">Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5147c-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5147c-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5147c-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5147c-118">Wanneer u groepen beheert in zelfstandige EOP PowerShell, kunt u beperkingen ondervinden.</span><span class="sxs-lookup"><span data-stu-id="5147c-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="5147c-119">De PowerShell-procedures in dit artikel gebruiken een batchverwerkingsmethode die resulteert in een vertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="5147c-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="5147c-120">U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5147c-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="5147c-121">U hebt met name de rol **Distributiegroepen** nodig,  die standaard is toegewezen aan de rollengroepen **Organisatiebeheer** en Geadresseerdenbeheer.</span><span class="sxs-lookup"><span data-stu-id="5147c-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5147c-122">Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="5147c-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="5147c-123">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="5147c-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5147c-124">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="5147c-124">Having problems?</span></span> <span data-ttu-id="5147c-125">Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="5147c-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="5147c-126">Het Exchange-beheercentrum gebruiken om distributiegroepen te beheren</span><span class="sxs-lookup"><span data-stu-id="5147c-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="5147c-127">Het EAC gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="5147c-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="5147c-128">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="5147c-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="5147c-129">Klik **op** ![ Nieuw pictogram Nieuw en selecteer een van de volgende ](../../media/ITPro-EAC-AddIcon.png) opties:</span><span class="sxs-lookup"><span data-stu-id="5147c-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="5147c-130">**Distributiegroep**</span><span class="sxs-lookup"><span data-stu-id="5147c-130">**Distribution group**</span></span>

   - <span data-ttu-id="5147c-131">**Beveiligingsgroep met e-mail**</span><span class="sxs-lookup"><span data-stu-id="5147c-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="5147c-132">Configureer de volgende instellingen op de nieuwe groepspagina die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="5147c-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="5147c-133">Instellingen die zijn gemarkeerd met <sup>\*</sup> een zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="5147c-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="5147c-134"><sup>\*</sup>**Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel  Aan: wanneer e-mail naar deze groep wordt verzonden en in de lijst Groepen in het EAC.</span><span class="sxs-lookup"><span data-stu-id="5147c-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="5147c-135">De weergavenaam is vereist, moet uniek zijn en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is.</span><span class="sxs-lookup"><span data-stu-id="5147c-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="5147c-136"><sup>\*</sup>**Alias:** Gebruik dit vak om de naam van de alias voor de groep te typen.</span><span class="sxs-lookup"><span data-stu-id="5147c-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="5147c-137">De alias mag niet meer dan 64 tekens bevatten en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="5147c-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="5147c-138">Wanneer een gebruiker de alias in de regel Aan van een e-mailbericht typen, wordt de naam van de groep opgelost.</span><span class="sxs-lookup"><span data-stu-id="5147c-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="5147c-139"><sup>\*</sup>**E-mailadres:** Het e-mailadres bestaat uit de alias aan de linkerkant van het symbool bij (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="5147c-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="5147c-140">Standaard wordt de waarde **van Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5147c-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="5147c-141">Voor de domeinwaarde klikt u op de vervolgkeuze en selecteert en accepteert u domein in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5147c-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="5147c-142">**Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in het EAC.</span><span class="sxs-lookup"><span data-stu-id="5147c-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="5147c-143"><sup>\*</sup>**Eigenaren:** een groepseigenaar kan het groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="5147c-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="5147c-144">De persoon die een groep maakt, is standaard de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="5147c-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="5147c-145">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="5147c-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="5147c-146">Als u eigenaren wilt toevoegen, klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5147c-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5147c-147">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="5147c-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="5147c-148">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="5147c-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5147c-149">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="5147c-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="5147c-150">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="5147c-151">**Leden:** Groepsleden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="5147c-152">Als u leden wilt toevoegen, klikt **u op Pictogram** Toevoegen ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5147c-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5147c-153">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="5147c-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="5147c-154">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="5147c-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5147c-155">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="5147c-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="5147c-156">Als u een lid wilt verwijderen, selecteert u het lid en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="5147c-157">Wanneer u klaar bent, klikt u op **Opslaan om** de distributiegroep te maken.</span><span class="sxs-lookup"><span data-stu-id="5147c-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="5147c-158">Het EAC gebruiken om distributiegroepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5147c-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="5147c-159">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="5147c-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="5147c-160">Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="5147c-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="5147c-161">Klik op de pagina eigenschappen van de distributiegroep die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5147c-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="5147c-162">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5147c-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="5147c-163">Algemeen</span><span class="sxs-lookup"><span data-stu-id="5147c-163">General</span></span>

<span data-ttu-id="5147c-164">Gebruik dit tabblad om basisgegevens over de groep weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5147c-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="5147c-165">**Weergavenaam:** Deze naam wordt weergegeven in het adresboek, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de **lijst Groepen.**</span><span class="sxs-lookup"><span data-stu-id="5147c-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="5147c-166">De weergavenaam is vereist en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is.</span><span class="sxs-lookup"><span data-stu-id="5147c-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="5147c-167">Het moet ook uniek zijn in uw domein.</span><span class="sxs-lookup"><span data-stu-id="5147c-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="5147c-168">Als u een groepsnaambeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die door het beleid is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="5147c-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="5147c-169">**Alias:** dit is het gedeelte van het e-mailadres dat links van het symbool bij (@) wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5147c-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="5147c-170">Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep ook gewijzigd en bevat u de nieuwe alias.</span><span class="sxs-lookup"><span data-stu-id="5147c-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="5147c-171">Het e-mailadres met de vorige alias wordt ook bewaard als proxyadres voor de groep.</span><span class="sxs-lookup"><span data-stu-id="5147c-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="5147c-172">**E-mailadres:** Het e-mailadres bestaat uit de alias aan de linkerkant van het symbool bij (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="5147c-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="5147c-173">Standaard wordt de waarde **van Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5147c-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="5147c-174">Voor de domeinwaarde klikt u op de vervolgkeuze en selecteert en accepteert u domein in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5147c-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="5147c-175">**Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in het EAC.</span><span class="sxs-lookup"><span data-stu-id="5147c-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="5147c-176">Eigendom</span><span class="sxs-lookup"><span data-stu-id="5147c-176">Ownership</span></span>

<span data-ttu-id="5147c-177">Gebruik dit tabblad om groepseigenaars toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="5147c-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="5147c-178">Een groepseigenaar kan het groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="5147c-178">A group owner can manage group membership.</span></span> <span data-ttu-id="5147c-179">De persoon die een groep maakt, is standaard de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="5147c-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="5147c-180">Alle groepen moeten ten minste één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="5147c-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="5147c-181">Als u eigenaren wilt toevoegen, klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5147c-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5147c-182">Zoek en selecteer een geadresseerde in het dialoogvenster dat wordt weergegeven en klik vervolgens **op Toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="5147c-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="5147c-183">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="5147c-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5147c-184">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="5147c-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="5147c-185">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="5147c-186">Lidmaatschap</span><span class="sxs-lookup"><span data-stu-id="5147c-186">Membership</span></span>

<span data-ttu-id="5147c-187">Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="5147c-188">Groepseigenaren hoeven geen lid te zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="5147c-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="5147c-189">Als u leden wilt toevoegen, klikt **u op Pictogram** Toevoegen ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5147c-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5147c-190">Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="5147c-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="5147c-191">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="5147c-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5147c-192">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="5147c-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="5147c-193">Als u een lid wilt verwijderen, selecteert u het lid en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="5147c-194">Het EAC gebruiken om groepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="5147c-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="5147c-195">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="5147c-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="5147c-196">Selecteer in de lijst met groepen de distributiegroep die u wilt verwijderen en klik vervolgens op **Pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5147c-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="5147c-197">PowerShell gebruiken om groepen te beheren</span><span class="sxs-lookup"><span data-stu-id="5147c-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="5147c-198">Zelfstandige EOP PowerShell gebruiken om groepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="5147c-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="5147c-199">Voer de volgende opdracht uit als u een overzichtslijst met alle distributiegroepen en beveiligingsgroepen met e-mail wilt retourneren in zelfstandige EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5147c-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="5147c-200">Als u de lijst met groepsleden wilt retourneren, vervangt u de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5147c-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="5147c-201">Zie Get-Recipient and Get-DistributionGroupMember [(Get-Recipient and](/powershell/module/exchange/get-recipient) [Get-DistributionGroupMember)](/powershell/module/exchange/get-distributiongroupmember)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="5147c-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="5147c-202">Zelfstandige EOP PowerShell gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="5147c-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="5147c-203">Als u distributiegroepen of beveiligingsgroepen met e-mail wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="5147c-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="5147c-204">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="5147c-204">**Notes**:</span></span>

- <span data-ttu-id="5147c-205">De _parameter_ Naam is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="5147c-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="5147c-206">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Naam_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="5147c-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="5147c-207">Als u de parameter _Alias_ niet gebruikt, wordt de parameter _Naam_ gebruikt voor de aliaswaarde.</span><span class="sxs-lookup"><span data-stu-id="5147c-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="5147c-208">Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).</span><span class="sxs-lookup"><span data-stu-id="5147c-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="5147c-209">Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de aliaswaarde gebruikt in de parameter _PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="5147c-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="5147c-210">Als u de parameter _Type_ niet gebruikt, is de standaardwaarde Verdeling.</span><span class="sxs-lookup"><span data-stu-id="5147c-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="5147c-211">In dit voorbeeld wordt een distributiegroep met de naam IT-beheerders gemaakt met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="5147c-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="5147c-212">Zie [New-EOPDistributionGroup voor](/powershell/module/exchange/New-EOPDistributionGroup)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="5147c-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="5147c-213">Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5147c-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="5147c-214">Als u groepen in zelfstandige EOP PowerShell wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="5147c-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="5147c-215">In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) voor de groep Werknemers van Seattle gewijzigd in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5147c-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="5147c-216">In dit voorbeeld worden de huidige leden van de groep Beveiligingsteam vervangen door Kitty Petersen en Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="5147c-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="5147c-217">In dit voorbeeld wordt een nieuwe gebruiker met de naam Tyson Fawcett toegevoegd aan de groep Beveiligingsteam met behoud van de huidige leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="5147c-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="5147c-218">Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="5147c-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="5147c-219">Een groep verwijderen met behulp van externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5147c-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="5147c-220">In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5147c-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="5147c-221">Zie [Remove-EOPDistributionGroup voor](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="5147c-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5147c-222">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="5147c-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="5147c-223">Ga als volgt te werk om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="5147c-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="5147c-224">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="5147c-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="5147c-225">Controleer of de groep wordt vermeld (of niet wordt weergegeven) en controleer de **waarde Groeptype.**</span><span class="sxs-lookup"><span data-stu-id="5147c-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="5147c-226">Selecteer de groep en bekijk de informatie in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.</span><span class="sxs-lookup"><span data-stu-id="5147c-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="5147c-227">Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt vermeld (of niet wordt vermeld):</span><span class="sxs-lookup"><span data-stu-id="5147c-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="5147c-228">Vervang \<GroupIdentity\> deze door de naam, alias of het e-mailadres van de groep en voer de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="5147c-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="5147c-229">Als u de groepsleden wilt weergeven, vervangt u de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5147c-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```