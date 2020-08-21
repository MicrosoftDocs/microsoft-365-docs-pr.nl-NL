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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Beheerders in zelfstandige Exchange Online Protection-organisaties (EOP) kunnen leren hoe u distributiegroepen en beveiligingsgroepen met e-mail kunt maken, wijzigen en verwijderen in het Exchange Admin Center (PowerShell) en zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826551"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="02898-103">Groepen beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="02898-103">Manage groups in EOP</span></span>

<span data-ttu-id="02898-104">U kunt de volgende typen groepen maken, wijzigen en verwijderen in zelfstandige Exchange Online Protection-organisaties (EOP) zonder postvakken van Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="02898-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="02898-105">**Distributiegroepen**: een verzameling e-mail gebruikers of andere distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="02898-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="02898-106">Bijvoorbeeld teams of andere ad hoc groepen die in een gemeenschappelijk gebied een e-mailbericht moeten ontvangen of verzenden.</span><span class="sxs-lookup"><span data-stu-id="02898-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="02898-107">Distributiegroepen zijn exclusief bedoeld voor het distribueren van e-mailberichten en geen beveiligings-principals (ze kunnen geen machtigingen aan hen toewijzen).</span><span class="sxs-lookup"><span data-stu-id="02898-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="02898-108">**Beveiligingsgroepen met e-mail**: een verzameling e-mail gebruikers en andere beveiligingsgroepen die toegangsmachtigingen nodig hebben voor beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="02898-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="02898-109">U kunt bijvoorbeeld bepaalde groep gebruikers beheerdersmachtigingen geven, zodat ze antispam-en anti-malware-instellingen kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="02898-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="02898-110">Nieuwe beveiligingsgroepen met e-mail kunnen standaardberichten van externe (niet-geverifieerde) afzenders weigeren.</span><span class="sxs-lookup"><span data-stu-id="02898-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="02898-111">Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="02898-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="02898-112">U kunt groepen beheren in het Exchange Admin Center (SBV) en zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02898-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02898-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="02898-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02898-114">Om het Exchange-Beheercentrum te openen, raadpleegt u het [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="02898-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="02898-115">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02898-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="02898-116">Wanneer u groepen beheert in zelfstandige EOP PowerShell, kan dit leiden tot vertraging.</span><span class="sxs-lookup"><span data-stu-id="02898-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="02898-117">Voor de PowerShell-procedures in dit onderwerp wordt een batch verwerkingsmethode gebruikt waarmee de vertragings vertraging van een paar minuten wordt veroorzaakt voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="02898-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="02898-118">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="02898-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="02898-119">Specifiek hebt u de rol van distributiegroepen nodig, dat is toegewezen aan de de organizationmanagement (algemene beheerders) en RecipientManagement rollen groepen.</span><span class="sxs-lookup"><span data-stu-id="02898-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="02898-120">Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="02898-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="02898-121">Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="02898-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="02898-122">Problemen?</span><span class="sxs-lookup"><span data-stu-id="02898-122">Having problems?</span></span> <span data-ttu-id="02898-123">Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="02898-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="02898-124">Het Exchange-Beheercentrum gebruiken voor het beheren van distributiegroepen</span><span class="sxs-lookup"><span data-stu-id="02898-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="02898-125">Het gebruik van de toepassing SBV gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="02898-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="02898-126">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="02898-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="02898-127">Klik op **Nieuw** ![ pictogram ](../../media/ITPro-EAC-AddIcon.png) en selecteer een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="02898-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="02898-128">**Distributiegroep**</span><span class="sxs-lookup"><span data-stu-id="02898-128">**Distribution group**</span></span>

   - <span data-ttu-id="02898-129">**Beveiligingsgroep met e-mail**</span><span class="sxs-lookup"><span data-stu-id="02898-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="02898-130">Configureer de volgende instellingen op de pagina nieuwe groep die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="02898-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="02898-131">Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="02898-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="02898-132"><sup>\*</sup>**Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel aan: wanneer e-mail wordt verzonden naar deze groep en in de lijst **groepen** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="02898-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="02898-133">De weergavenaam is vereist en moet uniek zijn en moet gebruikersvriendelijk zijn, zodat de persoon de naam herkent.</span><span class="sxs-lookup"><span data-stu-id="02898-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="02898-134"><sup>\*</sup>**Alias**: gebruik dit vak om de naam van de alias voor de groep te typen.</span><span class="sxs-lookup"><span data-stu-id="02898-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="02898-135">De alias mag niet langer zijn dan 64 tekens en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="02898-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="02898-136">Wanneer een gebruiker de alias typt in de regel aan van een e-mailbericht, wordt deze herleid tot de weergavenaam van de groep.</span><span class="sxs-lookup"><span data-stu-id="02898-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="02898-137"><sup>\*</sup>**E-mailadres**: het e-mailadres bestaat uit de alias aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="02898-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="02898-138">Standaard wordt de waarde van **alias** gebruikt voor de alias waarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="02898-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="02898-139">Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer het domein dat u in uw organisatie hebt geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="02898-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="02898-140">**Beschrijving**: deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="02898-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="02898-141"><sup>\*</sup>**Eigenaren**: een groepseigenaar kan groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="02898-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="02898-142">Standaard is de persoon die een groep maakt, de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="02898-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="02898-143">Alle groepen moeten minimaal één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="02898-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="02898-144">Als u eigenaren wilt **Add** toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="02898-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="02898-145">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**.</span><span class="sxs-lookup"><span data-stu-id="02898-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="02898-146">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="02898-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="02898-147">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="02898-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="02898-148">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt **u op** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="02898-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="02898-149">**Leden**: groepsleden toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="02898-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="02898-150">Als u leden **wilt toevoegen, klikt u** op ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="02898-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="02898-151">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**.</span><span class="sxs-lookup"><span data-stu-id="02898-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="02898-152">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="02898-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="02898-153">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="02898-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="02898-154">Als u een lid wilt verwijderen, selecteert u het lid en klikt **u op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="02898-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="02898-155">Wanneer u klaar bent, klikt u op **Opslaan** om de distributiegroep te maken.</span><span class="sxs-lookup"><span data-stu-id="02898-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="02898-156">De Exchange-distributiegroepen wijzigen</span><span class="sxs-lookup"><span data-stu-id="02898-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="02898-157">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="02898-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="02898-158">Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik vervolgens op het pictogram bewerken **bewerken** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="02898-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="02898-159">Op de pagina met eigenschappen van distributiegroep die wordt geopend, klikt u op een van de volgende tabbladen om de eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="02898-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="02898-160">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="02898-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="02898-161">Algemeen</span><span class="sxs-lookup"><span data-stu-id="02898-161">General</span></span>

<span data-ttu-id="02898-162">Via dit tabblad kunt u algemene informatie over de groep weergeven of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="02898-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="02898-163">**Weergavenaam**: deze naam wordt weergegeven in het adresboek, op de regel aan wanneer e-mail wordt verzonden naar deze groep en in de **lijst met groepen**.</span><span class="sxs-lookup"><span data-stu-id="02898-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="02898-164">De weergavenaam is vereist en moet gebruikersvriendelijk zijn, zodat de persoon de naam herkent.</span><span class="sxs-lookup"><span data-stu-id="02898-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="02898-165">Het domein moet ook uniek zijn in uw domein.</span><span class="sxs-lookup"><span data-stu-id="02898-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="02898-166">Als u een Groepsbeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die is gedefinieerd door het beleid.</span><span class="sxs-lookup"><span data-stu-id="02898-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="02898-167">**Alias**: dit is het gedeelte van het e-mailadres dat links van het @-symbool wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="02898-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="02898-168">Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep eveneens gewijzigd en bevat de nieuwe alias.</span><span class="sxs-lookup"><span data-stu-id="02898-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="02898-169">Ook wordt het e-mailadres met de vorige alias bewaard als een proxyadres voor de groep.</span><span class="sxs-lookup"><span data-stu-id="02898-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="02898-170">**E-mailadres**: het e-mailadres bestaat uit de alias aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="02898-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="02898-171">Standaard wordt de waarde van **alias** gebruikt voor de alias waarde, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="02898-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="02898-172">Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer het domein dat u in uw organisatie hebt geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="02898-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="02898-173">**Beschrijving**: deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="02898-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="02898-174">Eigendom</span><span class="sxs-lookup"><span data-stu-id="02898-174">Ownership</span></span>

<span data-ttu-id="02898-175">Gebruik dit tabblad om groepseigenaren toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="02898-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="02898-176">Een groepseigenaar kan groepslidmaatschap beheren.</span><span class="sxs-lookup"><span data-stu-id="02898-176">A group owner can manage group membership.</span></span> <span data-ttu-id="02898-177">Standaard is de persoon die een groep maakt, de eigenaar.</span><span class="sxs-lookup"><span data-stu-id="02898-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="02898-178">Alle groepen moeten minimaal één eigenaar hebben.</span><span class="sxs-lookup"><span data-stu-id="02898-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="02898-179">Als u eigenaren wilt **Add** toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="02898-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="02898-180">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde en klikt u vervolgens op **add->**.</span><span class="sxs-lookup"><span data-stu-id="02898-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="02898-181">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="02898-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="02898-182">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="02898-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="02898-183">Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt **u op** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="02898-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="02898-184">Waartoe</span><span class="sxs-lookup"><span data-stu-id="02898-184">Membership</span></span>

<span data-ttu-id="02898-185">Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="02898-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="02898-186">Groepseigenaren hoeven niet lid te zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="02898-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="02898-187">Als u leden **wilt toevoegen, klikt u** op ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="02898-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="02898-188">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**.</span><span class="sxs-lookup"><span data-stu-id="02898-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="02898-189">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="02898-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="02898-190">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="02898-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="02898-191">Als u een lid wilt verwijderen, selecteert u het lid en klikt **u op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="02898-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="02898-192">Het Exchange-Beheercentrum gebruiken om groepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="02898-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="02898-193">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="02898-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="02898-194">Selecteer in de lijst met groepen de distributiegroep die u **wilt verwijderen en klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="02898-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="02898-195">PowerShell gebruiken om groepen te beheren</span><span class="sxs-lookup"><span data-stu-id="02898-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="02898-196">Standalone EOP PowerShell gebruiken om groepen weer te geven</span><span class="sxs-lookup"><span data-stu-id="02898-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="02898-197">Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle distributiegroepen en beveiligingsgroepen met e-mail in standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02898-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="02898-198">Als u de lijst met groepsleden wilt weergeven, vervangt u \<GroupIdentity\> de naam, alias of het e-mailadres van de groep en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="02898-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="02898-199">Zie [Get-](https://docs.microsoft.com/powershell/module/exchange/get-recipient) [DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)voor meer informatie over de syntaxis en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="02898-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="02898-200">Standalone EOP PowerShell gebruiken om groepen te maken</span><span class="sxs-lookup"><span data-stu-id="02898-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="02898-201">Als u distributiegroepen of beveiligingsgroepen met e-mail wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="02898-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="02898-202">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="02898-202">**Notes**:</span></span>

- <span data-ttu-id="02898-203">De _naam_ parameter is vereist, mag maximaal 64 tekens lang zijn en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="02898-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="02898-204">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _name_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="02898-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="02898-205">Als u de parameter _alias_ niet gebruikt, wordt de parameter _name_ gebruikt voor de alias waarde.</span><span class="sxs-lookup"><span data-stu-id="02898-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="02898-206">Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).</span><span class="sxs-lookup"><span data-stu-id="02898-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="02898-207">Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de waarde van de alias gebruikt in de _PrimarySmtpAddress_ -parameter.</span><span class="sxs-lookup"><span data-stu-id="02898-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="02898-208">Als u de parameter _type_ niet gebruikt, is de standaardwaarde distributie.</span><span class="sxs-lookup"><span data-stu-id="02898-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="02898-209">In dit voorbeeld wordt een distributiegroep met de naam beheerders gemaakt met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="02898-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="02898-210">Zie [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="02898-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="02898-211">Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="02898-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="02898-212">Gebruik de volgende syntaxis om groepen in een zelfstandige EOP PowerShell te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="02898-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="02898-213">In dit voorbeeld wordt het primaire SMTP-adres (ook wel antwoordadres genoemd) voor de groep werknemers in de Seattle gebruikt in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="02898-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="02898-214">In dit voorbeeld worden de huidige leden van de groep beveiligings team vervangen door grappige Petersen en Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="02898-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="02898-215">In dit voorbeeld wordt een nieuwe gebruiker met de naam Tyson Fawcett toegevoegd aan de groep met de naam Security team, en de huidige leden van de groep behouden.</span><span class="sxs-lookup"><span data-stu-id="02898-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="02898-216">Zie [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="02898-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="02898-217">Een groep verwijderen via externe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02898-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="02898-218">In dit voorbeeld wordt de distributiegroep met de naam beheerders verwijderd.</span><span class="sxs-lookup"><span data-stu-id="02898-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="02898-219">Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="02898-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="02898-220">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="02898-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="02898-221">Voer een van de volgende stappen uit om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="02898-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="02898-222">Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="02898-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="02898-223">Controleer of de groep wel of niet in de lijst staat, en controleer de waarde van het **groeps type** .</span><span class="sxs-lookup"><span data-stu-id="02898-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="02898-224">Selecteer de groep en Bekijk de informatie in het detailvenster of klik op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-AddIcon.png) om de instellingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="02898-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="02898-225">Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt weergegeven (of niet wordt weergegeven):</span><span class="sxs-lookup"><span data-stu-id="02898-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="02898-226">Vervang de \<GroupIdentity\> naam, alias of het e-mailadres van de groep en voer de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="02898-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="02898-227">Als u de groepsleden wilt weergeven, vervangt u de \<GroupIdentity\> naam, alias of het e-mailadres van de groep en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="02898-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
