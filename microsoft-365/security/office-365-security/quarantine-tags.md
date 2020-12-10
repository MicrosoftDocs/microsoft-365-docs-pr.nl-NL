---
title: Quarantaine Tags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Beheerders kunnen meer informatie over het gebruik van quarantaine-Tags om te bepalen wat gebruikers kunnen doen met hun Quarantine-berichten.
ms.openlocfilehash: 498a5f45fa62481f7f4f8dfe5ece8a51a038f99a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616006"
---
# <a name="quarantine-tags"></a><span data-ttu-id="3fcbc-103">Quarantaine Tags</span><span class="sxs-lookup"><span data-stu-id="3fcbc-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="3fcbc-104">De functies die in dit artikel worden beschreven, zijn momenteel in de preview-versie, zijn niet beschikbaar voor iedereen en kunnen worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="3fcbc-105">Met quarantaine-labels in Exchange Online Protection (EOP) kunnen beheerders aangeven wat gebruikers kunnen doen met hun Quarantine-berichten op basis van de ontvangst van het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="3fcbc-106">EOP is traditioneel toegestaan of voorkomen dat bepaalde niveaus van interactiviteit voor berichten in [quarantaine](find-and-release-quarantined-messages-as-a-user.md) en [spam meldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md)zijn toegestaan.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="3fcbc-107">Eindgebruikers kunnen bijvoorbeeld berichten weergeven en vrijgeven die zijn gequarantined via antispam filteren als spam of bulksgewijs, maar ze kunnen geen berichten weergeven of vrijgeven die zijn gequarantined als phishing met een hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="3fcbc-108">Voor [ondersteunde beveiligingsfuncties](#step-2-assign-a-quarantine-tag-to-supported-features)opgeven welke gebruikers e-mail meldingen voor eindgebruikers mogen doen en in hun quarantaine berichten in quarantaine (berichten waarbij de gebruiker een geadresseerde is).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="3fcbc-109">Standaard wordt er automatisch quarantaine Tags toegewezen voor het afdwingen van de historische mogelijkheden voor eindgebruikers van berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="3fcbc-110">U kunt ook aangepaste quarantaine Tags maken en toewijzen om te voorkomen dat eindgebruikers bepaalde acties op quarantaine berichten uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="3fcbc-111">De afzonderlijke machtigingen worden gecombineerd in de volgende vooraf ingestelde machtigingsgroepen:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="3fcbc-112">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-112">No access</span></span>
- <span data-ttu-id="3fcbc-113">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-113">Limited access</span></span>
- <span data-ttu-id="3fcbc-114">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-114">Full access</span></span>

<span data-ttu-id="3fcbc-115">De beschikbare afzonderlijke machtigingen en de beschikbare afzonderlijke machtigingen in de vooraf ingestelde machtigingsgroepen worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="3fcbc-116">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="3fcbc-116">Permission</span></span>|<span data-ttu-id="3fcbc-117">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-117">No access</span></span>|<span data-ttu-id="3fcbc-118">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-118">Limited access</span></span>|<span data-ttu-id="3fcbc-119">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="3fcbc-120">**Afzender toestaan** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fcbc-122">**Afzender blokkeren** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fcbc-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-125">**Delete** (_PermissionToDelete_)</span></span>||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fcbc-128">**Voorbeeld** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-128">**Preview** (_PermissionToPreview_)</span></span>||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fcbc-131">**Toestaan dat geadresseerden een bericht uit Quarantine vrijgeven** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fcbc-133">**Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit Quarantine** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="3fcbc-135">Als u de standaardmachtigingen in de vooraf ingestelde machtigingsgroepen niet bevalt, kunt u aangepaste machtigingen gebruiken wanneer u aangepaste quarantaine Tags maakt of wijzigt.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="3fcbc-136">Zie voor meer informatie over wat u doet met de machtiging de sectie Machtigingen voor quarantaine voor de [quarantaine-label](#quarantine-tag-permission-details) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="3fcbc-137">U maakt en wijst quarantaine tags toe in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken van Exchange Online; zelfstandige EOP PowerShell in EOP-organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3fcbc-138">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="3fcbc-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3fcbc-139">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3fcbc-140">Als u rechtstreeks naar de pagina met **quarantaine Tags** wilt gaan, opent u deze <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="3fcbc-141">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3fcbc-142">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3fcbc-143">Als u quarantaine codes wilt weergeven, maken, wijzigen of verwijderen, moet u lid zijn van de rollen **Organisatiebeheer** of **beveiligingsbeheerder** in het [beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fcbc-144">Stap 1: quarantaine Tags maken in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="3fcbc-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="3fcbc-145">Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \>  en selecteer vervolgens **quarantaine Tags**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fcbc-146">Selecteer op de pagina **Quarantine-Tags** de optie **aangepaste tag toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="3fcbc-147">De wizard **nieuwe code** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="3fcbc-148">Voer op de pagina **labelnaam** een korte maar unieke naam in het veld **labelnaam** in.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="3fcbc-149">U moet de tag op naam identificeren en selecteren in de komende stappen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="3fcbc-150">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3fcbc-151">Selecteer op de pagina **bericht toegang voor geadresseerde** een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="3fcbc-152">**Geen toegang**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-152">**No access**</span></span>
   - <span data-ttu-id="3fcbc-153">**Beperkte toegang**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-153">**Limited access**</span></span>
   - <span data-ttu-id="3fcbc-154">**Volledige toegang**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-154">**Full access**</span></span>

   <span data-ttu-id="3fcbc-155">Eerder in dit artikel worden de afzonderlijke machtigingen van deze machtigingsgroepen beschreven.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="3fcbc-156">Als u aangepaste machtigingen wilt opgeven, selecteert u **specifieke toegang instellen (Geavanceerd)** en configureert u de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="3fcbc-157">**Selecteer voorkeur van release actie**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="3fcbc-158">**Geen uitgave actie**: dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="3fcbc-159">**Toestaan dat geadresseerden een bericht uit Quarantine vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="3fcbc-160">**Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit Quarantine**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="3fcbc-161">**Selecteer extra acties geadresseerden kunnen berichten in quarantaine plaatsen**: Selecteer enkele, alle of geen van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="3fcbc-162">**Wissen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-162">**Delete**</span></span>
       - <span data-ttu-id="3fcbc-163">**Voorbeeld**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-163">**Preview**</span></span>
       - <span data-ttu-id="3fcbc-164">**Afzender toestaan**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-164">**Allow sender**</span></span>
       - <span data-ttu-id="3fcbc-165">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-165">**Block sender**</span></span>

   <span data-ttu-id="3fcbc-166">Deze machtigingen en hun effect op quarantaine berichten en de spam meldingen van eindgebruikers worden beschreven in de sectie [machtigingsgegevens van Quarantine](#quarantine-tag-permission-details) voor de tag verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="3fcbc-167">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3fcbc-168">Controleer de instellingen op de pagina **overzicht** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="3fcbc-169">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3fcbc-170">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="3fcbc-171">Op de bevestigingspagina die verschijnt, klikt u op **gereed** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="3fcbc-172">U bent nu klaar om de code van Quarantine toe te wijzen aan een Quarantine-functie, zoals wordt beschreven in de sectie [stap 2](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="3fcbc-173">Quarantaine Tags maken in PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcbc-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fcbc-174">Als u liever PowerShell gebruikt voor het maken van quarantaine Tags, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de **nieuwe QuarantineTag-** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="3fcbc-175">U kunt kiezen uit twee verschillende methoden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="3fcbc-176">Gebruik de parameter _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="3fcbc-177">Gebruik de parameter _EndUserQuarantinePermissions_ .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="3fcbc-178">In de volgende secties wordt beschreven welke methoden worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="3fcbc-179">De parameter EndUserQuarantinePermissionsValue gebruiken</span><span class="sxs-lookup"><span data-stu-id="3fcbc-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="3fcbc-180">Gebruik de volgende syntaxis om een Quarantine-tag te maken met behulp van de parameter _EndUserQuarantinePermissionsValue_ :</span><span class="sxs-lookup"><span data-stu-id="3fcbc-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="3fcbc-181">De parameter _EndUserQuarantinePermissionsValue_ gebruikt een decimale waarde die wordt geconverteerd van een binaire waarde.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="3fcbc-182">De binaire waarde komt overeen met de beschikbare Quarantine-machtigingen voor eindgebruikers in een specifieke volgorde.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="3fcbc-183">Voor elke machtiging is de waarde 1 gelijk aan waar en is de waarde 0 gelijk aan false.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="3fcbc-184">In de volgende tabel vindt u een beschrijving van de vereiste volgorde en waarden voor elke afzonderlijke machtiging in vooraf ingestelde machtigingsgroepen:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="3fcbc-185">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="3fcbc-185">Permission</span></span>|<span data-ttu-id="3fcbc-186">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-186">No access</span></span>|<span data-ttu-id="3fcbc-187">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-187">Limited access</span></span>|<span data-ttu-id="3fcbc-188">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="3fcbc-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="3fcbc-189">PermissionToAllowSender</span></span>|<span data-ttu-id="3fcbc-190">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-190">0</span></span>|<span data-ttu-id="3fcbc-191">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-191">0</span></span>|<span data-ttu-id="3fcbc-192">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-192">1</span></span>|
|<span data-ttu-id="3fcbc-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="3fcbc-193">PermissionToBlockSender</span></span>|<span data-ttu-id="3fcbc-194">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-194">0</span></span>|<span data-ttu-id="3fcbc-195">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-195">1</span></span>|<span data-ttu-id="3fcbc-196">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-196">1</span></span>|
|<span data-ttu-id="3fcbc-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="3fcbc-197">PermissionToDelete</span></span>|<span data-ttu-id="3fcbc-198">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-198">0</span></span>|<span data-ttu-id="3fcbc-199">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-199">1</span></span>|<span data-ttu-id="3fcbc-200">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-200">1</span></span>|
|<span data-ttu-id="3fcbc-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fcbc-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="3fcbc-202">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-202">0</span></span>|<span data-ttu-id="3fcbc-203">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-203">0</span></span>|<span data-ttu-id="3fcbc-204">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-204">0</span></span>|
|<span data-ttu-id="3fcbc-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="3fcbc-205">PermissionToPreview</span></span>|<span data-ttu-id="3fcbc-206">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-206">0</span></span>|<span data-ttu-id="3fcbc-207">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-207">1</span></span>|<span data-ttu-id="3fcbc-208">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-208">1</span></span>|
|<span data-ttu-id="3fcbc-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fcbc-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="3fcbc-210">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-210">0</span></span>|<span data-ttu-id="3fcbc-211">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-211">0</span></span>|<span data-ttu-id="3fcbc-212">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-212">1</span></span>|
|<span data-ttu-id="3fcbc-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fcbc-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="3fcbc-214">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-214">0</span></span>|<span data-ttu-id="3fcbc-215">1</span><span class="sxs-lookup"><span data-stu-id="3fcbc-215">1</span></span>|<span data-ttu-id="3fcbc-216">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-216">0</span></span>|
|<span data-ttu-id="3fcbc-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fcbc-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="3fcbc-218">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-218">0</span></span>|<span data-ttu-id="3fcbc-219">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-219">0</span></span>|<span data-ttu-id="3fcbc-220">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-220">0</span></span>|
|<span data-ttu-id="3fcbc-221">Binaire waarde</span><span class="sxs-lookup"><span data-stu-id="3fcbc-221">Binary value</span></span>|<span data-ttu-id="3fcbc-222">00000000</span><span class="sxs-lookup"><span data-stu-id="3fcbc-222">00000000</span></span>|<span data-ttu-id="3fcbc-223">01101010</span><span class="sxs-lookup"><span data-stu-id="3fcbc-223">01101010</span></span>|<span data-ttu-id="3fcbc-224">11101100</span><span class="sxs-lookup"><span data-stu-id="3fcbc-224">11101100</span></span>|
|<span data-ttu-id="3fcbc-225">Te gebruiken decimale waarde</span><span class="sxs-lookup"><span data-stu-id="3fcbc-225">Decimal value to use</span></span>|<span data-ttu-id="3fcbc-226">0</span><span class="sxs-lookup"><span data-stu-id="3fcbc-226">0</span></span>|<span data-ttu-id="3fcbc-227">106</span><span class="sxs-lookup"><span data-stu-id="3fcbc-227">106</span></span>|<span data-ttu-id="3fcbc-228">236</span><span class="sxs-lookup"><span data-stu-id="3fcbc-228">236</span></span>|

<span data-ttu-id="3fcbc-229"><sup>\*</sup> Deze waarde is op dit moment altijd 0.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="3fcbc-230">Voor PermissionToViewHeader wordt met de waarde 0 de knop berichtkop **weergeven** niet verborgen voor de details van het gequarantinee bericht (de knop is altijd beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="3fcbc-231"><sup>\*\*</sup> Stel niet beide waarden in op 1.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="3fcbc-232">Stel een in op 1 en de andere 0, of stel deze in op 0.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="3fcbc-233">In het volgende voorbeeld wordt de nieuwe naam van de naam van de Quarantine-tag geopend en worden de machtigingen geen toegang toegewezen, zoals beschreven in de vorige tabel.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="3fcbc-234">Gebruik voor machtigingen voor beperkte toegang de waarde 106.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="3fcbc-235">Gebruik voor volledige toegangsmachtigingen de waarde 236.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="3fcbc-236">Gebruik voor aangepaste machtigingen de eerdere tabel voor de binaire waarde die overeenkomt met de gewenste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="3fcbc-237">Converteer de binaire waarde naar een decimale waarde en gebruik de decimale waarde voor de parameter _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="3fcbc-238">Zie [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="3fcbc-239">De parameter EndUserQuarantinePermissions gebruiken</span><span class="sxs-lookup"><span data-stu-id="3fcbc-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="3fcbc-240">Voer de volgende stappen uit om een Quarantine-tag te maken met behulp van de parameter _EndUserQuarantinePermissionsValue_ :</span><span class="sxs-lookup"><span data-stu-id="3fcbc-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="3fcbc-241">Een.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-241">A.</span></span> <span data-ttu-id="3fcbc-242">Een quarantaine machtigingen object in een variabele opslaan met de **nieuwe QuarantinePermissions-** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="3fcbc-243">BB.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-243">B.</span></span> <span data-ttu-id="3fcbc-244">Gebruik de variabele als _EndUserQuarantinePermissions_ waarde in de opdracht **New-QuarantineTag** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="3fcbc-245">Stap A: een quarantaine machtigingen object opslaan in een variabele</span><span class="sxs-lookup"><span data-stu-id="3fcbc-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="3fcbc-246">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="3fcbc-247">De standaardwaarde voor ongebruikte parameters is `$false` , dus u hoeft de parameters alleen te gebruiken waarvoor u een waarde wilt instellen `$true` .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="3fcbc-248">In de volgende voorbeelden ziet u hoe u machtigingsobjecten kunt maken die overeenkomen met de vooraf ingestelde machtigingsgroepen:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="3fcbc-249">**Geen toegang**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="3fcbc-250">**Beperkte toegang**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="3fcbc-251">**Volledige toegang**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="3fcbc-252">Als u de waarden wilt weergeven die u hebt ingesteld, voert u de variabele naam uit als een opdracht (bijvoorbeeld de opdracht uitvoeren `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="3fcbc-253">Stel voor aangepaste machtigingen de parameters _PermissionToRelease_ en _PermissionToRequestRelease_ niet in op `$true` .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="3fcbc-254">Stel een in `$true` en sluit het `$false` af, of houd beide ingedrukt `$false` .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="3fcbc-255">U kunt ook een bestaande machtigings objectvariabele wijzigen nadat u deze hebt gemaakt, maar voordat u deze gebruikt met behulp van de cmdlet **set-QuarantinePermissions** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="3fcbc-256">Zie [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) en [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="3fcbc-257">Stap B: gebruik de variabele in de opdracht New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="3fcbc-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="3fcbc-258">Nadat u het object permissions hebt gemaakt en opgeslagen in een variabele, gebruikt u de variabele voor de waarde van de _EndUserQuarantinePermission_ -parameter in de volgende opdracht **New-QuarantineTag** :</span><span class="sxs-lookup"><span data-stu-id="3fcbc-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="3fcbc-259">In dit voorbeeld wordt een nieuwe Quarantine-tag met de naam LimitedAccess gemaakt met behulp van het `$LimitedAccess` machtigingen object dat in de vorige stap is beschreven en gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="3fcbc-260">Zie [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="3fcbc-261">Stap 2: een quarantaine-tag toewijzen aan ondersteunde functies</span><span class="sxs-lookup"><span data-stu-id="3fcbc-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="3fcbc-262">In _ondersteunde_ beveiligingsfuncties waarmee u berichten of bestanden (automatisch of als configureerbare actie) kunt toewijzen, kunt u een Quarantine-tag toewijzen aan de beschikbare quarantaine acties.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="3fcbc-263">In de volgende tabel vindt u een beschrijving van de functies voor quarantaine en de beschikbaarheid van quarantaine Tags:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="3fcbc-264">Functie</span><span class="sxs-lookup"><span data-stu-id="3fcbc-264">Feature</span></span>|<span data-ttu-id="3fcbc-265">Ondersteunde labels voor quarantaine?</span><span class="sxs-lookup"><span data-stu-id="3fcbc-265">Quarantine tags supported?</span></span>|<span data-ttu-id="3fcbc-266">Standaard gebruikte quarantaine Tags</span><span class="sxs-lookup"><span data-stu-id="3fcbc-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="3fcbc-267">[Anti spam beleid](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="3fcbc-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="3fcbc-268">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="3fcbc-269">**Hoge betrouwbaarheid spam** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="3fcbc-270">**Malafide e-mailadres** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="3fcbc-271">**E-mail met malafide vertrouwens kwaliteit** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="3fcbc-272">**Bulk-e-mail** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="3fcbc-273">Ja</span><span class="sxs-lookup"><span data-stu-id="3fcbc-273">Yes</span></span>|<ul><li><span data-ttu-id="3fcbc-274">DefaultSpamTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="3fcbc-275">DefaultHighConfSpamTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="3fcbc-276">DefaultPhishTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="3fcbc-277">DefaultHighConfPhishTag (geen toegang)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="3fcbc-278">DefaultBulkTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="3fcbc-279">Anti malafide beleid:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="3fcbc-280">[Spoof Intelligence-bescherming](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="3fcbc-281">[Imitatie bescherming](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fcbc-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="3fcbc-282">**E-mail wordt verzonden door een geïmiteerde gebruiker** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="3fcbc-283">**E-mail wordt verzonden door een geïmiteerd domein** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="3fcbc-284">**Postvak intelligentie** \> **E-mail wordt verzonden door een geïmiteerde gebruiker** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="3fcbc-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="3fcbc-285">Nee</span><span class="sxs-lookup"><span data-stu-id="3fcbc-285">No</span></span>|<span data-ttu-id="3fcbc-286">n/b</span><span class="sxs-lookup"><span data-stu-id="3fcbc-286">n/a</span></span>|
|<span data-ttu-id="3fcbc-287">[Beleid voor anti-malware](configure-anti-malware-policies.md): alle gevonden berichten worden altijd in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="3fcbc-288">Nee</span><span class="sxs-lookup"><span data-stu-id="3fcbc-288">No</span></span>|<span data-ttu-id="3fcbc-289">n/b</span><span class="sxs-lookup"><span data-stu-id="3fcbc-289">n/a</span></span>|
|[<span data-ttu-id="3fcbc-290">ATP voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fcbc-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="3fcbc-291">Nee</span><span class="sxs-lookup"><span data-stu-id="3fcbc-291">No</span></span>|<span data-ttu-id="3fcbc-292">n/b</span><span class="sxs-lookup"><span data-stu-id="3fcbc-292">n/a</span></span>|
|<span data-ttu-id="3fcbc-293">Voor [e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transport-regels genoemd) met de actie: **Bezorg het bericht in de gehoste quarantaine** (_quarantaine_).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="3fcbc-294">Nee</span><span class="sxs-lookup"><span data-stu-id="3fcbc-294">No</span></span>|<span data-ttu-id="3fcbc-295">n/b</span><span class="sxs-lookup"><span data-stu-id="3fcbc-295">n/a</span></span>|
|

<span data-ttu-id="3fcbc-296"><sup>\*</sup> De instellingen voor imitatie beveiliging zijn alleen beschikbaar in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="3fcbc-297">Als u tevreden bent met de machtigingen voor eindgebruikers van de standaard Quarantine-Tags, hoeft u niets te doen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="3fcbc-298">Als u de capaciteiten van de eindgebruikers wilt aanpassen (beschikbare knoppen) in spam meldingen voor eindgebruikers of in het ontvangen van Details van een bericht, kunt u een aangepaste Quarantine-markering toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="3fcbc-299">Quarantaine tags toewijzen in Antispambeleid in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="3fcbc-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="3fcbc-300">Volledige instructies voor het maken en wijzigen van anti-spam beleid vindt u in het onderwerp [Antispambeleid in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="3fcbc-301">Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \>  \> en selecteer vervolgens **anti spam**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="3fcbc-302">Of open <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="3fcbc-303">Zoek en selecteer een bestaand Antispambeleid om dit te bewerken, of maak een nieuw anti-spam beleid.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="3fcbc-304">Ga in het vervolgmenu met beleidsdetails naar het gedeelte **spam-en Bulkacties** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="3fcbc-305">Als u **quarantaine bericht** hebt geselecteerd voor de actie van een beschikbare spamfilter Verdict, is het dialoogvenster **quarantainebeleid toepassen** beschikbaar voor het selecteren van de Quarantine-tag voor die Verdict.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="3fcbc-306">**Opmerking**: wanneer u een nieuw beleid maakt, wordt er een lege Quarantine-label waarde voor een spam filterd verdict aangegeven</span><span class="sxs-lookup"><span data-stu-id="3fcbc-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="3fcbc-307">Wanneer u de beleidsregels later bewerkt, worden de lege waarden vervangen door de werkelijke namen van de werkelijke namen van quarantaine Tags, zoals beschreven in de vorige tabel.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Selectie van quarantaine-Tags in een Antispambeleid](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="3fcbc-309">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="3fcbc-310">Quarantaine tags toewijzen in Antispambeleid in PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcbc-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="3fcbc-311">Als u liever PowerShell gebruikt om quarantaine tags toe te wijzen in Antispambeleid, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="3fcbc-312">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-312">**Notes**:</span></span>

- <span data-ttu-id="3fcbc-313">De standaardwaarde voor de _HighConfidencePhishAction_ -parameter is Quarantine, dus u hoeft de Quarantine-actie niet in te stellen voor de detectie van hoge betrouwbaarheid in nieuwe antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="3fcbc-314">Voor alle andere Verdicts voor spamfilters in een nieuw of bestaand Antispambeleid, is de quarantaine-tag alleen van kracht als de actiewaarde Quarantine is.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="3fcbc-315">Voer de volgende opdracht uit als u de actiewaarden wilt weergeven in een bestaand Antispambeleid:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="3fcbc-316">Zie [EOP antispam beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)voor informatie over de standaardactie waarden en de aanbevolen actiewaarden voor de standaard en strikte.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="3fcbc-317">Een spam filtering verdict zonder een bijbehorende Quarantine-label parameter betekent de [standaard Quarantine-tag](#step-2-assign-a-quarantine-tag-to-supported-features) voor dat verdict wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="3fcbc-318">U hoeft alleen de standaardindeling van Quarantine te vervangen door een aangepaste Quarantine-tag als u de standaardfuncties voor eindgebruikers van quarantaine berichten wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="3fcbc-319">Voor een nieuw Antispambeleid in PowerShell is een spamfilter beleid vereist met behulp van de **New-HostedContentFilterPolicy** -cmdlet en een nieuwe regel voor spamfilter (Recipient filters) met behulp van de **New-HostedContentFilterRule-** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="3fcbc-320">Zie [PowerShell gebruiken om Antispambeleid te maken](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="3fcbc-321">In dit voorbeeld wordt een nieuw beleid voor het filteren van ongewenste e-mail gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="3fcbc-322">De actie voor alle spam filtering Verdicts is ingesteld op Quarantine.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="3fcbc-323">De aangepaste map met de naam waartoe **geen toegangsrechten wordt** toegewezen, vervangt standaard Quarantine Tags waaraan geen **toegangs** machtigingen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="3fcbc-324">Zie [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="3fcbc-325">In dit voorbeeld wordt het bestaande spamfilter beleid met de naam Human resources gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="3fcbc-326">De actie voor de spam Quarantine verdict is ingesteld op Quarantine en de aangepaste Quarantine-tag heeft de naam toegang toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="3fcbc-327">Zie [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="3fcbc-328">Instellingen voor globaal Quarantine-meldingen configureren in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="3fcbc-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="3fcbc-329">Met de algemene instellingen voor quarantaine Tags kunt u de spam meldingen voor eindgebruikers aanpassen die worden verzonden naar geadresseerden van berichten die zijn gequarantined.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="3fcbc-330">Voor meer informatie over deze meldingen raadpleegt u [spam meldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="3fcbc-331">Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \>  en selecteer vervolgens **quarantaine Tags**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fcbc-332">Selecteer op de pagina **Quarantine-Tags** de optie **globale instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="3fcbc-333">Configureer enkele of alle van de volgende instellingen in het vervolgmenu met **instellingen voor Quarantine-meldingen** dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="3fcbc-334">**Mijn bedrijfslogo gebruiken**: Selecteer deze optie om het standaardlogo van Microsoft te vervangen dat wordt gebruikt voor spam meldingen voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="3fcbc-335">Voordat u dit doet, moet u de instructies volgen in [het Microsoft 365-thema aanpassen voor uw organisatie](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) om het aangepaste logo te uploaden.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="3fcbc-336">In de volgende schermafbeelding ziet u een aangepast logo in een spam melding voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Een aangepast logo in een melding voor spam van eindgebruikers](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="3fcbc-338">**Taal kiezen**: spam meldingen voor eindgebruikers zijn al gelokaliseerd op basis van de taalinstellingen van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="3fcbc-339">U kunt aangepaste tekst in verschillende talen opgeven voor de **weergavenaam** en de **vrijwarings** waarden.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="3fcbc-340">Selecteer minimaal één taal in het vak voor de eerste taal en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="3fcbc-341">U kunt meerdere talen selecteren door op **toevoegen** te klikken.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="3fcbc-342">Een vak van de sectie taal bevat alle talen die u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Geselecteerde talen in het tweede vak van de taal in de instellingen voor algemeen Quarantine-meldingen van quarantaine markeringen](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="3fcbc-344">**Weergavenaam**: de weergavenaam van de afzender aanpassen die wordt gebruikt voor spam meldingen voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="3fcbc-345">Voor elke taal die u hebt toegevoegd, selecteert u de taal in het tweede vak taal (niet op de X) en typt u de gewenste tekstwaarde in het vak **weergavenaam** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="3fcbc-346">In de volgende schermafbeelding wordt de aangepaste weergavenaam weergegeven in een spam melding voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Een aangepaste weergavenaam van de afzender in een spam melding voor eindgebruikers](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="3fcbc-348">**Vrijwaring**: een aangepaste Disclaimer toevoegen aan de onderkant van spam meldingen voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="3fcbc-349">De gelokaliseerde tekst, **een afwijzing van uw organisatie:** wordt altijd eerst opgenomen, gevolgd door de tekst die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="3fcbc-350">Voor elke taal die u hebt toegevoegd, selecteert u de taal in het tweede vak taal (niet op de X) en typt u de gewenste tekstwaarde in het vak **Disclaimer** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="3fcbc-351">In de volgende schermafbeelding ziet u de aangepaste disclaimer in een melding voor spam van eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Een aangepaste Disclaimer onder aan een spam melding voor eindgebruikers](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fcbc-353">Quarantaine tags weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="3fcbc-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="3fcbc-354">Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \>  en selecteer vervolgens **quarantaine Tags**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="3fcbc-355">Als u de instellingen van ingebouwde of aangepaste Quarantine-tags wilt bekijken, selecteert u de quarantaine-tag in de lijst (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="3fcbc-356">Als u de algemene instellingen wilt bekijken, selecteert u **algemene instellingen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="3fcbc-357">Quarantaine-markeringen weergeven in PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcbc-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fcbc-358">Voer een van de volgende stappen uit als u liever PowerShell gebruikt om quarantaine Tags weer te geven:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="3fcbc-359">Voer de volgende opdracht uit als u een overzichtslijst met alle ingebouwde of aangepaste tags wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="3fcbc-360">Als u de instellingen van ingebouwde of aangepaste Quarantine-tags wilt bekijken, vervangt u \<TagName\> de naam van de quarantaine-tag en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="3fcbc-361">Voer de volgende opdracht uit om de algemene instellingen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="3fcbc-362">Zie [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fcbc-363">Quarantaine markeringen verwijderen in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="3fcbc-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="3fcbc-364">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-364">**Notes**:</span></span>

- <span data-ttu-id="3fcbc-365">U kunt ingebouwde Quarantine-Tags niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="3fcbc-366">Voordat u een aangepaste Quarantine-tag verwijdert, controleert u of deze niet wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="3fcbc-367">Voer bijvoorbeeld de volgende opdracht uit in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="3fcbc-368">Als u de tag Quarantine gebruikt, moet u [de toegewezen quarantaine-tag vervangen](#step-2-assign-a-quarantine-tag-to-supported-features) voordat u deze verwijdert.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="3fcbc-369">Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \>  en selecteer vervolgens **quarantaine Tags**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fcbc-370">Selecteer op de pagina **Quarantine-Tags** de aangepaste Quarantine-tag die u wilt verwijderen en klik vervolgens op **markering verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="3fcbc-371">Klik in het bevestigingsvenster dat wordt weergegeven op **tag verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="3fcbc-372">Quarantaine markeringen verwijderen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcbc-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fcbc-373">Als u liever PowerShell gebruikt om een aangepaste Quarantine-tag te verwijderen, vervangt u \<TagName\> de naam van de quarantaine-tag en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="3fcbc-374">Zie [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="3fcbc-375">Details van een quarantaine label machtiging</span><span class="sxs-lookup"><span data-stu-id="3fcbc-375">Quarantine tag permission details</span></span>

<span data-ttu-id="3fcbc-376">In de volgende secties wordt de werking beschreven van vooraf ingestelde machtigingsgroepen en afzonderlijke machtigingen in de details van quarantaine berichten en spam meldingen voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="3fcbc-377">Vooraf ingestelde machtigingsgroepen</span><span class="sxs-lookup"><span data-stu-id="3fcbc-377">Preset permissions groups</span></span>

<span data-ttu-id="3fcbc-378">De afzonderlijke machtigingen in de vooraf ingestelde machtigingsgroepen worden weergegeven in de tabel aan het begin van dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="3fcbc-379">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-379">No access</span></span>

<span data-ttu-id="3fcbc-380">Als u in het deel van de Quarantine de machtigingen **geen toegangs** rechten (geen machtigingen) toewijst, krijgen gebruikers nog enkele basismogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="3fcbc-381">**Details van quarantaine berichten**: de knop **koptekst van bericht weergeven** is altijd beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![De beschikbare knoppen in de details van het gequarantinete bericht als met het quarantaine-label de gebruiker geen toegang heeft](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="3fcbc-383">**Meldingen voor spam van eindgebruikers**: de knop **controleren** waarmee de gebruiker het bericht in quarantaine afneemt is altijd beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met het quarantaine-label de gebruiker geen toegang heeft](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="3fcbc-385">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-385">Limited access</span></span>

<span data-ttu-id="3fcbc-386">Als het Quarantine-label de machtigingen voor **beperkte toegang** toewijst, krijgen gebruikers de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="3fcbc-387">**Details van quarantaine bericht**: de volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fcbc-388">**Release aanvragen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-388">**Request release**</span></span>
  - <span data-ttu-id="3fcbc-389">**Koptekst van bericht weergeven**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-389">**View message header**</span></span>
  - <span data-ttu-id="3fcbc-390">**Voorbeeld van bericht**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-390">**Preview message**</span></span>
  - <span data-ttu-id="3fcbc-391">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-391">**Block sender**</span></span>
  - <span data-ttu-id="3fcbc-392">**Uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-392">**Remove from quarantine**</span></span>

  ![De beschikbare knoppen in de details van het gequarantinete bericht als de quarantaine-tag de gebruikers beperkte toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="3fcbc-394">**Spam meldingen voor eindgebruikers**: de volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fcbc-395">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-395">**Block sender**</span></span>
  - <span data-ttu-id="3fcbc-396">**Gereviseerd**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-396">**Review**</span></span>

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met het quarantaine-label de gebruikers beperkte toegangsmachtigingen](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="3fcbc-398">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="3fcbc-398">Full access</span></span>

<span data-ttu-id="3fcbc-399">Als het Quarantine-label de **volledige toegangs** machtigingen (alle beschikbare machtigingen) toewijst, krijgen gebruikers de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="3fcbc-400">**Details van quarantaine bericht**: de volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fcbc-401">**Bericht uitbrengen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-401">**Release message**</span></span>
  - <span data-ttu-id="3fcbc-402">**Koptekst van bericht weergeven**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-402">**View message header**</span></span>
  - <span data-ttu-id="3fcbc-403">**Voorbeeld van bericht**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-403">**Preview message**</span></span>
  - <span data-ttu-id="3fcbc-404">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-404">**Block sender**</span></span>
  - <span data-ttu-id="3fcbc-405">**Afzender toestaan**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-405">**Allow sender**</span></span>
  - <span data-ttu-id="3fcbc-406">**Uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-406">**Remove from quarantine**</span></span>

  ![De beschikbare knoppen in de details van het gequarantinete bericht als de Quarantine-tag de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="3fcbc-408">**Spam meldingen voor eindgebruikers**: de volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fcbc-409">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-409">**Block sender**</span></span>
  - <span data-ttu-id="3fcbc-410">**Release**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-410">**Release**</span></span>
  - <span data-ttu-id="3fcbc-411">**Gereviseerd**</span><span class="sxs-lookup"><span data-stu-id="3fcbc-411">**Review**</span></span>

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met de tag Quarantine de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="3fcbc-413">Afzonderlijke machtigingen</span><span class="sxs-lookup"><span data-stu-id="3fcbc-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="3fcbc-414">Let op: gebruikers krijgen altijd de knoppen die worden beschreven in de sectie [geen toegang](#no-access) .</span><span class="sxs-lookup"><span data-stu-id="3fcbc-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="3fcbc-415">Deze knoppen zijn niet opgenomen in de afzonderlijke beschrijvingen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="3fcbc-416">Toestemming voor afzender toestaan</span><span class="sxs-lookup"><span data-stu-id="3fcbc-416">Allow sender permission</span></span>

<span data-ttu-id="3fcbc-417">Met de machtiging **afzender toestaan** (_PermissionToAllowSender_) kunt u de toegang tot de knop beheren waarmee gebruikers de verzender van het gequarantinete bericht eenvoudig kunnen toevoegen aan hun lijst met veilige afzenders.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="3fcbc-418">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-419">Toestemming voor **afzender toestaan** ingeschakeld: de knop **afzender toestaan** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="3fcbc-420">Toestemming voor **afzender toestaan** uitgeschakeld: de knop **afzender toestaan** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="3fcbc-421">**Meldingen voor spam van eindgebruikers**: geen effect.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="3fcbc-422">Zie voor meer informatie over de lijst met veilige afzenders de [Geblokkeerde afzenders verhinderen](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) en [Exchange Online PowerShell gebruiken voor het configureren van de veilige lijst-verzameling voor een postvak](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="3fcbc-423">Machtigingen voor afzender blokkeren</span><span class="sxs-lookup"><span data-stu-id="3fcbc-423">Block sender permission</span></span>

<span data-ttu-id="3fcbc-424">Met de machtiging **afzender blokkeren** (_PermissionToBlockSender_) kunt u de toegang tot de knop beheren waarmee gebruikers op de lijst met geblokkeerde afzenders in de lijst met geblokkeerde afzenders de juiste afzender kunnen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="3fcbc-425">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-426">Machtigingen voor **afzender blokkeren** ingeschakeld: de knop **afzender blokkeren** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="3fcbc-427">Toestemming voor **afzender blokkeren** uitgeschakeld: de knop **afzender blokkeren** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="3fcbc-428">**Spam meldingen voor eindgebruikers**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="3fcbc-429">Toestemming voor **afzender blokkeren** uitgeschakeld: de knop **afzender blokkeren** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="3fcbc-430">Machtigingen voor **afzender blokkeren** ingeschakeld: de knop **afzender blokkeren** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="3fcbc-431">Zie voor meer informatie over de lijst met geblokkeerde afzenders [berichten van iemand blokkeren](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) en [Exchange Online PowerShell gebruiken om de veilige lijst-verzameling te configureren voor een postvak](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="3fcbc-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="3fcbc-432">Machtiging verwijderen</span><span class="sxs-lookup"><span data-stu-id="3fcbc-432">Delete permission</span></span>

<span data-ttu-id="3fcbc-433">Met de machtiging **verwijderen** (_PermissionToDelete_) kunt u gebruikers de mogelijkheid bieden hun berichten te verwijderen (berichten waarvan de gebruiker een geadresseerde is) uit Quarantine.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="3fcbc-434">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-435">Machtigingen voor **verwijderen** ingeschakeld: de knop **verwijderen uit quarantaine** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="3fcbc-436">**Verwijderen** machtiging uitgeschakeld: de knop **verwijderen uit quarantaine** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="3fcbc-437">**Meldingen voor spam van eindgebruikers**: geen effect.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="3fcbc-438">Voorbeeld van machtiging</span><span class="sxs-lookup"><span data-stu-id="3fcbc-438">Preview permission</span></span>

<span data-ttu-id="3fcbc-439">Met de machtiging **voorbeeld** (_PermissionToPreview_) kunt u bepalen of gebruikers hun berichten in quarantaine weergeven.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="3fcbc-440">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-441">**Voorbeeld** van machtigingen ingeschakeld: de knop **voorbeeld van bericht** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="3fcbc-442">**Voorbeeld** van machtiging uitgeschakeld: de knop **voorbeeld van bericht** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="3fcbc-443">**Meldingen voor spam van eindgebruikers**: geen effect.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="3fcbc-444">Toestaan dat geadresseerden een bericht uit quarantaine vrijgeven</span><span class="sxs-lookup"><span data-stu-id="3fcbc-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="3fcbc-445">Met de mogelijkheid om te zorgen dat de gebruikers van de **quarantaine machtiging een bericht vrijgeven** (_PermissionToRelease_), kunt u de mogelijkheid van gebruikers de mogelijkheid bieden rechtstreeks hun berichten in quarantaine te brengen en zonder de goedkeuring van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="3fcbc-446">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-447">Machtigingen ingeschakeld: de knop **bericht vrijgeven** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="3fcbc-448">Machtiging uitgeschakeld: de knop **bericht vrijgeven** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="3fcbc-449">**Spam meldingen voor eindgebruikers**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="3fcbc-450">Machtigingen ingeschakeld: de knop **uitbrengen** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="3fcbc-451">Machtiging uitgeschakeld: de knop **release** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="3fcbc-452">Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit de quarantaine machtiging</span><span class="sxs-lookup"><span data-stu-id="3fcbc-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="3fcbc-453">De mogelijkheid van de _gebruikers om de_ vrijgave van de geplaatste berichtenin te stellen, wordt bepaald door de mogelijkheid **dat geadresseerden een bericht aanvragen voor** de toegang tot de Quarantine.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="3fcbc-454">Het bericht wordt alleen vrijgegeven nadat een beheerder de aanvraag heeft goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="3fcbc-455">**Details van quarantaine berichten**:</span><span class="sxs-lookup"><span data-stu-id="3fcbc-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fcbc-456">Machtigingen ingeschakeld: de knop **release aanvragen** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="3fcbc-457">Machtiging uitgeschakeld: de knop **release aanvragen** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="3fcbc-458">**Meldingen voor spam van eindgebruikers**: de knop **uitbrengen** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3fcbc-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
