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
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822007"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="65fa9-103">Uitgaande spamfilters configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="65fa9-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="65fa9-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="65fa9-104">**Applies to**</span></span>
- [<span data-ttu-id="65fa9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="65fa9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="65fa9-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="65fa9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="65fa9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65fa9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="65fa9-108">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendingsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="65fa9-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="65fa9-109">Uitgaande spam van een gebruiker in uw organisatie geeft meestal een gekromd account aan.</span><span class="sxs-lookup"><span data-stu-id="65fa9-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="65fa9-110">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het betrouwbaarheidsniveau voor spam of SCL) en worden door de groep met risicovolle bezorging gerouteerd om de reputatie van de service te beschermen (dat wil zeggen dat Microsoft 365 bron-e-mailservers buiten [ip-bloklijsten](high-risk-delivery-pool-for-outbound-messages.md) blijven).</span><span class="sxs-lookup"><span data-stu-id="65fa9-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="65fa9-111">Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteit en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="65fa9-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="65fa9-112">EOP gebruikt uitgaand spambeleid als onderdeel van de algemene verdediging van uw organisatie tegen spam.</span><span class="sxs-lookup"><span data-stu-id="65fa9-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="65fa9-113">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="65fa9-114">Beheerders kunnen het standaardbeleid voor uitgaande spam weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="65fa9-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="65fa9-115">Voor meer granulariteit kunt u ook aangepaste uitgaande spambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="65fa9-116">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="65fa9-117">U kunt uitgaand spambeleid configureren in het Microsoft 365-beveiligingscentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="65fa9-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="65fa9-118">De basiselementen van een uitgaand spambeleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="65fa9-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="65fa9-119">**Het beleid voor uitgaand spamfilter:** geeft de acties voor uitgaande spamfilters en de meldingsopties op.</span><span class="sxs-lookup"><span data-stu-id="65fa9-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="65fa9-120">**De regel voor uitgaand spamfilter:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="65fa9-121">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam polices beheert in het beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="65fa9-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="65fa9-122">Wanneer u een beleid maakt, maakt u tegelijkertijd een regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="65fa9-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="65fa9-123">Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en adressenfilters de regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="65fa9-124">Alle andere instellingen wijzigen het bijbehorende beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="65fa9-125">Wanneer u een beleid verwijdert, worden de regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="65fa9-126">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="65fa9-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="65fa9-127">Zie de sectie Gebruik Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) voor het configureren van uitgaand spambeleid verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="65fa9-128">Elke organisatie heeft een ingebouwd uitgaand spambeleid met de naam Standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="65fa9-129">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen regel voor uitgaand spamfilter (geadresseerdenfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="65fa9-130">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="65fa9-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="65fa9-131">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="65fa9-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="65fa9-132">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="65fa9-133">Als u de effectiviteit van uitgaande spamfilters wilt vergroten, kunt u aangepaste uitgaande spambeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="65fa9-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65fa9-134">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="65fa9-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="65fa9-135">U opent het beveiligingscentrum in <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="65fa9-135">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="65fa9-136">Gebruik <https://security.microsoft.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="65fa9-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="65fa9-137">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65fa9-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="65fa9-138">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65fa9-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="65fa9-139">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="65fa9-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="65fa9-140">Als u uitgaande spambeleidsregels wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="65fa9-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="65fa9-141">Als u alleen-lezen toegang wilt tot uitgaand spambeleid, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="65fa9-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="65fa9-142">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="65fa9-143">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="65fa9-143">**Notes**:</span></span>

  - <span data-ttu-id="65fa9-144">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65fa9-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="65fa9-145">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="65fa9-146">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="65fa9-147">Zie [EOP outbound spamfilterbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)voor onze aanbevolen instellingen voor uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="65fa9-148">De [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleidsregels met de naam Verzendlimiet voor e-mail zijn **overschreden,** Verdachte patronen voor het verzenden van e-mail zijn gedetecteerd en gebruikers kunnen geen e-mailmeldingen verzenden naar leden van de **groep TenantAdmins** **(Globale** beheerders) over ongebruikelijke uitgaande e-mailactiviteit en geblokkeerde gebruikers vanwege uitgaande spam. </span><span class="sxs-lookup"><span data-stu-id="65fa9-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="65fa9-149">Zie De waarschuwingsinstellingen voor beperkte gebruikers controleren [voor meer informatie.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="65fa9-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="65fa9-150">U wordt aangeraden dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="65fa9-151">Het beveiligingscentrum gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="65fa9-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="65fa9-152">Als u een aangepast uitgaand spambeleid maakt in het beveiligingscentrum, worden de filterregel voor spam en het bijbehorende spamfilterbeleid tegelijkertijd met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="65fa9-153">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-154">Klik op **de pagina Antispambeleid** op Pictogram Maken Beleid maken en selecteer vervolgens ![ ](../../media/m365-cc-sc-create-icon.png)  **Uitgaand** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="65fa9-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="65fa9-155">De wizard van het beleid wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="65fa9-155">The policy wizard opens.</span></span> <span data-ttu-id="65fa9-156">Configureer de volgende instellingen op de pagina **Uw beleid een naam geven**:</span><span class="sxs-lookup"><span data-stu-id="65fa9-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="65fa9-157">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="65fa9-158">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="65fa9-159">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="65fa9-160">Zoek op de pagina **Gebruikers, groepen en domeinen** die wordt weergegeven, de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):</span><span class="sxs-lookup"><span data-stu-id="65fa9-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="65fa9-161">**Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="65fa9-162">**Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="65fa9-163">**Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="65fa9-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="65fa9-164">Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="65fa9-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="65fa9-165">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="65fa9-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="65fa9-166">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="65fa9-166">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="65fa9-168">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="65fa9-168">next to the value.</span></span>

   <span data-ttu-id="65fa9-169">Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="65fa9-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="65fa9-170">Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="65fa9-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="65fa9-171">Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="65fa9-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="65fa9-172">Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="65fa9-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="65fa9-173">**Deze gebruikers, groepen en domeinen uitsluiten**: als u uitzonderingen wilt toevoegen voor de interne geadresseerden op wie het beleid van toepassing is (uitzonderingen op ontvangers), selecteert u deze optie en configureert u de uitzonderingen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="65fa9-174">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="65fa9-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="65fa9-175">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="65fa9-176">Configureer **de volgende** instellingen op de pagina Beveiligingsinstellingen die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="65fa9-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="65fa9-177">**Berichtlimieten:** De instellingen in deze sectie configureren de limieten voor uitgaande e-mailberichten **uit Exchange Online** postvakken:</span><span class="sxs-lookup"><span data-stu-id="65fa9-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="65fa9-178">**Een externe berichtlimiet instellen:** het maximum aantal externe geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="65fa9-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="65fa9-179">**Een interne berichtlimiet instellen:** het maximum aantal interne geadresseerden per uur.</span><span class="sxs-lookup"><span data-stu-id="65fa9-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="65fa9-180">**Een dagelijkse berichtlimiet instellen:** het maximumtotaal aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="65fa9-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="65fa9-181">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="65fa9-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="65fa9-182">De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="65fa9-183">Zie Limieten verzenden [voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="65fa9-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="65fa9-184">Voer een waarde in het vak in of gebruik de pijlen voor het vergroten/verlagen van het vak.</span><span class="sxs-lookup"><span data-stu-id="65fa9-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="65fa9-185">**Beperking voor gebruikers die de berichtlimiet** bereiken: Selecteer een actie in de  vervolgkeuzelijst wanneer een van de limieten in de sectie Beveiligingsinstellingen wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="65fa9-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="65fa9-186">Voor alle acties ontvangen de geadresseerden die in de gebruiker zijn opgegeven, geen e-mailwaarschuwingsbeleid meer (en in het nu redundante Bericht deze gebruikers en groepen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** later op deze pagina) e-mailmeldingen ontvangen. </span><span class="sxs-lookup"><span data-stu-id="65fa9-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="65fa9-187">**De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="65fa9-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="65fa9-188">Er worden e-mailmeldingen verzonden en de gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="65fa9-189">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="65fa9-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="65fa9-190">De activiteitswaarschuwing **met de naam Gebruiker die geen e-mail** mag verzenden, meldt beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).</span><span class="sxs-lookup"><span data-stu-id="65fa9-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="65fa9-191">Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="65fa9-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="65fa9-192">De gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="65fa9-193">De beheerder kan dit blok niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="65fa9-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="65fa9-194">**De** gebruiker beperken van het verzenden van e-mail:  e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan Beperkte gebruikers in het beveiligingscentrum en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder is verwijderd uit beperkte <https://security.microsoft.com/restrictedusers> gebruikers.  Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="65fa9-195">Zie Een gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van [spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="65fa9-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="65fa9-196">**Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="65fa9-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="65fa9-197">**Regels voor doorsturen:** Gebruik de instellingen in deze sectie om automatische doorsturen van e-mail door postvakken Exchange Online **externe** afzenders te beheren.</span><span class="sxs-lookup"><span data-stu-id="65fa9-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="65fa9-198">Zie Automatische externe e-mail doorsturen [in](external-email-forwarding.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65fa9-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="65fa9-199">Wanneer automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) als externe afzenders e-mail verzenden naar een postvak dat is doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="65fa9-200">Als het bericht wordt verzonden door een interne afzender en de doorsturenmethode postvak doorsturen [is](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR. </span><span class="sxs-lookup"><span data-stu-id="65fa9-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="65fa9-201">De interne afzender krijgt geen NDR als het doorsturen is gebeurd vanwege een regel voor postvak IN.</span><span class="sxs-lookup"><span data-stu-id="65fa9-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="65fa9-202">Selecteer een van de volgende acties in de vervolgkeuzelijst Regels **voor** automatisch doorsturen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="65fa9-203">**Automatisch - Systeemgestuurd:** hiermee kunt u uitgaande spamfilters gebruiken om automatische doorsturen van externe e-mail te controleren.</span><span class="sxs-lookup"><span data-stu-id="65fa9-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="65fa9-204">Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="65fa9-204">This is the default value.</span></span>
     - <span data-ttu-id="65fa9-205">**Op**: Automatische externe e-mail doorsturen is niet uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="65fa9-206">**Uit:** Alle automatische externe e-mail doorsturen is uitgeschakeld door het beleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="65fa9-207">**Meldingen:** Gebruik de instellingen in de sectie om extra geadresseerden te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="65fa9-208">**Een kopie verzenden van verdachte uitgaande** personen die deze limieten overschrijden voor deze gebruikers en groepen: met deze instelling worden de opgegeven geadresseerden toegevoegd aan het BCC-veld met verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="65fa9-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="65fa9-209">Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="65fa9-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="65fa9-210">Het werkt niet in aangepaste uitgaande spambeleidsregels die u maakt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="65fa9-211">Schakel het selectievakje in om deze instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="65fa9-212">Klik in het vak dat wordt weergegeven in het vak, voer een geldig e-mailadres in en druk vervolgens op Enter of selecteer de volledige waarde die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="65fa9-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="65fa9-213">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="65fa9-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="65fa9-214">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="65fa9-214">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="65fa9-216">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="65fa9-216">next to the value.</span></span>

   - <span data-ttu-id="65fa9-217">**Informeer deze gebruikers en groepen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam**</span><span class="sxs-lookup"><span data-stu-id="65fa9-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="65fa9-218">Deze instelling wordt momenteel verwijderd uit uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="65fa9-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="65fa9-219">Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid met de naam **Gebruiker** die geen e-mail mag verzenden, verzendt al e-mailmeldingen naar leden van de **groep TenantAdmins** **(Globale** beheerders) wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie Geadresseerdenlimieten. </span><span class="sxs-lookup"><span data-stu-id="65fa9-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="65fa9-220">**We raden u ten zeerste aan het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="65fa9-221">Zie De [waarschuwingsinstellingen voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)beperkte gebruikers controleren voor instructies.</span><span class="sxs-lookup"><span data-stu-id="65fa9-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="65fa9-222">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="65fa9-223">Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="65fa9-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="65fa9-224">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="65fa9-225">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="65fa9-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="65fa9-226">Klik op **Maken** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="65fa9-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="65fa9-227">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="65fa9-228">Het beveiligingscentrum gebruiken om uitgaand spambeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="65fa9-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="65fa9-229">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-230">Zoek op de pagina **Antispambeleid** een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="65fa9-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="65fa9-231">De **waarde Type** is Aangepast uitgaande **spambeleid**</span><span class="sxs-lookup"><span data-stu-id="65fa9-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="65fa9-232">De **waarde Naam** is **uitgaand beleid antispam (standaard)**</span><span class="sxs-lookup"><span data-stu-id="65fa9-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="65fa9-233">De volgende eigenschappen worden weergegeven in de lijst met antispambeleidsregels:</span><span class="sxs-lookup"><span data-stu-id="65fa9-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="65fa9-234">**Naam**</span><span class="sxs-lookup"><span data-stu-id="65fa9-234">**Name**</span></span>
   - <span data-ttu-id="65fa9-235">**Status**</span><span class="sxs-lookup"><span data-stu-id="65fa9-235">**Status**</span></span>
   - <span data-ttu-id="65fa9-236">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="65fa9-236">**Priority**</span></span>
   - <span data-ttu-id="65fa9-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="65fa9-237">**Type**</span></span>

3. <span data-ttu-id="65fa9-238">Wanneer u een uitgaand spambeleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="65fa9-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="65fa9-239">Het beveiligingscentrum gebruiken om uitgaand spambeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="65fa9-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="65fa9-240">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-241">Selecteer op **de pagina Anti-spambeleid** een uitgaand spambeleid in de lijst door op de naam te klikken:</span><span class="sxs-lookup"><span data-stu-id="65fa9-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="65fa9-242">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**</span><span class="sxs-lookup"><span data-stu-id="65fa9-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="65fa9-243">Het standaardbeleid met de naam **Anti-spam uitgaande beleid (standaard)**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="65fa9-244">U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="65fa9-245">Zie het vorige gedeelte Het beveiligingscentrum gebruiken om uitgaand [spambeleid](#use-the-security-center-to-create-outbound-spam-policies) te maken in dit artikel voor meer informatie over de instellingen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="65fa9-246">Voor het standaardbeleid voor  uitgaande spam is de sectie Toegepast op niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="65fa9-247">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="65fa9-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="65fa9-248">Aangepaste beleidsregels voor uitgaande spam in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="65fa9-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="65fa9-249">U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="65fa9-250">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-251">Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="65fa9-252">Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="65fa9-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="65fa9-253">**Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="65fa9-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="65fa9-254">**Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="65fa9-255">Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="65fa9-256">Klik in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="65fa9-257">Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="65fa9-258">De prioriteit instellen van aangepaste beleidsregels voor uitgaande spam</span><span class="sxs-lookup"><span data-stu-id="65fa9-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="65fa9-259">Uitgaande spambeleidsregels krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="65fa9-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="65fa9-260">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="65fa9-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="65fa9-261">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="65fa9-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="65fa9-262">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in het beveiligingscentrum).</span><span class="sxs-lookup"><span data-stu-id="65fa9-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="65fa9-263">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="65fa9-264">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="65fa9-264">**Notes**:</span></span>

- <span data-ttu-id="65fa9-265">In het beveiligingscentrum kunt u alleen de prioriteit van het uitgaande spambeleid wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="65fa9-266">In PowerShell kunt u de standaardprioriteit vervangen wanneer u de spamfilterbeleidsregel maakt (die kan de prioriteit van bestaande regels beïnvloeden).</span><span class="sxs-lookup"><span data-stu-id="65fa9-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="65fa9-267">Uitgaande spambeleidsregels worden verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="65fa9-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="65fa9-268">Het standaardbeleid voor uitgaande spam heeft de **prioriteitswaarde Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="65fa9-269">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-270">Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="65fa9-271">Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="65fa9-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="65fa9-272">Het uitgaande spambeleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="65fa9-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="65fa9-273">Het uitgaande spambeleid met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="65fa9-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="65fa9-274">Als u drie of meer uitgaande spambeleidsregels hebt, hebben beleidsregels tussen  de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar. </span><span class="sxs-lookup"><span data-stu-id="65fa9-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="65fa9-275">Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="65fa9-276">Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="65fa9-277">Het beveiligingscentrum gebruiken om aangepaste beleidsregels voor uitgaande spam te verwijderen</span><span class="sxs-lookup"><span data-stu-id="65fa9-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="65fa9-278">Wanneer u het beveiligingscentrum gebruikt om een aangepast uitgaand spambeleid te verwijderen, worden de spamfilterregel en het bijbehorende spamfilterbeleid beide verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="65fa9-279">U kunt het standaardbeleid voor uitgaande spam niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="65fa9-280">Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="65fa9-281">Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="65fa9-282">Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="65fa9-283">Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="65fa9-284">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om uitgaand spambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="65fa9-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="65fa9-285">Zoals eerder beschreven, bestaat een uitgaand spambeleid uit een uitgaand spamfilterbeleid en een regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="65fa9-286">In Exchange Online PowerShell of zelfstandige EOP PowerShell is het verschil tussen beleidsregels voor uitgaand spamfilter en regels voor uitgaand spamfilter duidelijk.</span><span class="sxs-lookup"><span data-stu-id="65fa9-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="65fa9-287">U beheert beleidsregels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterPolicy** en u beheert regels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="65fa9-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="65fa9-288">In PowerShell maakt u eerst het beleid voor uitgaand spamfilter en vervolgens maakt u de regel voor uitgaand spamfilter waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="65fa9-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="65fa9-289">In PowerShell wijzigt u de instellingen in het beleid voor uitgaand spamfilter en de regel voor uitgaand spamfilter afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="65fa9-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="65fa9-290">Wanneer u een beleid voor uitgaand spamfilter uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaand spamfilter niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="65fa9-291">PowerShell gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="65fa9-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="65fa9-292">Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="65fa9-293">Maak het beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="65fa9-294">Maak de regel voor uitgaande spamfilters die het beleid voor uitgaand spamfilter aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="65fa9-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="65fa9-295">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="65fa9-295">**Notes**:</span></span>

   - <span data-ttu-id="65fa9-296">U kunt een nieuwe regel voor uitgaand spamfilter maken en er een bestaand, niet-verbonden beleid voor uitgaand spamfilter aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="65fa9-297">Een regel voor uitgaand spamfilter kan niet worden gekoppeld aan meer dan één beleid voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="65fa9-298">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaand spamfilter in PowerShell die pas beschikbaar zijn in het beveiligingscentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="65fa9-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="65fa9-299">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="65fa9-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="65fa9-300">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ op de _\<Number\>_ **cmdlet New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="65fa9-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="65fa9-301">Een nieuw beleid voor uitgaand spamfilter dat u in PowerShell maakt, is pas zichtbaar in het beveiligingscentrum als u het beleid toewijst aan een regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="65fa9-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="65fa9-302">Stap 1: PowerShell gebruiken om een beleid voor uitgaand spamfilter te maken</span><span class="sxs-lookup"><span data-stu-id="65fa9-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="65fa9-303">Als u een beleid voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="65fa9-304">In dit voorbeeld wordt een nieuw beleid voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="65fa9-305">De limieten voor het aantal geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="65fa9-306">Zie Limieten voor [Microsoft 365 verzenden voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="65fa9-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="65fa9-307">Nadat een van de limieten is bereikt, kan de gebruiker geen berichten meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="65fa9-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="65fa9-308">Zie [New-HostedOutboundSpamFilterPolicy voor](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="65fa9-309">Stap 2: PowerShell gebruiken om een regel voor uitgaand spamfilter te maken</span><span class="sxs-lookup"><span data-stu-id="65fa9-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="65fa9-310">Als u een regel voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="65fa9-311">In dit voorbeeld wordt een nieuwe regel voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="65fa9-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="65fa9-312">Het beleid voor uitgaand spamfilter met de naam Contoso Executives is gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="65fa9-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="65fa9-313">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="65fa9-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="65fa9-314">Zie [New-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="65fa9-315">PowerShell gebruiken om uitgaand spamfilterbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="65fa9-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="65fa9-316">Voer deze opdracht uit als u een overzichtslijst met alle beleidsregels voor uitgaand spamfilter wilt retourneren:</span><span class="sxs-lookup"><span data-stu-id="65fa9-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="65fa9-317">Als u gedetailleerde informatie wilt retourneren over een specifiek beleid voor uitgaand spamfilter, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="65fa9-318">Dit voorbeeld retourneert alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="65fa9-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="65fa9-319">Zie [Get-HostedOutboundSpamFilterPolicy (Get-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="65fa9-320">PowerShell gebruiken om regels voor uitgaande spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="65fa9-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="65fa9-321">Als u bestaande regels voor uitgaand spamfilter wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="65fa9-322">Voer deze opdracht uit als u een overzichtslijst met alle regels voor uitgaand spamfilter wilt retourneren:</span><span class="sxs-lookup"><span data-stu-id="65fa9-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="65fa9-323">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="65fa9-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="65fa9-324">Als u gedetailleerde informatie wilt retourneren over een specifieke regel voor uitgaand spamfilter, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="65fa9-325">In dit voorbeeld worden alle eigenschapswaarden voor de regel voor uitgaand spamfilter met de naam Contoso Executives als retourneert.</span><span class="sxs-lookup"><span data-stu-id="65fa9-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="65fa9-326">Zie [Get-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/get-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="65fa9-327">PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te wijzigen</span><span class="sxs-lookup"><span data-stu-id="65fa9-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="65fa9-328">Dezelfde instellingen zijn beschikbaar wanneer u een malwarefilterbeleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilterbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="65fa9-329">U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="65fa9-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="65fa9-330">Wanneer u de naam van een uitgaand spambeleid in het beveiligingscentrum wijzigt, wijzigt u alleen de naam van de regel voor uitgaand _spamfilter._</span><span class="sxs-lookup"><span data-stu-id="65fa9-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="65fa9-331">Als u een beleid voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="65fa9-332">Zie [Set-HostedOutboundSpamFilterPolicy (Set-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="65fa9-333">PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="65fa9-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="65fa9-334">De enige instelling die niet beschikbaar is wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="65fa9-335">Zie de volgende sectie als u bestaande regels voor uitgaand spamfilter wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="65fa9-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="65fa9-336">Anders zijn er geen extra instellingen beschikbaar wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="65fa9-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="65fa9-337">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilter te maken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="65fa9-338">Als u een regel voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="65fa9-339">Zie [Set-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/set-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="65fa9-340">PowerShell gebruiken om regels voor uitgaande spamfilters in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="65fa9-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="65fa9-341">Als u een regel voor uitgaand spamfilter in PowerShell in- of uitschakelen, wordt het hele uitgaande spambeleid (de regel voor uitgaand spamfilter en het toegewezen beleid voor uitgaand spamfilter) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="65fa9-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="65fa9-342">U kunt het standaardbeleid voor uitgaande spam niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="65fa9-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="65fa9-343">Als u een uitgaande spamfilterregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="65fa9-344">In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="65fa9-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="65fa9-345">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="65fa9-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="65fa9-346">Zie [Enable-HostedOutboundSpamFilterRule and Disable-HostedOutboundSpamFilterRule (Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule)](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="65fa9-347">PowerShell gebruiken om de prioriteit in te stellen van regels voor uitgaande spamfilters</span><span class="sxs-lookup"><span data-stu-id="65fa9-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="65fa9-348">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="65fa9-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="65fa9-349">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="65fa9-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="65fa9-350">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="65fa9-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="65fa9-351">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="65fa9-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="65fa9-352">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="65fa9-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="65fa9-353">Gebruik de volgende syntaxis om de prioriteit in te stellen van een uitgaande spamfilterregel in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65fa9-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="65fa9-354">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="65fa9-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="65fa9-355">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="65fa9-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="65fa9-356">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="65fa9-356">**Notes**:</span></span>

- <span data-ttu-id="65fa9-357">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="65fa9-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="65fa9-358">Het standaardbeleid voor uitgaand spamfilter heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifieerbare prioriteitswaarde **Laag**.</span><span class="sxs-lookup"><span data-stu-id="65fa9-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="65fa9-359">PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te verwijderen</span><span class="sxs-lookup"><span data-stu-id="65fa9-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="65fa9-360">Wanneer u PowerShell gebruikt om een beleid voor uitgaand spamfilter te verwijderen, wordt de bijbehorende regel voor uitgaand spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="65fa9-361">Als u een beleid voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="65fa9-362">In dit voorbeeld wordt het beleid voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="65fa9-363">Zie [Remove-HostedOutboundSpamFilterPolicy (Remove-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="65fa9-364">PowerShell gebruiken om regels voor uitgaand spamfilter te verwijderen</span><span class="sxs-lookup"><span data-stu-id="65fa9-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="65fa9-365">Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor uitgaand spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="65fa9-366">Als u een regel voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="65fa9-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="65fa9-367">In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="65fa9-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="65fa9-368">Zie [Remove-HostedOutboundSpamFilterRule (Remove-HostedOutboundSpamFilterRule)](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="65fa9-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="65fa9-369">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="65fa9-369">For more information</span></span>

[<span data-ttu-id="65fa9-370">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="65fa9-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="65fa9-371">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="65fa9-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="65fa9-372">Veelgestelde vragen over beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="65fa9-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="65fa9-373">Rapport over automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="65fa9-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
