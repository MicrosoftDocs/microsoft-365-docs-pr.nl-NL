---
title: Filteren van uitgaande spam configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van uitgaand spambeleid in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aec3149a4a91e011c6d6d206d9fc10f36a3d6588
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903902"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="08751-103">Uitgaande spamfilters configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="08751-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="08751-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="08751-104">**Applies to**</span></span>
- [<span data-ttu-id="08751-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="08751-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="08751-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="08751-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="08751-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08751-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="08751-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendende activiteiten.</span><span class="sxs-lookup"><span data-stu-id="08751-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="08751-109">Uitgaande spam van een gebruiker in uw organisatie geeft meestal een gekromd account aan.</span><span class="sxs-lookup"><span data-stu-id="08751-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="08751-110">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het betrouwbaarheidsniveau voor spam of SCL) en worden door de groep met risicovolle bezorging gerouteerd om de reputatie van de service te beschermen (dat wil zeggen, microsoft 365-bron-e-mailservers buiten [ip-bloklijsten](high-risk-delivery-pool-for-outbound-messages.md) houden).</span><span class="sxs-lookup"><span data-stu-id="08751-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="08751-111">Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteit en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="08751-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="08751-112">EOP gebruikt uitgaand spambeleid als onderdeel van de algemene verdediging van uw organisatie tegen spam.</span><span class="sxs-lookup"><span data-stu-id="08751-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="08751-113">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="08751-114">Beheerders kunnen het standaardbeleid voor uitgaande spam weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="08751-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="08751-115">Voor meer granulariteit kunt u ook aangepaste uitgaande spambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="08751-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="08751-116">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="08751-117">U kunt uitgaand spambeleid configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="08751-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="08751-118">De basiselementen van een uitgaand spambeleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="08751-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="08751-119">**Het beleid voor uitgaand spamfilter:** geeft de acties voor uitgaande spamfilters en de meldingsopties op.</span><span class="sxs-lookup"><span data-stu-id="08751-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="08751-120">**De regel voor uitgaand spamfilter:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="08751-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="08751-121">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam polices beheert in het Beveiligings- & Compliance center:</span><span class="sxs-lookup"><span data-stu-id="08751-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="08751-122">Wanneer u een beleid maakt, maakt u tegelijkertijd een regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="08751-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="08751-123">Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en adressenfilters de regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="08751-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="08751-124">Alle andere instellingen wijzigen het bijbehorende beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="08751-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="08751-125">Wanneer u een beleid verwijdert, worden de regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08751-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="08751-126">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="08751-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="08751-127">Zie de sectie Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken voor het configureren van [uitgaand spambeleid](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="08751-128">Elke organisatie heeft een ingebouwd uitgaand spambeleid met de naam Standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="08751-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="08751-129">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen regel voor uitgaand spamfilter (geadresseerdenfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="08751-130">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="08751-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="08751-131">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="08751-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="08751-132">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="08751-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="08751-133">Als u de effectiviteit van uitgaande spamfilters wilt vergroten, kunt u aangepaste uitgaande spambeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="08751-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="08751-134">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="08751-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="08751-135">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="08751-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="08751-136">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="08751-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="08751-137">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08751-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="08751-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08751-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="08751-139">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="08751-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="08751-140">Als u uitgaande spambeleidsregels wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="08751-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="08751-141">Als u alleen-lezen toegang wilt tot uitgaand spambeleid, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="08751-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="08751-142">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="08751-143">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="08751-143">**Notes**:</span></span>

  - <span data-ttu-id="08751-144">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08751-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="08751-145">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="08751-146">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="08751-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="08751-147">Zie [EOP outbound spamfilterbeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)voor onze aanbevolen instellingen voor uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="08751-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="08751-148">De [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleidsregels met de naam Verzendlimiet voor e-mail zijn **overschreden,** Verdachte patronen voor het verzenden van e-mail zijn gedetecteerd en gebruikers kunnen geen e-mailmeldingen verzenden naar leden van de **groep TenantAdmins** **(Globale** beheerders) over ongebruikelijke uitgaande e-mailactiviteit en geblokkeerde gebruikers vanwege uitgaande spam. </span><span class="sxs-lookup"><span data-stu-id="08751-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="08751-149">Zie De waarschuwingsinstellingen voor beperkte gebruikers controleren [voor meer informatie.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="08751-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="08751-150">U wordt aangeraden dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="08751-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="08751-151">Gebruik het Beveiligings- & compliancecentrum om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="08751-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="08751-152">Als u een aangepast uitgaand spambeleid maakt in het Beveiligings- & Compliancecentrum, worden de filterregel voor spam en het bijbehorende spamfilterbeleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="08751-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="08751-153">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-154">Klik op **de pagina Antispam-instellingen** op **Uitgaand beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="08751-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="08751-155">Configureer de volgende instellingen in het beleid voor uitgaand **spamfilter** dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="08751-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="08751-156">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="08751-157">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="08751-158">(Optioneel) Vouw de **sectie Meldingen uit** om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="08751-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="08751-159">**Een kopie van verdachte uitgaande** e-mailberichten naar specifieke personen verzenden: met deze instelling worden de opgegeven gebruikers als BCC-geadresseerden toegevoegd aan de verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="08751-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="08751-160">Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="08751-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="08751-161">Het werkt niet in aangepaste uitgaande spambeleidsregels die u maakt.</span><span class="sxs-lookup"><span data-stu-id="08751-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="08751-162">Als u deze instelling wilt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="08751-162">To enable this setting:</span></span>

     1. <span data-ttu-id="08751-163">Schakel het selectievakje in om de instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="08751-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="08751-164">Klik **op Personen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="08751-164">Click **Add people**.</span></span> <span data-ttu-id="08751-165">In het **flyout Geadresseerden toevoegen of** verwijderen dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="08751-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="08751-166">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="08751-166">Enter the sender's email address.</span></span> <span data-ttu-id="08751-167">U kunt meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één geadresseerde per regel.</span><span class="sxs-lookup"><span data-stu-id="08751-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="08751-168">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="08751-168">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="08751-170">om de geadresseerden toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="08751-170">to add the recipients.</span></span>

        <span data-ttu-id="08751-171">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="08751-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="08751-172">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Lijst met** geadresseerden in de flyout.</span><span class="sxs-lookup"><span data-stu-id="08751-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="08751-173">Als u een geadresseerde wilt verwijderen, klikt ![ u op Knop ](../../media/scc-remove-icon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="08751-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="08751-174">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="08751-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="08751-175">Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.</span><span class="sxs-lookup"><span data-stu-id="08751-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="08751-176">**Informeer specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**</span><span class="sxs-lookup"><span data-stu-id="08751-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="08751-177">Deze instelling wordt momenteel verwijderd uit uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="08751-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="08751-178">Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid met de naam **Gebruiker** die geen e-mail mag verzenden, verzendt al e-mailmeldingen naar leden van de **groep TenantAdmins** **(Globale** beheerders) wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie Geadresseerdenlimieten. </span><span class="sxs-lookup"><span data-stu-id="08751-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="08751-179">**We raden u ten zeerste aan het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="08751-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="08751-180">Zie De [waarschuwingsinstellingen voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)beperkte gebruikers controleren voor instructies.</span><span class="sxs-lookup"><span data-stu-id="08751-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="08751-181">(Optioneel) Vouw de **sectie Geadresseerdenlimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:</span><span class="sxs-lookup"><span data-stu-id="08751-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="08751-182">Deze instellingen zijn alleen van toepassing op postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="08751-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="08751-183">**Maximum aantal geadresseerden per gebruiker**</span><span class="sxs-lookup"><span data-stu-id="08751-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="08751-184">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="08751-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="08751-185">De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="08751-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="08751-186">Zie Limieten verzenden [voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="08751-186">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="08751-187">**Externe uurlimiet:** het maximum aantal externe geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="08751-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="08751-188">**Interne uurlimiet:** het maximum aantal interne geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="08751-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="08751-189">**Daglimiet:** Het maximumtotaal aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="08751-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="08751-190">**Actie wanneer een gebruiker de bovenstaande limieten** overschrijdt: Configureer de actie die moet worden ondernomen wanneer een van de limieten voor **geadresseerden** wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="08751-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="08751-191">Voor alle acties hebben de geadresseerden die in de gebruiker zijn opgegeven, het verzenden van e-mailwaarschuwingsbeleid beperkt (en in het nu redundante Bericht specifieke personen informeren als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam in het uitgaande **spambeleid** ontvangen e-mailmeldingen. </span><span class="sxs-lookup"><span data-stu-id="08751-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="08751-192">**De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="08751-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="08751-193">Er worden e-mailmeldingen verzonden en de gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="08751-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="08751-194">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="08751-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="08751-195">De activiteitswaarschuwing **met de naam Gebruiker die geen e-mail** mag verzenden, meldt beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).</span><span class="sxs-lookup"><span data-stu-id="08751-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="08751-196">Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="08751-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="08751-197">De gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="08751-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="08751-198">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="08751-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="08751-199">De gebruiker beperken van het verzenden van e-mail: e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de **portal [Beperkte <https://sip.protection.office.com/restrictedusers> gebruikers]** in het beveiligings- & compliancecentrum en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder uit de portal Beperkte gebruikers is verwijderd.   Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt.</span><span class="sxs-lookup"><span data-stu-id="08751-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="08751-200">Zie Een gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van [spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="08751-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="08751-201">**Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="08751-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="08751-202">(Optioneel) Vouw **de sectie Automatisch doorsturen** uit om automatische doorsturen van e-mail door gebruikers naar externe afzenders te controleren.</span><span class="sxs-lookup"><span data-stu-id="08751-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="08751-203">Zie Automatische externe e-mail [doorsturen in Microsoft 365](external-email-forwarding.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="08751-204">Vóór september 2020 zijn deze instellingen beschikbaar, maar niet afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="08751-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="08751-205">Deze instellingen zijn alleen van toepassing op postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="08751-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="08751-206">Wanneer automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) als externe afzenders e-mail verzenden naar een postvak dat is doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="08751-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="08751-207">Als het bericht wordt verzonden door een interne afzender en de doorsturenmethode postvak doorsturen [is](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR. </span><span class="sxs-lookup"><span data-stu-id="08751-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="08751-208">De interne afzender krijgt geen NDR als het doorsturen is gebeurd vanwege een regel voor postvak IN.</span><span class="sxs-lookup"><span data-stu-id="08751-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="08751-209">De beschikbare waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="08751-209">The available values are:</span></span>

   - <span data-ttu-id="08751-210">**Automatisch - Systeemgestuurd:** hiermee kunt u uitgaande spamfilters gebruiken om automatische doorsturen van externe e-mail te controleren.</span><span class="sxs-lookup"><span data-stu-id="08751-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="08751-211">Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="08751-211">This is the default value.</span></span>
   - <span data-ttu-id="08751-212">**Op**: Automatische externe e-mail doorsturen is niet uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="08751-213">**Uit:** Alle automatische externe e-mail doorsturen is uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="08751-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="08751-214">(Vereist) Vouw de **sectie Toegepast op uit** om de interne afzenders te identificeren waar het beleid op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="08751-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="08751-215">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="08751-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="08751-216">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="08751-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="08751-217">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="08751-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="08751-218">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="08751-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="08751-219">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="08751-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="08751-220">**Het afzenderdomein is:** hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="08751-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="08751-221">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="08751-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="08751-222">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="08751-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="08751-223">**Afzender is:** hiermee geeft u een of meer gebruikers in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="08751-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="08751-224">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="08751-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="08751-225">Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="08751-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="08751-226">**Afzender is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="08751-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="08751-227">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="08751-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="08751-228">Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="08751-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="08751-229">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="08751-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="08751-230">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="08751-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="08751-231">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="08751-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="08751-232">Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="08751-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="08751-233">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-234">Klik op **de pagina Antispam-instellingen** op ![ Pictogram uitvvllen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="08751-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="08751-235">Het standaardbeleid met de naam **Beleid voor uitgaand spamfilter**.</span><span class="sxs-lookup"><span data-stu-id="08751-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="08751-236">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="08751-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="08751-237">De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u kunt op **Beleid bewerken klikken.**</span><span class="sxs-lookup"><span data-stu-id="08751-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="08751-238">Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="08751-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="08751-239">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-240">Klik op **de pagina Antispam-instellingen** op ![ Pictogram uitvvllen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="08751-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="08751-241">Het standaardbeleid met de naam **Beleid voor uitgaand spamfilter**.</span><span class="sxs-lookup"><span data-stu-id="08751-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="08751-242">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="08751-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="08751-243">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="08751-243">Click **Edit policy**.</span></span>

<span data-ttu-id="08751-244">Voor aangepast uitgaand spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan de instellingen die worden beschreven in het sectie Gebruik het [beveiligings- & compliancecentrum](#use-the-security--compliance-center-to-create-outbound-spam-policies) om uitgaand spambeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="08751-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="08751-245">Voor het standaardbeleid voor uitgaande spam met  de naam Beleid voor uitgaand **spamfilter** is de sectie Toegepast op niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="08751-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="08751-246">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="08751-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="08751-247">Uitgaand spambeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="08751-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="08751-248">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-249">Klik op **de pagina Antispam-instellingen** op Pictogram uitvvuilen om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom Type ![ is Aangepast uitgaande ](../../media/scc-expand-icon.png) **spambeleid).** </span><span class="sxs-lookup"><span data-stu-id="08751-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="08751-250">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="08751-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="08751-251">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="08751-251">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="08751-253">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="08751-253">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/scc-toggle-on.png)

<span data-ttu-id="08751-255">U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="08751-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="08751-256">De prioriteit instellen van aangepaste beleidsregels voor uitgaande spam</span><span class="sxs-lookup"><span data-stu-id="08751-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="08751-257">Uitgaande spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="08751-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="08751-258">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="08751-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="08751-259">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="08751-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="08751-260">Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="08751-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="08751-261">Het standaardbeleid voor uitgaande spam met de naam Beleid voor **uitgaand spamfilter** heeft de prioriteitswaarde **Laag** en u kunt het niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="08751-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="08751-262">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="08751-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="08751-263">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-264">Zoek op **de pagina Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="08751-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="08751-265">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="08751-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="08751-266">Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft de waarde ![ Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="08751-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="08751-267">Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft de waarde Pijl-omhoog ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **pictogram n** (bijvoorbeeld Pijl-omhoog ![ pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**</span><span class="sxs-lookup"><span data-stu-id="08751-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="08751-268">Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, hebben de beleidsregels tussen de hoogste en laagste prioriteit de waarden Pijl-omhoog pictogram Pijl-omlaag n (bijvoorbeeld pijl-omhoog pictogram Pijl-omlaag ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ pictogram ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**</span><span class="sxs-lookup"><span data-stu-id="08751-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="08751-269">Klik op</span><span class="sxs-lookup"><span data-stu-id="08751-269">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="08751-271">of</span><span class="sxs-lookup"><span data-stu-id="08751-271">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="08751-273">om het aangepaste uitgaande spambeleid omhoog of omlaag in de prioriteitenlijst te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="08751-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="08751-274">Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="08751-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="08751-275">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="08751-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="08751-276">Klik op **de pagina Antispam-instellingen** op Pictogram uitvvuilen om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom Type ![ is Aangepast uitgaande ](../../media/scc-expand-icon.png) **spambeleid).** </span><span class="sxs-lookup"><span data-stu-id="08751-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="08751-277">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="08751-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="08751-278">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="08751-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="08751-279">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="08751-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="08751-280">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="08751-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="08751-281">Zoals eerder beschreven, bestaat een uitgaand spambeleid uit een uitgaand spamfilterbeleid en een regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="08751-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="08751-282">In Exchange Online PowerShell of zelfstandige EOP PowerShell is het verschil tussen beleidsregels voor uitgaand spamfilter en regels voor uitgaand spamfilter duidelijk.</span><span class="sxs-lookup"><span data-stu-id="08751-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="08751-283">U beheert beleidsregels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterPolicy** en u beheert regels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="08751-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="08751-284">In PowerShell maakt u eerst het beleid voor uitgaand spamfilter en vervolgens maakt u de regel voor uitgaand spamfilter waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="08751-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="08751-285">In PowerShell wijzigt u de instellingen in het beleid voor uitgaand spamfilter en de regel voor uitgaand spamfilter afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="08751-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="08751-286">Wanneer u een beleid voor uitgaand spamfilter uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaand spamfilter niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="08751-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="08751-287">PowerShell gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="08751-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="08751-288">Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="08751-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="08751-289">Maak het beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="08751-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="08751-290">Maak de regel voor uitgaande spamfilters die het beleid voor uitgaand spamfilter aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="08751-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="08751-291">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="08751-291">**Notes**:</span></span>

- <span data-ttu-id="08751-292">U kunt een nieuwe regel voor uitgaand spamfilter maken en er een bestaand, niet-verbonden beleid voor uitgaand spamfilter aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="08751-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="08751-293">Een regel voor uitgaand spamfilter kan niet worden gekoppeld aan meer dan één beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="08751-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="08751-294">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaand spamfilter in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="08751-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="08751-295">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="08751-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="08751-296">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ op de _\<Number\>_ **cmdlet New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="08751-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="08751-297">Een nieuw beleid voor uitgaand spamfilter dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliancecentrum als u het beleid aan een spamfilterregel toewijst.</span><span class="sxs-lookup"><span data-stu-id="08751-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="08751-298">Stap 1: PowerShell gebruiken om een beleid voor uitgaand spamfilter te maken</span><span class="sxs-lookup"><span data-stu-id="08751-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="08751-299">Als u een beleid voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="08751-300">In dit voorbeeld wordt een nieuw beleid voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="08751-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="08751-301">De limieten voor het aantal geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="08751-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="08751-302">Zie Limieten verzenden [voor Microsoft 365-opties](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08751-302">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="08751-303">Nadat een van de limieten is bereikt, kan de gebruiker geen berichten meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="08751-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="08751-304">Zie [New-HostedOutboundSpamFilterPolicy voor](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="08751-305">Stap 2: PowerShell gebruiken om een regel voor uitgaand spamfilter te maken</span><span class="sxs-lookup"><span data-stu-id="08751-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="08751-306">Als u een regel voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="08751-307">In dit voorbeeld wordt een nieuwe regel voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="08751-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="08751-308">Het beleid voor uitgaand spamfilter met de naam Contoso Executives is gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="08751-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="08751-309">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="08751-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="08751-310">Zie [New-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="08751-311">PowerShell gebruiken om uitgaand spamfilterbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="08751-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="08751-312">Voer deze opdracht uit als u een overzichtslijst met alle beleidsregels voor uitgaand spamfilter wilt retourneren:</span><span class="sxs-lookup"><span data-stu-id="08751-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="08751-313">Als u gedetailleerde informatie wilt retourneren over een specifiek beleid voor uitgaand spamfilter, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="08751-314">Dit voorbeeld retourneert alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="08751-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="08751-315">Zie [Get-HostedOutboundSpamFilterPolicy (Get-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="08751-316">PowerShell gebruiken om regels voor uitgaande spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="08751-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="08751-317">Als u bestaande regels voor uitgaand spamfilter wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="08751-318">Voer deze opdracht uit als u een overzichtslijst met alle regels voor uitgaand spamfilter wilt retourneren:</span><span class="sxs-lookup"><span data-stu-id="08751-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="08751-319">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="08751-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="08751-320">Als u gedetailleerde informatie wilt retourneren over een specifieke regel voor uitgaand spamfilter, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="08751-321">In dit voorbeeld worden alle eigenschapswaarden voor de regel voor uitgaand spamfilter met de naam Contoso Executives als retourneert.</span><span class="sxs-lookup"><span data-stu-id="08751-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="08751-322">Zie [Get-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/get-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="08751-323">PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te wijzigen</span><span class="sxs-lookup"><span data-stu-id="08751-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="08751-324">Dezelfde instellingen zijn beschikbaar wanneer u een malwarefilterbeleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilterbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="08751-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="08751-325">U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="08751-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="08751-326">Wanneer u de naam van een uitgaand spambeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de regel voor uitgaand _spamfilter._</span><span class="sxs-lookup"><span data-stu-id="08751-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="08751-327">Als u een beleid voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="08751-328">Zie [Set-HostedOutboundSpamFilterPolicy (Set-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="08751-329">PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="08751-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="08751-330">De enige instelling die niet beschikbaar is wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="08751-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="08751-331">Zie de volgende sectie als u bestaande regels voor uitgaand spamfilter wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="08751-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="08751-332">Anders zijn er geen extra instellingen beschikbaar wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="08751-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="08751-333">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilter te maken.</span><span class="sxs-lookup"><span data-stu-id="08751-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="08751-334">Als u een regel voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="08751-335">Zie [Set-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/set-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="08751-336">PowerShell gebruiken om regels voor uitgaande spamfilters in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="08751-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="08751-337">Als u een regel voor uitgaand spamfilter in PowerShell in- of uitschakelen, wordt het hele uitgaande spambeleid (de regel voor uitgaand spamfilter en het toegewezen beleid voor uitgaand spamfilter) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="08751-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="08751-338">U kunt het standaardbeleid voor uitgaande spam niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="08751-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="08751-339">Als u een uitgaande spamfilterregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="08751-340">In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="08751-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="08751-341">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="08751-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="08751-342">Zie [Enable-HostedOutboundSpamFilterRule and Disable-HostedOutboundSpamFilterRule (Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule)](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="08751-343">PowerShell gebruiken om de prioriteit in te stellen van regels voor uitgaande spamfilters</span><span class="sxs-lookup"><span data-stu-id="08751-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="08751-344">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="08751-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="08751-345">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="08751-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="08751-346">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08751-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="08751-347">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="08751-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="08751-348">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="08751-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="08751-349">Gebruik de volgende syntaxis om de prioriteit in te stellen van een uitgaande spamfilterregel in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08751-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="08751-350">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="08751-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="08751-351">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="08751-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="08751-352">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="08751-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="08751-353">Het standaardbeleid voor uitgaand spamfilter heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifieerbare prioriteitswaarde **Laag**.</span><span class="sxs-lookup"><span data-stu-id="08751-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="08751-354">PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te verwijderen</span><span class="sxs-lookup"><span data-stu-id="08751-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="08751-355">Wanneer u PowerShell gebruikt om een beleid voor uitgaand spamfilter te verwijderen, wordt de bijbehorende regel voor uitgaand spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08751-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="08751-356">Als u een beleid voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="08751-357">In dit voorbeeld wordt het beleid voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08751-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="08751-358">Zie [Remove-HostedOutboundSpamFilterPolicy (Remove-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="08751-359">PowerShell gebruiken om regels voor uitgaand spamfilter te verwijderen</span><span class="sxs-lookup"><span data-stu-id="08751-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="08751-360">Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor uitgaand spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08751-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="08751-361">Als u een regel voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="08751-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="08751-362">In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08751-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="08751-363">Zie [Remove-HostedOutboundSpamFilterRule (Remove-HostedOutboundSpamFilterRule)](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="08751-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="08751-364">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="08751-364">For more information</span></span>

[<span data-ttu-id="08751-365">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="08751-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="08751-366">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="08751-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="08751-367">Veelgestelde vragen over beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="08751-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="08751-368">Rapport over automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="08751-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)