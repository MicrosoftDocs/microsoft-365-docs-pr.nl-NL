---
title: Spamfilterbeleid configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Beheerders kunnen het antispambeleid in Exchange Online Protection (EOP) bekijken, maken, wijzigen en verwijderen.
ms.openlocfilehash: c129ca73da516a5b4c420136abf0b5068e19e195
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204861"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="12276-103">Antispambeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="12276-103">Configure anti-spam policies in EOP</span></span>

<span data-ttu-id="12276-104">In Microsoft 365-organisaties met postvakken in Exchange Online of standalone EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, zijn binnenkomende e-mailberichten automatisch tegen spam beschermd door EOP.</span><span class="sxs-lookup"><span data-stu-id="12276-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="12276-105">EOP gebruikt antispambeleid (ook wel bekend als spamfilterbeleid of inhoudsfilterbeleid) als onderdeel van de algehele bescherming van uw bedrijf tegen spam.</span><span class="sxs-lookup"><span data-stu-id="12276-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="12276-106">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12276-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="12276-107">Beheerders kunnen het standaardbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="12276-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="12276-108">Voor grotere nauwkeurigheid kunt u ook aangepast antispambeleid maken dat wordt toegepast op specifieke gebruikers, groepen of domeinen binnen uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="12276-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="12276-109">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="12276-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="12276-110">U kunt antispambeleid configureren in het Beveiligings- en compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="12276-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="12276-111">Antispambeleid in het Beveiligings- en compliancecentrum versus PowerShell</span><span class="sxs-lookup"><span data-stu-id="12276-111">Anti-spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="12276-112">De basiselementen van antispambeleid in EOP zijn: </span><span class="sxs-lookup"><span data-stu-id="12276-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="12276-113">**Het spamfilterbeleid**: omschrijft de acties voor spamfilterbeoordelingen en de meldingsopties.</span><span class="sxs-lookup"><span data-stu-id="12276-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="12276-114">**De spamfilterregel**: omschrijft de prioriteits- en geadresseerdenfilters (waarop het beleid van toepassing is) voor spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="12276-115">Het verschil tussen deze twee elementen is niet overduidelijk wanneer u antispambeleid beheert in het Beveiligings- en compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="12276-115">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="12276-116">Wanneer u antispambeleid maakt in het Beveiligings- en compliancecentrum maakt u in feite tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="12276-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="12276-117">Wanneer u antispambeleid wijzigt in het Beveiligings- en compliancecentrum wordt de spamfilterregel gewijzigd door instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters.</span><span class="sxs-lookup"><span data-stu-id="12276-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="12276-118">Alle andere instellingen wijzigen het bijbehorende spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="12276-119">Wanneer u antispambeleid verwijdert uit het Beveiligings- en compliancecentrum worden de spamfilterregel en het bijbehorende spamfilterbeleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="12276-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="12276-120">In Exchange Online PowerShell of standalone EOP PowerShell is het verschil tussen spamfilterbeleid en spamfilterregels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="12276-120">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="12276-121">U beheert spamfilterbeleid door de cmdlets **\*-HostedContentFilterPolicy** te gebruiken en u beheert spamfilterregels door de cmdlets **\*-HostedContentFilterRule** te gebruiken. </span><span class="sxs-lookup"><span data-stu-id="12276-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="12276-122">In PowerShell maakt u eerst het spamfilterbeleid en vervolgens maakt u de spamfilterregel die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="12276-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="12276-123">In PowerShell wijzigt u de instellingen in het spamfilterbeleid en de spamfilterregel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="12276-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="12276-124">Wanneer u spamfilterbeleid verwijdert uit PowerShell, wordt de bijbehorende spamfilterregel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="12276-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="12276-125">Standaardantispambeleid</span><span class="sxs-lookup"><span data-stu-id="12276-125">Default anti-spam policy</span></span>

<span data-ttu-id="12276-126">Elk bedrijf heeft een ingebouwd antispambeleid met de naam Standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="12276-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="12276-127">Het spamfilterbeleid met de naam Standaard wordt toegepast op alle geadresseerden in het bedrijf, ook als is er geen spamfilterregel (geadresseerdenregels) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="12276-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="12276-128">Het beleid met de naam Standaard heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="12276-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="12276-129">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="12276-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="12276-130">Het beleid met de naam Standaard is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="12276-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="12276-131">Om de effectiviteit van spamfilters te verhogen, kunt u aangepast antispambeleid maken met strengere instellingen dat wordt toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="12276-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12276-132">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="12276-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="12276-133">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="12276-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="12276-134">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="12276-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="12276-135">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12276-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="12276-136">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12276-136">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="12276-137">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="12276-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="12276-138">U moet lid zijn van een van de volgende rolgroepen om een antispambeleid toe te voegen, te wijzigen en te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="12276-138">To add, modify, and delete anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="12276-139">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="12276-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="12276-140">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="12276-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="12276-141">Voor alleen-lezentoegang tot het antispambeleid moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="12276-141">For read-only access to anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="12276-142">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="12276-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="12276-143">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="12276-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="12276-144">Zie [EOP-antispambeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings) voor onze aanbevolen instellingen voor beleidsinstellingen voor antimalwarebeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-144">For our recommended settings for anti-malware policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="12276-145">Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="12276-145">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="12276-146">Wanneer u antispambeleid maakt in het Beveiligings- en compliancecentrum worden tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="12276-146">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="12276-147">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-148">Kies op de pagina **Antispaminstellingen** op **Beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="12276-148">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="12276-149">Configureer in het deelvenster **Nieuw spamfilterbeleid** dat wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-149">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="12276-150">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="12276-150">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="12276-151">U mag de volgende tekens niet gebruiken: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span><span class="sxs-lookup"><span data-stu-id="12276-151">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="12276-152">Als u eerder al antispambeleid hebt gemaakt in het Exchange-beheercentrum (EAC) dat deze tekens bevat, moet u het antispambeleid in PowerShell hernoemen.</span><span class="sxs-lookup"><span data-stu-id="12276-152">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="12276-153">Zie de sectie [PowerShell gebruiken om spamfilterregels te wijzigen](#use-powershell-to-modify-spam-filter-rules) verderop in dit artikel voor instructies.</span><span class="sxs-lookup"><span data-stu-id="12276-153">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="12276-154">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="12276-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="12276-155">(Optioneel) Vouw de sectie **Spam- en bulkbewerkingen** uit en controleer of configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-155">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="12276-156">**Selecteer de actie die moet worden uitgevoerd voor binnenkomende spam en bulk-e-mail**: selecteer of bekijk de actie die moet worden uitgevoerd op berichten op basis van de volgende spamfilterbeoordelingen:</span><span class="sxs-lookup"><span data-stu-id="12276-156">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="12276-157">**Spam**</span><span class="sxs-lookup"><span data-stu-id="12276-157">**Spam**</span></span>
     - <span data-ttu-id="12276-158">**Hoogstwaarschijnlijk spam**</span><span class="sxs-lookup"><span data-stu-id="12276-158">**High confidence spam**</span></span>
     - <span data-ttu-id="12276-159">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-159">**Phishing email**</span></span>
     - <span data-ttu-id="12276-160">**Hoogstwaarschijnlijk Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-160">**High confidence phishing email**</span></span>
     - <span data-ttu-id="12276-161">**Bulk-e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-161">**Bulk email**</span></span>

     <span data-ttu-id="12276-162">De beschikbare acties voor spamfilterbeoordelingen worden beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="12276-162">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="12276-163">Een vinkje (</span><span class="sxs-lookup"><span data-stu-id="12276-163">A check mark (</span></span> ![vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="12276-165">) geeft aan dat de actie beschikbaar is (niet alle acties zijn beschikbaar voor alle spamfilterbeoordelingen).</span><span class="sxs-lookup"><span data-stu-id="12276-165">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="12276-166">Een asterisk (<sup>\*</sup>) na het vinkje geeft de standaardactie aan voor de spamfilterbeoordeling. </span><span class="sxs-lookup"><span data-stu-id="12276-166">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||<span data-ttu-id="12276-167">**Spam**</span><span class="sxs-lookup"><span data-stu-id="12276-167">**Spam**</span></span>|<span data-ttu-id="12276-168">**Hoogst<br/>waarschijnlijk<br/>Spam**</span><span class="sxs-lookup"><span data-stu-id="12276-168">**High<br/>confidence<br/>spam**</span></span>|<span data-ttu-id="12276-169">**Phishing-<br/>e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-169">**Phishing<br/>email**</span></span>|<span data-ttu-id="12276-170">**Hoogst<br/>waarschijnlijk <br/>Phishing<br/>-e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-170">**High<br/>confidence<br/>phishing<br/>email**</span></span>|<span data-ttu-id="12276-171">**Bulk-<br/>e-mail**</span><span class="sxs-lookup"><span data-stu-id="12276-171">**Bulk<br/>email**</span></span>|
    |<span data-ttu-id="12276-172">**Bericht verplaatsen naar de map Ongewenste e-mail**: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="12276-172">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="12276-173">![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12276-173">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="12276-174">![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12276-174">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="12276-177">![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12276-177">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="12276-178">**X-kop toevoegen**: hiermee wordt een X-kop toegevoegd aan de berichtkop en het bericht bezorgd in het postvak.</span><span class="sxs-lookup"><span data-stu-id="12276-178">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="12276-179">U voert de veldnaam (niet de waarde) van de X-kop later in het vak **Deze X-koptekst toevoegen** in. </span><span class="sxs-lookup"><span data-stu-id="12276-179">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="12276-180">Bij de beoordelingen **Spam** en **Hoogstwaarschijnlijk spam** wordt het bericht verplaatst nar de map Ongewenste e-mail.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="12276-180">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="12276-184">![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12276-184">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="12276-185">**Onderwerpregel vooraan uitbreiden met tekst**: hiermee wordt tekst toegevoegd aan het begin van de onderwerpregel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="12276-185">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="12276-186">Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="12276-186">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="12276-187">U voert de tekst later in het vak **Voeg deze tekst toe vooraan de onderwerpregel** in.</span><span class="sxs-lookup"><span data-stu-id="12276-187">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="12276-192">**Bericht naar e-mailadres omleiden**: hiermee wordt het bericht omgeleid naar andere geadresseerden in plaats van de beoogde geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="12276-192">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="12276-193">U geeft de geadresseerden later op in het vak **Omleiden naar dit e-mailadres**.</span><span class="sxs-lookup"><span data-stu-id="12276-193">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="12276-199">**Bericht verwijderen**: hiermee wordt het volledige bericht verwijderd, inclusief alle bijlagen.</span><span class="sxs-lookup"><span data-stu-id="12276-199">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="12276-204">**Bericht in quarantaine**: hiermee wordt het bericht in quarantaine geplaatst in plaats van verzonden naar de beoogde geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="12276-204">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="12276-205">U geeft later in het vak **Quarantaine** aan hoelang het bericht in quarantaine moet blijven.</span><span class="sxs-lookup"><span data-stu-id="12276-205">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="12276-208">![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12276-208">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="12276-211">**Geen actie**</span><span class="sxs-lookup"><span data-stu-id="12276-211">**No action**</span></span>|||||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <span data-ttu-id="12276-213"><sup>1</sup> In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel Ongewenste e-mail is ingeschakeld voor het postvak (standaard is die regel ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="12276-213"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="12276-214">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12276-214">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span><br/><span data-ttu-id="12276-215">In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="12276-215">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="12276-216">Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. </span><span class="sxs-lookup"><span data-stu-id="12276-216">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span><br/><br/><span data-ttu-id="12276-217"><sup>2</sup> U kunt deze waarde gebruiken als voorwaarde in e-mailstroomregels (ook wel transportregels) om het bericht te filteren of om te leiden.</span><span class="sxs-lookup"><span data-stu-id="12276-217"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="12276-218">**De drempelwaarde selecteren**: hiermee wordt het bulkklachtniveau (BCL) van een bericht aangegeven dat de gespecificeerde actie activeert voor de **Bulk-e-mail**-spamfilterbeoordeling (groter dan de opgegeven waarde, niet groter dan of gelijk aan).</span><span class="sxs-lookup"><span data-stu-id="12276-218">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="12276-219">Een hogere waarde geeft aan dat het bericht minder wenselijk is (grotere kans dat het bericht spam is).</span><span class="sxs-lookup"><span data-stu-id="12276-219">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="12276-220">De standaardwaarde is 7.</span><span class="sxs-lookup"><span data-stu-id="12276-220">The default value is 7.</span></span> <span data-ttu-id="12276-221">Zie [Bulkklachtniveau (BCL) in EOP](bulk-complaint-level-values.md) en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12276-221">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="12276-222">Standaard is de enige PowerShell-instelling _MarkAsSpamBulkMail_ `On` in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-222">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="12276-223">Deze instelling is van grote invloed op de resultaten van een **Bulk-e-mail**-filterbeoordeling:</span><span class="sxs-lookup"><span data-stu-id="12276-223">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="12276-224">**_MarkAsSpamBulkMail_ is ingeschakeld**: een BCL dat groter is dan de drempelwaarde wordt geconverteerd naar een SCL 6, wat overeenkomt met een filterbeoordeling van **Spam** en de actie voor de **Bulk-e-mail**-filterbeoordeling wordt toegepast op het bericht.</span><span class="sxs-lookup"><span data-stu-id="12276-224">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="12276-225">**_MarkAsSpamBulkMail_ is uitgeschakeld**: het bericht krijgt het stempel BCL, maar er wordt _geen actie_ uitgevoerd voor een **Bulk-e-mail**-filterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-225">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="12276-226">Het gevolg is dat de BCL-drempelwaarde en de actie voor de **Bulk-e-mail**-filterbeoordeling niet relevant zijn.</span><span class="sxs-lookup"><span data-stu-id="12276-226">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="12276-227">**Quarantaine**: geeft aan hoe lang het bericht in quarantaine moet worden gehouden als u de actie **Bericht in quarantaine plaatsen** hebt geselecteerd voor een spamfilterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-227">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="12276-228">Na het verlopen van de periode wordt het bericht verwijderd.</span><span class="sxs-lookup"><span data-stu-id="12276-228">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="12276-229">De standaardwaarde is 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="12276-229">The default value is 30 days.</span></span> <span data-ttu-id="12276-230">Een geldige waarde ligt tussen de 1 en 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="12276-230">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="12276-231">Zie de volgende artikelen voor meer informatie over quarantaine:</span><span class="sxs-lookup"><span data-stu-id="12276-231">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="12276-232">Berichten in quarantaine in EOP</span><span class="sxs-lookup"><span data-stu-id="12276-232">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="12276-233">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="12276-233">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="12276-234">Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP</span><span class="sxs-lookup"><span data-stu-id="12276-234">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="12276-235">**Deze X-koptekst toevoegen**: dit vak is alleen vereist en beschikbaar als u de actie **X-kop toevoegen** hebt geselecteerd voor een spamfilterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-235">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="12276-236">De waarde die u opgeeft, is de naam van het *kopveld* dat wordt toegevoegd aan de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="12276-236">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="12276-237">De kopveld*waarde* is altijd `This message appears to be spam`.</span><span class="sxs-lookup"><span data-stu-id="12276-237">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="12276-238">De maximumlengte is 255 tekens en de waarde kan geen spaties of dubbele punten (:) bevatten.</span><span class="sxs-lookup"><span data-stu-id="12276-238">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="12276-239">Als u bijvoorbeeld de waarde `X-This-is-my-custom-header` opgeeft, wordt de X-kop `X-This-is-my-custom-header: This message appears to be spam.` toegevoegd aan het bericht.</span><span class="sxs-lookup"><span data-stu-id="12276-239">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="12276-240">Als u een waarde opgeeft die spaties of dubbele punten (:) bevat, wordt de ingevoerde waarde genegeerd en wordt de standaard-X-kop (`X-This-Is-Spam: This message appears to be spam.`) aan het bericht toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="12276-240">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="12276-241">**Onderwerpregel vooraan uitbreiden met deze tekst**: dit vak is alleen vereist en beschikbaar als u de actie **Onderwerpregel vooraan uitbreiden met tekst** hebt geselecteerd voor een spamfilterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-241">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="12276-242">Voer de tekst in die moet worden toegevoegd aan het begin van de onderwerpregel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="12276-242">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="12276-243">**Bericht naar dit e-mailadres omleiden**: dit vak is alleen vereist en beschikbaar als u de actie **Bericht naar e-mailadres omleiden** hebt geselecteerd voor een spamfilterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-243">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="12276-244">Voer het e-mailadres in waarnaar u het bericht wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="12276-244">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="12276-245">U kunt meerdere waarden opgeven, gescheiden door puntkomma’s (;).</span><span class="sxs-lookup"><span data-stu-id="12276-245">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="12276-246">**Veiligheidstips**: standaard staan veiligheidstips ingeschakeld, maar u kunt ze uitschakelen door het selectievakje **Aan** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-246">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="12276-247">Zie [Veiligheidstips in e-mailberichten](safety-tips-in-office-365.md) voor meer informatie over veiligheidstips.</span><span class="sxs-lookup"><span data-stu-id="12276-247">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="12276-248">**Zero-hour auto purge**-instellingen: ZAP detecteert en voert actie uit op berichten die al zijn afgeleverd aan Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="12276-248">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="12276-249">Zie [Zero-hour auto purge - beveiliging tegen ongewenste e-mail en malware](zero-hour-auto-purge.md) voor meer informatie over ZAP.</span><span class="sxs-lookup"><span data-stu-id="12276-249">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="12276-250">**Spam ZAP**: ZAP is standaard ingeschakeld voor spamdetectie, maar u kunt het uitschakelen door het selectievakje **Aan** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-250">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="12276-251">**Phish ZAP**: ZAP is standaard ingeschakeld voor phishingdetectie, maar u kunt het uitschakelen door het selectievakje **Aan** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-251">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="12276-252">(Optioneel) Vouw de sectie **Lijsten toestaan** uit om op basis van e-mailadres of e-maildomein afzenders van berichten te configureren die de spamfilters mogen overslaan:</span><span class="sxs-lookup"><span data-stu-id="12276-252">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   > <span data-ttu-id="12276-253">• Denk goed na voordat u hier domeinen toevoegt.</span><span class="sxs-lookup"><span data-stu-id="12276-253">• Think very carefully before you add domains here.</span></span> <span data-ttu-id="12276-254">Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12276-254">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span> <br/><br/> <span data-ttu-id="12276-255">• Voeg nooit geaccepteerde domeinen (domeinen waarvan u eigenaar bent) of algemene domeinen (bijv.: microsoft.com of office.com) toe aan de lijst met toegestane domeinen.</span><span class="sxs-lookup"><span data-stu-id="12276-255">• Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="12276-256">Hiermee kunnen kwaadwillende gebruikers e-mail verzenden die de e-mailspamfilters in uw bedrijf overslaat.</span><span class="sxs-lookup"><span data-stu-id="12276-256">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="12276-257">**Afzender toelaten**: klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-257">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="12276-258">In het deelvenster **Lijst met toegestane afzenders** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12276-258">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="12276-259">a.</span><span class="sxs-lookup"><span data-stu-id="12276-259">a.</span></span> <span data-ttu-id="12276-260">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="12276-260">Enter the sender's email address.</span></span> <span data-ttu-id="12276-261">U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma’s (;).</span><span class="sxs-lookup"><span data-stu-id="12276-261">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="12276-262">b.</span><span class="sxs-lookup"><span data-stu-id="12276-262">b.</span></span> <span data-ttu-id="12276-263">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-263">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="12276-265">om de afzenders toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="12276-265">to add the senders.</span></span>

      <span data-ttu-id="12276-266">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-266">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="12276-267">De afzenders die u hebt toegevoegd worden weergegeven in de sectie **Toegestane afzenders** in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-267">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="12276-268">Om een afzender te verwijderen, klikt u op ![Pictogram verwijderen](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="12276-268">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="12276-269">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-269">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="12276-270">**Domein toelaten**: klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-270">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="12276-271">In het deelvenster **Lijst met toegestane domeinen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12276-271">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="12276-272">a.</span><span class="sxs-lookup"><span data-stu-id="12276-272">a.</span></span> <span data-ttu-id="12276-273">Voert u het domein in.</span><span class="sxs-lookup"><span data-stu-id="12276-273">Enter the domain.</span></span> <span data-ttu-id="12276-274">U kunt meerdere domeinen opgeven, gescheiden door puntkomma’s (;).</span><span class="sxs-lookup"><span data-stu-id="12276-274">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="12276-275">b.</span><span class="sxs-lookup"><span data-stu-id="12276-275">b.</span></span> <span data-ttu-id="12276-276">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-276">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="12276-278">om de domeinen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="12276-278">to add the domains.</span></span>

      <span data-ttu-id="12276-279">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-279">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="12276-280">De domeinen die u hebt toegevoegd worden weergegeven in de sectie **Toegestane domeinen** in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-280">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="12276-281">Om een domein te verwijderen, klikt u op ![Pictogram verwijderen](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="12276-281">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="12276-282">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-282">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="12276-283">(Optioneel) Vouw de sectie **Geblokkeerd** uit om op basis van e-mailadres of e-maildomein afzenders van berichten te configureren die altijd worden gemarkeerd als Hoogstwaarschijnlijk spam:</span><span class="sxs-lookup"><span data-stu-id="12276-283">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="12276-284">Het is niet gevaarlijk handmatig domeinen te blokkeren, maar het kan de werkbelasting vergroten</span><span class="sxs-lookup"><span data-stu-id="12276-284">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="12276-285">Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12276-285">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="12276-286">**Afzender blokkeren**: klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-286">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="12276-287">In het deelvenster **Lijst met geblokkeerde afzenders** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12276-287">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="12276-288">a.</span><span class="sxs-lookup"><span data-stu-id="12276-288">a.</span></span> <span data-ttu-id="12276-289">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="12276-289">Enter the sender's email address.</span></span> <span data-ttu-id="12276-290">U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma’s (;).</span><span class="sxs-lookup"><span data-stu-id="12276-290">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="12276-291">Jokertekens (\*) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="12276-291">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="12276-292">b.</span><span class="sxs-lookup"><span data-stu-id="12276-292">b.</span></span> <span data-ttu-id="12276-293">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-293">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="12276-295">om de afzenders toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="12276-295">to add the senders.</span></span>

      <span data-ttu-id="12276-296">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-296">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="12276-297">De afzenders die u hebt toegevoegd worden weergegeven in de sectie **Geblokkeerde afzenders** in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-297">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="12276-298">Om een afzender te verwijderen, klikt u op de knop ![Verwijderen](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="12276-298">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="12276-299">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-299">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="12276-300">**Domein blokkeren**: klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-300">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="12276-301">In het deelvenster **Lijst met geblokkeerde domeinen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="12276-301">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="12276-302">a.</span><span class="sxs-lookup"><span data-stu-id="12276-302">a.</span></span> <span data-ttu-id="12276-303">Voert u het domein in.</span><span class="sxs-lookup"><span data-stu-id="12276-303">Enter the domain.</span></span> <span data-ttu-id="12276-304">U kunt meerdere domeinen opgeven, gescheiden door puntkomma’s (;).</span><span class="sxs-lookup"><span data-stu-id="12276-304">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="12276-305">Jokertekens (\*) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="12276-305">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="12276-306">b.</span><span class="sxs-lookup"><span data-stu-id="12276-306">b.</span></span> <span data-ttu-id="12276-307">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-307">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="12276-309">om de domeinen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="12276-309">to add the domains.</span></span>

      <span data-ttu-id="12276-310">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-310">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="12276-311">De domeinen die u hebt toegevoegd worden weergegeven in de lijst **Geblokkeerde domeinen** in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-311">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="12276-312">Om een domein te verwijderen, klikt u op knop ![Verwijderen](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="12276-312">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="12276-313">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-313">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="12276-314">(Optioneel) Vouw de sectie **Internationale spam** uit om de e-mailtalen of herkomstlanden te configureren die worden geblokkeerd door spamfilters:</span><span class="sxs-lookup"><span data-stu-id="12276-314">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="12276-315">**E-mailberichten in de volgende talen filteren**: deze instelling is standaard uitgeschakeld (**Satus: UIT**).</span><span class="sxs-lookup"><span data-stu-id="12276-315">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="12276-316">Klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-316">Click **Edit**.</span></span> <span data-ttu-id="12276-317">Configureer in het deelvenster **Internationale spaminstellingen** dat wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-317">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="12276-318">**E-mailberichten in de volgende talen filteren**: selecteer het selectievakje om deze instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-318">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="12276-319">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-319">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="12276-320">Klik in het vak en begin de *naam* van de taal te typen.</span><span class="sxs-lookup"><span data-stu-id="12276-320">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="12276-321">Er wordt een gefilterde lijst met ondersteunde talen weergegeven, samen met de bijbehorende ISO 639-2-taalcode.</span><span class="sxs-lookup"><span data-stu-id="12276-321">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="12276-322">Wanneer u de gezochte taal vindt, selecteert u die.</span><span class="sxs-lookup"><span data-stu-id="12276-322">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="12276-323">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-323">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="12276-324">De lijst met talen die u hebt geselecteerd, verschijnt in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-324">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="12276-325">Om een taal te verwijderen, klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-325">To delete a language, click</span></span> ![de knop Verwijderen](../../media/scc-remove-icon.png)<span data-ttu-id="12276-327">.</span><span class="sxs-lookup"><span data-stu-id="12276-327">.</span></span>

     <span data-ttu-id="12276-328">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-328">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="12276-329">**E-mailberichten uit de volgende landen of regio’s filteren**: deze instelling is standaard uitgeschakeld (**Satus: UIT**).</span><span class="sxs-lookup"><span data-stu-id="12276-329">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="12276-330">Klik op **Bewerken** om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-330">To enable it, click **Edit**.</span></span> <span data-ttu-id="12276-331">Configureer in het deelvenster **Internationale spaminstellingen** dat wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-331">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="12276-332">**E-mailberichten uit de volgende landen of regio’s filteren**: selecteer het selectievakje om deze instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-332">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="12276-333">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-333">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="12276-334">Klik in het vak en begin de *naam* van het land of de regio te typen.</span><span class="sxs-lookup"><span data-stu-id="12276-334">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="12276-335">Er wordt een gefilterde lijst met ondersteunde landen weergegeven, samen met de bijbehorende tweeletterige ISO 3166-1-landcode.</span><span class="sxs-lookup"><span data-stu-id="12276-335">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="12276-336">Selecteer het land of de regio waarnaar u zocht als het is gevonden.</span><span class="sxs-lookup"><span data-stu-id="12276-336">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="12276-337">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="12276-337">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="12276-338">De lijst met landen die u hebt geselecteerd, verschijnt in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="12276-338">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="12276-339">Om een land of regio te verwijderen, klikt u op</span><span class="sxs-lookup"><span data-stu-id="12276-339">To delete a country or region, click</span></span> ![de knop Verwijderen](../../media/scc-remove-icon.png)<span data-ttu-id="12276-341">.</span><span class="sxs-lookup"><span data-stu-id="12276-341">.</span></span>

     <span data-ttu-id="12276-342">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-342">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="12276-343">De optionele sectie **Spameigenschappen** bevat ASF-instellingen (geavanceerde instellingen voor spamfilters) die standaard zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="12276-343">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="12276-344">ASF-instellingen worden afgeschaft en hun functionaliteit wordt opgenomen in andere onderdelen van de filterstack.</span><span class="sxs-lookup"><span data-stu-id="12276-344">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="12276-345">Het is raadzaam dat u al deze ASF-instellingen uitgeschakeld laat in uw antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-345">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="12276-346">Zie [Geavanceerde instellingen voor spamfilters in EOP](advanced-spam-filtering-asf-options.md) voor meer informatie over deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="12276-346">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="12276-347">(Verplicht) Vouw de sectie **Toegepast op** uit om de interne geadresseerden te bepalen op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="12276-347">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="12276-348">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="12276-348">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="12276-349">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="12276-349">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="12276-350">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="12276-350">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="12276-351">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="12276-351">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="12276-352">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="12276-352">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="12276-353">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="12276-353">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="12276-354">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="12276-354">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="12276-355">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="12276-355">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="12276-356">**Geadresseerde is**: specificeert een of meer postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="12276-356">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="12276-357">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="12276-357">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="12276-358">Klik opnieuw op het vak **Tag toevoegen** om aanvullende geadresseerden te selecteren.</span><span class="sxs-lookup"><span data-stu-id="12276-358">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="12276-359">**Geadresseerde is een lid van**: specificeert een of meer groepen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="12276-359">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="12276-360">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="12276-360">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="12276-361">Klik opnieuw op het vak **Tag toevoegen** om aanvullende geadresseerden te selecteren.</span><span class="sxs-lookup"><span data-stu-id="12276-361">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="12276-362">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="12276-362">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="12276-363">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="12276-363">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="12276-364">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-364">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="12276-365">Het Beveiligings- en compliancecentrum gebruiken om antispambeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="12276-365">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="12276-366">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-366">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-367">Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="12276-367">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="12276-368">Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.</span><span class="sxs-lookup"><span data-stu-id="12276-368">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="12276-369">Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.</span><span class="sxs-lookup"><span data-stu-id="12276-369">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="12276-370">De belangrijke beleidsinstellingen worden weergegeven in de uitgebreide beleidsgegevens.</span><span class="sxs-lookup"><span data-stu-id="12276-370">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="12276-371">Klik op **Beleid bewerken** voor meer gegevens.</span><span class="sxs-lookup"><span data-stu-id="12276-371">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="12276-372">Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="12276-372">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="12276-373">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-373">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-374">Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="12276-374">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="12276-375">Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.</span><span class="sxs-lookup"><span data-stu-id="12276-375">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="12276-376">Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.</span><span class="sxs-lookup"><span data-stu-id="12276-376">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="12276-377">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="12276-377">Click **Edit policy**.</span></span>

<span data-ttu-id="12276-378">De beschikbare instellingen in het deelvenster zijn voor aangepast antispambeleid hetzelfde als die zijn beschreven in de sectie [Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken](#use-the-security--compliance-center-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="12276-378">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="12276-379">Voor het standaardantispambeleid met de naam **Standaardbeleid voor spamfilters** is de sectie **Toegepast op** niet beschikbaar (het beleid is op iedereen van toepassing) en u kunt de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="12276-379">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="12276-380">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="12276-380">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="12276-381">Antispambeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="12276-381">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="12276-382">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-382">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-383">Klik in de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is **Aangepast antispambeleid**).</span><span class="sxs-lookup"><span data-stu-id="12276-383">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="12276-384">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="12276-384">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="12276-385">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="12276-385">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="12276-387">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="12276-387">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="12276-389">U kunt het standaardantispambeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-389">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="12276-390">De prioriteit instellen voor aangepast antispambeleid</span><span class="sxs-lookup"><span data-stu-id="12276-390">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="12276-391">Standaard krijgt antispambeleid een prioriteit op basis van de volgorde waarin het is gemaakt (nieuwer beleid heeft een hogere prioriteit dan ouder beleid).</span><span class="sxs-lookup"><span data-stu-id="12276-391">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="12276-392">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="12276-392">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="12276-393">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="12276-393">No two policies can have the same priority.</span></span>

<span data-ttu-id="12276-394">Aangepast antispambeleid wordt weergegeven in de volgorde waarin het wordt verwerkt (het eerste beleid heeft de **Prioriteit**swaarde 0).</span><span class="sxs-lookup"><span data-stu-id="12276-394">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="12276-395">Het standaardantispambeleid met de naam **Standaardbeleid voor spamfilters** heeft de prioriteitswaarde **Laagste** en dat kunt u niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="12276-395">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="12276-396">**Opmerking**: In het Beveiligings- en compliancecentrum kunt u alleen de prioriteit wijzigen van het antispambeleid nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="12276-396">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="12276-397">In PowerShell kunt u de standaardprioriteit vervangen wanneer u de spamfilterbeleidsregel maakt (die kan de prioriteit van bestaande regels beïnvloeden).</span><span class="sxs-lookup"><span data-stu-id="12276-397">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="12276-398">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="12276-398">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="12276-399">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-399">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-400">Zoek in de pagina **Antispaminstellingen**het beleid waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.</span><span class="sxs-lookup"><span data-stu-id="12276-400">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="12276-401">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="12276-401">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="12276-402">Het aangepaste antispambeleid met de hoogste prioriteit heeft de waarde ![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="12276-402">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="12276-403">Het aangepaste antispambeleid met de laagste prioriteit heeft de waarde ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijv.: ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="12276-403">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="12276-404">Als u drie of meer aangepaste antispambeleidsregels hebt, hebben de regels tussen de hoogste en laagste prioriteit de waarden ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **n** (bijv.: ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="12276-404">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="12276-405">Klik op</span><span class="sxs-lookup"><span data-stu-id="12276-405">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="12276-407">of</span><span class="sxs-lookup"><span data-stu-id="12276-407">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="12276-409">om het aangepaste antispambeleid omhoog of omlaag te verplaatsen in de prioriteitslijst.</span><span class="sxs-lookup"><span data-stu-id="12276-409">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="12276-410">Spammeldingen voor eindgebruikers configureren</span><span class="sxs-lookup"><span data-stu-id="12276-410">Configure end-user spam notifications</span></span>

<span data-ttu-id="12276-411">Wanneer in een spamfilterbeoordeling een bericht in quarantaine wordt geplaatst, kunt u spammeldingen voor eindgebruikers configureren om geadresseerden te laten weten wat er is gebeurd met berichten die naar hen zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="12276-411">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="12276-412">Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie over deze meldingen.</span><span class="sxs-lookup"><span data-stu-id="12276-412">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="12276-413">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-413">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-414">Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="12276-414">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="12276-415">Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.</span><span class="sxs-lookup"><span data-stu-id="12276-415">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="12276-416">Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.</span><span class="sxs-lookup"><span data-stu-id="12276-416">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="12276-417">Klik op **Spammeldingen voor eindgebruikers configureren** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="12276-417">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="12276-418">Configureer de volgende instellingen in het dialoogvenster **\<Policy Name\>** dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="12276-418">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="12276-419">**Spammeldingen voor eindgebruikers inschakelen**: vink het selectievakje aan om meldingen in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-419">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="12276-420">Schakel het selectievakje uit om meldingen uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-420">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="12276-421">\*\*Iedere (dagen) spammeldingen voor eindgebruikers verzenden \*\*: selecteer hoe vaak meldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="12276-421">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="12276-422">De standaardwaarde is 3 dagen.</span><span class="sxs-lookup"><span data-stu-id="12276-422">The default value is 3 days.</span></span> <span data-ttu-id="12276-423">U kunt 1 tot 15 dagen opgeven.</span><span class="sxs-lookup"><span data-stu-id="12276-423">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="12276-424">Er zijn drie cycli van spammeldingen voor eindgebruikers binnen een periode van 24 uur die beginnen op de volgende tijden: 01:00 UTC, 08:00 UTC en 16:00 UTC.</span><span class="sxs-lookup"><span data-stu-id="12276-424">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="12276-425">Als we tijdens een vorige cyclus een melding hebben gemist, wordt in de volgende cyclus de melding gepusht.</span><span class="sxs-lookup"><span data-stu-id="12276-425">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="12276-426">Dit geeft de indruk van meerdere meldingen op dezelfde dag.</span><span class="sxs-lookup"><span data-stu-id="12276-426">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="12276-427">**Taal van meldingen**: klik op de vervolgkeuzelijst en selecteer een beschikbare taal in de lijst.</span><span class="sxs-lookup"><span data-stu-id="12276-427">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="12276-428">De standaardwaarde is **Standaard**, oftewel de standaardtaal van de cloudorganisatie.</span><span class="sxs-lookup"><span data-stu-id="12276-428">The default value is **Default**, which means the default language of the cloud-based organization.</span></span>

   <span data-ttu-id="12276-429">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="12276-429">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="12276-430">Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te verplaatsen</span><span class="sxs-lookup"><span data-stu-id="12276-430">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="12276-431">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="12276-431">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12276-432">Klik in de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de waarde in de kolom **Type** is **Aangepast antispambeleid**).</span><span class="sxs-lookup"><span data-stu-id="12276-432">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="12276-433">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="12276-433">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="12276-434">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="12276-434">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="12276-435">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="12276-435">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="12276-436">Exchange Online PowerShell of standalone EOP PowerShell gebruiken om antispambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="12276-436">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="12276-437">De volgende antispambeleidsinstellingen zijn alleen beschikbaar in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12276-437">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="12276-438">De parameter _MarkAsSpamBulkMail_, die standaard `On` is.</span><span class="sxs-lookup"><span data-stu-id="12276-438">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="12276-439">De gevolgen van deze instelling zijn eerder in dit artikel uitgelegd in de sectie [Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken](#use-the-security--compliance-center-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="12276-439">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="12276-440">De volgende instellingen voor quarantainemeldingen voor eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="12276-440">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="12276-441">De parameter_DownloadLink_ toont of verbergt de koppeling naar het rapportagehulpmiddel voor ongewenste e-mail voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="12276-441">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="12276-442">De parameter _EndUserSpamNotificationCustomSubject_ die u kunt gebruiken om de onderwerpregel van de melding aan te passen.</span><span class="sxs-lookup"><span data-stu-id="12276-442">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="12276-443">PowerShell gebruiken om antispambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="12276-443">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="12276-444">Antispambeleid maken in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="12276-444">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="12276-445">Het spamfilterbeleid maken.</span><span class="sxs-lookup"><span data-stu-id="12276-445">Create the spam filter policy.</span></span>

2. <span data-ttu-id="12276-446">De spamfilterbeleidsregel maken die het spamfilterbeleid opgeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="12276-446">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="12276-447">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="12276-447">**Notes**:</span></span>

- <span data-ttu-id="12276-448">U kunt een nieuwe spamfilterbeleidsregel maken en een bestaand, niet-gekoppeld spamfilterbeleid eraan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="12276-448">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="12276-449">Een spamfilterbeleidsregel kan niet worden gekoppeld aan meer dan één spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="12276-449">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="12276-450">U kunt de volgende instellingen voor nieuw spamfilterbeleid configureren in PowerShell die niet beschikbaar zijn in het Beveiligings- en compliancecentrum tot nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="12276-450">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="12276-451">Schakel het nieuwe beleid uit (_Ingeschakeld_ `$false` in het cmdlet **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="12276-451">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="12276-452">Stel de prioriteit van het beleid in tijdens het maken (_Prioriteit_ _\<Number\>_) in de cmdlet **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="12276-452">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="12276-453">Nieuw spamfilterbeleid dat u maakt in PowerShell is niet zichtbaar in het Beveiligings- en compliancecentrum totdat u het beleid toewijst aan een spamfilterregel.</span><span class="sxs-lookup"><span data-stu-id="12276-453">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="12276-454">Stap 1: PowerShell gebruiken om spamfilterbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="12276-454">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="12276-455">Gebruik de volgende syntaxis om spamfilterbeleid te maken:</span><span class="sxs-lookup"><span data-stu-id="12276-455">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="12276-456">Dit voorbeeld maakt spamfilterbeleid met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-456">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="12276-457">Quarantainemeldingen wanneer de spamfilterbeoordeling Spam of Hoogstwaarschijnlijk spam is.</span><span class="sxs-lookup"><span data-stu-id="12276-457">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="12276-458">BCL 6 activeert de actie voor een bulk-e-mail-spamfilterbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="12276-458">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="12276-459">**New-HostedContentFilterPolicy** en **Set-HostedContentFilterPolicy** bevatten een oudere parameter _ZapEnabled_ en nieuwere parameters_PhishZapEnabled_ en _SpamZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="12276-459">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="12276-460">De parameter _ZapEnabled_ is in februari 2020 afgeschaft.</span><span class="sxs-lookup"><span data-stu-id="12276-460">The _ZapEnabled_ parameter was deprecated in February, 2020.</span></span> <span data-ttu-id="12276-461">The parameters _PhishZapEnabled_ en _SpamZapEnabled_ namen hun waarden over van de parameter _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="12276-461">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="12276-462">Maar als u de parameters _PhishZapEnabled_ en _SpamZapEnabled_ gebruikt in een opdracht of de instelling **Spam ZAP** of **Phish ZAP** in het antispambeleid in het Beveiligings- en compliancecentrum, wordt de waarde van de parameter _ZapEnabled_ genegeerd.</span><span class="sxs-lookup"><span data-stu-id="12276-462">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="12276-463">Met andere woorden, gebruik de parameter _ZapEnabled_ niet, maar gebruik hiervoor in de plaats de parameters _PhishZapEnabled_ en _SpamZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="12276-463">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="12276-464">Zie [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-464">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="12276-465">Stap 2: PowerShell gebruiken om een spamfilterregel te maken</span><span class="sxs-lookup"><span data-stu-id="12276-465">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="12276-466">Gebruik de volgende syntaxis om een spamfilterregel te maken:</span><span class="sxs-lookup"><span data-stu-id="12276-466">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="12276-467">Dit voorbeeld maakt een nieuwe spamfilterregel met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="12276-467">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="12276-468">Het spamfilterbeleid met de naam Contoso Executives wordt gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="12276-468">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="12276-469">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="12276-469">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="12276-470">Zie [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-470">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="12276-471">PowerShell gebruiken om spamfilterbeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="12276-471">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="12276-472">Voer de volgende opdracht uit om een overzicht van alle spamfilterbeleid weer te geven:</span><span class="sxs-lookup"><span data-stu-id="12276-472">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="12276-473">Gebruik deze syntaxis voor gedetailleerde informatie over specifiek spamfilterbeleid:</span><span class="sxs-lookup"><span data-stu-id="12276-473">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="12276-474">In dit voorbeeld worden alle eigenschapswaarden weergegeven voor het spamfilterbeleid met de naam Executives.</span><span class="sxs-lookup"><span data-stu-id="12276-474">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="12276-475">Zie [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-475">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="12276-476">PowerShell gebruiken om spamfilterregels te bekijken</span><span class="sxs-lookup"><span data-stu-id="12276-476">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="12276-477">Gebruik de volgende syntaxis om bestaande spamfilterregels te bekijken:</span><span class="sxs-lookup"><span data-stu-id="12276-477">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="12276-478">Voer de volgende opdracht uit om een overzicht van alle spamfilterregels weer te geven:</span><span class="sxs-lookup"><span data-stu-id="12276-478">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="12276-479">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="12276-479">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="12276-480">Gebruik deze syntaxis voor gedetailleerde informatie over een specifieke spamfilterregel:</span><span class="sxs-lookup"><span data-stu-id="12276-480">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="12276-481">In dit voorbeeld worden alle eigenschapswaarden weergegeven voor het spamfilterregel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="12276-481">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="12276-482">Zie [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-482">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="12276-483">PowerShell gebruiken om spamfilterbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="12276-483">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="12276-484">Naast de volgende items zijn dezelfde instellingen beschikbaar voor het wijzigen van malwarefilterbeleid in PowerShell als bij het maken van het beleid zoals eerder in dit artikel beschreven in de sectie [Stap 1: PowerShell gebruiken om spamfilterbeleid te maken](#step-1-use-powershell-to-create-a-spam-filter-policy).</span><span class="sxs-lookup"><span data-stu-id="12276-484">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="12276-485">De schakeloptie _MakeDefault_ die het specifieke beleid wijzigt in het standaardbeleid (toegepast op iedereen, altijd **Laagste** prioriteit en kan niet worden verwijderd) is alleen beschikbaar wanneer u spamfilterbeleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12276-485">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="12276-486">U kunt de naam van het spamfilterbeleid niet wijzigen (het cmdlet **Set-HostedContentFilterPolicy** heeft geen parameter _Naam_).</span><span class="sxs-lookup"><span data-stu-id="12276-486">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="12276-487">Wanneer u de naam van antispambeleid in het Beveiligings- en compliancecentrum wijzigt, wijzigt u alleen de naam van de spamfilter_regel_.</span><span class="sxs-lookup"><span data-stu-id="12276-487">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="12276-488">Gebruik de volgende syntaxis om spamfilterbeleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="12276-488">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="12276-489">Zie [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-489">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="12276-490">PowerShell gebruiken om spamfilterregels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="12276-490">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="12276-491">De enige instelling die niet beschikbaar is wanneer u een spamfilterregel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="12276-491">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="12276-492">Zie de volgende sectie om bestaande spamfilterregels in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="12276-492">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="12276-493">Er zijn geen extra instellingen beschikbaar wanneer u een spamfilterregel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12276-493">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="12276-494">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals eerder in dit artikel beschreven in de sectie [Stap 2: PowerShell gebruiken om een spamfilterregel te maken](#step-2-use-powershell-to-create-a-spam-filter-rule).</span><span class="sxs-lookup"><span data-stu-id="12276-494">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="12276-495">Gebruik de volgende syntaxis om een spamfilterregel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="12276-495">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="12276-496">In dit voorbeeld wordt de naam veranderd van de bestaande spamfilterregel met de naam `{Fabrikam Spam Filter}` die problemen kan veroorzaken in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="12276-496">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="12276-497">Zie [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-497">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="12276-498">PowerShell gebruiken om spamfilterregels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="12276-498">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="12276-499">Het in- of uitschakelen van een spamfilterregel in PowerShell, schakelt het hele antispambeleid in of uit (de spamfilterregel en het bijbehorende spamfilterbeleid).</span><span class="sxs-lookup"><span data-stu-id="12276-499">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="12276-500">U kunt het standaardbeleid niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="12276-500">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="12276-501">Gebruik de volgende syntaxis om een spamfilterregel in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="12276-501">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="12276-502">In dit voorbeeld wordt de spamfilterregel uitgeschakeld met de naam Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12276-502">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12276-503">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="12276-503">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12276-504">Zie [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) en [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-504">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="12276-505">PowerShell gebruiken om de prioriteit van spamfilterregels in te stellen</span><span class="sxs-lookup"><span data-stu-id="12276-505">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="12276-506">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="12276-506">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="12276-507">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="12276-507">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="12276-508">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="12276-508">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="12276-509">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="12276-509">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="12276-510">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="12276-510">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="12276-511">Gebruik de volgende syntaxis om de prioriteit van een spamfilterregel in te stellen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12276-511">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="12276-512">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="12276-512">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="12276-513">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="12276-513">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="12276-514">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="12276-514">**Notes**:</span></span>

- <span data-ttu-id="12276-515">Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ in het cmdlet **New-HostedContentFilterRule**.</span><span class="sxs-lookup"><span data-stu-id="12276-515">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="12276-516">Het standaardbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de waarde **Laagste** die niet kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="12276-516">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="12276-517">PowerShell gebruiken om spamfilterbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="12276-517">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="12276-518">Wanneer u PowerShell gebruikt om spamfilterbeleid te verwijderen, wordt de bijbehorende spamfilterregel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="12276-518">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="12276-519">Gebruik deze syntaxis om spamfilterbeleid in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="12276-519">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="12276-520">In dit voorbeeld wordt het spamfilterbeleid verwijderd met de naam Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12276-520">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="12276-521">Zie [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-521">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="12276-522">PowerShell gebruiken om spamfilterregels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="12276-522">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="12276-523">Wanneer u PowerShell gebruikt om een spamfilterregel te verwijderen, wordt het bijbehorende spamfilterbeleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="12276-523">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="12276-524">Gebruik deze syntaxis om een spamfilterregel in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="12276-524">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="12276-525">In dit voorbeeld wordt de spamfilterregel verwijderd met de naam Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12276-525">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12276-526">Zie [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="12276-526">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="12276-527">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="12276-527">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="12276-528">Een GTUBE-bericht zenden om de instellingen van uw spambeleid te testen</span><span class="sxs-lookup"><span data-stu-id="12276-528">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="12276-529">Deze stappen werken alleen als het e-mailbedrijf waarvandaan u het GTUBE-bericht stuurt, niet scant op uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="12276-529">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="12276-530">Als het bedrijf dat wel doet, kan het testbericht niet worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="12276-530">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="12276-531">GTUBE (Generic Test for Unsolicited Bulk Email) is een tekenreeks die u opneemt in een testbericht om de antispaminstellingen van uw bedrijf te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="12276-531">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="12276-532">Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.</span><span class="sxs-lookup"><span data-stu-id="12276-532">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="12276-533">Neem de volgende GTUBE-tekst op in een e-mailbericht op één regel zonder spaties of regeleinden:</span><span class="sxs-lookup"><span data-stu-id="12276-533">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="12276-534">Lijsten toestaan/blokkeren</span><span class="sxs-lookup"><span data-stu-id="12276-534">Allow/Block Lists</span></span>

<span data-ttu-id="12276-535">Er zijn momenten waarop de filters het bericht missen of het duurt even voor de systemen helemaal bijgewerkt zijn.</span><span class="sxs-lookup"><span data-stu-id="12276-535">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="12276-536">In die gevallen heeft het antispambeleid een lijst Toestaan en een lijst Blokkeren beschikbaar om de huidige beoordeling te negeren.</span><span class="sxs-lookup"><span data-stu-id="12276-536">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="12276-537">Deze optie moet spaarzaam en tijdelijk worden gebruikt, omdat de lijsten onbeheerbaar kunnen worden, omdat de filterstack moet doen waarvoor die is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="12276-537">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="12276-538">Er kunnen situaties zijn waar uw bedrijf het niet eens is met de beoordeling die de service aflevert.</span><span class="sxs-lookup"><span data-stu-id="12276-538">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="12276-539">In dat geval wilt u mogelijk de lijsten Toestaan en Blokkeren permanent behouden.</span><span class="sxs-lookup"><span data-stu-id="12276-539">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="12276-540">Als u echter een domein voor een langere periode op de lijst Toestaan plaatst, moet u dat de afzender laten weten om zeker te weten dat het domein is geverifieerd en instellen op DMARC als dat niet zo is.</span><span class="sxs-lookup"><span data-stu-id="12276-540">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
