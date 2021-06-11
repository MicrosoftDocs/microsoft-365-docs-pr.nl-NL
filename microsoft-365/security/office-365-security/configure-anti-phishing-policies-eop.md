---
title: Antiphishingbeleid configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze het anti-phishingbeleid kunnen maken, wijzigen en verwijderen dat beschikbaar is in Exchange Online Protection (EOP) organisaties met of zonder Exchange Online postvakken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec944a2bf6fa7600a9970a7354332d140293ab5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878542"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="3a586-103">Antiphishingbeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="3a586-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a586-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3a586-104">**Applies to**</span></span>
- [<span data-ttu-id="3a586-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3a586-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3a586-106">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection(EOP) organisaties zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal anti-spoofing-functies bevat die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3a586-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="3a586-107">Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="3a586-108">Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="3a586-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="3a586-109">Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3a586-110">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3a586-111">Organisaties met Exchange Online postvakken kunnen anti-phishingbeleid configureren in Microsoft 365 Defender-portal of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a586-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="3a586-112">Zelfstandige EOP-organisaties kunnen alleen de portal Microsoft 365 Defender gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a586-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="3a586-113">Zie Anti-phishingbeleid configureren in Microsoft Office 365 Defender voor Office 365 voor meer informatie over het maken en wijzigen van het meer geavanceerde [anti-phishingbeleid](configure-atp-anti-phishing-policies.md)dat beschikbaar is in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a586-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="3a586-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="3a586-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="3a586-115">**Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="3a586-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3a586-116">**De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3a586-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in Microsoft 365 Defender-portal:</span><span class="sxs-lookup"><span data-stu-id="3a586-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="3a586-118">Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="3a586-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3a586-119">Wanneer u een anti-phishingbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="3a586-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3a586-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3a586-121">Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3a586-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="3a586-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3a586-123">Zie de sectie Gebruik Exchange Online PowerShell voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="3a586-124">Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="3a586-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3a586-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3a586-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="3a586-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3a586-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="3a586-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3a586-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3a586-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3a586-129">Als u de effectiviteit van anti-phishingbeveiliging wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3a586-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3a586-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="3a586-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3a586-131">U opent de Microsoft 365 Defender-portal op <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="3a586-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="3a586-132">Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="3a586-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="3a586-133">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a586-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="3a586-134">U kunt anti-phishingbeleid niet beheren in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a586-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="3a586-135">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="3a586-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3a586-136">Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="3a586-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3a586-137">Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="3a586-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3a586-138">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="3a586-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3a586-139">**Notes**:</span></span>

  - <span data-ttu-id="3a586-140">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3a586-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3a586-141">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3a586-142">De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="3a586-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="3a586-143">Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3a586-144">Maximaal 30 minuten toestaan dat het bijgewerkte beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="3a586-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="3a586-145">Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="3a586-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="3a586-146">Gebruik de Microsoft 365 Defender-portal om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="3a586-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="3a586-147">Als u een aangepast anti-phishingbeleid maakt in de Microsoft 365 Defender-portal, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="3a586-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3a586-148">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-149">Klik op **de pagina Anti-phishing** op ![ Pictogram Maken ](../../media/m365-cc-sc-create-icon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="3a586-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="3a586-150">De wizard van het beleid wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="3a586-150">The policy wizard opens.</span></span> <span data-ttu-id="3a586-151">Configureer **deze instellingen op de** pagina Beleidsnaam:</span><span class="sxs-lookup"><span data-stu-id="3a586-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="3a586-152">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="3a586-153">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3a586-154">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a586-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3a586-155">Zoek op de pagina **Gebruikers, groepen en domeinen** die wordt weergegeven, de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):</span><span class="sxs-lookup"><span data-stu-id="3a586-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="3a586-156">**Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3a586-157">**Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="3a586-158">**Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="3a586-159">Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="3a586-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="3a586-160">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="3a586-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="3a586-161">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="3a586-161">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="3a586-163">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="3a586-163">next to the value.</span></span>

   <span data-ttu-id="3a586-164">Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="3a586-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="3a586-165">Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3a586-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="3a586-166">Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="3a586-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3a586-167">Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3a586-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="3a586-168">**Deze gebruikers, groepen en domeinen uitsluiten**: als u uitzonderingen wilt toevoegen voor de interne geadresseerden op wie het beleid van toepassing is (uitzonderingen op ontvangers), selecteert u deze optie en configureert u de uitzonderingen.</span><span class="sxs-lookup"><span data-stu-id="3a586-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="3a586-169">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="3a586-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3a586-170">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a586-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3a586-171">Op de **pagina Phishing-&** die wordt weergegeven, gebruikt u het selectievakje Spoof **intelligence** inschakelen om spoofinformatie in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="3a586-172">De standaardwaarde is ingeschakeld (geselecteerd) en u wordt aangeraden deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="3a586-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="3a586-173">U configureert de actie voor geblokkeerde vervalste berichten op de volgende pagina.</span><span class="sxs-lookup"><span data-stu-id="3a586-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="3a586-174">Schakel het selectievakje uit om spoofinformatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a586-175">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3a586-176">Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="3a586-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="3a586-177">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a586-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3a586-178">Configureer de volgende instellingen op de pagina **Acties** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="3a586-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="3a586-179">**Als bericht wordt gedetecteerd als spoof:** Deze instelling is alleen beschikbaar als u **Spoofinformatie inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="3a586-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="3a586-180">Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten van geblokkeerde vervalste afzenders:</span><span class="sxs-lookup"><span data-stu-id="3a586-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="3a586-181">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="3a586-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3a586-182">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="3a586-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="3a586-183">**Veiligheidstips & indicatoren:** deze instelling is alleen beschikbaar als u **Spoof intelligence inschakelen** op de vorige pagina hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="3a586-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="3a586-184">**Weergeven (?)** voor niet-nautische afzenders voor spoof: Hiermee wordt een vraagteken toegevoegd aan de foto van de afzender in het  vak Van in Outlook als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="3a586-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="3a586-185">**Tag 'via' tonen:** hiermee voegt u een via-tag (chris@contoso.com via fabrikam.com) toe aan het Van-adres als deze verschilt van het domein in de DKIM-handtekening of het **MAIL** FROM-adres.</span><span class="sxs-lookup"><span data-stu-id="3a586-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="3a586-186">Op dit moment is de taginstelling **'via'** tonen niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="3a586-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="3a586-187">Als u de taginstelling **'via'** tonen niet hebt, worden het vraagteken en de via-tag beide beheerd door de instelling Tonen  **(?)** voor niet-genauteerde afzenders voor spoofinstelling in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a586-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="3a586-188">Schakel het selectievakje in om een instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3a586-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="3a586-189">Schakel het selectievakje uit om het uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="3a586-190">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a586-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="3a586-191">Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a586-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="3a586-192">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3a586-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3a586-193">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="3a586-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="3a586-194">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="3a586-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="3a586-195">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="3a586-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="3a586-196">Gebruik de Microsoft 365 Defender-portal om anti-phishingbeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="3a586-196">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="3a586-197">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-197">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-198">Op de **pagina Anti-phishing** worden de volgende eigenschappen weergegeven in de lijst met anti-phishingbeleidsregels:</span><span class="sxs-lookup"><span data-stu-id="3a586-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="3a586-199">**Naam**</span><span class="sxs-lookup"><span data-stu-id="3a586-199">**Name**</span></span>
   - <span data-ttu-id="3a586-200">**Status**</span><span class="sxs-lookup"><span data-stu-id="3a586-200">**Status**</span></span>
   - <span data-ttu-id="3a586-201">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="3a586-201">**Priority**</span></span>
   - <span data-ttu-id="3a586-202">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="3a586-202">**Last modified**</span></span>

3. <span data-ttu-id="3a586-203">Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3a586-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="3a586-204">Gebruik de Microsoft 365 Defender-portal om anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="3a586-204">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="3a586-205">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-205">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-206">Selecteer op **de pagina Anti-phishing** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="3a586-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3a586-207">U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3a586-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3a586-208">Zie de portal Use [the Microsoft 365 Defender om anti-phishingbeleid](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) te maken eerder in dit artikel voor meer informatie over de instellingen.</span><span class="sxs-lookup"><span data-stu-id="3a586-208">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="3a586-209">Voor het standaard anti-phishingbeleid is de sectie **Gebruikers,** groepen en domeinen niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3a586-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3a586-210">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="3a586-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="3a586-211">Aangepaste anti-phishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="3a586-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="3a586-212">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3a586-213">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-213">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-214">Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="3a586-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3a586-215">Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3a586-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="3a586-216">**Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="3a586-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="3a586-217">**Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="3a586-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="3a586-218">Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="3a586-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="3a586-219">Klik in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3a586-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="3a586-220">Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="3a586-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="3a586-221">De prioriteit instellen van aangepast anti-phishingbeleid</span><span class="sxs-lookup"><span data-stu-id="3a586-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="3a586-222">Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="3a586-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3a586-223">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="3a586-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3a586-224">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="3a586-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3a586-225">Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in de portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="3a586-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="3a586-226">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="3a586-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="3a586-227">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3a586-227">**Notes**:</span></span>

- <span data-ttu-id="3a586-228">In de Microsoft 365 Defender-portal kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u deze hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3a586-228">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="3a586-229">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="3a586-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="3a586-230">Anti-phishingbeleid wordt verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="3a586-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3a586-231">Het standaard anti-phishingbeleid heeft de prioriteitswaarde **Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3a586-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="3a586-232">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-232">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-233">Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="3a586-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3a586-234">Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="3a586-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="3a586-235">Het anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3a586-235">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="3a586-236">Het anti-phishingbeleid met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="3a586-236">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="3a586-237">Als u drie of meer anti-phishingbeleidsregels hebt, hebben beleidsregels tussen  de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar. </span><span class="sxs-lookup"><span data-stu-id="3a586-237">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="3a586-238">Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3a586-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="3a586-239">Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3a586-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="3a586-240">Gebruik de Microsoft 365 Defender-portal om aangepaste anti-phishingbeleidsregels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="3a586-240">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="3a586-241">Wanneer u de portal Microsoft 365 Defender gebruikt om een aangepast anti-phishingbeleid te verwijderen, worden de anti-phish-regel en het bijbehorende anti-phish-beleid beide verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-241">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="3a586-242">U kunt het standaard anti-phishingbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3a586-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3a586-243">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-243">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3a586-244">Selecteer een aangepast beleid in de lijst door op de naam van het beleid te klikken.</span><span class="sxs-lookup"><span data-stu-id="3a586-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="3a586-245">Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3a586-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="3a586-246">Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3a586-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="3a586-247">Gebruik Exchange Online PowerShell om anti-phishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="3a586-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="3a586-248">Zoals eerder beschreven, bestaat een anti-phishingbeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="3a586-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3a586-249">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="3a586-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3a586-250">U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3a586-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3a586-251">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="3a586-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3a586-252">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="3a586-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3a586-253">Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="3a586-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="3a586-254">De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties met Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a586-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3a586-255">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="3a586-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3a586-256">Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="3a586-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3a586-257">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3a586-258">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="3a586-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3a586-259">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3a586-259">**Notes**:</span></span>

- <span data-ttu-id="3a586-260">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3a586-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3a586-261">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="3a586-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3a586-262">U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in de Microsoft 365 Defender-portal nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="3a586-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="3a586-263">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="3a586-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3a586-264">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="3a586-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3a586-265">Een nieuw anti-phish-beleid dat u maakt in PowerShell, is niet zichtbaar in de Microsoft 365 Defender-portal totdat u het beleid toewijst aan een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="3a586-265">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3a586-266">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="3a586-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3a586-267">Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="3a586-268">In dit voorbeeld wordt een anti-phish-beleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="3a586-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3a586-269">De beschrijving is: Het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="3a586-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="3a586-270">Wijzigt de standaardactie voor spoofing in Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="3a586-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="3a586-271">Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3a586-272">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="3a586-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3a586-273">Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3a586-274">In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="3a586-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3a586-275">De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="3a586-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3a586-276">De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="3a586-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3a586-277">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3a586-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3a586-278">Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3a586-279">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="3a586-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3a586-280">Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="3a586-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3a586-281">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a586-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3a586-282">Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="3a586-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3a586-283">Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3a586-284">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="3a586-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3a586-285">Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3a586-286">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a586-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3a586-287">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="3a586-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3a586-288">Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="3a586-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3a586-289">Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3a586-290">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="3a586-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3a586-291">Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u een beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.</span><span class="sxs-lookup"><span data-stu-id="3a586-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="3a586-292">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a586-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="3a586-293">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="3a586-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3a586-294">Wanneer u de naam van een anti-phishingbeleid wijzigt in Microsoft 365 Defender-portal, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="3a586-294">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3a586-295">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3a586-296">Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3a586-297">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="3a586-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3a586-298">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="3a586-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3a586-299">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="3a586-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3a586-300">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.</span><span class="sxs-lookup"><span data-stu-id="3a586-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="3a586-301">Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3a586-302">Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3a586-303">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="3a586-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3a586-304">Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3a586-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3a586-305">U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="3a586-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3a586-306">Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3a586-307">In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3a586-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a586-308">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3a586-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a586-309">Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3a586-310">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="3a586-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3a586-311">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="3a586-311">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3a586-312">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="3a586-312">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3a586-313">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a586-313">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3a586-314">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="3a586-314">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3a586-315">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="3a586-315">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3a586-316">Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3a586-317">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="3a586-317">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="3a586-318">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="3a586-318">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3a586-319">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3a586-319">**Notes**:</span></span>

- <span data-ttu-id="3a586-320">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3a586-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="3a586-321">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.</span><span class="sxs-lookup"><span data-stu-id="3a586-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3a586-322">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="3a586-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3a586-323">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3a586-324">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3a586-325">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3a586-326">Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3a586-327">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="3a586-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3a586-328">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3a586-329">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3a586-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3a586-330">In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3a586-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a586-331">Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="3a586-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3a586-332">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="3a586-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="3a586-333">Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in EOP, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="3a586-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="3a586-334">Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3a586-334">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="3a586-335">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="3a586-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3a586-336">Als u meer details wilt weergeven, selecteert u het beleid in de lijst door op de naam te klikken en de details weer te geven in de flyout die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a586-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="3a586-337">Vervang Exchange Online PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="3a586-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
