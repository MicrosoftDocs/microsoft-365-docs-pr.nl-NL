---
title: Quarantainebeleid
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Beheerders kunnen leren hoe ze quarantainebeleid kunnen gebruiken om te bepalen wat gebruikers kunnen doen met hun in quarantaine geplaatste berichten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055192"
---
# <a name="quarantine-policies"></a><span data-ttu-id="2f342-103">Quarantainebeleid</span><span class="sxs-lookup"><span data-stu-id="2f342-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="2f342-104">De functies die in dit artikel worden beschreven, zijn momenteel beschikbaar in Preview, zijn niet voor iedereen beschikbaar en kunnen worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2f342-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="2f342-105">Met quarantainebeleid (voorheen quarantainelabels genoemd) in Exchange Online Protection (EOP) kunnen beheerders bepalen wat gebruikers kunnen doen met hun in quarantaine geplaatste berichten op basis van hoe het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="2f342-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="2f342-106">EOP heeft vanouds bepaalde interactiviteitsniveaus toegestaan of voorkomen voor berichten in [quarantaine](find-and-release-quarantined-messages-as-a-user.md) en in [spammeldingen van eindgebruikers.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="2f342-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="2f342-107">Gebruikers kunnen bijvoorbeeld berichten bekijken en vrijgeven die in quarantaine zijn geplaatst door antispamfilters als spam of bulksgewijs, maar ze kunnen berichten die in quarantaine zijn geplaatst, niet weergeven of vrijgeven als phishing met hoog vertrouwen (alleen beheerders kunnen dat doen).</span><span class="sxs-lookup"><span data-stu-id="2f342-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="2f342-108">Voor [ondersteunde](#step-2-assign-a-quarantine-policy-to-supported-features)beveiligingsfuncties geeft quarantainebeleid aan wat gebruikers mogen doen in spammeldingen van eindgebruikers en in hun in quarantaine geplaatste berichten in quarantaine (berichten waarbij de gebruiker een geadresseerde is).</span><span class="sxs-lookup"><span data-stu-id="2f342-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="2f342-109">Standaard quarantainebeleid wordt automatisch toegewezen om de historische mogelijkheden voor gebruikers op in quarantaine geplaatste berichten af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="2f342-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="2f342-110">U kunt ook aangepaste quarantainebeleidsregels maken en toewijzen om te voorkomen dat eindgebruikers specifieke acties uitvoeren voor in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="2f342-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="2f342-111">De afzonderlijke machtigingen worden gecombineerd in de volgende vooraf ingestelde machtigingsgroepen:</span><span class="sxs-lookup"><span data-stu-id="2f342-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="2f342-112">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-112">No access</span></span>
- <span data-ttu-id="2f342-113">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-113">Limited access</span></span>
- <span data-ttu-id="2f342-114">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-114">Full access</span></span>

<span data-ttu-id="2f342-115">De beschikbare afzonderlijke machtigingen en wat al dan niet is opgenomen in de vooraf ingestelde machtigingsgroepen, worden in de volgende tabel beschreven:</span><span class="sxs-lookup"><span data-stu-id="2f342-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2f342-116">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2f342-116">Permission</span></span>|<span data-ttu-id="2f342-117">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-117">No access</span></span>|<span data-ttu-id="2f342-118">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-118">Limited access</span></span>|<span data-ttu-id="2f342-119">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="2f342-120">**Afzender toestaan** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="2f342-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Vinkje](../../media/checkmark.png)|
|<span data-ttu-id="2f342-122">**Afzender blokkeren** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="2f342-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|<span data-ttu-id="2f342-125">**Verwijderen** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="2f342-125">**Delete** (_PermissionToDelete_)</span></span>||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|<span data-ttu-id="2f342-128">**Preview** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="2f342-128">**Preview** (_PermissionToPreview_)</span></span>||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|<span data-ttu-id="2f342-131">**Geadresseerden toestaan een bericht uit quarantaine te laten** gaan (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="2f342-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Vinkje](../../media/checkmark.png)|
|<span data-ttu-id="2f342-133">**Ontvangers toestaan om een bericht uit quarantaine** te laten gaan (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="2f342-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Vinkje](../../media/checkmark.png)||
|

<span data-ttu-id="2f342-135">Als de standaardmachtigingen in de vooraf ingestelde machtigingsgroepen u niet be staan, kunt u aangepaste machtigingen gebruiken wanneer u aangepaste quarantainebeleidsregels maakt of wijzigt.</span><span class="sxs-lookup"><span data-stu-id="2f342-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="2f342-136">Zie de sectie Machtigingsgegevens voor [](#quarantine-policy-permission-details) quarantainebeleid verder in dit artikel voor meer informatie over wat elke machtiging doet.</span><span class="sxs-lookup"><span data-stu-id="2f342-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="2f342-137">U maakt en wijst quarantainebeleid toe in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met Exchange Online Postvakken; zelfstandige EOP PowerShell in EOP-organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="2f342-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f342-138">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2f342-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f342-139">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="2f342-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="2f342-140">Of als u rechtstreeks naar de pagina **Quarantainebeleid wilt** gaan, opent <https://security.microsoft.com/quarantineTags> u .</span><span class="sxs-lookup"><span data-stu-id="2f342-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="2f342-141">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f342-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2f342-142">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f342-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2f342-143">Als u quarantainebeleid wilt weergeven, maken, wijzigen of verwijderen, moet  u lid zijn van de rollen Organisatiebeheer of Beveiligingsbeheerder in de Microsoft 365 Defender portal. </span><span class="sxs-lookup"><span data-stu-id="2f342-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="2f342-144">Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f342-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-145">Stap 1: Quarantainebeleid maken in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2f342-146">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingSbeleidsregels sectie Quarantainebeleid en selecteer vervolgens \>  \>  \>  **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2f342-147">Klik op **de pagina Quarantainebeleid** op ![ Aangepast beleidspictogram Toevoegen Aangepast beleid ](../../media/m365-cc-sc-create-icon.png) **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="2f342-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="2f342-148">De **wizard Nieuw beleid** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2f342-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="2f342-149">Voer op **de pagina Beleidsnaam** een korte, maar unieke naam in het vak **Beleidsnaam** in.</span><span class="sxs-lookup"><span data-stu-id="2f342-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="2f342-150">U moet het quarantainebeleid identificeren en selecteren op naam in de komende stappen.</span><span class="sxs-lookup"><span data-stu-id="2f342-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="2f342-151">Wanneer je klaar bent, klik je op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2f342-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2f342-152">Selecteer op **de pagina Berichttoegang** van geadresseerde een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2f342-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="2f342-153">**Geen toegang**</span><span class="sxs-lookup"><span data-stu-id="2f342-153">**No access**</span></span>
   - <span data-ttu-id="2f342-154">**Beperkte toegang**</span><span class="sxs-lookup"><span data-stu-id="2f342-154">**Limited access**</span></span>
   - <span data-ttu-id="2f342-155">**Volledige toegang**</span><span class="sxs-lookup"><span data-stu-id="2f342-155">**Full access**</span></span>

   <span data-ttu-id="2f342-156">De afzonderlijke machtigingen die in deze machtigingsgroepen zijn opgenomen, worden eerder in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="2f342-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="2f342-157">Als u aangepaste machtigingen wilt opgeven, selecteert u **Specifieke toegang instellen (Geavanceerd)** en configureert u de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="2f342-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="2f342-158">**Selecteer releaseactievoorkeur**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2f342-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="2f342-159">**Geen releaseactie:** dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="2f342-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="2f342-160">**Geadresseerden toestaan een bericht uit quarantaine te plaatsen**</span><span class="sxs-lookup"><span data-stu-id="2f342-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="2f342-161">**Geadresseerden toestaan om een bericht uit quarantaine te laten worden geplaatst**</span><span class="sxs-lookup"><span data-stu-id="2f342-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="2f342-162">**Selecteer extra acties die geadresseerden kunnen uitvoeren op in quarantaine** geplaatste berichten: Selecteer enkele, alle of geen van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2f342-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="2f342-163">**Verwijderen**</span><span class="sxs-lookup"><span data-stu-id="2f342-163">**Delete**</span></span>
       - <span data-ttu-id="2f342-164">**Voorbeeld**</span><span class="sxs-lookup"><span data-stu-id="2f342-164">**Preview**</span></span>
       - <span data-ttu-id="2f342-165">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2f342-165">**Block sender**</span></span>

   <span data-ttu-id="2f342-166">Deze machtigingen en het effect ervan op in quarantaine geplaatste [](#quarantine-policy-permission-details) berichten en spammeldingen van eindgebruikers worden beschreven in de sectie Machtigingsgegevens voor quarantainebeleid verder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2f342-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="2f342-167">Wanneer je klaar bent, klik je op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2f342-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2f342-168">Controleer uw **instellingen op de** pagina Beleid controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f342-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="2f342-169">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2f342-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="2f342-170">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="2f342-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="2f342-171">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="2f342-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="2f342-172">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="2f342-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="2f342-173">U kunt nu het quarantainebeleid toewijzen aan een quarantainefunctie, zoals beschreven in de sectie [Stap 2.](#step-2-assign-a-quarantine-policy-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="2f342-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="2f342-174">Quarantainebeleid maken in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f342-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="2f342-175">Als u Liever PowerShell gebruikt om quarantainebeleid te maken, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="2f342-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="2f342-176">U kunt kiezen uit twee verschillende methoden:</span><span class="sxs-lookup"><span data-stu-id="2f342-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="2f342-177">Gebruik de _parameter EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="2f342-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="2f342-178">Gebruik de _parameter EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="2f342-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="2f342-179">Deze methoden worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="2f342-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="2f342-180">De parameter EndUserQuarantinePermissionsValue gebruiken</span><span class="sxs-lookup"><span data-stu-id="2f342-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="2f342-181">Als u een quarantainebeleid wilt maken met de parameter _EndUserQuarantinePermissionsValue,_ gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2f342-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="2f342-182">De _parameter EndUserQuarantinePermissionsValue_ gebruikt een decimale waarde die wordt geconverteerd van een binaire waarde.</span><span class="sxs-lookup"><span data-stu-id="2f342-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="2f342-183">De binaire waarde komt overeen met de beschikbare quarantainemachtigingen voor eindgebruikers in een specifieke volgorde.</span><span class="sxs-lookup"><span data-stu-id="2f342-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="2f342-184">Voor elke machtiging is de waarde 1 gelijk aan Waar en is de waarde 0 gelijk aan Onwaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="2f342-185">De vereiste volgorde en waarden voor elke afzonderlijke machtiging in vooraf ingestelde machtigingsgroepen worden in de volgende tabel beschreven:</span><span class="sxs-lookup"><span data-stu-id="2f342-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2f342-186">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2f342-186">Permission</span></span>|<span data-ttu-id="2f342-187">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-187">No access</span></span>|<span data-ttu-id="2f342-188">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-188">Limited access</span></span>|<span data-ttu-id="2f342-189">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="2f342-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="2f342-190">PermissionToAllowSender</span></span>|<span data-ttu-id="2f342-191">0</span><span class="sxs-lookup"><span data-stu-id="2f342-191">0</span></span>|<span data-ttu-id="2f342-192">0</span><span class="sxs-lookup"><span data-stu-id="2f342-192">0</span></span>|<span data-ttu-id="2f342-193">1</span><span class="sxs-lookup"><span data-stu-id="2f342-193">1</span></span>|
|<span data-ttu-id="2f342-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="2f342-194">PermissionToBlockSender</span></span>|<span data-ttu-id="2f342-195">0</span><span class="sxs-lookup"><span data-stu-id="2f342-195">0</span></span>|<span data-ttu-id="2f342-196">1</span><span class="sxs-lookup"><span data-stu-id="2f342-196">1</span></span>|<span data-ttu-id="2f342-197">1</span><span class="sxs-lookup"><span data-stu-id="2f342-197">1</span></span>|
|<span data-ttu-id="2f342-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="2f342-198">PermissionToDelete</span></span>|<span data-ttu-id="2f342-199">0</span><span class="sxs-lookup"><span data-stu-id="2f342-199">0</span></span>|<span data-ttu-id="2f342-200">1</span><span class="sxs-lookup"><span data-stu-id="2f342-200">1</span></span>|<span data-ttu-id="2f342-201">1</span><span class="sxs-lookup"><span data-stu-id="2f342-201">1</span></span>|
|<span data-ttu-id="2f342-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f342-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="2f342-203">0</span><span class="sxs-lookup"><span data-stu-id="2f342-203">0</span></span>|<span data-ttu-id="2f342-204">0</span><span class="sxs-lookup"><span data-stu-id="2f342-204">0</span></span>|<span data-ttu-id="2f342-205">0</span><span class="sxs-lookup"><span data-stu-id="2f342-205">0</span></span>|
|<span data-ttu-id="2f342-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="2f342-206">PermissionToPreview</span></span>|<span data-ttu-id="2f342-207">0</span><span class="sxs-lookup"><span data-stu-id="2f342-207">0</span></span>|<span data-ttu-id="2f342-208">1</span><span class="sxs-lookup"><span data-stu-id="2f342-208">1</span></span>|<span data-ttu-id="2f342-209">1</span><span class="sxs-lookup"><span data-stu-id="2f342-209">1</span></span>|
|<span data-ttu-id="2f342-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f342-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="2f342-211">0</span><span class="sxs-lookup"><span data-stu-id="2f342-211">0</span></span>|<span data-ttu-id="2f342-212">0</span><span class="sxs-lookup"><span data-stu-id="2f342-212">0</span></span>|<span data-ttu-id="2f342-213">1</span><span class="sxs-lookup"><span data-stu-id="2f342-213">1</span></span>|
|<span data-ttu-id="2f342-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f342-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="2f342-215">0</span><span class="sxs-lookup"><span data-stu-id="2f342-215">0</span></span>|<span data-ttu-id="2f342-216">1</span><span class="sxs-lookup"><span data-stu-id="2f342-216">1</span></span>|<span data-ttu-id="2f342-217">0</span><span class="sxs-lookup"><span data-stu-id="2f342-217">0</span></span>|
|<span data-ttu-id="2f342-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f342-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="2f342-219">0</span><span class="sxs-lookup"><span data-stu-id="2f342-219">0</span></span>|<span data-ttu-id="2f342-220">0</span><span class="sxs-lookup"><span data-stu-id="2f342-220">0</span></span>|<span data-ttu-id="2f342-221">0</span><span class="sxs-lookup"><span data-stu-id="2f342-221">0</span></span>|
|<span data-ttu-id="2f342-222">Binaire waarde</span><span class="sxs-lookup"><span data-stu-id="2f342-222">Binary value</span></span>|<span data-ttu-id="2f342-223">00000000</span><span class="sxs-lookup"><span data-stu-id="2f342-223">00000000</span></span>|<span data-ttu-id="2f342-224">01101010</span><span class="sxs-lookup"><span data-stu-id="2f342-224">01101010</span></span>|<span data-ttu-id="2f342-225">11101100</span><span class="sxs-lookup"><span data-stu-id="2f342-225">11101100</span></span>|
|<span data-ttu-id="2f342-226">Decimaal te gebruiken waarde</span><span class="sxs-lookup"><span data-stu-id="2f342-226">Decimal value to use</span></span>|<span data-ttu-id="2f342-227">0</span><span class="sxs-lookup"><span data-stu-id="2f342-227">0</span></span>|<span data-ttu-id="2f342-228">106</span><span class="sxs-lookup"><span data-stu-id="2f342-228">106</span></span>|<span data-ttu-id="2f342-229">236</span><span class="sxs-lookup"><span data-stu-id="2f342-229">236</span></span>|
|

<span data-ttu-id="2f342-230"><sup>\*</sup> Op dit moment is deze waarde altijd 0.</span><span class="sxs-lookup"><span data-stu-id="2f342-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="2f342-231">Voor PermissionToViewHeader verbergt de waarde 0 de knop **Berichtkopweergave** niet in de details van het in quarantaine geplaatste bericht (de knop is altijd beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="2f342-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="2f342-232"><sup>\*\*</sup> Stel beide waarden niet in op 1.</span><span class="sxs-lookup"><span data-stu-id="2f342-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="2f342-233">Stel een op 1 en de andere in op 0 of stel beide in op 0.</span><span class="sxs-lookup"><span data-stu-id="2f342-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="2f342-234">In dit voorbeeld wordt een nieuwe naam voor het quarantainebeleid NoAccess gemaakt waarin de machtiging Geen toegang wordt toegewezen, zoals beschreven in de vorige tabel.</span><span class="sxs-lookup"><span data-stu-id="2f342-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="2f342-235">Gebruik de waarde 106 voor beperkte toegangsmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="2f342-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="2f342-236">Voor machtigingen voor volledige toegang gebruikt u de waarde 236.</span><span class="sxs-lookup"><span data-stu-id="2f342-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="2f342-237">Voor aangepaste machtigingen gebruikt u de vorige tabel om de binaire waarde te krijgen die overeenkomt met de gepersonaliseerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2f342-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="2f342-238">Converteert de binaire waarde naar een decimale waarde en gebruik de decimaalwaarde voor de parameter _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="2f342-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="2f342-239">Zie [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="2f342-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="2f342-240">De parameter EndUserQuarantinePermissions gebruiken</span><span class="sxs-lookup"><span data-stu-id="2f342-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="2f342-241">Als u een quarantainebeleid wilt maken met de parameter _EndUserQuarantinePermissionsValue,_ gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="2f342-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="2f342-242">A.</span><span class="sxs-lookup"><span data-stu-id="2f342-242">A.</span></span> <span data-ttu-id="2f342-243">Sla een quarantainemachtigingsobject op in een variabele met de **cmdlet New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="2f342-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="2f342-244">B.</span><span class="sxs-lookup"><span data-stu-id="2f342-244">B.</span></span> <span data-ttu-id="2f342-245">Gebruik de variabele als _de waarde EndUserQuarantinePermissions_ in de **opdracht New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="2f342-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="2f342-246">Stap A: Een quarantainemachtigingsobject opslaan in een variabele</span><span class="sxs-lookup"><span data-stu-id="2f342-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="2f342-247">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2f342-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="2f342-248">De standaardwaarde voor ongebruikte parameters is , dus u hoeft alleen de parameters te gebruiken waarop u de waarde `$false` wilt `$true` instellen.</span><span class="sxs-lookup"><span data-stu-id="2f342-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="2f342-249">In de volgende voorbeelden kunt u zien hoe u machtigingsobjecten maakt die overeenkomen met de vooraf ingestelde machtigingengroepen:</span><span class="sxs-lookup"><span data-stu-id="2f342-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="2f342-250">**Geen toegang:**</span><span class="sxs-lookup"><span data-stu-id="2f342-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="2f342-251">**Beperkte toegang:**</span><span class="sxs-lookup"><span data-stu-id="2f342-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="2f342-252">**Volledige toegang:**</span><span class="sxs-lookup"><span data-stu-id="2f342-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="2f342-253">Als u de waarden wilt zien die u hebt ingesteld, moet u de variabelenaam uitvoeren als een opdracht (bijvoorbeeld de opdracht `$NoAccess` uitvoeren).</span><span class="sxs-lookup"><span data-stu-id="2f342-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="2f342-254">Stel voor aangepaste machtigingen de parameters _PermissionToRelease_ en _PermissionToRequestRelease_ niet in op `$true` .</span><span class="sxs-lookup"><span data-stu-id="2f342-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="2f342-255">Stel de `$true` ene in en laat de andere als `$false` , of laat beide als `$false` .</span><span class="sxs-lookup"><span data-stu-id="2f342-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="2f342-256">U kunt ook een bestaande objectvariabele voor machtigingen wijzigen nadat u deze hebt gemaakt, maar voordat u deze gebruikt met de cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="2f342-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="2f342-257">Zie [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="2f342-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="2f342-258">Stap B: De variabele gebruiken in de New-QuarantineTag opdracht</span><span class="sxs-lookup"><span data-stu-id="2f342-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="2f342-259">Nadat u het machtigingsobject in een variabele hebt gemaakt en opgeslagen, gebruikt u de variabele voor de _parameterwaarde EndUserQuarantinePermission_ in de volgende opdracht **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="2f342-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="2f342-260">In dit voorbeeld wordt een nieuw quarantainebeleid met de naam LimitedAccess gemaakt met het machtigingsobject dat in de vorige stap `$LimitedAccess` is beschreven en gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2f342-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="2f342-261">Zie [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="2f342-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="2f342-262">Stap 2: Een quarantainebeleid toewijzen aan ondersteunde functies</span><span class="sxs-lookup"><span data-stu-id="2f342-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="2f342-263">In _ondersteunde_ beveiligingsfuncties die berichten of bestanden in quarantaine plaatsen (automatisch of als een configureerbare actie), kunt u een quarantainebeleid toewijzen aan de beschikbare quarantaineacties.</span><span class="sxs-lookup"><span data-stu-id="2f342-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="2f342-264">Functies die berichten in quarantaine plaatsen en de beschikbaarheid van quarantainebeleid worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="2f342-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2f342-265">Functie</span><span class="sxs-lookup"><span data-stu-id="2f342-265">Feature</span></span>|<span data-ttu-id="2f342-266">Wordt quarantainebeleid ondersteund?</span><span class="sxs-lookup"><span data-stu-id="2f342-266">Quarantine policies supported?</span></span>|<span data-ttu-id="2f342-267">Standaard quarantainebeleid gebruikt</span><span class="sxs-lookup"><span data-stu-id="2f342-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="2f342-268">[Antispambeleid:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2f342-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="2f342-269">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2f342-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="2f342-270">**Spam met hoog vertrouwen** _(HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="2f342-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="2f342-271">**Phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2f342-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="2f342-272">**Phishing met hoog vertrouwen** _(HighConfidencePhishAction)_</span><span class="sxs-lookup"><span data-stu-id="2f342-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="2f342-273">**Bulksgewijs** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2f342-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="2f342-274">Ja</span><span class="sxs-lookup"><span data-stu-id="2f342-274">Yes</span></span>|<ul><li><span data-ttu-id="2f342-275">DefaultSpamTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="2f342-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="2f342-276">DefaultHighConfSpamTag (Volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="2f342-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="2f342-277">DefaultPhishTag (volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="2f342-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="2f342-278">DefaultHighConfPhishTag (Geen toegang)</span><span class="sxs-lookup"><span data-stu-id="2f342-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="2f342-279">DefaultBulkTag (Volledige toegang)</span><span class="sxs-lookup"><span data-stu-id="2f342-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="2f342-280">Anti-phishingbeleid:</span><span class="sxs-lookup"><span data-stu-id="2f342-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="2f342-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="2f342-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="2f342-282">[Imitatiebeveiliging:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f342-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="2f342-283">**Als bericht wordt gedetecteerd als een imiteerde gebruiker** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="2f342-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="2f342-284">**Als bericht wordt gedetecteerd als een nagebootsd domein** _(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="2f342-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="2f342-285">**Als postvakinformatie gebruikers detecteert en nabootst** _(MailboxIntelligenceProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="2f342-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="2f342-286">Nee</span><span class="sxs-lookup"><span data-stu-id="2f342-286">No</span></span>|<span data-ttu-id="2f342-287">n/a</span><span class="sxs-lookup"><span data-stu-id="2f342-287">n/a</span></span>|
|<span data-ttu-id="2f342-288">[Anti-malwarebeleid:](configure-anti-malware-policies.md)Alle gedetecteerde berichten worden altijd in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="2f342-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="2f342-289">Nee</span><span class="sxs-lookup"><span data-stu-id="2f342-289">No</span></span>|<span data-ttu-id="2f342-290">n/a</span><span class="sxs-lookup"><span data-stu-id="2f342-290">n/a</span></span>|
|[<span data-ttu-id="2f342-291">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f342-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="2f342-292">Nee</span><span class="sxs-lookup"><span data-stu-id="2f342-292">No</span></span>|<span data-ttu-id="2f342-293">n/a</span><span class="sxs-lookup"><span data-stu-id="2f342-293">n/a</span></span>|
|<span data-ttu-id="2f342-294">[Regels voor e-mailstroom](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) met de actie: Het bericht verzenden **naar de gehoste quarantaine** _(Quarantaine)._</span><span class="sxs-lookup"><span data-stu-id="2f342-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="2f342-295">Nee</span><span class="sxs-lookup"><span data-stu-id="2f342-295">No</span></span>|<span data-ttu-id="2f342-296">n/a</span><span class="sxs-lookup"><span data-stu-id="2f342-296">n/a</span></span>|
|

<span data-ttu-id="2f342-297"><sup>\*</sup>Instellingen voor imitatiebeveiliging zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f342-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="2f342-298">Als u tevreden bent met de machtigingen voor eindgebruikers die worden geleverd door het standaard quarantainebeleid, hoeft u niets te doen.</span><span class="sxs-lookup"><span data-stu-id="2f342-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="2f342-299">Als u de mogelijkheden van eindgebruikers (beschikbare knoppen) wilt aanpassen in spammeldingen van eindgebruikers of in in quarantaine geplaatste berichtgegevens, kunt u een aangepast quarantainebeleid toewijzen.</span><span class="sxs-lookup"><span data-stu-id="2f342-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-300">Quarantainebeleid toewijzen in antispambeleid in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2f342-301">Volledige instructies voor het maken en wijzigen van antispambeleid worden beschreven in [Antispambeleid](configure-your-spam-filter-policies.md)configureren in EOP.</span><span class="sxs-lookup"><span data-stu-id="2f342-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="2f342-302">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels \>  \>  \> **Anti-spam.**</span><span class="sxs-lookup"><span data-stu-id="2f342-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="2f342-303">Of open <https://security.microsoft.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="2f342-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="2f342-304">Ga op **de pagina Antispambeleid** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="2f342-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="2f342-305">Een bestaand antispambeleid **voor inkomende** e-mail zoeken en selecteren.</span><span class="sxs-lookup"><span data-stu-id="2f342-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="2f342-306">Een nieuw  antispambeleid voor inkomende e-mail maken.</span><span class="sxs-lookup"><span data-stu-id="2f342-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="2f342-307">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="2f342-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="2f342-308">**Bestaand antispambeleid bewerken:** Ga in de flyout beleidsdetails naar de sectie Acties en klik vervolgens op **Acties bewerken.** </span><span class="sxs-lookup"><span data-stu-id="2f342-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="2f342-309">**Nieuw antispambeleid maken:** Ga in de nieuwe beleidswizard naar **de** pagina Acties.</span><span class="sxs-lookup"><span data-stu-id="2f342-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="2f342-310">Op de **pagina** Acties.</span><span class="sxs-lookup"><span data-stu-id="2f342-310">On the **Actions** page.</span></span> <span data-ttu-id="2f342-311">Elke uitspraak met de actie **Quarantainebericht** bevat ook het vak Quarantainebeleid selecteren om een bijbehorend quarantainebeleid te selecteren. </span><span class="sxs-lookup"><span data-stu-id="2f342-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="2f342-312">**Opmerking:** Wanneer u een nieuw  beleid maakt, geeft een lege waarde voor quarantainebeleid selecteren het standaardbeleid voor quarantaine voor dat vonnis aan.</span><span class="sxs-lookup"><span data-stu-id="2f342-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="2f342-313">Wanneer u het beleid later bewerkt, worden de lege waarden vervangen door de werkelijke standaardnamen van het quarantainebeleid, zoals beschreven in de vorige tabel.</span><span class="sxs-lookup"><span data-stu-id="2f342-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![Selecties van quarantainebeleid in een antispambeleid](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="2f342-315">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="2f342-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="2f342-316">Quarantainebeleid toewijzen in antispambeleid in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f342-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="2f342-317">Als u Liever PowerShell gebruikt om quarantainebeleid toe te wijzen in antispambeleid, maakt u verbinding met Exchange Online PowerShell Exchange Online Protection PowerShell en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2f342-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="2f342-318">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="2f342-318">**Notes**:</span></span>

- <span data-ttu-id="2f342-319">De standaardwaarde voor de parameter _HighConfidencePhishAction_ is Quarantaine, dus u hoeft de actie Quarantaine niet in te stellen voor phishingdetectie met veel vertrouwen in nieuwe antispambeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="2f342-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="2f342-320">Voor alle andere vonnissen voor spamfilters in nieuw of bestaand antispambeleid is het quarantainebeleid alleen van kracht als de actiewaarde Quarantaine is.</span><span class="sxs-lookup"><span data-stu-id="2f342-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="2f342-321">Voer de volgende opdracht uit om de actiewaarden in bestaand antispambeleid te bekijken:</span><span class="sxs-lookup"><span data-stu-id="2f342-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="2f342-322">Zie [EOP-antispambeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor EOP voor informatie over de standaardactiewaarden en de aanbevolen actiewaarden voor Standaard en Strikt.</span><span class="sxs-lookup"><span data-stu-id="2f342-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="2f342-323">Een vonnis voor spamfilters zonder een bijbehorende quarantainebeleidsparameter betekent dat het [standaard](#step-2-assign-a-quarantine-policy-to-supported-features) quarantainebeleid voor dat vonnis wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2f342-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="2f342-324">U hoeft alleen een standaard quarantainebeleid te vervangen door een aangepast quarantainebeleid als u de standaardmogelijkheden van eindgebruikers voor in quarantaine geplaatste berichten wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2f342-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="2f342-325">Voor een nieuw antispambeleid in PowerShell is een spamfilterbeleid (instellingen) vereist met de cmdlet **New-HostedContentFilterPolicy** en een nieuwe spamfilterregel (ontvangersfilters) met de cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="2f342-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="2f342-326">Zie [PowerShell gebruiken om antispambeleid te maken](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2f342-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="2f342-327">In dit voorbeeld wordt een nieuw spamfilterbeleid met de naam Onderzoeksafdeling gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="2f342-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="2f342-328">De actie voor alle vonnissen voor spamfilters is ingesteld op Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="2f342-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="2f342-329">Het aangepaste quarantainebeleid met de naam  NoAccess dat geen toegangsmachtigingen  toewijst, vervangt standaard quarantainebeleid dat standaard geen toegangsmachtigingen toewijst.</span><span class="sxs-lookup"><span data-stu-id="2f342-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="2f342-330">Zie [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2f342-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="2f342-331">Dit voorbeeld wijzigt het bestaande spamfilterbeleid met de naam Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2f342-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="2f342-332">De actie voor de quarantaine van spam is ingesteld op Quarantaine en het aangepaste quarantainebeleid met de naam NoAccess is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2f342-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="2f342-333">Zie [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2f342-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-334">Instellingen voor globale quarantainemeldingen configureren in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2f342-335">Met de algemene instellingen voor quarantainebeleid kunt u de spammeldingen van eindgebruikers aanpassen die worden verzonden naar geadresseerden van berichten die in quarantaine zijn geplaatst.</span><span class="sxs-lookup"><span data-stu-id="2f342-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="2f342-336">Zie [Spammeldingen](use-spam-notifications-to-release-and-report-quarantined-messages.md)voor eindgebruikers voor meer informatie over deze meldingen.</span><span class="sxs-lookup"><span data-stu-id="2f342-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="2f342-337">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingSbeleidsregels sectie Quarantainebeleid en selecteer vervolgens \>  \>  \>  **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2f342-338">Selecteer globale instellingen op **de pagina** **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="2f342-339">Configureer **enkele** of alle volgende instellingen in het flyout Quarantainemeldingsinstellingen dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="2f342-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="2f342-340">**Weergavenaam:** Pas de weergavenaam van de afzender aan die wordt gebruikt in spammeldingen van eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2f342-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="2f342-341">Voor elke taal die u hebt toegevoegd, selecteert u de taal in het vak tweede taal (klik niet op de X) en typt u de tekstwaarde die u wilt gebruiken in het vak **Weergavenaam.**</span><span class="sxs-lookup"><span data-stu-id="2f342-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="2f342-342">In de volgende schermafbeelding ziet u de aangepaste weergavenaam in een spammelding voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="2f342-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Een aangepaste weergavenaam voor afzenders in een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="2f342-344">**Vrijwaring:** Voeg een aangepaste vrijwaring toe aan de onderkant van spammeldingen van eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2f342-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="2f342-345">De gelokaliseerde tekst, **Een vrijwaring van uw organisatie:** wordt altijd eerst opgenomen, gevolgd door de tekst die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2f342-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="2f342-346">Voor elke taal die u hebt toegevoegd, selecteert u de taal in het vak tweede taal (klik niet op de X) en typt u de tekstwaarde die u wilt gebruiken in het vak **Vrijwaring.**</span><span class="sxs-lookup"><span data-stu-id="2f342-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="2f342-347">In de volgende schermafbeelding ziet u de aangepaste vrijwaring in een spammelding voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="2f342-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Een aangepaste vrijwaring onder aan een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="2f342-349">**Taal kiezen:** spammeldingen van eindgebruikers zijn al gelokaliseerd op basis van de taalinstellingen van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="2f342-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="2f342-350">U kunt aangepaste tekst opgeven in verschillende talen voor de **waarden Weergavenaam** en **Vrijwaring.**</span><span class="sxs-lookup"><span data-stu-id="2f342-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="2f342-351">Selecteer ten minste één taal in het vak eerste taal en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="2f342-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="2f342-352">U kunt meerdere talen selecteren door na elke taal op **Toevoegen** te klikken.</span><span class="sxs-lookup"><span data-stu-id="2f342-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="2f342-353">In een sectietaalvak ziet u alle talen die u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="2f342-353">A section language box shows all of the languages that you've selected:</span></span>

     ![Geselecteerde talen in het vak tweede taal in de algemene quarantainemeldingsinstellingen van quarantainebeleid](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="2f342-355">**Mijn bedrijfslogo gebruiken:** Selecteer deze optie om het standaard Microsoft-logo te vervangen dat boven aan spammeldingen van eindgebruikers wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2f342-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="2f342-356">Voordat u dit doet, moet u de instructies volgen in Het thema [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) uw organisatie aanpassen om uw aangepaste logo te uploaden.</span><span class="sxs-lookup"><span data-stu-id="2f342-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="2f342-357">In de volgende schermafbeelding ziet u een aangepast logo in een spammelding voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="2f342-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Een aangepast logo in een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-359">Quarantainebeleid weergeven in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2f342-360">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingSbeleidsregels sectie Quarantainebeleid en selecteer vervolgens \>  \>  \>  **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2f342-361">Op **de pagina Quarantainebeleid** ziet u de lijst met beleidsregels **op Naam** en **Laatst bijgewerkte** datum.</span><span class="sxs-lookup"><span data-stu-id="2f342-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="2f342-362">Als u de instellingen van ingebouwd of aangepast quarantainebeleid wilt weergeven, selecteert u het quarantainebeleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="2f342-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="2f342-363">Als u de algemene instellingen wilt weergeven, klikt u op **Algemene instellingen**</span><span class="sxs-lookup"><span data-stu-id="2f342-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="2f342-364">Quarantainebeleid weergeven in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f342-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="2f342-365">Als u Liever PowerShell gebruikt om quarantainebeleid weer te geven, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="2f342-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="2f342-366">Voer de volgende opdracht uit als u een overzichtslijst met alle ingebouwde of aangepaste beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="2f342-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="2f342-367">Als u de instellingen van ingebouwd of aangepast quarantainebeleid wilt weergeven, vervangt u de naam van het quarantainebeleid en voer \<QuarantinePolicyName\> u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="2f342-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="2f342-368">Voer de volgende opdracht uit om de algemene instellingen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2f342-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="2f342-369">Zie [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2f342-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-370">Quarantainebeleid wijzigen in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2f342-371">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingSbeleidsregels sectie Quarantainebeleid en selecteer vervolgens \>  \>  \>  **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2f342-372">Selecteer op **de pagina** Quarantainebeleid het beleid door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="2f342-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="2f342-373">Nadat u het beleid hebt geselecteerd, klikt u op het pictogram Beleid bewerken ![ ](../../media/m365-cc-sc-edit-icon.png) **dat** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f342-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="2f342-374">De **wizard Beleid bewerken** die wordt  geopend, is vrijwel identiek aan de wizard Nieuw beleid, zoals beschreven in het quarantainebeleid maken in de sectie [Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2f342-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="2f342-375">Het belangrijkste verschil is: u kunt de naam van een bestaand beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2f342-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="2f342-376">Wanneer u klaar bent met het wijzigen van het beleid, gaat u naar **de** pagina Overzicht en klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="2f342-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="2f342-377">Quarantainebeleid wijzigen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f342-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="2f342-378">Als u Liever PowerShell gebruikt om een aangepast quarantainebeleid te wijzigen, vervangt u de naam van het quarantainebeleid en gebruikt u \<QuarantinePolicyName\> de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2f342-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="2f342-379">De beschikbare instellingen zijn hetzelfde als beschreven voor het maken van quarantainebeleid eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2f342-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="2f342-380">Zie Quarantainetag instellen voor gedetailleerde syntaxis- en [parametergegevens.](/powershell/module/exchange/set-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="2f342-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2f342-381">Quarantainebeleid verwijderen in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="2f342-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2f342-382">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="2f342-382">**Notes**:</span></span>

- <span data-ttu-id="2f342-383">U kunt ingebouwde quarantainebeleidsregels niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2f342-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="2f342-384">Controleer voordat u een aangepast quarantainebeleid verwijdert of het niet wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2f342-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="2f342-385">Voer bijvoorbeeld de volgende opdracht uit in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2f342-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="2f342-386">Als het quarantainebeleid wordt gebruikt, [vervangt u het toegewezen quarantainebeleid](#step-2-assign-a-quarantine-policy-to-supported-features) voordat u het verwijdert.</span><span class="sxs-lookup"><span data-stu-id="2f342-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="2f342-387">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingSbeleidsregels sectie Quarantainebeleid en selecteer vervolgens \>  \>  \>  **Quarantainebeleid.**</span><span class="sxs-lookup"><span data-stu-id="2f342-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2f342-388">Selecteer op **de pagina** Quarantainebeleid het aangepaste quarantainebeleid dat u wilt verwijderen door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="2f342-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="2f342-389">Nadat u het beleid hebt geselecteerd, klikt u op het pictogram Beleid ![ verwijderen ](../../media/m365-cc-sc-delete-icon.png) **dat** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f342-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="2f342-390">Klik **op Beleid verwijderen** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f342-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="2f342-391">Quarantainebeleid verwijderen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f342-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="2f342-392">Als u Liever PowerShell gebruikt om een aangepast quarantainebeleid te verwijderen, vervangt u door de naam van het quarantainebeleid en voer u \<QuarantinePolicyName\> de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="2f342-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="2f342-393">Zie [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="2f342-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="2f342-394">Machtigingsgegevens voor quarantainebeleid</span><span class="sxs-lookup"><span data-stu-id="2f342-394">Quarantine policy permission details</span></span>

<span data-ttu-id="2f342-395">In de volgende secties worden de effecten beschreven van vooraf ingestelde machtigingsgroepen en afzonderlijke machtigingen in de details van in quarantaine geplaatste berichten en in spammeldingen van eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2f342-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="2f342-396">Vooraf ingestelde machtigingengroepen</span><span class="sxs-lookup"><span data-stu-id="2f342-396">Preset permissions groups</span></span>

<span data-ttu-id="2f342-397">De afzonderlijke machtigingen die zijn opgenomen in vooraf ingestelde machtigingsgroepen, worden weergegeven in de tabel aan het begin van dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2f342-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="2f342-398">Geen toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-398">No access</span></span>

<span data-ttu-id="2f342-399">Als het quarantainebeleid  geen toegangsmachtigingen (geen machtigingen) toewijst, krijgen gebruikers nog steeds enkele basislijnfuncties:</span><span class="sxs-lookup"><span data-stu-id="2f342-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="2f342-400">**Berichtdetails in quarantaine:** **de knop Berichtkop** weergeven is altijd beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als het quarantainebeleid de gebruiker geen toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="2f342-402">**Spammeldingen van eindgebruikers:** **de** knop Controleren waarmee de gebruiker in quarantaine naar het bericht gaat, is altijd beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als het quarantainebeleid de gebruiker geen toegangsmachtigingen geeft](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="2f342-404">Beperkte toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-404">Limited access</span></span>

<span data-ttu-id="2f342-405">Als het quarantainebeleid  de machtiging beperkte toegang toewijst, krijgen gebruikers de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="2f342-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="2f342-406">**Details van berichten in quarantaine**: De volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2f342-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="2f342-407">**Release aanvragen**</span><span class="sxs-lookup"><span data-stu-id="2f342-407">**Request release**</span></span>
  - <span data-ttu-id="2f342-408">**Berichtkop weergeven**</span><span class="sxs-lookup"><span data-stu-id="2f342-408">**View message header**</span></span>
  - <span data-ttu-id="2f342-409">**Voorbeeld van bericht**</span><span class="sxs-lookup"><span data-stu-id="2f342-409">**Preview message**</span></span>
  - <span data-ttu-id="2f342-410">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2f342-410">**Block sender**</span></span>
  - <span data-ttu-id="2f342-411">**Uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="2f342-411">**Remove from quarantine**</span></span>

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als het quarantainebeleid de gebruiker beperkte toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="2f342-413">**Spammeldingen voor eindgebruikers:** De volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2f342-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="2f342-414">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2f342-414">**Block sender**</span></span>
  - <span data-ttu-id="2f342-415">**Controle**</span><span class="sxs-lookup"><span data-stu-id="2f342-415">**Review**</span></span>

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als het quarantainebeleid de gebruiker beperkte toegangsmachtigingen geeft](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="2f342-417">Volledige toegang</span><span class="sxs-lookup"><span data-stu-id="2f342-417">Full access</span></span>

<span data-ttu-id="2f342-418">Als het quarantainebeleid de machtigingEn voor volledige **toegang** (alle beschikbare machtigingen) toewijst, krijgen gebruikers de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="2f342-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="2f342-419">**Details van berichten in quarantaine**: De volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2f342-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="2f342-420">**Releasebericht**</span><span class="sxs-lookup"><span data-stu-id="2f342-420">**Release message**</span></span>
  - <span data-ttu-id="2f342-421">**Berichtkop weergeven**</span><span class="sxs-lookup"><span data-stu-id="2f342-421">**View message header**</span></span>
  - <span data-ttu-id="2f342-422">**Voorbeeld van bericht**</span><span class="sxs-lookup"><span data-stu-id="2f342-422">**Preview message**</span></span>
  - <span data-ttu-id="2f342-423">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2f342-423">**Block sender**</span></span>
  - <span data-ttu-id="2f342-424">**Afzender toestaan**</span><span class="sxs-lookup"><span data-stu-id="2f342-424">**Allow sender**</span></span>
  - <span data-ttu-id="2f342-425">**Uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="2f342-425">**Remove from quarantine**</span></span>

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als het quarantainebeleid de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="2f342-427">**Spammeldingen voor eindgebruikers:** De volgende knoppen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2f342-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="2f342-428">**Afzender blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2f342-428">**Block sender**</span></span>
  - <span data-ttu-id="2f342-429">**Vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="2f342-429">**Release**</span></span>
  - <span data-ttu-id="2f342-430">**Controle**</span><span class="sxs-lookup"><span data-stu-id="2f342-430">**Review**</span></span>

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als het quarantainebeleid de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="2f342-432">Afzonderlijke machtigingen</span><span class="sxs-lookup"><span data-stu-id="2f342-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="2f342-433">Vergeet niet dat gebruikers altijd de knoppen krijgen die worden beschreven in [de sectie Geen toegang.](#no-access)</span><span class="sxs-lookup"><span data-stu-id="2f342-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="2f342-434">Deze knoppen zijn niet opgenomen in de afzonderlijke machtigingsbeschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="2f342-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="2f342-435">Afzendermachtiging toestaan</span><span class="sxs-lookup"><span data-stu-id="2f342-435">Allow sender permission</span></span>

<span data-ttu-id="2f342-436">Met **de machtiging Afzender** toestaan _(PermissionToAllowSender)_ wordt de toegang tot de knop besturingselementen waarmee gebruikers de afzender van het in quarantaine geplaatste bericht gemakkelijk kunnen toevoegen aan de lijst met Safe afzenders.</span><span class="sxs-lookup"><span data-stu-id="2f342-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="2f342-437">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-438">**Afzendermachtiging** toestaan ingeschakeld: **de knop Afzender toestaan** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="2f342-439">**Afzendermachtiging** toestaan uitgeschakeld: **de knop Afzender toestaan** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="2f342-440">**Spammeldingen van eindgebruikers:** Geen effect.</span><span class="sxs-lookup"><span data-stu-id="2f342-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="2f342-441">Zie Voorkomen dat vertrouwde [afzenders](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) worden geblokkeerd en Gebruik Exchange Online PowerShell om de [safelistverzameling](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)in een postvak te configureren voor meer informatie over de lijst met Safe-afzenders.</span><span class="sxs-lookup"><span data-stu-id="2f342-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="2f342-442">Afzendermachtiging blokkeren</span><span class="sxs-lookup"><span data-stu-id="2f342-442">Block sender permission</span></span>

<span data-ttu-id="2f342-443">De **machtiging Afzender blokkeren** _(PermissionToBlockSender)_ bepaalt de toegang tot de knop waarmee gebruikers de afzender van het in quarantaine geplaatste bericht gemakkelijk kunnen toevoegen aan hun lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="2f342-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="2f342-444">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-445">**Afzendermachtiging** blokkeren ingeschakeld: de **knop Afzender blokkeren** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="2f342-446">**Afzendermachtiging** blokkeren uitgeschakeld: de **knop Afzender blokkeren** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="2f342-447">**Spammeldingen voor eindgebruikers:**</span><span class="sxs-lookup"><span data-stu-id="2f342-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="2f342-448">**Afzendermachtiging** blokkeren uitgeschakeld: de **knop Afzender blokkeren** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="2f342-449">**Afzendermachtiging** blokkeren ingeschakeld: de **knop Afzender blokkeren** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="2f342-450">Zie Berichten van iemand blokkeren en [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) Gebruik Exchange Online PowerShell om de safelistverzameling in een postvak te configureren voor meer informatie over de lijst geblokkeerde [afzenders.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="2f342-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="2f342-451">Machtiging voor verwijderen</span><span class="sxs-lookup"><span data-stu-id="2f342-451">Delete permission</span></span>

<span data-ttu-id="2f342-452">Met **de machtiging** Verwijderen _(PermissionToDelete)_ wordt de mogelijkheid van gebruikers om hun berichten (berichten waar de gebruiker een geadresseerde is) uit quarantaine te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2f342-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="2f342-453">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-454">**Machtiging** verwijderen ingeschakeld: de **knop Verwijderen uit quarantaine** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="2f342-455">**Machtiging** verwijderen uitgeschakeld: de **knop Verwijderen uit quarantaine** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="2f342-456">**Spammeldingen van eindgebruikers:** Geen effect.</span><span class="sxs-lookup"><span data-stu-id="2f342-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="2f342-457">Voorbeeldmachtiging</span><span class="sxs-lookup"><span data-stu-id="2f342-457">Preview permission</span></span>

<span data-ttu-id="2f342-458">De **machtiging Voorbeeld** (_PermissionToPreview_) bepaalt de mogelijkheid voor gebruikers om een voorbeeld van hun berichten in quarantaine te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2f342-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="2f342-459">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-460">**Voorbeeldmachtiging** ingeschakeld: de **knop Voorbeeldbericht** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="2f342-461">**Voorbeeldmachtiging** uitgeschakeld: de **knop Voorbeeldbericht** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="2f342-462">**Spammeldingen van eindgebruikers:** Geen effect.</span><span class="sxs-lookup"><span data-stu-id="2f342-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="2f342-463">Toestaan dat geadresseerden een bericht vrijgeven van quarantainemachtigingen</span><span class="sxs-lookup"><span data-stu-id="2f342-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="2f342-464">Met **De machtiging** Toestaan dat geadresseerden een bericht vrijgeven van quarantainemachtigingen _(PermissionToRelease)_ bepaalt de mogelijkheid van gebruikers om hun in quarantaine geplaatste berichten rechtstreeks en zonder de goedkeuring van een beheerder vrij te geven.</span><span class="sxs-lookup"><span data-stu-id="2f342-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="2f342-465">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-466">Machtiging ingeschakeld: de **knop Bericht vrijgeven** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="2f342-467">Machtiging uitgeschakeld: de **knop Bericht vrijgeven** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="2f342-468">**Spammeldingen voor eindgebruikers:**</span><span class="sxs-lookup"><span data-stu-id="2f342-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="2f342-469">Machtiging ingeschakeld: de **knop Release** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="2f342-470">Machtiging uitgeschakeld: de **knop Release** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="2f342-471">Ontvangers toestaan om een bericht te vragen om uit quarantainemachtigingen te worden vrijgegeven</span><span class="sxs-lookup"><span data-stu-id="2f342-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="2f342-472">Met **De machtiging** Geadresseerden toestaan om een bericht uit quarantainemachtigingen te verwijderen  _(PermissionToRequestRelease)_ bepaalt de mogelijkheid van gebruikers om de release van hun in quarantaine geplaatste berichten aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="2f342-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="2f342-473">Het bericht wordt alleen uitgebracht nadat een beheerder de aanvraag heeft goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="2f342-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="2f342-474">**Details van berichten in quarantaine:**</span><span class="sxs-lookup"><span data-stu-id="2f342-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2f342-475">Machtiging ingeschakeld: de **knop Release aanvragen** is beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="2f342-476">Machtiging uitgeschakeld: de **knop Release** aanvragen is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="2f342-477">**Spammeldingen van eindgebruikers:** de **knop Release** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2f342-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
