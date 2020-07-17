---
title: Anti-phishingbeleid configureren in EOP
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
description: Beheerders kunnen leren hoe u het anti-phishingbeleid maakt, wijzigt en verwijdert dat beschikbaar is in EOP-organisaties (Exchange Online Protection) met of zonder Exchange Online-postvakken.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726783"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="80187-103">Anti-phishingbeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="80187-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="80187-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, is er een standaard antiphishingbeleid dat een beperkt aantal anti-spoofingfuncties bevat die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80187-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="80187-105">Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="80187-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="80187-106">Beheerders kunnen het standaard antiphishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="80187-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="80187-107">Voor meer granulariteit u ook aangepaste antiphishingbeleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="80187-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="80187-108">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="80187-109">Organisaties met Exchange Online-postvakken kunnen antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80187-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="80187-110">Zelfstandige EOP-organisaties kunnen alleen het Security & Compliance Center gebruiken.</span><span class="sxs-lookup"><span data-stu-id="80187-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="80187-111">Zie ATP-antiphishingbeleid configureren voor informatie over het maken en wijzigen van het geavanceerdere [ATP-antiphishingbeleid](configure-atp-anti-phishing-policies.md)dat beschikbaar is in Office 365 Advanced Threat Protection (Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="80187-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="80187-112">Anti-phishingbeleid in het Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="80187-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="80187-113">De basiselementen van een anti-phishing beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="80187-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="80187-114">**Het anti-phish-beleid**: Hiermee geeft u de bescherming tegen phishing op om in te schakelen of uit te schakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="80187-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="80187-115">**De anti-phish regel**: Hiermee geeft u de prioriteit en ontvanger filters (die het beleid van toepassing is op) voor een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="80187-116">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="80187-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="80187-117">Wanneer u een anti-phishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="80187-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="80187-118">Wanneer u een antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en ontvangersfilters de anti-phishregel.</span><span class="sxs-lookup"><span data-stu-id="80187-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="80187-119">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="80187-120">Wanneer u een anti-phishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phishregel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80187-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="80187-121">In Exchange Online PowerShell is het verschil tussen anti-phish beleid en anti-phish regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="80187-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="80187-122">Je beheert anti-phish beleid met behulp van de \*\* \* -AntiPhishPolicy\*\* cmdlets, en je beheert anti-phish regels met behulp van de \*\* \* -AntiPhishRule\*\* cmdlets.</span><span class="sxs-lookup"><span data-stu-id="80187-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="80187-123">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="80187-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="80187-124">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="80187-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="80187-125">Standaard ATP-antiphishingbeleid</span><span class="sxs-lookup"><span data-stu-id="80187-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="80187-126">Elke organisatie heeft een ingebouwd antiphishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="80187-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="80187-127">Het beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish regel (geadresseerdefilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="80187-128">Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="80187-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="80187-129">Alle aangepaste beleidsregels die u maakt, hebben altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="80187-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="80187-130">Het beleid met de naam Office365 AntiPhish Default is het standaardbeleid (de eigenschap **IsDefault** heeft de `True` waarde) en u het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80187-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="80187-131">Om de effectiviteit van anti-phishing-bescherming te vergroten, u aangepaste anti-phishing-beleid met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="80187-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80187-132">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="80187-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80187-133">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="80187-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="80187-134">Als u rechtstreeks naar de **anti-phishingpagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="80187-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="80187-135">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80187-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="80187-136">U het beleid voor phishing niet beheren in standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80187-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="80187-137">U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="80187-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="80187-138">Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="80187-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="80187-139">**Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="80187-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="80187-140">**Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="80187-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="80187-141">Voor alleen-lezen toegang tot antiphishingbeleid moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="80187-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="80187-142">**Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="80187-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="80187-143">**Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="80187-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="80187-144">Om antispambeleid in standalone EOP te kunnen maken en wijzigen, moet u iets doen waarvoor _hydratatie_ voor uw tenant vereist is.</span><span class="sxs-lookup"><span data-stu-id="80187-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="80187-145">In het Exchange-beheercentrum (EAC) u bijvoorbeeld naar het tabblad **Machtigingen** gaan, een bestaande rolgroep selecteren, **op** ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) klikken en een rol verwijderen (die u uiteindelijk weer toevoegt).</span><span class="sxs-lookup"><span data-stu-id="80187-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="80187-146">Als uw tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **Organisatie-instellingen bijwerken** met een voortgangsbalk die moet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="80187-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="80187-147">Zie de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in standalone EOP PowerShell of in het Security & Compliance Center) voor meer informatie over hydratatie.</span><span class="sxs-lookup"><span data-stu-id="80187-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="80187-148">Zie [EOP-standaardbeleidsinstellingen voor antiphishing voor](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)onze aanbevolen instellingen voor antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="80187-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="80187-149">Sta maximaal 30 minuten toe om het bijgewerkte beleid toe te passen.</span><span class="sxs-lookup"><span data-stu-id="80187-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="80187-150">Zie [Volgorde en voorrang van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.</span><span class="sxs-lookup"><span data-stu-id="80187-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="80187-151">Gebruik het Security & Compliance Center om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="80187-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="80187-152">Als u een aangepast antiphishingbeleid maakt in het Security & Compliance Center, worden tegelijkertijd de anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="80187-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="80187-153">Wanneer u een antiphishingbeleid maakt, u alleen de beleidsnaam, de beschrijving en het ontvangerfilter opgeven waarop wordt aangegeven op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="80187-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="80187-154">Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te bekijken.</span><span class="sxs-lookup"><span data-stu-id="80187-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="80187-155">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-156">Klik op de pagina **Anti-phishing** op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="80187-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="80187-157">De wizard Een nieuw beleid maken met **een ander beleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="80187-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="80187-158">Configureer op de pagina **Naam van uw beleid** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="80187-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="80187-159">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="80187-160">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="80187-161">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="80187-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="80187-162">Identificeer **op** de pagina Toegepast op die wordt weergegeven de interne ontvangers waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="80187-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="80187-163">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="80187-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="80187-164">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="80187-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="80187-165">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="80187-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="80187-166">Klik **op Een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="80187-166">Click **Add a condition**.</span></span> <span data-ttu-id="80187-167">Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:</span><span class="sxs-lookup"><span data-stu-id="80187-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="80187-168">**De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="80187-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="80187-169">**De ontvanger is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="80187-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="80187-170">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="80187-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="80187-171">Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met **een van deze** opties.</span><span class="sxs-lookup"><span data-stu-id="80187-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="80187-172">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="80187-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="80187-173">Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="80187-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="80187-174">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="80187-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="80187-175">Als u afzonderlijke vermeldingen wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="80187-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="80187-176">Als u de hele **Remove** voorwaarde wilt verwijderen, klikt u ![ op pictogram Verwijderen op de ](../../media/scc-remove-icon.png) voorwaarde verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80187-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="80187-177">Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="80187-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="80187-178">Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="80187-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="80187-179">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="80187-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="80187-180">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="80187-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="80187-181">Controleer **op** de pagina Uw instellingen die wordt weergegeven de instellingen controleren.</span><span class="sxs-lookup"><span data-stu-id="80187-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="80187-182">U op Elke instelling op **Bewerken** klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="80187-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="80187-183">Klik op **Dit beleid maken**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="80187-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="80187-184">Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="80187-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="80187-185">Nadat u het antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="80187-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="80187-186">Gebruik het Security & Compliance Center om het antiphishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="80187-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="80187-187">Gebruik de volgende procedures om het antiphishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of een bestaand beleid dat u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="80187-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="80187-188">Als u er nog niet bent, opent u het Security & Compliance Center en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-189">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="80187-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="80187-190">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="80187-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="80187-191">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="80187-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="80187-192">Als u op **Bewerken** in een sectie klikt, krijgt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="80187-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="80187-193">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in willekeurige volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="80187-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="80187-194">Nadat u in een sectie op Bewerken hebt **geklikt,** worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in willekeurige volgorde binnen de pagina's springen en op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten sluiten** om terug te keren naar de pagina Uw beleid ![ ](../../media/scc-remove-icon.png) \*\* \<name\> bewerken\*\* (u hoeft de laatste pagina van de wizard niet te bezoeken om op te slaan of te vertrekken).</span><span class="sxs-lookup"><span data-stu-id="80187-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="80187-195">**Beleidsinstelling**: klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="80187-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="80187-196">**Naam**</span><span class="sxs-lookup"><span data-stu-id="80187-196">**Name**</span></span>
   - <span data-ttu-id="80187-197">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="80187-197">**Description**</span></span>
   - <span data-ttu-id="80187-198">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="80187-198">**Applied to**</span></span>
   - <span data-ttu-id="80187-199">**Uw instellingen bekijken**</span><span class="sxs-lookup"><span data-stu-id="80187-199">**Review your settings**</span></span>

   <span data-ttu-id="80187-200">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="80187-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="80187-201">**Spoof**: klik op **Bewerken** om spoofinformatie in of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="80187-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="80187-202">Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="80187-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="80187-203">Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in het ATP-anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="80187-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="80187-204">**Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten.</span><span class="sxs-lookup"><span data-stu-id="80187-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="80187-205">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.</span><span class="sxs-lookup"><span data-stu-id="80187-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="80187-206">Zie [Spoofintelligentie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="80187-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="80187-207">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u in plaats daarvan Uitgebreide filtering voor connectoren inschakelt.</span><span class="sxs-lookup"><span data-stu-id="80187-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="80187-208">Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="80187-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="80187-209">**Functie niet-geverifieerde afzender inschakelen:** de standaardwaarde is **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="80187-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="80187-210">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.</span><span class="sxs-lookup"><span data-stu-id="80187-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="80187-211">**Acties**: Geef de actie op die moet worden uitgevoerd op berichten die niet intelligentie hebben:</span><span class="sxs-lookup"><span data-stu-id="80187-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="80187-212">**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**</span><span class="sxs-lookup"><span data-stu-id="80187-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="80187-213">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="80187-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="80187-214">**Quarantaine het bericht**</span><span class="sxs-lookup"><span data-stu-id="80187-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="80187-215">**Uw instellingen bekijken:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="80187-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="80187-216">U in elke sectie op **Bewerken** klikken om terug te springen naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="80187-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="80187-217">U de volgende instellingen rechtstreeks **in-** of **uitschakelen** op deze pagina:</span><span class="sxs-lookup"><span data-stu-id="80187-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="80187-218">**Bescherming tegenpoofing inschakelen**</span><span class="sxs-lookup"><span data-stu-id="80187-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="80187-219">**Functie niet-geverifieerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="80187-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="80187-220">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="80187-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="80187-221">Terug op de pagina **Uw beleid \<Name\> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="80187-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="80187-222">Gebruik het Security & Compliance Center om het standaard anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="80187-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="80187-223">Het standaardbeleid voor antiphishing wordt Office365 AntiPhish Default genoemd en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="80187-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="80187-224">Als u het standaardbeleid voor antiphishing wilt wijzigen, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="80187-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="80187-225">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-226">Klik op de pagina **Antiphishing** op **Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="80187-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="80187-227">De pagina **Office365 AntiPhish Default-standaard** van het beleid bewerken, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="80187-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="80187-228">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="80187-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="80187-229">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="80187-229">**Impersonation**</span></span>
   - <span data-ttu-id="80187-230">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="80187-230">**Spoof**</span></span>
   - <span data-ttu-id="80187-231">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="80187-231">**Advanced settings**</span></span>

   <span data-ttu-id="80187-232">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="80187-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="80187-233">U de sectie **Beleidsinstelling** en waarden zien, maar er is geen koppeling **bewerken,** dus u de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (het is van toepassing op alle ontvangers)).</span><span class="sxs-lookup"><span data-stu-id="80187-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="80187-234">U het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80187-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="80187-235">U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="80187-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="80187-236">Bekijk op de pagina **Office365 AntiPhish Default bewerken** de instellingen en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="80187-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="80187-237">Aangepast antiphishingbeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80187-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="80187-238">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-239">Let op de waarde in de kolom **Status:**</span><span class="sxs-lookup"><span data-stu-id="80187-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="80187-240">Schuif de schakel naar **Uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="80187-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="80187-241">Schuif de schakelaar **naar Aan** om het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="80187-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="80187-242">U het standaardbeleid voor antiphishing niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="80187-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="80187-243">De prioriteit van aangepast antiphishingbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="80187-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="80187-244">Antiphishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="80187-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="80187-245">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="80187-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="80187-246">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="80187-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="80187-247">Aangepaste anti-phishingbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="80187-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="80187-248">Het standaardbeleid voor antiphishing met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste**en u deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="80187-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="80187-249">**Opmerking:** In het Security & Compliance Center u de prioriteit van het antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="80187-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="80187-250">In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="80187-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="80187-251">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet direct wijzigen in het Security & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="80187-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="80187-252">Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="80187-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="80187-253">Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.</span><span class="sxs-lookup"><span data-stu-id="80187-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="80187-254">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="80187-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="80187-255">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="80187-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="80187-256">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="80187-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="80187-257">Het aangepaste anti-phishingbeleid met de **prioriteitswaarde** **0** heeft alleen de knop **Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="80187-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="80187-258">Het aangepaste anti-phishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="80187-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="80187-259">Als u drie of meer aangepaste antiphishingbeleid hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de knoppen **Prioriteit Verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="80187-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="80187-260">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="80187-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="80187-261">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="80187-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="80187-262">Gebruik het Security & Compliance Center om antiphishingbeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="80187-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="80187-263">In het Security & Compliance Center en ga naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-264">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="80187-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="80187-265">Selecteer een aangepast antiphishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="80187-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="80187-266">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="80187-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="80187-267">Klik **op Standaardbeleid** om het standaardbeleid voor phishing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="80187-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="80187-268">De flyout **van uw beleid \<name\> bewerken** wordt weergegeven, waar u de instellingen en waarden bekijken.</span><span class="sxs-lookup"><span data-stu-id="80187-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="80187-269">Gebruik het Security & Compliance Center om antiphishingbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="80187-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="80187-270">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="80187-271">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80187-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="80187-272">Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="80187-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="80187-273">Klik in de flyout **beleid \<name\> bewerken** die wordt weergegeven op **Beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="80187-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="80187-274">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80187-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="80187-275">Exchange Online PowerShell gebruiken om antiphishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="80187-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="80187-276">De volgende procedures zijn niet beschikbaar in zelfstandige EOP-organisaties.</span><span class="sxs-lookup"><span data-stu-id="80187-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="80187-277">PowerShell gebruiken om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="80187-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="80187-278">Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="80187-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="80187-279">Maak het anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="80187-280">Maak de anti-phish regel die het anti-phish beleid aangeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="80187-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="80187-281">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="80187-281">**Notes**:</span></span>

- <span data-ttu-id="80187-282">U een nieuwe anti-phish regel maken en er een bestaand, niet-gekoppeld anti-phish beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="80187-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="80187-283">Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="80187-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="80187-284">U de volgende instellingen voor nieuw antifromancebeleid configureren in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="80187-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="80187-285">Maak het nieuwe beleid als uitgeschakeld (_Ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="80187-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="80187-286">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="80187-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="80187-287">Een nieuw anti-phish-beleid dat u maakt in PowerShell, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish regel.</span><span class="sxs-lookup"><span data-stu-id="80187-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="80187-288">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="80187-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="80187-289">Als u een anti-phish-beleid wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="80187-290">In dit voorbeeld wordt een anti-phish-beleid met de naam Research Quarantine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="80187-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="80187-291">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld niet_ en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="80187-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="80187-292">De beschrijving is: Onderzoek afdelingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="80187-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="80187-293">Hiermee wijzigt u de standaardactie voor spoofing in Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="80187-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="80187-294">Zie [Nieuw-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="80187-295">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="80187-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="80187-296">Als u een anti-phish-regel wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="80187-297">In dit voorbeeld wordt een anti-phish-regel met de naam Research Department gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="80187-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="80187-298">De regel is gekoppeld aan het anti-phish beleid genaamd Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="80187-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="80187-299">De regel is van toepassing op leden van de groep met de naam Research Department.</span><span class="sxs-lookup"><span data-stu-id="80187-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="80187-300">Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="80187-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="80187-301">Zie [Nieuw-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="80187-302">PowerShell gebruiken om anti-phish-beleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="80187-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="80187-303">Als u bestaande anti-phish-beleid wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80187-304">In dit voorbeeld wordt een overzichtslijst geretourneerd met alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="80187-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="80187-305">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phish-beleid met de naam Executives.</span><span class="sxs-lookup"><span data-stu-id="80187-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="80187-306">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="80187-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="80187-307">PowerShell gebruiken om anti-phish regels te bekijken</span><span class="sxs-lookup"><span data-stu-id="80187-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="80187-308">Als u bestaande anti-phishregels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80187-309">In dit voorbeeld wordt een overzichtslijst van alle anti-phishregels samen met de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="80187-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="80187-310">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="80187-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="80187-311">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="80187-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="80187-312">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="80187-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="80187-313">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="80187-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="80187-314">Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish beleidssectie te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)</span><span class="sxs-lookup"><span data-stu-id="80187-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="80187-315">De _Schakelaar Fout maken_ die het opgegeven beleid verandert in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u deze niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80187-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="80187-316">U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen parameter _Name)._</span><span class="sxs-lookup"><span data-stu-id="80187-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="80187-317">Wanneer u de naam van een anti-phishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel .</span><span class="sxs-lookup"><span data-stu-id="80187-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="80187-318">Als u een anti-phish-beleid wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="80187-319">Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="80187-320">PowerShell gebruiken om anti-phish regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="80187-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="80187-321">De enige instelling die niet beschikbaar is wanneer u een anti-phish regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="80187-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="80187-322">Zie de volgende sectie om bestaande anti-phishregels in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="80187-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="80187-323">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80187-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="80187-324">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish regelsectie te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)</span><span class="sxs-lookup"><span data-stu-id="80187-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="80187-325">Als u een anti-phishregel wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="80187-326">Zie [Set-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="80187-327">PowerShell gebruiken om anti-phishregels in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="80187-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="80187-328">Het in- of uitschakelen van een anti-phish-regel in PowerShell maakt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) mogelijk of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80187-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="80187-329">U het standaardbeleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="80187-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="80187-330">Als u een anti-phishregel in PowerShell wilt in- of uitschakelen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="80187-331">In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80187-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="80187-332">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80187-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="80187-333">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) en [AntiPhishRule uitschakelen](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="80187-334">PowerShell gebruiken om de prioriteit van anti-phish regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="80187-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="80187-335">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="80187-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="80187-336">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="80187-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="80187-337">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="80187-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="80187-338">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="80187-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="80187-339">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="80187-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="80187-340">Als u de prioriteit van een anti-phishregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="80187-341">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="80187-341">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="80187-342">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="80187-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="80187-343">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="80187-343">**Notes**:</span></span>

- <span data-ttu-id="80187-344">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="80187-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="80187-345">De standaard anti-phish beleid heeft geen overeenkomstige anti-phish regel, en het heeft altijd de onmodifiable **prioriteitswaarde Laagste**.</span><span class="sxs-lookup"><span data-stu-id="80187-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="80187-346">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="80187-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="80187-347">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phishregel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80187-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="80187-348">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="80187-349">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80187-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="80187-350">Zie [Remove-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="80187-351">PowerShell gebruiken om anti-phish regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="80187-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="80187-352">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80187-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="80187-353">Als u een anti-phishregel in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="80187-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="80187-354">In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80187-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="80187-355">Zie [Remove-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="80187-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="80187-356">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="80187-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="80187-357">Als u wilt controleren of u het ATP-antiphishingbeleid hebt geconfigureerd, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="80187-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="80187-358">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="80187-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="80187-359">Controleer de lijst met beleidsregels, **hun statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="80187-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="80187-360">Als u meer details wilt weergeven, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="80187-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="80187-361">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="80187-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="80187-362">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="80187-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="80187-363">Vervang in Exchange Online PowerShell \<Name\> de naam van het beleid of de regel en voer de volgende opdracht uit en verifieer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="80187-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
