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
description: Beheerders kunnen leren hoe u de geavanceerde antiphishingbeleidsregels maken, wijzigen en verwijderen die beschikbaar zijn in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: efecd830db7ed10210605e31aa0ded2599de1b72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208885"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-103">ATP-beleid tegen phishing configureren</span><span class="sxs-lookup"><span data-stu-id="7fdf2-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="7fdf2-104">ATP-beleid voor phishing maakt deel uit van [Office 365 Advanced Threat Protection.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7fdf2-105">ATP-beleid tegen phishing kan uw organisatie beschermen tegen schadelijke phishing-aanvallen en andere vormen van phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="7fdf2-106">Zie [Anti-phishingbescherming](anti-phishing-protection.md)voor meer informatie over de verschillen tussen antiphishingbeleid in Exchange Online Protection (EOP) en ATP-antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="7fdf2-107">Beheerders kunnen het standaard ATP-antiphishingbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="7fdf2-108">Voor meer granulariteit u ook aangepaste ATP-antiphishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="7fdf2-109">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="7fdf2-110">U ATP-antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="7fdf2-111">Zie [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van de beperktere antiphishingbeleidsregels die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen Microsoft 365-organisaties zonder Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="7fdf2-112">ATP-antiphishingbeleid in het Security & Compliance Center vs Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fdf2-112">ATP anti-phishing policies in the Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="7fdf2-113">De basiselementen van een ATP anti-phishing beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="7fdf2-114">**Het anti-phish-beleid**: Hiermee geeft u de phishingbeveiligingen op om in te schakelen of uit te schakelen, en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="7fdf2-115">**De anti-phish-regel**: Geeft de prioriteits- en ontvangerfilters (op wie het beleid van toepassing is) op voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="7fdf2-116">Het verschil tussen deze twee elementen is niet duidelijk wanneer u ATP-antiphishingbeleid beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="7fdf2-117">Wanneer u een ATP-antiphishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="7fdf2-118">Wanneer u een ATP-antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en wijzigen de filters voor ontvangers de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="7fdf2-119">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="7fdf2-120">Wanneer u een ATP-antiphishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="7fdf2-121">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="7fdf2-122">U beheert anti-phish-beleid met behulp van de cmdlets \*\* \* -AntiPhishPolicy\*\* en u beheert anti-phish-regels met behulp van de \*\* \* cmdlets -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="7fdf2-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="7fdf2-123">In PowerShell maakt u eerst het anti-phish-beleid, vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="7fdf2-124">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="7fdf2-125">Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="7fdf2-126">Standaard ATP anti-phishing beleid</span><span class="sxs-lookup"><span data-stu-id="7fdf2-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="7fdf2-127">Elke ATP-organisatie heeft een ingebouwd ATP-antiphishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="7fdf2-128">Het anti-phish-beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="7fdf2-129">Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="7fdf2-130">Elk aangepast beleid dat u maakt, heeft altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="7fdf2-131">Het beleid met de naam Office365 AntiPhish Default is het standaardbeleid (de eigenschap **IsDefault** heeft de `True` waarde) en u het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="7fdf2-132">Om de effectiviteit van anti-phishingbescherming te vergroten, u aangepaste ATP-antiphishingbeleidsregels maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7fdf2-133">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="7fdf2-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7fdf2-134">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7fdf2-135">Gebruik **ATP anti-phishing** <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="7fdf2-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="7fdf2-136">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7fdf2-137">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7fdf2-138">Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="7fdf2-139">Voor alleen-lezen toegang tot anti-phishingbeleid moet u lid zijn van de rolgroep **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="7fdf2-140">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7fdf2-141">Zie Beleidsinstellingen voor [antiphishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)van Office ATP voor onze aanbevolen instellingen voor atp-antiphishing.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-141">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="7fdf2-142">Sta maximaal 30 minuten toe om een nieuw of bijgewerkt beleid toe te passen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="7fdf2-143">Zie [Volgorde en voorrang van e-mailbeveiliging voor](how-policies-and-protections-are-combined.md)informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-144">Gebruik het Security & Compliance Center om ATP-antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="7fdf2-144">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="7fdf2-145">Als u een aangepast ATP-antiphishingbeleid maakt in het Security & Compliance Center, wordt de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-145">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="7fdf2-146">Wanneer u een ATP-antiphishingbeleid maakt, u alleen de beleidsnaam, beschrijving en het filter voor de ontvanger opgeven dat aangeeft op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-146">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="7fdf2-147">Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="7fdf2-148">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-149">Klik op de **antiphishingpagina** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="7fdf2-150">De wizard Een nieuwe wizard **antiphishingbeleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="7fdf2-151">Configureer op **de pagina Naam van uw beleid** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="7fdf2-152">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="7fdf2-153">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="7fdf2-154">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7fdf2-155">Identificeer **op** de pagina Toegepast op die wordt weergegeven, de interne ontvangers waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="7fdf2-156">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="7fdf2-157">Meerdere waarden van dezelfde voorwaarde of uitzondering gebruiken OF-logica (bijv.: _\<afzender1\>_ of _\<afzender2\>_).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="7fdf2-158">Verschillende voorwaarden of uitzonderingen gebruiken EN-logica (bijv.: _\<geadresseerde1\>_ en _\<lid van groep 1\>_).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="7fdf2-159">Klik **op Een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-159">Click **Add a condition**.</span></span> <span data-ttu-id="7fdf2-160">Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="7fdf2-161">**De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="7fdf2-162">**De ontvanger is lid van**: Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="7fdf2-163">**Het domein van de geadresseerde is**: Hiermee geeft u ontvangers op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="7fdf2-164">Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met een **elk vak.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="7fdf2-165">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="7fdf2-166">Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="7fdf2-167">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="7fdf2-168">Als u afzonderlijke vermeldingen **Remove** wilt verwijderen, klikt u ![ op Pictogram Verwijderen op de waarde ](../../media/scc-remove-icon.png) verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="7fdf2-169">Als u de hele **Remove** voorwaarde wilt verwijderen, klikt u ![ op Pictogram Verwijderen op ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="7fdf2-170">Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="7fdf2-171">Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="7fdf2-172">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="7fdf2-173">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7fdf2-174">Controleer op de pagina **Uw instellingen controleren** die wordt weergegeven, uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="7fdf2-175">U op **Bewerken** op elke instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="7fdf2-176">Klik op **Dit beleid maken**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="7fdf2-177">Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="7fdf2-178">Nadat u het ATP-antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-178">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-179">Gebruik het Security & Compliance Center om het ANTI-phishingbeleid van ATP te wijzigen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-179">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="7fdf2-180">Gebruik de volgende procedures om het ANTI-phishingbeleid van ATP te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-180">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="7fdf2-181">Als u er nog niet bent, opent u het Beveiligingscentrum & Compliance center en gaat u naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-182">Selecteer het aangepaste ATP-antiphishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-182">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="7fdf2-183">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7fdf2-184">De flyout met de naam bewerken van \*\*uw beleid \< \> \*\* wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="7fdf2-185">Als u in een sectie op **Bewerken** klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="7fdf2-186">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="7fdf2-187">Nadat u in een sectie op **Bewerken** hebt geklikt, worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in elke volgorde binnen de pagina's springen en u op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten** sluiten om terug te keren naar de pagina Uw ![ ](../../media/scc-remove-icon.png) \*\* \< beleidsnaam \> \*\* bewerken (u hoeft niet de laatste pagina van de wizard te bezoeken om op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="7fdf2-188">**Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het beleid in de vorige sectie [maakte:](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="7fdf2-189">**Naam**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-189">**Name**</span></span>
   - <span data-ttu-id="7fdf2-190">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-190">**Description**</span></span>
   - <span data-ttu-id="7fdf2-191">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-191">**Applied to**</span></span>
   - <span data-ttu-id="7fdf2-192">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-192">**Review your settings**</span></span>

   <span data-ttu-id="7fdf2-193">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="7fdf2-194">**Imitatie**: Klik op **Bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="7fdf2-195">Deze instellingen zijn een voorwaarde voor het beleid dat vervalste afzenders identificeert om te zoeken (individueel of per domein) in het Adres van binnenkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="7fdf2-196">Zie [Instellingen voor imitatie in het ANTI-phishingbeleid van ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="7fdf2-196">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="7fdf2-197">**Gebruikers toevoegen om te beschermen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-198">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**en klikt u op de **knop Gebruiker toevoegen** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="7fdf2-199">Configureer in de flyout **van de gebruiker toevoegen** de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="7fdf2-200">**E-mailadres:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-200">**Email address**:</span></span>

        - <span data-ttu-id="7fdf2-201">Klik in het vak en blader door de lijst met gebruikers om te selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-201">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="7fdf2-202">Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-202">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="7fdf2-203">Als u een **Remove** item wilt verwijderen, klikt u ![ op Pictogram Verwijderen op de ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="7fdf2-204">**Naam:** Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="7fdf2-205">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-205">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="7fdf2-206">Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-206">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="7fdf2-207">**Domeinen toevoegen om te beschermen:** Configureer een of beide van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-207">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="7fdf2-208">**Automatisch de domeinen opnemen die ik bezit:** De standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-208">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-209">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-209">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="7fdf2-210">**Aangepaste domeinen opnemen:** de standaardwaarde is **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-210">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-211">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**en voert u in het vak **Domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaal t/m indien nodig.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-211">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="7fdf2-212">**Acties**: Klik op **Bewerken**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-212">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="7fdf2-213">**Als e-mail wordt verzonden door een nagebootste gebruiker:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in **Gebruikers toevoegen om te beschermen:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-213">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="7fdf2-214">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-214">**Don't apply any action**</span></span>
       - <span data-ttu-id="7fdf2-215">**Bericht doorverwijzen naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-215">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="7fdf2-216">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-216">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="7fdf2-217">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-217">**Quarantine the message**</span></span>
       - <span data-ttu-id="7fdf2-218">**Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-218">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="7fdf2-219">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-219">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="7fdf2-220">**Als e-mail wordt verzonden door een nagebootst domein:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender zich bevindt in een van de beveiligde domeinen die u hebt opgegeven in **Domeinen toevoegen om te beschermen:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-220">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="7fdf2-221">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-221">**Don't apply any action**</span></span>
     - <span data-ttu-id="7fdf2-222">**Bericht doorverwijzen naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-222">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="7fdf2-223">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-223">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="7fdf2-224">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-224">**Quarantine the message**</span></span>
     - <span data-ttu-id="7fdf2-225">**Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-225">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="7fdf2-226">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-226">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="7fdf2-227">Klik **op veiligheidstips voor imitatie inschakelen** en configureer een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-227">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="7fdf2-228">**Tip weergeven voor geïmiteerde gebruikers:** de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-228">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-229">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-229">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="7fdf2-230">**Tip weergeven voor nagebootste domeinen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-230">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-231">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="7fdf2-232">**Tip weergeven voor ongebruikelijke tekens:** de standaardwaarde is **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-232">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="7fdf2-233">Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-233">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="7fdf2-234">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-234">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="7fdf2-235">**Postvak intelligentie:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-235">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="7fdf2-236">**Postvakintelligentie inschakelen?**: De standaardwaarde is **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-236">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="7fdf2-237">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-237">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="7fdf2-238">**Bescherming voor op postinformatie gebaseerde imitatiebeveiliging inschakelen?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen?** is **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-238">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="7fdf2-239">Als **e-mail wordt verzonden door een nagebootste gebruiker,** u een van de volgende acties opgeven die moeten worden uitgevoerd op berichten die niet voldoen aan postvakinformatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="7fdf2-239">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="7fdf2-240">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-240">**Don't apply any action**</span></span>
       - <span data-ttu-id="7fdf2-241">**Bericht doorverwijzen naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-241">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="7fdf2-242">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-242">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="7fdf2-243">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-243">**Quarantine the message**</span></span>
       - <span data-ttu-id="7fdf2-244">**Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-244">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="7fdf2-245">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-245">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="7fdf2-246">**Vertrouwde afzenders en domeinen toevoegen:** Geef uitzonderingen op voor het beleid:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-246">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="7fdf2-247">**Vertrouwde afzenders:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-247">**Trusted senders**:</span></span>

       - <span data-ttu-id="7fdf2-248">Klik in het vak en blader door de lijst met gebruikers om te selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-248">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="7fdf2-249">Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-249">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="7fdf2-250">Als u een **Remove** item wilt verwijderen, klikt u ![ op Pictogram Verwijderen op de ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-250">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="7fdf2-251">**Vertrouwde domeinen**: Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal indien nodig.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-251">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="7fdf2-252">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-252">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="7fdf2-253">U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-253">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="7fdf2-254">U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-254">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="7fdf2-255">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-255">**Protected users**</span></span>
       - <span data-ttu-id="7fdf2-256">**Beveiligde domeinen** \> **Domeinen opnemen waarvan ik eigenaar ben**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-256">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="7fdf2-257">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-257">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="7fdf2-258">**Postvakintelligentie**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-258">**Mailbox intelligence**</span></span>

   <span data-ttu-id="7fdf2-259">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-259">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="7fdf2-260">**Spoof:** klik op **Bewerken** om spoofinformatie in- of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-260">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="7fdf2-261">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-261">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="7fdf2-262">Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in anti-phishingbeleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-262">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="7fdf2-263">**Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-263">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="7fdf2-264">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-264">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="7fdf2-265">Zie [Spoofinformatie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-265">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="7fdf2-266">U hoeft anti-spoofingbescherming niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u schakelt in plaats daarvan Uitgebreide filtering voor connectors in.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-266">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="7fdf2-267">Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .</span><span class="sxs-lookup"><span data-stu-id="7fdf2-267">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="7fdf2-268">**Functie Niet-geverifieerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-268">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="7fdf2-269">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-269">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="7fdf2-270">**Acties:** Geef de actie op die moet worden uitgevoerd met berichten die niet in de spoofinformatie zijn geslaagd:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-270">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="7fdf2-271">**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-271">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="7fdf2-272">**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-272">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="7fdf2-273">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-273">**Quarantine the message**</span></span>

   - <span data-ttu-id="7fdf2-274">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-274">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="7fdf2-275">U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-275">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="7fdf2-276">U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-276">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="7fdf2-277">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-277">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="7fdf2-278">**Functie Niet-geverifieerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-278">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="7fdf2-279">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-279">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="7fdf2-280">**Geavanceerde instellingen:** Klik op **Bewerken** om de geavanceerde phishingdrempels te configureren.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-280">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="7fdf2-281">Zie [Geavanceerde phishingdrempels in het ATP-beleid voor phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-281">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="7fdf2-282">**Geavanceerde phishingdrempels:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-282">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="7fdf2-283">**1 - Standaard** (dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-283">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="7fdf2-284">**2 - Agressief**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-284">**2 - Aggressive**</span></span>
   - <span data-ttu-id="7fdf2-285">**3 - Agressiever**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-285">**3 - More aggressive**</span></span>
   - <span data-ttu-id="7fdf2-286">**4 - Meest agressieve**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-286">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="7fdf2-287">**Uw instellingen controleren:** klik op **Bewerken** om terug te gaan naar de pagina **Geavanceerde phishingdrempels.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-287">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="7fdf2-288">Klik op Opslaan op **een** van beide pagina's als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-288">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="7fdf2-289">Terug op de pagina **Uw \< beleidsnaam \> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**klikken.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-289">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="7fdf2-290">Gebruik het Beveiligings- & Compliance Center om het standaard BELEID voor ANTI-phishing van ATP te wijzigen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-290">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="7fdf2-291">Het standaard BELEID voor antiphishing van ATP heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-291">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="7fdf2-292">Ga als volgt te werk om het standaard BELEID voor ANTI-phishing van ATP te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-292">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="7fdf2-293">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-293">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-294">Klik op de pagina **Anti-phishing** op **Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-294">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="7fdf2-295">De pagina **Standaardinstelling voor uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-295">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="7fdf2-296">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-296">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="7fdf2-297">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-297">**Impersonation**</span></span>
   - <span data-ttu-id="7fdf2-298">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-298">**Spoof**</span></span>
   - <span data-ttu-id="7fdf2-299">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-299">**Advanced settings**</span></span>

   <span data-ttu-id="7fdf2-300">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-300">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="7fdf2-301">U de sectie **Beleidsinstelling** en waarden zien, maar er is geen **koppeling Bewerken,** dus u de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is op niet wijzigen (het is van toepassing op alle ontvangers)).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-301">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="7fdf2-302">U het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-302">You can't delete the default policy.</span></span>
   - <span data-ttu-id="7fdf2-303">U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-303">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="7fdf2-304">Controleer op de pagina **Standaardbeleid Office365 AntiPhish bewerken** uw instellingen en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-304">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-305">Aangepaste ATP-antiphishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-305">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7fdf2-306">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-306">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-307">Let op de waarde in de kolom **Status:**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-307">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="7fdf2-308">Schuif de schakel naar **Uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-308">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="7fdf2-309">Schuif de schakelaar naar **Aan** om het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-309">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="7fdf2-310">U het standaard antiphishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-310">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-311">De prioriteit instellen van aangepast ATP-antiphishingbeleid</span><span class="sxs-lookup"><span data-stu-id="7fdf2-311">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="7fdf2-312">Standaard krijgt het ATP-antiphishingbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwer beleid heeft een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-312">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="7fdf2-313">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-313">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="7fdf2-314">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-314">No two policies can have the same priority.</span></span>

<span data-ttu-id="7fdf2-315">Aangepaste ATP-antiphishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="7fdf2-316">Het standaard antiphishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste**en u deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="7fdf2-317">**Opmerking:** In het Security & Compliance Center u de prioriteit van het ATP-antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="7fdf2-318">In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="7fdf2-319">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet rechtstreeks wijzigen in het Beveiligings& Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="7fdf2-320">Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="7fdf2-321">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-322">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="7fdf2-323">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7fdf2-324">De flyout met de naam bewerken van \*\*uw beleid \< \> \*\* wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="7fdf2-325">Het aangepaste ATP-antiphishingbeleid met de **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="7fdf2-326">Het aangepaste ATP-antiphishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="7fdf2-327">Als u drie of meer aangepaste antiphishingbeleidsregels hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de **prioriteitsprioriteit verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="7fdf2-328">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="7fdf2-329">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-330">Gebruik het Beveiligingscentrum & Compliance Center om het ANTI-phishingbeleid van ATP weer te geven</span><span class="sxs-lookup"><span data-stu-id="7fdf2-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7fdf2-331">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-332">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="7fdf2-333">Selecteer een aangepast ATP-antiphishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="7fdf2-334">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="7fdf2-335">Klik **op Standaardbeleid** om het standaard beleid voor antiphishing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="7fdf2-336">De flyout met de naam bewerken van \*\*uw beleid \< \> \*\* wordt weergegeven, waar u de instellingen en waarden bekijken.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-337">Gebruik het Beveiligings- & Compliance Center om het ANTI-phishingbeleid van ATP te verwijderen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7fdf2-338">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7fdf2-339">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="7fdf2-340">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7fdf2-341">Klik in de flyout **van de \< \> beleidsnaam bewerken** die wordt weergegeven op Beleid **verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="7fdf2-342">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="7fdf2-343">Exchange Online PowerShell gebruiken om ATP-antiphishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="7fdf2-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="7fdf2-344">PowerShell gebruiken om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="7fdf2-344">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="7fdf2-345">Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-345">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="7fdf2-346">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-346">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="7fdf2-347">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-347">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="7fdf2-348">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-348">**Notes**:</span></span>

- <span data-ttu-id="7fdf2-349">U een nieuwe anti-phish-regel maken en er een bestaand, niet-geassocieerd anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-349">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="7fdf2-350">Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-350">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="7fdf2-351">U de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-351">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="7fdf2-352">Het nieuwe beleid als uitgeschakeld maken _(ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-352">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="7fdf2-353">Stel de prioriteit in van het beleid tijdens het maken ( _ \< \> Prioriteitsnummer_) op de cmdlet **Nieuw-AntiPhishRule.** _Priority_</span><span class="sxs-lookup"><span data-stu-id="7fdf2-353">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="7fdf2-354">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-354">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="7fdf2-355">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="7fdf2-355">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="7fdf2-356">Als u een anti-phish-beleid wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-356">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="7fdf2-357">In dit voorbeeld wordt anti-phish-beleid met de naam Research Quarantine met de volgende instellingen gemaakt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-357">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="7fdf2-358">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-358">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="7fdf2-359">De beschrijving is: Het beleid van de afdeling van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-359">The description is: Research department policy.</span></span>
- <span data-ttu-id="7fdf2-360">Hiermee u organisatiedomeinen beveiliging voor alle geaccepteerde domeinen en gerichte domeinenbescherming voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-360">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="7fdf2-361">Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker om te beschermen tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-361">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="7fdf2-362">Hiermee schakelt u postvakintelligentie in.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-362">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="7fdf2-363">Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-363">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="7fdf2-364">Hiermee kunnen veiligheidstips worden gegeven.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-364">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="7fdf2-365">Zie [Nieuw-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-365">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="7fdf2-366">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="7fdf2-366">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="7fdf2-367">Als u een anti-phish-regel wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-367">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="7fdf2-368">In dit voorbeeld wordt een anti-phish-regel met de naam Research Department met de volgende voorwaarden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-368">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="7fdf2-369">De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-369">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="7fdf2-370">De regel is van toepassing op leden van de groep met de naam Research Department.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-370">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="7fdf2-371">Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-371">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="7fdf2-372">Zie [Nieuw-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-372">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="7fdf2-373">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="7fdf2-373">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="7fdf2-374">Als u bestaande anti-phish-beleidsregels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-374">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7fdf2-375">In dit voorbeeld wordt een overzichtslijst geretourneerd van alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-375">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="7fdf2-376">In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-376">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="7fdf2-377">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-377">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="7fdf2-378">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="7fdf2-378">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="7fdf2-379">Als u bestaande anti-phish-regels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-379">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7fdf2-380">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels geretourneerd, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-380">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="7fdf2-381">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-381">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="7fdf2-382">In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-382">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="7fdf2-383">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-383">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="7fdf2-384">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-384">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="7fdf2-385">Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp een sectie [anti-phish-beleid te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-385">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="7fdf2-386">De _Switch MakeDefault_ die het opgegeven beleid inschakelt in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-386">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="7fdf2-387">U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _parameter Naam)._</span><span class="sxs-lookup"><span data-stu-id="7fdf2-387">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="7fdf2-388">Wanneer u de naam van een antiphishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-388">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="7fdf2-389">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-389">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="7fdf2-390">Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-390">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="7fdf2-391">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-391">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="7fdf2-392">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-392">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="7fdf2-393">Zie de volgende sectie om bestaande anti-phish-regels in te schakelen of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-393">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="7fdf2-394">Anders zijn er geen aanvullende instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-394">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="7fdf2-395">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een sectie anti-phish-regel te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)</span><span class="sxs-lookup"><span data-stu-id="7fdf2-395">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="7fdf2-396">Als u een anti-phish-regel wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-396">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="7fdf2-397">Zie [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="7fdf2-397">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="7fdf2-398">PowerShell gebruiken om anti-phish-regels in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-398">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="7fdf2-399">Het in- of uitschakelen van een anti-phish-regel in PowerShell schakelt of schakelt het hele anti-phishingbeleid in of uit (de anti-phish-regel en het toegewezen anti-phish-beleid).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-399">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="7fdf2-400">U het standaard beleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-400">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="7fdf2-401">Gebruik de als volgt te houden of een anti-phish-regel in PowerShell in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-401">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="7fdf2-402">In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-402">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7fdf2-403">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-403">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7fdf2-404">Zie [Inschakelen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-404">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="7fdf2-405">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-405">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="7fdf2-406">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-406">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="7fdf2-407">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-407">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="7fdf2-408">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-408">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="7fdf2-409">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-409">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="7fdf2-410">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-410">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="7fdf2-411">Als u de prioriteit van een anti-phish-regel in PowerShell wilt instellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-411">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="7fdf2-412">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-412">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="7fdf2-413">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="7fdf2-413">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="7fdf2-414">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-414">**Notes**:</span></span>

- <span data-ttu-id="7fdf2-415">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-415">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="7fdf2-416">Het standaard anti-phish-beleid heeft geen overeenkomstige anti-phish-regel en heeft altijd de onaanpasbare prioriteitswaarde **Laagste**.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-416">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="7fdf2-417">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-417">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="7fdf2-418">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-418">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="7fdf2-419">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-419">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="7fdf2-420">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-420">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="7fdf2-421">Zie [Verwijderen-antiphishbeleid voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="7fdf2-421">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="7fdf2-422">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="7fdf2-422">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="7fdf2-423">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-423">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="7fdf2-424">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-424">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="7fdf2-425">In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-425">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7fdf2-426">Zie [Verwijderen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-426">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7fdf2-427">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="7fdf2-427">How do you know these procedures worked?</span></span>

<span data-ttu-id="7fdf2-428">Ga een van de volgende stappen uit om te controleren of u het ANTI-phishingbeleid van ATP hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-428">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="7fdf2-429">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-429">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="7fdf2-430">Controleer de lijst met beleidsregels, hun **statuswaarden** en hun **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="7fdf2-430">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="7fdf2-431">Ga als volgt te werk om meer details te bekijken:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-431">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="7fdf2-432">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-432">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="7fdf2-433">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="7fdf2-433">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="7fdf2-434">Vervang in Exchange Online PowerShell \< Naam door de naam van het beleid of de regel en voer de volgende opdracht uit en controleer \> de instellingen:</span><span class="sxs-lookup"><span data-stu-id="7fdf2-434">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
