---
title: ATP-beleid tegen phishing configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u het geavanceerde antiphishingbeleid maakt, wijzigt en verwijdert dat beschikbaar is in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726765"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-103">ATP-beleid tegen phishing configureren</span><span class="sxs-lookup"><span data-stu-id="d1ecd-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="d1ecd-104">Atp-antiphishingbeleid maakt deel uit van [Geavanceerde bedreigingsbeveiliging van Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="d1ecd-105">Atp-antiphishingbeleid kan uw organisatie beschermen tegen schadelijke imitatiegebaseerde phishing-aanvallen en andere soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="d1ecd-106">Zie [Anti-phishing-beveiliging voor](anti-phishing-protection.md)meer informatie over de verschillen tussen het anti-phishingbeleid in Exchange Online Protection (EOP) en atp-antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="d1ecd-107">Beheerders kunnen het standaard ATP-antiphishingbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="d1ecd-108">Voor meer granulariteit u ook aangepaste ATP-antiphishingbeleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d1ecd-109">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d1ecd-110">U atp-antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="d1ecd-111">Zie [Anti-phishingbeleid configureren](configure-anti-phishing-policies-eop.md)in EOP voor informatie over het configureren van de beperkter beleid voor antiphishingbeleid dat beschikbaar is in Organisaties voor Online bescherming van Exchange (dat wil zeggen Microsoft 365-organisaties zonder Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="d1ecd-112">ATP-antiphishingbeleid in het Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1ecd-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="d1ecd-113">De basiselementen van een ATP anti-phishing beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="d1ecd-114">**Het anti-phish-beleid**: Hiermee geeft u de bescherming tegen phishing op om in te schakelen of uit te schakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="d1ecd-115">**De anti-phish regel**: Hiermee geeft u de prioriteit en ontvanger filters (die het beleid van toepassing is op) voor een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="d1ecd-116">Het verschil tussen deze twee elementen is niet duidelijk wanneer u atp-antiphishingbeleid beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d1ecd-117">Wanneer u een ATP-antiphishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="d1ecd-118">Wanneer u een ATP-antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en ontvangersfilters de anti-phishregel.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="d1ecd-119">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="d1ecd-120">Wanneer u een ATP-antiphishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phishregel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="d1ecd-121">In Exchange Online PowerShell is het verschil tussen anti-phish beleid en anti-phish regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="d1ecd-122">Je beheert anti-phish beleid met behulp van de \*\* \* -AntiPhishPolicy\*\* cmdlets, en je beheert anti-phish regels met behulp van de \*\* \* -AntiPhishRule\*\* cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="d1ecd-123">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="d1ecd-124">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="d1ecd-125">Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phishregel niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="d1ecd-126">Standaard ATP-antiphishingbeleid</span><span class="sxs-lookup"><span data-stu-id="d1ecd-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="d1ecd-127">Elke ATP-organisatie heeft een ingebouwd ATP-antiphishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="d1ecd-128">Het anti-phish-beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish-regel (ontvangerfilters) die aan het beleid is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="d1ecd-129">Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d1ecd-130">Alle aangepaste beleidsregels die u maakt, hebben altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="d1ecd-131">Het beleid met de naam Office365 AntiPhish Default is het standaardbeleid (de eigenschap **IsDefault** heeft de `True` waarde) en u het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d1ecd-132">Om de effectiviteit van anti-phishing-bescherming te vergroten, u aangepaste ATP-antiphishingbeleid maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d1ecd-133">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d1ecd-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d1ecd-134">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d1ecd-135">Als u rechtstreeks naar de **ATP-anti-phishingpagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d1ecd-136">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d1ecd-137">U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d1ecd-138">Als u atp-antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d1ecd-139">**Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d1ecd-140">**Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d1ecd-141">Voor alleen-lezen toegang tot atp-antiphishingbeleid moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d1ecd-142">**Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d1ecd-143">**Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d1ecd-144">Zie Beleidsinstellingen voor [Office ATP-beleid voor antiphishing van Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor ATP-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="d1ecd-145">Sta maximaal 30 minuten toe om een nieuw of bijgewerkt beleid toe te passen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="d1ecd-146">Zie [Volgorde en voorrang van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-147">Gebruik het Security & Compliance Center om ATP-antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="d1ecd-148">Als u een aangepast ATP-antiphishingbeleid maakt in het Security & Compliance Center, worden tegelijkertijd de anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="d1ecd-149">Wanneer u een ATP-antiphishingbeleid maakt, u alleen de beleidsnaam, de beschrijving en het filter van de ontvanger opgeven waarop wordt aangegeven op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="d1ecd-150">Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="d1ecd-151">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-152">Klik op de pagina **Anti-phishing** op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="d1ecd-153">De wizard Een nieuw beleid maken met **een ander beleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="d1ecd-154">Configureer op de pagina **Naam van uw beleid** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d1ecd-155">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d1ecd-156">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d1ecd-157">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d1ecd-158">Identificeer **op** de pagina Toegepast op die wordt weergegeven de interne ontvangers waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d1ecd-159">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d1ecd-160">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d1ecd-161">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d1ecd-162">Klik **op Een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-162">Click **Add a condition**.</span></span> <span data-ttu-id="d1ecd-163">Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d1ecd-164">**De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d1ecd-165">**De ontvanger is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d1ecd-166">Het domein van de **ontvanger is:** Hiermee geeft u geadresseerden op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="d1ecd-167">Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met **een van deze** opties.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d1ecd-168">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d1ecd-169">Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d1ecd-170">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d1ecd-171">Als u afzonderlijke vermeldingen wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d1ecd-172">Als u de hele **Remove** voorwaarde wilt verwijderen, klikt u ![ op pictogram Verwijderen op de ](../../media/scc-remove-icon.png) voorwaarde verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d1ecd-173">Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d1ecd-174">Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d1ecd-175">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d1ecd-176">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d1ecd-177">Controleer **op** de pagina Uw instellingen die wordt weergegeven de instellingen controleren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d1ecd-178">U op Elke instelling op **Bewerken** klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d1ecd-179">Klik op **Dit beleid maken**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="d1ecd-180">Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="d1ecd-181">Nadat u het ATP-antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-182">Gebruik het Security & Compliance Center om het ATP-antiphishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="d1ecd-183">Gebruik de volgende procedures om het ATP-antiphishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of een bestaand beleid dat u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="d1ecd-184">Als u er nog niet bent, opent u het Security **Threat management** & Compliance Center en gaat u naar \> **Policy** \> **ATP-antiphishing**voor bedreigingsbeheerbeleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-185">Selecteer het aangepaste ATP-antiphishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="d1ecd-186">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1ecd-187">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="d1ecd-188">Als u op **Bewerken** in een sectie klikt, krijgt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="d1ecd-189">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in willekeurige volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="d1ecd-190">Nadat u in een sectie op Bewerken hebt **geklikt,** worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in willekeurige volgorde binnen de pagina's springen en op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten sluiten** om terug te keren naar de pagina Uw beleid ![ ](../../media/scc-remove-icon.png) \*\* \<name\> bewerken\*\* (u hoeft de laatste pagina van de wizard niet te bezoeken om op te slaan of te vertrekken).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="d1ecd-191">**Beleidsinstelling**: klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het beleid](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="d1ecd-192">**Naam**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-192">**Name**</span></span>
   - <span data-ttu-id="d1ecd-193">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-193">**Description**</span></span>
   - <span data-ttu-id="d1ecd-194">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-194">**Applied to**</span></span>
   - <span data-ttu-id="d1ecd-195">**Uw instellingen bekijken**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-195">**Review your settings**</span></span>

   <span data-ttu-id="d1ecd-196">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="d1ecd-197">**Imitatie**: klik op **Bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="d1ecd-198">Deze instellingen zijn een voorwaarde voor het beleid waarmee vervalste afzenders moeten zoeken (individueel of per domein) in het adres Van binnenkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="d1ecd-199">Zie [Imitatie-instellingen in het ATP-antiphishingbeleid voor](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="d1ecd-200">**Gebruikers toevoegen om te beschermen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-201">Als u deze wilt inschakelen, schuift u de schakelaar in **Op**en klikt u op de **knop Gebruiker toevoegen** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="d1ecd-202">Configureer in de flyout **voor gebruikers toevoegen** die wordt weergegeven de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="d1ecd-203">**E-mailadres**:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-203">**Email address**:</span></span>

        - <span data-ttu-id="d1ecd-204">Klik in het vak en blader door de lijst met gebruikers om te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="d1ecd-205">Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="d1ecd-206">Als u een item wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="d1ecd-207">**Naam**: Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="d1ecd-208">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="d1ecd-209">Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="d1ecd-210">**Domeinen toevoegen om te beschermen:** Een of beide van de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="d1ecd-211">**Voeg automatisch de domeinen op die ik bezit:** De standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-212">Als u deze wilt inschakelen, schuift u de schakelaar **naar Aan**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="d1ecd-213">**Aangepaste domeinen opnemen:** de standaardwaarde is **uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-214">Als u deze wilt inschakelen, schuift u de schakelaar op **Aan**en voert u in het vak **Domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaal indien nodig.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="d1ecd-215">**Acties**: Klik op **Bewerken**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="d1ecd-216">**Als e-mail wordt verzonden door een geïmiteerde gebruiker:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in **Gebruikers toevoegen om te beschermen:**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="d1ecd-217">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="d1ecd-218">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="d1ecd-219">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="d1ecd-220">**Quarantaine het bericht**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="d1ecd-221">**Het bericht overbrengen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="d1ecd-222">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="d1ecd-223">**Als e-mail wordt verzonden door een geïmiteerd domein:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender zich in een van de beveiligde domeinen bevindt die u hebt opgegeven in **Domeinen toevoegen om te beschermen:**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="d1ecd-224">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="d1ecd-225">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="d1ecd-226">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="d1ecd-227">**Quarantaine het bericht**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="d1ecd-228">**Het bericht overbrengen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="d1ecd-229">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="d1ecd-230">Klik **op Impersonation safety tips inschakelen** en configureer een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="d1ecd-231">**Tip weergeven voor geïmiteerde gebruikers**: de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-232">Als u deze wilt inschakelen, schuift u de schakelaar **naar Aan**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="d1ecd-233">**Tip weergeven voor geïmiteerde domeinen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-234">Als u deze wilt inschakelen, schuift u de schakelaar **naar Aan**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="d1ecd-235">**Tip weergeven voor ongebruikelijke tekens**: de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="d1ecd-236">Als u deze wilt inschakelen, schuift u de schakelaar **naar Aan**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="d1ecd-237">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="d1ecd-238">**Postvakintelligentie**:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="d1ecd-239">**Postvakintelligentie inschakelen?**: De standaardwaarde is **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="d1ecd-240">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="d1ecd-241">**Postvakintelligentie inschakelen op basis van imitatiebeveiliging?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen** is **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="d1ecd-242">Als **e-mail wordt verzonden door een geïmiteerde gebruiker,** u een van de volgende acties opgeven die moeten worden uitgevoerd op berichten die niet intelligen voor postvakintelligentie zijn (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="d1ecd-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="d1ecd-243">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="d1ecd-244">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="d1ecd-245">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="d1ecd-246">**Quarantaine het bericht**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="d1ecd-247">**Het bericht overbrengen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="d1ecd-248">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="d1ecd-249">**Vertrouwde afzenders en domeinen toevoegen:** uitzonderingen voor het beleid opgeven:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="d1ecd-250">**Vertrouwde afzenders:**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="d1ecd-251">Klik in het vak en blader door de lijst met gebruikers om te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="d1ecd-252">Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="d1ecd-253">Als u een item wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="d1ecd-254">**Vertrouwde domeinen**: Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal indien nodig.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="d1ecd-255">**Uw instellingen bekijken:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d1ecd-256">U in elke sectie op **Bewerken** klikken om terug te springen naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d1ecd-257">U de volgende instellingen rechtstreeks **in-** of **uitschakelen** op deze pagina:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d1ecd-258">**Beschermde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-258">**Protected users**</span></span>
       - <span data-ttu-id="d1ecd-259">**Beveiligde domeinen** \> **Domeinen opnemen die ik bezit**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="d1ecd-260">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="d1ecd-261">**Postvakintelligentie**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="d1ecd-262">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="d1ecd-263">**Spoof**: klik op **Bewerken** om spoofinformatie in of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="d1ecd-264">Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="d1ecd-265">Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in het anti-phishingbeleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="d1ecd-266">**Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="d1ecd-267">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="d1ecd-268">Zie [Spoofintelligentie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d1ecd-269">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u in plaats daarvan Uitgebreide filtering voor connectoren inschakelt.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="d1ecd-270">Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="d1ecd-271">**Functie niet-geverifieerde afzender inschakelen:** de standaardwaarde is **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="d1ecd-272">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="d1ecd-273">**Acties**: Geef de actie op die moet worden uitgevoerd op berichten die niet intelligentie hebben:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="d1ecd-274">**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="d1ecd-275">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="d1ecd-276">**Quarantaine het bericht**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="d1ecd-277">**Uw instellingen bekijken:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d1ecd-278">U in elke sectie op **Bewerken** klikken om terug te springen naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d1ecd-279">U de volgende instellingen rechtstreeks **in-** of **uitschakelen** op deze pagina:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d1ecd-280">**Bescherming tegenpoofing inschakelen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="d1ecd-281">**Functie niet-geverifieerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="d1ecd-282">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="d1ecd-283">**Geavanceerde instellingen**: Klik op **Bewerken** om de geavanceerde phishingdrempels te configureren.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="d1ecd-284">Zie [Geavanceerde phishingdrempels in het ATP-antiphishingbeleid](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="d1ecd-285">**Geavanceerde phishingdrempels**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="d1ecd-286">**1 - Standaard** (Dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="d1ecd-287">**2 - Agressief**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="d1ecd-288">**3 - Agressiever**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="d1ecd-289">**4 - Meest agressieve**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="d1ecd-290">**Bekijk uw instellingen**: Klik op **Bewerken** om terug te gaan naar de pagina **Geavanceerde phishingdrempels.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="d1ecd-291">Wanneer u klaar bent, klikt u op **Opslaan** op een van beide pagina's.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="d1ecd-292">Terug op de pagina **Uw beleid \<Name\> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="d1ecd-293">Gebruik het Security & Compliance Center om het standaard ATP-antiphishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="d1ecd-294">Het standaard-atp-antiphishingbeleid heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="d1ecd-295">Als u het standaard-atp-antiphishingbeleid wilt wijzigen, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="d1ecd-296">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-297">Klik op de pagina **Antiphishing** op **Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="d1ecd-298">De pagina **Office365 AntiPhish Default-standaard** van het beleid bewerken, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="d1ecd-299">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="d1ecd-300">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-300">**Impersonation**</span></span>
   - <span data-ttu-id="d1ecd-301">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-301">**Spoof**</span></span>
   - <span data-ttu-id="d1ecd-302">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-302">**Advanced settings**</span></span>

   <span data-ttu-id="d1ecd-303">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="d1ecd-304">U de sectie **Beleidsinstelling** en waarden zien, maar er is geen koppeling **bewerken,** dus u de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (het is van toepassing op alle ontvangers)).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="d1ecd-305">U het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="d1ecd-306">U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="d1ecd-307">Bekijk op de pagina **Office365 AntiPhish Default bewerken** de instellingen en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-308">Aangepast ATP-antiphishingbeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="d1ecd-309">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-310">Let op de waarde in de kolom **Status:**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d1ecd-311">Schuif de schakel naar **Uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="d1ecd-312">Schuif de schakelaar **naar Aan** om het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="d1ecd-313">U het standaardbeleid voor antiphishing niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-314">De prioriteit instellen van het aangepaste ATP-anti-phishingbeleid</span><span class="sxs-lookup"><span data-stu-id="d1ecd-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="d1ecd-315">Standaard krijgt atp-antiphishingbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="d1ecd-316">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d1ecd-317">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="d1ecd-318">Aangepaste ATP-antiphishingbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d1ecd-319">Het standaardbeleid voor antiphishing met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste**en u deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="d1ecd-320">**Opmerking:** In het Security & Compliance Center u de prioriteit van het ATP-antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="d1ecd-321">In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d1ecd-322">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet direct wijzigen in het Security & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="d1ecd-323">Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="d1ecd-324">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-325">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="d1ecd-326">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1ecd-327">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="d1ecd-328">Het aangepaste ATP-antiphishingbeleid met de **prioriteitswaarde** **0** heeft alleen de knop **Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d1ecd-329">Het aangepaste ATP-antiphishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d1ecd-330">Als u drie of meer aangepaste antiphishingbeleid hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de knoppen **Prioriteit Verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d1ecd-331">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d1ecd-332">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-333">Gebruik het Security & Compliance Center om het ATP-beleid voor antiphishing te bekijken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="d1ecd-334">In het Security & Compliance Center en ga naar **Threat Management** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-335">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="d1ecd-336">Selecteer een aangepast ATP-antiphishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="d1ecd-337">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="d1ecd-338">Klik **op Standaardbeleid** om het standaardbeleid voor phishing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="d1ecd-339">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven, waar u de instellingen en waarden bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-340">Gebruik het Security & Compliance Center om atp-antiphishingbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="d1ecd-341">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1ecd-342">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="d1ecd-343">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1ecd-344">Klik in de flyout **beleid \<name\> bewerken** die wordt weergegeven op **Beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d1ecd-345">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="d1ecd-346">Exchange Online PowerShell gebruiken om atp-antiphishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="d1ecd-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="d1ecd-347">PowerShell gebruiken om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="d1ecd-348">Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d1ecd-349">Maak het anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="d1ecd-350">Maak de anti-phish regel die het anti-phish beleid aangeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="d1ecd-351">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-351">**Notes**:</span></span>

- <span data-ttu-id="d1ecd-352">U een nieuwe anti-phish regel maken en er een bestaand, niet-gekoppeld anti-phish beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="d1ecd-353">Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="d1ecd-354">U de volgende instellingen voor nieuw antifromancebeleid configureren in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d1ecd-355">Maak het nieuwe beleid als uitgeschakeld (_Ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="d1ecd-356">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="d1ecd-357">Een nieuw anti-phish-beleid dat u maakt in PowerShell, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish regel.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="d1ecd-358">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="d1ecd-359">Als u een anti-phish-beleid wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d1ecd-360">In dit voorbeeld wordt een anti-phish-beleid met de naam Research Quarantine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="d1ecd-361">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld niet_ en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="d1ecd-362">De beschrijving is: Onderzoek afdelingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="d1ecd-363">Hiermee biedt organisatiedomeinen bescherming voor alle geaccepteerde domeinen en is er bescherming van doeldomeinen voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="d1ecd-364">Hiermee geeft Mai Fujito (mfujito@fabrikam.com) op als gebruiker om te beschermen tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="d1ecd-365">Maakt postvakintelligentie mogelijk.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="d1ecd-366">Hiermee maakt u postvakintelligentiebeveiliging mogelijk en wordt de quarantaineactie opgegeven.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="d1ecd-367">Maakt veiligheidstips mogelijk.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="d1ecd-368">Zie [Nieuw-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="d1ecd-369">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="d1ecd-370">Als u een anti-phish-regel wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d1ecd-371">In dit voorbeeld wordt een anti-phish-regel met de naam Research Department gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="d1ecd-372">De regel is gekoppeld aan het anti-phish beleid genaamd Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="d1ecd-373">De regel is van toepassing op leden van de groep met de naam Research Department.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="d1ecd-374">Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="d1ecd-375">Zie [Nieuw-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="d1ecd-376">PowerShell gebruiken om anti-phish-beleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="d1ecd-377">Als u bestaande anti-phish-beleid wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d1ecd-378">In dit voorbeeld wordt een overzichtslijst geretourneerd met alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="d1ecd-379">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phish-beleid met de naam Executives.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="d1ecd-380">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="d1ecd-381">PowerShell gebruiken om anti-phish regels te bekijken</span><span class="sxs-lookup"><span data-stu-id="d1ecd-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="d1ecd-382">Als u bestaande anti-phishregels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d1ecd-383">In dit voorbeeld wordt een overzichtslijst van alle anti-phishregels samen met de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="d1ecd-384">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="d1ecd-385">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="d1ecd-386">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="d1ecd-387">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="d1ecd-388">Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish beleidssectie te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="d1ecd-389">De _Schakelaar Fout maken_ die het opgegeven beleid verandert in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u deze niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="d1ecd-390">U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen parameter _Name)._</span><span class="sxs-lookup"><span data-stu-id="d1ecd-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d1ecd-391">Wanneer u de naam van een anti-phishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="d1ecd-392">Als u een anti-phish-beleid wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d1ecd-393">Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="d1ecd-394">PowerShell gebruiken om anti-phish regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="d1ecd-395">De enige instelling die niet beschikbaar is wanneer u een anti-phish regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d1ecd-396">Zie de volgende sectie om bestaande anti-phishregels in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="d1ecd-397">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="d1ecd-398">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish regelsectie te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d1ecd-399">Als u een anti-phishregel wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d1ecd-400">Zie [Set-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="d1ecd-401">PowerShell gebruiken om anti-phishregels in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="d1ecd-402">Het in- of uitschakelen van een anti-phish-regel in PowerShell maakt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) mogelijk of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="d1ecd-403">U het standaardbeleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="d1ecd-404">Als u een anti-phishregel in PowerShell wilt in- of uitschakelen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="d1ecd-405">In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1ecd-406">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1ecd-407">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) en [AntiPhishRule uitschakelen](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="d1ecd-408">PowerShell gebruiken om de prioriteit van anti-phish regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="d1ecd-409">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d1ecd-410">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d1ecd-411">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d1ecd-412">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d1ecd-413">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d1ecd-414">Als u de prioriteit van een anti-phishregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d1ecd-415">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-415">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d1ecd-416">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="d1ecd-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d1ecd-417">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-417">**Notes**:</span></span>

- <span data-ttu-id="d1ecd-418">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="d1ecd-419">De standaard anti-phish beleid heeft geen overeenkomstige anti-phish regel, en het heeft altijd de onmodifiable **prioriteitswaarde Laagste**.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="d1ecd-420">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="d1ecd-421">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phishregel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="d1ecd-422">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d1ecd-423">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d1ecd-424">Zie [Remove-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="d1ecd-425">PowerShell gebruiken om anti-phish regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1ecd-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="d1ecd-426">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="d1ecd-427">Als u een anti-phishregel in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="d1ecd-428">In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1ecd-429">Zie [Remove-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="d1ecd-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d1ecd-430">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="d1ecd-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="d1ecd-431">Als u wilt controleren of u het ATP-antiphishingbeleid hebt geconfigureerd, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="d1ecd-432">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="d1ecd-433">Controleer de lijst met beleidsregels, **hun statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="d1ecd-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d1ecd-434">Als u meer details wilt weergeven, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="d1ecd-435">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="d1ecd-436">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="d1ecd-437">Vervang in Exchange Online PowerShell \<Name\> de naam van het beleid of de regel en voer de volgende opdracht uit en verifieer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
