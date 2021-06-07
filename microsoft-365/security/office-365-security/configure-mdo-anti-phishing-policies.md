---
title: Anti-phishingbeleid configureren in Microsoft Defender voor Office 365
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
description: Beheerders kunnen leren hoe ze geavanceerde anti-phishingbeleidsregels kunnen maken, wijzigen en verwijderen die beschikbaar zijn in organisaties met Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8cbe517ef2a702e3e4fd7f6af4ee1d7ed1dd13d2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789133"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a3f33-103">Anti-phishingbeleid configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a3f33-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3f33-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="a3f33-104">**Applies to**</span></span>
- [<span data-ttu-id="a3f33-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a3f33-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a3f33-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3f33-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a3f33-107">Anti-phishingbeleid in [Microsoft Defender voor Office 365](defender-for-office-365.md) kan uw organisatie helpen beschermen tegen kwaadaardige phishingaanvallen op basis van imitaties en andere soorten phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="a3f33-108">Zie [Anti-phishingbeveiliging](anti-phishing-protection.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in Exchange Online Protection (EOP) en anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3f33-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="a3f33-109">Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="a3f33-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="a3f33-110">Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a3f33-111">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a3f33-112">U kunt anti-phishingbeleid configureren in Defender voor Office 365 in het Microsoft 365 beveiligingscentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3f33-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="a3f33-113">Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor informatie over het configureren van de meer beperkte anti-phishingbeleidsregels die beschikbaar zijn in Exchange Online Protection (dat wil zeggen organisaties zonder Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="a3f33-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="a3f33-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="a3f33-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="a3f33-115">**Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="a3f33-116">**De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="a3f33-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid in het beveiligingscentrum beheert:</span><span class="sxs-lookup"><span data-stu-id="a3f33-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="a3f33-118">Wanneer u een beleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="a3f33-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a3f33-119">Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="a3f33-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="a3f33-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="a3f33-121">Wanneer u een beleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="a3f33-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="a3f33-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a3f33-123">Zie de sectie Gebruik Exchange Online PowerShell voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="a3f33-124">Elke Defender voor Office 365 organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="a3f33-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="a3f33-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a3f33-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="a3f33-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a3f33-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="a3f33-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="a3f33-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a3f33-129">Als u de effectiviteit van anti-phishingbeveiliging in Defender voor Office 365 wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a3f33-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3f33-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="a3f33-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3f33-131">U opent het beveiligingscentrum in <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="a3f33-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a3f33-132">Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="a3f33-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="a3f33-133">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3f33-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a3f33-134">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a3f33-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a3f33-135">Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a3f33-136">Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="a3f33-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="a3f33-137">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a3f33-138">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="a3f33-138">**Notes**:</span></span>

  - <span data-ttu-id="a3f33-139">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3f33-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a3f33-140">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a3f33-141">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a3f33-142">Voor onze aanbevolen instellingen voor anti-phishingbeleid in Defender voor Office 365, zie [Anti-phishingbeleid in Defender voor Office 365 instellingen.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="a3f33-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="a3f33-143">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="a3f33-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="a3f33-144">Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="a3f33-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="a3f33-145">Gebruik het beveiligingscentrum om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="a3f33-145">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="a3f33-146">Als u een aangepast anti-phishingbeleid maakt in het beveiligingscentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="a3f33-146">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a3f33-147">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-147">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-148">Klik op **de pagina Anti-phishing** op ![ Pictogram Maken ](../../media/m365-cc-sc-create-icon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="a3f33-149">De wizard van het beleid wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="a3f33-149">The policy wizard opens.</span></span> <span data-ttu-id="a3f33-150">Configureer **deze instellingen op de** pagina Beleidsnaam:</span><span class="sxs-lookup"><span data-stu-id="a3f33-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="a3f33-151">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="a3f33-152">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a3f33-153">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a3f33-154">Zoek op de pagina **Gebruikers, groepen en domeinen** die wordt weergegeven, de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):</span><span class="sxs-lookup"><span data-stu-id="a3f33-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="a3f33-155">**Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a3f33-156">**Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="a3f33-157">**Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="a3f33-158">Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="a3f33-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a3f33-159">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a3f33-160">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-160">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a3f33-162">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="a3f33-162">next to the value.</span></span>

   <span data-ttu-id="a3f33-163">Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="a3f33-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a3f33-164">Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="a3f33-165">Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a3f33-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a3f33-166">Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a3f33-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="a3f33-167">**Deze gebruikers, groepen en domeinen uitsluiten**: als u uitzonderingen wilt toevoegen voor de interne geadresseerden op wie het beleid van toepassing is (uitzonderingen op ontvangers), selecteert u deze optie en configureert u de uitzonderingen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a3f33-168">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="a3f33-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a3f33-169">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a3f33-170">Configureer de volgende **instellingen & op de** pagina Phishing-beveiliging die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3f33-171">**Drempelwaarde voor** phishing-e-mail: gebruik de schuifregelaar om een van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="a3f33-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="a3f33-172">**1 - Standaard** (Dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="a3f33-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="a3f33-173">**2 - Agressief**</span><span class="sxs-lookup"><span data-stu-id="a3f33-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="a3f33-174">**3 - Agressiever**</span><span class="sxs-lookup"><span data-stu-id="a3f33-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="a3f33-175">**4 - Meest agressief**</span><span class="sxs-lookup"><span data-stu-id="a3f33-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="a3f33-176">Zie Advanced [phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="a3f33-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="a3f33-177">**Imitatie:** deze instellingen zijn een voorwaarde voor het beleid dat specifieke afzenders identificeert die moeten zoeken (afzonderlijk of per domein) in het Van-adres van binnenkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="a3f33-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="a3f33-178">Zie Instellingen voor imitatie [in anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3f33-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="a3f33-179">In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers opgeven (e-mailadressen van afzenders).</span><span class="sxs-lookup"><span data-stu-id="a3f33-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="a3f33-180">U kunt niet dezelfde beveiligde gebruiker opgeven in meerdere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="a3f33-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="a3f33-181">Gebruikersbeveiliging werkt niet als de afzender en geadresseerde eerder via e-mail hebben gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="a3f33-182">Als de afzender en geadresseerde nooit via e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.</span><span class="sxs-lookup"><span data-stu-id="a3f33-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="a3f33-183">**Gebruikers inschakelen om te beveiligen:** de standaardwaarde is uitgeschakeld (niet geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="a3f33-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="a3f33-184">Schakel het selectievakje in en klik vervolgens op de koppeling **Afzender(nn) beheren (nn)** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="a3f33-185">Ga als volgt te werk in het fly-out Afzenders voor **imitatiebeveiliging** beheren dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="a3f33-186">**Interne afzenders:** Klik ![ op Intern pictogram Toevoegen Selecteer ](../../media/m365-cc-sc-add-internal-icon.png) **intern**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="a3f33-187">Klik in het fly-out Interne **afzenders** toevoegen dat wordt weergegeven in het vak en selecteer een interne gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a3f33-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="a3f33-188">U kunt de lijst filteren door de gebruiker te typen en vervolgens de gebruiker te selecteren in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="a3f33-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="a3f33-189">U kunt de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="a3f33-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="a3f33-190">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a3f33-191">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-191">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a3f33-193">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="a3f33-193">next to the value.</span></span>

         <span data-ttu-id="a3f33-194">Wanneer u klaar bent, klikt u op **Toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="a3f33-195">**Externe afzenders:** Klik ![ op Extern pictogram Toevoegen Selecteer ](../../media/m365-cc-sc-create-icon.png) **extern**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="a3f33-196">Voer in het flyout Externe **afzenders** toevoegen dat  wordt weergegeven, een weergavenaam in het vak Een naam toevoegen en een e-mailadres in het vak Een **vaild-e-mail** toevoegen in en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="a3f33-197">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a3f33-198">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-198">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a3f33-200">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="a3f33-200">next to the value.</span></span>

         <span data-ttu-id="a3f33-201">Wanneer u klaar bent, klikt u op **Toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="a3f33-202">Terug in de **flyout Afzenders beheren** voor imitatie, kunt u items verwijderen door een of meer items in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a3f33-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="a3f33-203">U kunt zoeken naar items met het ![ zoekpictogram ](../../media/m365-cc-sc-create-icon.png) **Zoeken.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="a3f33-204">Nadat u ten minste één item hebt geselecteerd, wordt het pictogram Geselecteerde gebruikers verwijderen pictogram Geselecteerde gebruikers verwijderen weergegeven, waarmee u de geselecteerde items ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png)  kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="a3f33-205">Klik op **Gereed** als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="a3f33-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="a3f33-206">**Domeinen beveiligen:** de standaardwaarde is uitgeschakeld (niet geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="a3f33-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="a3f33-207">Als u deze optie wilt in- of uitschakelen, selecteert u het selectievakje en configureert u een of beide van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="a3f33-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="a3f33-208">**Neem de domeinen op die ik bezit:** schakel het selectievakje in om deze instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="a3f33-209">Als u de domeinen wilt weergeven die u bezit, klikt u **op Mijn domeinen weergeven.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="a3f33-210">**Aangepaste domeinen opnemen:** Als u deze instelling wilt in- of uit- zetten, selecteert u het selectievakje en klikt u vervolgens op de koppeling Aangepaste **domein(nn) beheren (nn)** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="a3f33-211">Klik in het flyout Manage **custom domains for impersonation protection** flyout that appears, click Add ![ domains icon Add ](../../media/m365-cc-sc-create-icon.png) **domains**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="a3f33-212">Klik in **het flyout** Aangepaste domeinen toevoegen  dat wordt weergegeven in het vak Domein, voer een waarde in en druk vervolgens op Enter of selecteer de waarde die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="a3f33-213">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a3f33-214">Als u een bestaande waarde wilt verwijderen, klikt u op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="a3f33-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="a3f33-215">Wanneer u klaar bent, klikt u op **Domeinen toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="a3f33-216">U kunt maximaal 50 domeinen hebben in alle anti-phishingbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="a3f33-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="a3f33-217">Terug in de flyout Aangepaste domeinen beheren voor **imitatie,** kunt u items verwijderen door een of meer items uit de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a3f33-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="a3f33-218">U kunt zoeken naar items met het ![ zoekpictogram ](../../media/m365-cc-sc-create-icon.png) **Zoeken.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="a3f33-219">Nadat u ten minste één item hebt geselecteerd, wordt het pictogram Verwijderen weergegeven, waarmee u de geselecteerde items ![ ](../../media/m365-cc-sc-delete-icon.png)  kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-219">After you select at least one entry, the ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="a3f33-220">**Vertrouwde afzenders** en domeinen toevoegen: : Geef uitzonderingen op voor imitatiebeveiliging voor het beleid door op Vertrouwde **afzender(s) en domein(s) beheren (nn) te klikken.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="a3f33-221">Configureer de volgende instellingen in het flyout Manage **custom domains for impersonation protection** flyout that appears:</span><span class="sxs-lookup"><span data-stu-id="a3f33-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="a3f33-222">**Afzenders:** controleer of het tabblad **Afzender** is geselecteerd en klik op ![ Pictogram Afzenders ](../../media/m365-cc-sc-create-icon.png) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="a3f33-223">Voer in het fly-out Vertrouwde **afzenders** toevoegen in het vak een e-mailadres in en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="a3f33-224">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a3f33-225">Als u een bestaand item wilt verwijderen, klikt ![ u op Pictogram verwijderen voor het ](../../media/m365-cc-sc-close-icon.png) item.</span><span class="sxs-lookup"><span data-stu-id="a3f33-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="a3f33-226">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="a3f33-227">**Domeinen:** Selecteer het tabblad **Domein** en klik ![ op Pictogram Domeinen ](../../media/m365-cc-sc-create-icon.png) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="a3f33-228">Klik in **het** fly-out Vertrouwde domeinen toevoegen  dat wordt weergegeven in het vak Domein, voer een waarde in en druk vervolgens op Enter of selecteer de waarde die onder het vak wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="a3f33-229">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a3f33-230">Als u een bestaande waarde wilt verwijderen, klikt u op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="a3f33-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="a3f33-231">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="a3f33-232">In het **flyout** Aangepaste domeinen beheren voor imitatie kunt u items  verwijderen uit de tabbladen **Afzender** en Domein door een of meer items in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a3f33-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="a3f33-233">U kunt zoeken naar items met het ![ zoekpictogram ](../../media/m365-cc-sc-create-icon.png) **Zoeken.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="a3f33-234">Nadat u ten minste één item hebt geselecteerd, wordt **het** pictogram Verwijderen weergegeven, waarmee u de geselecteerde items kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="a3f33-235">Klik op **Gereed** als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="a3f33-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="a3f33-236">**Postvakintelligentie** inschakelen: de standaardwaarde is ingeschakeld (geselecteerd) en u wordt aangeraden deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="a3f33-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="a3f33-237">Schakel het selectievakje uit om het uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="a3f33-238">**Beveiliging van imitatie op basis van intelligentie inschakelen:** deze instelling is alleen beschikbaar als **Postvakintelligentie** inschakelen is ingeschakeld (geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="a3f33-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="a3f33-239">Met deze instelling kan postvakinformatie actie ondernemen voor berichten die worden geïdentificeerd als imitatiepogingen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="a3f33-240">U geeft de actie op die u moet ondernemen in de instelling Als **postvakintelligentie** een instelling voor een nagebootsde gebruiker op de volgende pagina detecteert.</span><span class="sxs-lookup"><span data-stu-id="a3f33-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="a3f33-241">U wordt aangeraden deze instelling in te stellen door het selectievakje in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="a3f33-242">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="a3f33-243">**Spoof:** Gebruik in deze sectie het selectievakje **Spoof intelligence in-** of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="a3f33-244">De standaardwaarde is ingeschakeld (geselecteerd) en u wordt aangeraden deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="a3f33-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="a3f33-245">U geeft de actie op om berichten van geblokkeerde vervalste afzenders op te nemen in de instelling Als bericht wordt gedetecteerd als **spoof** op de volgende pagina.</span><span class="sxs-lookup"><span data-stu-id="a3f33-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="a3f33-246">Schakel het selectievakje uit om spoofinformatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a3f33-247">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a3f33-248">Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="a3f33-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="a3f33-249">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a3f33-250">Configureer de volgende instellingen op de pagina **Acties** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3f33-251">**Berichtacties:** Configureer de volgende acties in deze sectie:</span><span class="sxs-lookup"><span data-stu-id="a3f33-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="a3f33-252">**Als bericht wordt gedetecteerd als een nagebootsde gebruiker:** Deze instelling is alleen beschikbaar als u **Gebruikers inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="a3f33-253">Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten waarin de afzender een van de beveiligde gebruikers is die u op de vorige pagina hebt opgegeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="a3f33-254">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="a3f33-255">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a3f33-256">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="a3f33-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a3f33-257">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="a3f33-258">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="a3f33-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a3f33-259">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="a3f33-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a3f33-260">**Als het bericht wordt gedetecteerd** als een nagebootsd domein: Deze instelling is alleen beschikbaar als u **Domeinen inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="a3f33-261">Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten met het e-mailadres van de afzender in een van de beveiligde domeinen die u op de vorige pagina hebt opgegeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="a3f33-262">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="a3f33-263">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a3f33-264">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="a3f33-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a3f33-265">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="a3f33-266">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="a3f33-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a3f33-267">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="a3f33-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a3f33-268">**Als met postvakinformatie een** nagebootsde gebruiker wordt gedetecteerd: Deze instelling is alleen beschikbaar als u **Intelligentie inschakelen** voor imitatiebeveiliging op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="a3f33-269">Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten die zijn geïdentificeerd als imitatiepogingen door postvakinformatie:</span><span class="sxs-lookup"><span data-stu-id="a3f33-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="a3f33-270">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="a3f33-271">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a3f33-272">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="a3f33-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a3f33-273">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="a3f33-274">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="a3f33-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a3f33-275">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="a3f33-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a3f33-276">**Als bericht wordt gedetecteerd als spoof:** Deze instelling is alleen beschikbaar als u **Spoofinformatie inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a3f33-277">Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten van geblokkeerde vervalste afzenders:</span><span class="sxs-lookup"><span data-stu-id="a3f33-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="a3f33-278">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="a3f33-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a3f33-279">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="a3f33-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="a3f33-280">**Veiligheidstips & indicatoren**: De volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="a3f33-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="a3f33-281">**Gebruikers imiteren veiligheidstip:** deze instelling is alleen beschikbaar als u **Gebruikers inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-281">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="a3f33-282">**Domein nabootsing veiligheidstip:** deze instelling is alleen beschikbaar als u **Domeinen inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-282">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="a3f33-283">**Ongebruikelijke tekens voor gebruikers imiteren veiligheidstip** Deze instelling is alleen beschikbaar als u Gebruikers inschakelen voor **het beveiligen** of **inschakelen van** domeinen op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-283">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="a3f33-284">**Toon (?) voor niet-nautische afzenders** voor spoof: Deze instelling is alleen beschikbaar als u **Spoof intelligence** op de vorige pagina inschakelen hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-284">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a3f33-285">Hiermee voegt u een vraagteken toe aan de foto van de afzender in het vak Van  in Outlook als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="a3f33-285">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="a3f33-286">**Tag 'via' tonen:** deze instelling is alleen beschikbaar als u **Spoof intelligence inschakelen** op de vorige pagina hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-286">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a3f33-287">Hiermee voegt u een via-tag (chris@contoso.com via fabrikam.com) toe aan het Van-adres als deze verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-287">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="a3f33-288">De standaardwaarde is ingeschakeld (geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="a3f33-288">The default value is on (selected).</span></span> <span data-ttu-id="a3f33-289">Schakel het selectievakje uit om het uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-289">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="a3f33-290">Op dit moment is de taginstelling **'via'** tonen niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="a3f33-290">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="a3f33-291">Als u de taginstelling **'via'** tonen niet  hebt, worden het vraagteken en de via-tag beide gecontroleerd door de instelling Tonen **(?)** voor niet-genauteerde afzenders voor spoofinstelling in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="a3f33-292">Schakel het selectievakje in om een instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="a3f33-293">Schakel het selectievakje uit om het uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="a3f33-294">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a3f33-295">Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="a3f33-296">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-296">You can select **Edit** in each section to modify the settings within the section.</span></span>

   <span data-ttu-id="a3f33-297">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-297">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="a3f33-298">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-298">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="a3f33-299">Het beveiligingscentrum gebruiken om anti-phishingbeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="a3f33-299">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="a3f33-300">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-300">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-301">Op de **pagina Anti-phishing** worden de volgende eigenschappen weergegeven in de lijst met anti-phishingbeleidsregels:</span><span class="sxs-lookup"><span data-stu-id="a3f33-301">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="a3f33-302">**Naam**</span><span class="sxs-lookup"><span data-stu-id="a3f33-302">**Name**</span></span>
   - <span data-ttu-id="a3f33-303">**Status**</span><span class="sxs-lookup"><span data-stu-id="a3f33-303">**Status**</span></span>
   - <span data-ttu-id="a3f33-304">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="a3f33-304">**Priority**</span></span>
   - <span data-ttu-id="a3f33-305">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="a3f33-305">**Last modified**</span></span>

3. <span data-ttu-id="a3f33-306">Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="a3f33-306">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="a3f33-307">Gebruik het beveiligingscentrum om anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a3f33-307">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="a3f33-308">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-308">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-309">Selecteer op **de pagina Anti-phishing** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-309">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a3f33-310">U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-310">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a3f33-311">Zie Het beveiligingscentrum gebruiken om [anti-phishingbeleid](#use-the-security-center-to-create-anti-phishing-policies) te maken eerder in dit artikel voor meer informatie over de instellingen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-311">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="a3f33-312">Voor het standaard anti-phishingbeleid is de sectie **Gebruikers,** groepen en domeinen niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-312">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="a3f33-313">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-313">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="a3f33-314">Aangepaste anti-phishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a3f33-314">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="a3f33-315">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-315">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="a3f33-316">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-316">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-317">Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-317">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a3f33-318">Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="a3f33-318">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="a3f33-319">**Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="a3f33-319">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="a3f33-320">**Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-320">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="a3f33-321">Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-321">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="a3f33-322">Klik in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-322">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="a3f33-323">Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-323">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="a3f33-324">De prioriteit instellen van aangepast anti-phishingbeleid</span><span class="sxs-lookup"><span data-stu-id="a3f33-324">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="a3f33-325">Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="a3f33-325">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a3f33-326">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="a3f33-326">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a3f33-327">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="a3f33-327">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a3f33-328">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in het beveiligingscentrum).</span><span class="sxs-lookup"><span data-stu-id="a3f33-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="a3f33-329">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="a3f33-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="a3f33-330">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="a3f33-330">**Notes**:</span></span>

- <span data-ttu-id="a3f33-331">In het beveiligingscentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a3f33-331">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="a3f33-332">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="a3f33-332">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="a3f33-333">Anti-phishingbeleid wordt verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="a3f33-333">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a3f33-334">Het standaard anti-phishingbeleid heeft de prioriteitswaarde **Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-334">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="a3f33-335">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-335">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-336">Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-336">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a3f33-337">Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="a3f33-337">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="a3f33-338">Het anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a3f33-338">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="a3f33-339">Het anti-phishingbeleid met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a3f33-339">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="a3f33-340">Als u drie of meer anti-phishingbeleidsregels hebt, hebben beleidsregels tussen  de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar. </span><span class="sxs-lookup"><span data-stu-id="a3f33-340">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="a3f33-341">Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-341">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="a3f33-342">Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-342">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="a3f33-343">Gebruik het beveiligingscentrum om aangepaste anti-phishingbeleidsregels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-343">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="a3f33-344">Wanneer u het beveiligingscentrum gebruikt om een aangepast anti-phishingbeleid te verwijderen, worden de anti-phish-regel en het bijbehorende anti-phish-beleid beide verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-344">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="a3f33-345">U kunt het standaard anti-phishingbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-345">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="a3f33-346">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-346">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3f33-347">Selecteer een aangepast beleid in de lijst door op de naam van het beleid te klikken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-347">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="a3f33-348">Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-348">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="a3f33-349">Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-349">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="a3f33-350">Gebruik Exchange Online PowerShell om anti-phishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="a3f33-350">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="a3f33-351">Zoals eerder beschreven, bestaat een antispambeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="a3f33-351">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="a3f33-352">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="a3f33-352">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="a3f33-353">U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-353">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="a3f33-354">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-354">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a3f33-355">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="a3f33-355">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="a3f33-356">Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-356">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="a3f33-357">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="a3f33-357">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="a3f33-358">Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="a3f33-358">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a3f33-359">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-359">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="a3f33-360">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="a3f33-360">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="a3f33-361">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="a3f33-361">**Notes**:</span></span>

- <span data-ttu-id="a3f33-362">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-362">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="a3f33-363">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="a3f33-363">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="a3f33-364">U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het beveiligingscentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="a3f33-364">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
  - <span data-ttu-id="a3f33-365">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a3f33-365">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="a3f33-366">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a3f33-366">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="a3f33-367">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligingscentrum als u het beleid aan een anti-phish-regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="a3f33-367">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="a3f33-368">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="a3f33-368">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="a3f33-369">Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-369">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="a3f33-370">In dit voorbeeld wordt anti-phishbeleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="a3f33-370">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="a3f33-371">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="a3f33-371">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="a3f33-372">De beschrijving is: Het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="a3f33-372">The description is: Research department policy.</span></span>
- <span data-ttu-id="a3f33-373">Hiermee wordt de beveiliging van organisatiedomeinen voor alle geaccepteerde domeinen en de bescherming van gerichte domeinen voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="a3f33-373">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="a3f33-374">Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker die u wilt beschermen tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="a3f33-374">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="a3f33-375">Hiermee schakelt u postvakintelligentie in.</span><span class="sxs-lookup"><span data-stu-id="a3f33-375">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="a3f33-376">Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.</span><span class="sxs-lookup"><span data-stu-id="a3f33-376">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="a3f33-377">Hiermee schakelt u veiligheidstips in.</span><span class="sxs-lookup"><span data-stu-id="a3f33-377">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="a3f33-378">Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-378">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="a3f33-379">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="a3f33-379">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="a3f33-380">Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-380">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a3f33-381">In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="a3f33-381">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="a3f33-382">De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="a3f33-382">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="a3f33-383">De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="a3f33-383">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="a3f33-384">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a3f33-384">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="a3f33-385">Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-385">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="a3f33-386">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="a3f33-386">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="a3f33-387">Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="a3f33-387">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a3f33-388">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-388">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="a3f33-389">Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="a3f33-389">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="a3f33-390">Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-390">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="a3f33-391">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="a3f33-391">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="a3f33-392">Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-392">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a3f33-393">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-393">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="a3f33-394">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="a3f33-394">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="a3f33-395">Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="a3f33-395">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="a3f33-396">Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-396">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="a3f33-397">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a3f33-397">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="a3f33-398">Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-398">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="a3f33-399">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3f33-399">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="a3f33-400">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="a3f33-400">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a3f33-401">Wanneer u de naam van een anti-phishingbeleid in het beveiligingscentrum wijzigt, wijzigt u alleen de naam van de anti-phish-regel. </span><span class="sxs-lookup"><span data-stu-id="a3f33-401">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="a3f33-402">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-402">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a3f33-403">Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-403">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="a3f33-404">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a3f33-404">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="a3f33-405">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-405">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a3f33-406">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="a3f33-406">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="a3f33-407">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="a3f33-407">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="a3f33-408">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-408">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="a3f33-409">Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-409">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a3f33-410">Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-410">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="a3f33-411">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="a3f33-411">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="a3f33-412">Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a3f33-412">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="a3f33-413">U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="a3f33-413">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="a3f33-414">Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-414">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="a3f33-415">In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a3f33-415">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3f33-416">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a3f33-416">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3f33-417">Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-417">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="a3f33-418">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="a3f33-418">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="a3f33-419">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="a3f33-419">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a3f33-420">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="a3f33-420">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a3f33-421">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a3f33-421">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a3f33-422">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="a3f33-422">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a3f33-423">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="a3f33-423">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a3f33-424">Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-424">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a3f33-425">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="a3f33-425">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a3f33-426">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="a3f33-426">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a3f33-427">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="a3f33-427">**Notes**:</span></span>

- <span data-ttu-id="a3f33-428">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-428">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="a3f33-429">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-429">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="a3f33-430">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-430">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="a3f33-431">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-431">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="a3f33-432">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-432">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a3f33-433">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-433">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a3f33-434">Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-434">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="a3f33-435">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="a3f33-435">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="a3f33-436">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-436">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="a3f33-437">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a3f33-437">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="a3f33-438">In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a3f33-438">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3f33-439">Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="a3f33-439">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a3f33-440">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="a3f33-440">How do you know these procedures worked?</span></span>

<span data-ttu-id="a3f33-441">Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in Defender voor Office 365, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="a3f33-441">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="a3f33-442">Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3f33-442">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="a3f33-443">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="a3f33-443">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a3f33-444">Als u meer details wilt weergeven, selecteert u het beleid in de lijst door op de naam te klikken en de details weer te geven in de flyout die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a3f33-444">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="a3f33-445">Vervang Exchange Online PowerShell door de naam van het beleid of de regel en voer de volgende opdracht uit \<Name\> en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="a3f33-445">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
