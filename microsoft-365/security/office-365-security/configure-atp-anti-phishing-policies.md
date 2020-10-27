---
title: ATP-beleid tegen phishing configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u het geavanceerde anti-phishingfilter kunt maken, wijzigen en verwijderen, dat beschikbaar is in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: d6655089556f7268222dc47e2196f8aa1fc3da4e
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769218"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-103">ATP-beleid tegen phishing configureren</span><span class="sxs-lookup"><span data-stu-id="be59b-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="be59b-104">ATP anti-Phishingfilter maakt deel uit van [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="be59b-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="be59b-105">Met een anti-phishingfilter van ATP kunt u uw organisatie beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige gebruikers en andere typen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="be59b-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="be59b-106">Zie [bescherming tegen phishing](anti-phishing-protection.md)voor meer informatie over de verschillen tussen het anti-virus beleid in Exchange Online Protection (EOP) en het ATP anti phishingfilter.</span><span class="sxs-lookup"><span data-stu-id="be59b-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="be59b-107">Beheerders kunnen het standaardbeleid voor de vrije voor uitphishing van vrije gebruikers weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="be59b-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="be59b-108">Voor een grotere nauwkeurigheid kunt u ook aangepast ATP anti-phishingfilter maken dat geldt voor specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="be59b-109">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="be59b-110">U kunt het beleid voor het instellen van ATP anti phishing configureren in de beveiligings & nalevings centrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="be59b-111">Zie [anti phishingberichten configureren in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van het meer beperkte beveiligingsbeleid dat beschikbaar is in Exchange Online Protection-organisaties (dat wil zeggen microsoft 365-organisaties zonder Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="be59b-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="be59b-112">ATP anti-phishingfilter in de beveiligings & nalevings centrum VS PowerShell</span><span class="sxs-lookup"><span data-stu-id="be59b-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="be59b-113">De basiselementen van een ATP anti-phishingfilter zijn:</span><span class="sxs-lookup"><span data-stu-id="be59b-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="be59b-114">**Het anti-virus beleid** : Hiermee geeft u de phishing-beveiliging op om in of uit te schakelen, en de acties voor het toepassen van opties.</span><span class="sxs-lookup"><span data-stu-id="be59b-114">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="be59b-115">**De anti-phishings regel** : Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (wie het beleid van toepassing is) voor een anti-phishing beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-115">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="be59b-116">Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid voor het beheren van ATP anti-phishing beheert in het beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="be59b-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="be59b-117">Wanneer u een beleid maakt, maakt u eigenlijk een anti-phishings regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="be59b-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="be59b-118">Wanneer u een beleid wijzigt, worden de instellingen voor de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden de anti-late regel gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="be59b-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="be59b-119">Alle andere instellingen wijzigen het bijbehorende anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="be59b-120">Wanneer u een beleid verwijdert, worden de anti-phishings regel en het bijbehorende anti-onphishings beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be59b-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="be59b-121">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="be59b-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="be59b-122">Zie voor meer informatie de sectie [Exchange Online PowerShell gebruiken voor het configureren van het onderdeel ATP anti-phishingfilter](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="be59b-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="be59b-123">Elke Office 365 ATP-organisatie heeft een ingebouwde ATP anti-phishingfilter met de naam Office365 AntiPhish standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="be59b-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="be59b-124">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-avond regel (Recipient filters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="be59b-125">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="be59b-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="be59b-126">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="be59b-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="be59b-127">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be59b-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="be59b-128">Om de effectiviteit van bescherming tegen phishing te bevorderen, kunt u aangepaste ATP anti-phishingfilter-beleidsregels maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="be59b-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="be59b-129">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="be59b-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="be59b-130">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="be59b-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="be59b-131">Als u direct naar de pagina voor het gebruik van **ATP anti phishing** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="be59b-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="be59b-132">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="be59b-133">U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="be59b-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="be59b-134">Als u een beleid wilt toevoegen, wijzigen of verwijderen uit het beleid van ATP, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="be59b-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="be59b-135">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="be59b-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="be59b-136">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="be59b-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="be59b-137">Voor alleen-lezen toegang tot ATP anti-phishingfilter moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="be59b-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="be59b-138">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="be59b-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="be59b-139">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="be59b-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="be59b-140">Voor de aanbevolen instellingen voor het anti-phishingfilter van ATP, raadpleegt u de [instellingen van het beleid voor het anti-phishingfilter van ATP](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="be59b-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="be59b-141">Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="be59b-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="be59b-142">Zie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar anti phishingfilter in de filter pijplijn wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="be59b-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-143">De beveiligings & voor compliance gebruiken om een ATP anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="be59b-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="be59b-144">Wanneer u een aangepast ATP anti-Phishingfilter maakt in het compliance-& Beveiligingscentrum, maakt de anti-phishings regel en het bijbehorende anti-phishings beleid op hetzelfde moment op dezelfde manier met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="be59b-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="be59b-145">Wanneer u een ATP anti-Phishingfilter maakt, kunt u alleen de Beleidsnaam, de beschrijving en het filter voor de ontvanger opgeven waarmee wordt aangegeven voor wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="be59b-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="be59b-146">Nadat u het beleid hebt gemaakt, kunt u het beleid wijzigen, zodat u de standaardinstellingen voor anti phishing kunt wijzigen of bekijken.</span><span class="sxs-lookup"><span data-stu-id="be59b-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="be59b-147">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-148">Op de **anti phishing** -pagina klikt u op **maken** .</span><span class="sxs-lookup"><span data-stu-id="be59b-148">On the **Anti-phishing** page, click **Create** .</span></span>

3. <span data-ttu-id="be59b-149">De wizard **nieuw anti-phishingfilterbeleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="be59b-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="be59b-150">Configureer de volgende instellingen op de pagina **naam van uw beleid** :</span><span class="sxs-lookup"><span data-stu-id="be59b-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="be59b-151">**Naam** : een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-151">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="be59b-152">**Beschrijving** : voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-152">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="be59b-153">Wanneer u klaar bent, klikt u op **volgende** .</span><span class="sxs-lookup"><span data-stu-id="be59b-153">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="be59b-154">Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="be59b-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="be59b-155">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="be59b-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="be59b-156">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="be59b-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="be59b-157">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="be59b-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="be59b-158">Klik op **een voorwaarde toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="be59b-158">Click **Add a condition** .</span></span> <span data-ttu-id="be59b-159">Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als** :</span><span class="sxs-lookup"><span data-stu-id="be59b-159">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="be59b-160">**De ontvanger is** : geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="be59b-160">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="be59b-161">**De ontvanger is lid van** : Hiermee geeft u een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-161">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="be59b-162">**Het domein van de ontvanger is** : geeft de geadresseerden op in een of meer van de geconfigureerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-162">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="be59b-163">Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.</span><span class="sxs-lookup"><span data-stu-id="be59b-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="be59b-164">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="be59b-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="be59b-165">Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="be59b-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="be59b-166">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="be59b-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="be59b-167">Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.</span><span class="sxs-lookup"><span data-stu-id="be59b-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="be59b-168">Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="be59b-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="be59b-169">Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als** .</span><span class="sxs-lookup"><span data-stu-id="be59b-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if** .</span></span>

   <span data-ttu-id="be59b-170">Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als** .</span><span class="sxs-lookup"><span data-stu-id="be59b-170">To add exceptions, click **Add a condition** and select an exception under **Except if** .</span></span> <span data-ttu-id="be59b-171">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="be59b-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="be59b-172">Wanneer u klaar bent, klikt u op **volgende** .</span><span class="sxs-lookup"><span data-stu-id="be59b-172">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="be59b-173">Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="be59b-174">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="be59b-175">Wanneer u klaar bent, klikt u op **dit beleid maken** .</span><span class="sxs-lookup"><span data-stu-id="be59b-175">When you're finished, click **Create this policy** .</span></span>

6. <span data-ttu-id="be59b-176">Klik op **OK** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="be59b-177">Nadat u het ATP anti-phishingfilter met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in het volgende gedeelte om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="be59b-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-178">U kunt het nalevings centrum voor beveiligings & gebruiken om het gebruik van ATP anti-phishing-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="be59b-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="be59b-179">Gebruik de volgende procedures voor het wijzigen van het gebruik van ATP anti-Phishingfilter: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="be59b-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="be59b-180">Als u dit nog niet hebt gedaan, opent u het beveiligings & nalevings centrum en gaat u naar het beleid voor het beleid voor **bedreigings beheer** voor \> **Policy** \> **ATP anti phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-181">Selecteer het aangepaste ATP anti phishing-beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="be59b-182">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="be59b-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="be59b-183">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="be59b-184">Als u in een sectie op **bewerken** klikt, krijgt u toegang tot de instellingen in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="be59b-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="be59b-185">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in een willekeurige volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="be59b-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="be59b-186">Nadat u op **bewerken** in een sectie hebt geklikt, worden de beschikbare instellingen in de wizard indeling weergegeven, maar u kunt wel binnen de pagina's in een willekeurige Volg **Cancel** orde springen **Close** , en u kunt op de pagina **Opslaan** of sluiten klikken op het pictogram voor het ![ ](../../media/scc-remove-icon.png) **bewerken van uw beleid \<name\>** (u hoeft niet te klikken op de laatste pagina van de wizard om de pagina te openen</span><span class="sxs-lookup"><span data-stu-id="be59b-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="be59b-187">**Beleidsinstelling** : Klik op **bewerken** als u de instellingen wilt wijzigen die beschikbaar waren wanneer u [het beleid hebt gemaakt](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in de vorige sectie:</span><span class="sxs-lookup"><span data-stu-id="be59b-187">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="be59b-188">**Naam**</span><span class="sxs-lookup"><span data-stu-id="be59b-188">**Name**</span></span>
   - <span data-ttu-id="be59b-189">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="be59b-189">**Description**</span></span>
   - <span data-ttu-id="be59b-190">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="be59b-190">**Applied to**</span></span>
   - <span data-ttu-id="be59b-191">**De instellingen bekijken**</span><span class="sxs-lookup"><span data-stu-id="be59b-191">**Review your settings**</span></span>

   <span data-ttu-id="be59b-192">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="be59b-193">**Imitatie** : Klik op **bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-193">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="be59b-194">Deze instellingen vormen een voorwaarde voor het beleid waarmee vervalste afzenders worden geïdentificeerd om te zoeken naar (afzonderlijk of per domein) in het van-adres van inkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="be59b-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="be59b-195">Zie voor meer informatie [imitatie-instellingen in het anti-phishingfilter-beleid](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="be59b-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="be59b-196">**Gebruikers toevoegen om te beveiligen** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-196">**Add users to protect** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-197">Als u de functie wilt inschakelen, verschuift u de schuifregelaar naar **aan** en klikt u op de knop **gebruiker toevoegen** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-197">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="be59b-198">Configureer de volgende waarden in het vervolgmenu **gebruiker toevoegen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="be59b-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="be59b-199">**E-mailadres** :</span><span class="sxs-lookup"><span data-stu-id="be59b-199">**Email address** :</span></span>

        - <span data-ttu-id="be59b-200">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="be59b-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="be59b-201">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="be59b-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="be59b-202">Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="be59b-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="be59b-203">**Naam** : deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt dit wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-203">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="be59b-204">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-204">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="be59b-205">Als u een bestaande vermelding wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="be59b-205">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="be59b-206">U kunt maximaal 60 gebruikers opgeven in het beveiligings & nalevings centrum of in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-206">You can enter a maximum of 60 users in the Security & Compliance Center or in PowerShell.</span></span>
       
   - <span data-ttu-id="be59b-207">**Domeinen toevoegen die u wilt beveiligen** : Configureer een of beide van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="be59b-207">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="be59b-208">**Automatisch de domeinen opnemen waarvan ik de eigenaar ben** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-208">**Automatically include the domains I own** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-209">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-209">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="be59b-210">**Aangepaste domeinen opnemen** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-210">**Include custom domains** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-211">Als u deze optie wilt inschakelen, verschuift u de schuifregelaar naar **aan** en voert u in het vak **domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaalt u de gewenste stappen.</span><span class="sxs-lookup"><span data-stu-id="be59b-211">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="be59b-212">U kunt maximaal 50 domeinen invoeren in het beveiligings & nalevings centrum of in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-212">You can enter a maximum of 50 domains in the Security & Compliance Center or in PowerShell.</span></span>

   - <span data-ttu-id="be59b-213">**Acties** : Klik op **bewerken**</span><span class="sxs-lookup"><span data-stu-id="be59b-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="be59b-214">**Als e-mail wordt verzonden door een geïmiteerde gebruiker** : Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in de **gebruikers toevoegen om te beschermen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="be59b-215">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="be59b-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="be59b-216">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="be59b-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="be59b-217">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="be59b-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="be59b-218">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="be59b-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="be59b-219">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="be59b-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="be59b-220">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="be59b-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="be59b-221">**Als e-mailberichten worden verzonden door een geïmiteerd domein** : Configureer een van de volgende acties voor berichten waarvan de vervalste verzender zich bevindt in een van de beveiligde domeinen die u hebt opgegeven in **domeinen toevoegen om te beschermen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

     - <span data-ttu-id="be59b-222">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="be59b-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="be59b-223">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="be59b-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="be59b-224">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="be59b-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="be59b-225">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="be59b-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="be59b-226">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="be59b-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="be59b-227">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="be59b-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="be59b-228">Klik op de **beveiligingstips voor imitatie inschakelen** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="be59b-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="be59b-229">**Tip weergeven voor geïmiteerde gebruikers** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-229">**Show tip for impersonated users** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-230">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-230">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="be59b-231">**Tip weergeven voor geïmiteerde domeinen** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-231">**Show tip for impersonated domains** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-232">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-232">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="be59b-233">**Tip voor ongebruikelijk tekens weergeven** : de standaardwaarde is **uitgeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-233">**Show tip for unusual characters** : The default value is **Off** .</span></span> <span data-ttu-id="be59b-234">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-234">To turn it on, slide the toggle to **On** .</span></span>

     <span data-ttu-id="be59b-235">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="be59b-235">When you're finished, click **Save** .</span></span>

   - <span data-ttu-id="be59b-236">**Postvak informatie** :</span><span class="sxs-lookup"><span data-stu-id="be59b-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="be59b-237">**Postvak intelligentie inschakelen?** : de standaardwaarde is **ingeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-237">**Enable mailbox intelligence?** : The default value is **On** .</span></span> <span data-ttu-id="be59b-238">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-238">To turn it off, slide the toggle to **Off** .</span></span>

     - <span data-ttu-id="be59b-239">**Schakelt u de bescherming van imitatie op basis van een postvak in?** : deze instelling is alleen beschikbaar als **Postvak Intelligence inschakelen?** is **ingeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On** .</span></span>

       <span data-ttu-id="be59b-240">In **als e-mailbericht wordt verzonden door een geïmiteerde gebruiker** , kunt u een van de volgende acties opgeven voor het uitvoeren van berichten die niet beschikbaar zijn voor de Postvak informatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="be59b-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="be59b-241">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="be59b-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="be59b-242">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="be59b-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="be59b-243">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="be59b-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="be59b-244">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="be59b-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="be59b-245">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="be59b-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="be59b-246">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="be59b-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="be59b-247">**Vertrouwde afzenders en domeinen toevoegen** : Geef uitzonderingen voor het beleid op:</span><span class="sxs-lookup"><span data-stu-id="be59b-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="be59b-248">**Vertrouwde afzenders** :</span><span class="sxs-lookup"><span data-stu-id="be59b-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="be59b-249">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="be59b-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="be59b-250">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="be59b-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="be59b-251">Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="be59b-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="be59b-252">**Vertrouwde domeinen** : Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal de gewenste stappen.</span><span class="sxs-lookup"><span data-stu-id="be59b-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="be59b-253">**Controleer uw instellingen** : in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="be59b-254">U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="be59b-255">U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="be59b-256">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="be59b-256">**Protected users**</span></span>
       - <span data-ttu-id="be59b-257">**Beveiligde domeinen** \> **Ook domeinen opnemen waarvan ik eigenaar ben**</span><span class="sxs-lookup"><span data-stu-id="be59b-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="be59b-258">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="be59b-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="be59b-259">**Postvak intelligentie**</span><span class="sxs-lookup"><span data-stu-id="be59b-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="be59b-260">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="be59b-261">**Spoof** : Klik op **bewerken** als u de identiteit van spoofing wilt in-of uitschakelen, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en configureer de actie die u wilt toepassen op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="be59b-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="be59b-262">Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="be59b-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="be59b-263">Deze instellingen zijn ook beschikbaar in het anti-phishings beleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="be59b-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="be59b-264">**Instellingen voor spoofing filter** : de standaardwaarde is **ingeschakeld** en u wordt aangeraden deze in te stellen.</span><span class="sxs-lookup"><span data-stu-id="be59b-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="be59b-265">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-265">To turn it off, slide the toggle to **Off** .</span></span> <span data-ttu-id="be59b-266">Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="be59b-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="be59b-267">U hoeft geen anti-spoofing-beveiliging uit te schakelen als uw MX-record niet verwijst naar Microsoft 365. u kunt in plaats hiervan uitgebreid filteren op connectors.</span><span class="sxs-lookup"><span data-stu-id="be59b-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="be59b-268">Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="be59b-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="be59b-269">**Functie niet-geverifieerde afzender inschakelen** : de standaardwaarde is **ingeschakeld** .</span><span class="sxs-lookup"><span data-stu-id="be59b-269">**Enable Unauthenticated Sender feature** : The default value is **On** .</span></span> <span data-ttu-id="be59b-270">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-270">To turn it off, slide the toggle to **Off** .</span></span>

   - <span data-ttu-id="be59b-271">**Acties** : de actie opgeven die moet worden uitgevoerd voor berichten die geen spoof Intelligence hebben:</span><span class="sxs-lookup"><span data-stu-id="be59b-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="be59b-272">**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen, doet u het** volgende:</span><span class="sxs-lookup"><span data-stu-id="be59b-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="be59b-273">**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="be59b-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="be59b-274">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="be59b-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="be59b-275">**Controleer uw instellingen** : in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="be59b-276">U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="be59b-277">U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="be59b-278">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="be59b-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="be59b-279">**Niet-geverifieerde afzender functie inschakelen**</span><span class="sxs-lookup"><span data-stu-id="be59b-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="be59b-280">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="be59b-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="be59b-281">**Geavanceerde instellingen** : Klik op **bewerken** om de drempelwaarden voor Geavanceerd phishing te configureren.</span><span class="sxs-lookup"><span data-stu-id="be59b-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="be59b-282">Zie voor meer informatie [Geavanceerde phishingberichten in het anti-phishingfilter-beleid](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="be59b-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="be59b-283">**Geavanceerde fraude drempels** : Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="be59b-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="be59b-284">**1-standaard** (dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="be59b-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="be59b-285">**2-agressief**</span><span class="sxs-lookup"><span data-stu-id="be59b-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="be59b-286">**3-meer agressief**</span><span class="sxs-lookup"><span data-stu-id="be59b-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="be59b-287">**4-de scherpste**</span><span class="sxs-lookup"><span data-stu-id="be59b-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="be59b-288">**Controleer uw instellingen** : Klik op **bewerken** om terug te gaan naar de pagina Geavanceerde instellingen voor **phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="be59b-289">Wanneer u klaar bent, klikt u op **Opslaan** op een van beide pagina's.</span><span class="sxs-lookup"><span data-stu-id="be59b-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="be59b-290">Ga op de pagina **\<Name\> beleid bewerken** naar de instellingen en klik op **sluiten** .</span><span class="sxs-lookup"><span data-stu-id="be59b-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close** .</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="be59b-291">Met behulp van het compliance-beveiligings & u het standaardbeleid voor het anti-phishingfilter van ATP</span><span class="sxs-lookup"><span data-stu-id="be59b-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="be59b-292">Het standaard-Phishingfilter anti-phishingfilter heeft de naam Office365 AntiPhish standaard en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="be59b-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="be59b-293">Voer de volgende stappen uit als u het standaard-Phishingfilter voor de vrije tijd wilt wijzigen:</span><span class="sxs-lookup"><span data-stu-id="be59b-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="be59b-294">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-295">Klik op de pagina **anti phishing** op **standaardbeleid** .</span><span class="sxs-lookup"><span data-stu-id="be59b-295">On the **Anti-phishing** page, click **Default policy** .</span></span>

3. <span data-ttu-id="be59b-296">De standaardpagina voor het **bewerken van uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="be59b-297">De volgende secties zijn beschikbaar, met een identieke instelling voor [het wijzigen van een aangepast beleid](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="be59b-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="be59b-298">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="be59b-298">**Impersonation**</span></span>
   - <span data-ttu-id="be59b-299">**Met**</span><span class="sxs-lookup"><span data-stu-id="be59b-299">**Spoof**</span></span>
   - <span data-ttu-id="be59b-300">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="be59b-300">**Advanced settings**</span></span>

   <span data-ttu-id="be59b-301">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="be59b-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="be59b-302">U ziet de secties en waarden van de **beleidsinstelling** , maar er is geen koppeling voor **bewerken** , zodat u de instellingen (Beleidsnaam en beschrijving, en wie het beleid van toepassing is op alle geadresseerden), niet kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="be59b-303">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be59b-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="be59b-304">Het is niet mogelijk om de prioriteit van het standaardbeleid te wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="be59b-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="be59b-305">Controleer de instellingen op de pagina **uw beleid Office365 AntiPhish standaard** instellen en klik op **sluiten** .</span><span class="sxs-lookup"><span data-stu-id="be59b-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close** .</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-306">Aangepaste ATP anti-phishings beleid in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="be59b-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="be59b-307">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-308">Let op de waarde in de kolom **status** :</span><span class="sxs-lookup"><span data-stu-id="be59b-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="be59b-309">Schuif de wisselknop naar **uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="be59b-310">Schuif de wisselknop naar **aan om het beleid in te** schakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="be59b-311">U kunt het standaard anti-Phishingfilter niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-312">De prioriteit van een aangepast ATP anti-phishings beleid instellen</span><span class="sxs-lookup"><span data-stu-id="be59b-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="be59b-313">Standaard krijgt u in het geval van een anti-phishingfilter een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="be59b-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="be59b-314">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="be59b-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="be59b-315">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="be59b-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="be59b-316">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="be59b-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="be59b-317">Aangepast ATP anti-phishingfilter worden weergegeven in de volgorde waarin ze zijn verwerkt (het eerste beleid heeft **de waarde 0** ).</span><span class="sxs-lookup"><span data-stu-id="be59b-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="be59b-318">Het standaard anti-phishingfilter met de naam Office365 AntiPhish standaard heeft de waarde van een aangepaste **prioriteit en kunt** deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="be59b-319">**Opmerking** : in het beveiligings & nalevings centrum kunt u alleen de prioriteit van het anti-phishingfilter wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="be59b-319">**Note** : In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="be59b-320">In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor de anti-phishing maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="be59b-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="be59b-321">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **prioriteit verhogen** of **prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **prioriteits** nummer niet rechtstreeks wijzigen in de beveiligings & compliance Center).</span><span class="sxs-lookup"><span data-stu-id="be59b-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="be59b-322">Als u meerdere beleidsregels hebt, kunt u de prioriteit van een beleid alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="be59b-323">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-324">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="be59b-325">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="be59b-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="be59b-326">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="be59b-327">Het aangepaste ATP anti-phishingfilter met de **prioriteits** waarde **0** heeft slechts de knop **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="be59b-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="be59b-328">Het aangepaste ATP anti-phishingfilter met de laagste **prioriteits** waarde (bijvoorbeeld **3** ) is slechts de knop **prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="be59b-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="be59b-329">Als u beschikt over drie of meer aangepaste anti phishingfilter-beleidsregels, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="be59b-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="be59b-330">Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="be59b-331">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="be59b-331">When you're finished, click **Close** .</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-332">Met behulp van het beveiligings & compliance</span><span class="sxs-lookup"><span data-stu-id="be59b-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="be59b-333">Ga in het beveiligings & compliance Center naar het beleid voor het beheer van bedreigingen en ga naar het beleid voor het **beheer van bedreigingen** \> **Policy** \> **ATP anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-334">Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="be59b-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="be59b-335">Selecteer een aangepast ATP anti phishing-beleid dat u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="be59b-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="be59b-336">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="be59b-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="be59b-337">Klik op **standaardbeleid** om het standaard anti-phishingfilter te bekijken.</span><span class="sxs-lookup"><span data-stu-id="be59b-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="be59b-338">De flyout voor het **beleid \<name\> bewerken** wordt weergegeven, waarin u de instellingen en waarden kunt weergeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-339">Met behulp van het beveiligings & compliance</span><span class="sxs-lookup"><span data-stu-id="be59b-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="be59b-340">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="be59b-341">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be59b-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="be59b-342">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="be59b-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="be59b-343">Klik in het vervolgmenu **uw beleidsregels \<name\> bewerken** dat wordt weergegeven op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="be59b-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="be59b-344">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be59b-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="be59b-345">PowerShell van Exchange Online gebruiken om een anti-phishings beleid van ATP te configureren</span><span class="sxs-lookup"><span data-stu-id="be59b-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="be59b-346">Zoals hierboven beschreven, bestaat een anti-spam beleid en een anti-phishings regel.</span><span class="sxs-lookup"><span data-stu-id="be59b-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="be59b-347">In Exchange Online PowerShell is het verschil tussen anti-malwarebeleid en anti-phishing regels zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="be59b-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="be59b-348">U een anti-phishings beleid beheert met behulp van de cmdlets **\* AntiPhishPolicy** en u beheert de anti-phishings regels met behulp van de cmdlets voor **\* AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="be59b-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="be59b-349">In PowerShell maakt u eerst het anti-phishings beleid en vervolgens maakt u een anti-phishings regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="be59b-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="be59b-350">In PowerShell wijzigt u de instellingen van het anti-phishings beleid en de anti-phishing regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="be59b-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="be59b-351">Wanneer u een anti-phishings beleid verwijdert uit PowerShell, wordt de overeenkomstige anti-phishing regel niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="be59b-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="be59b-352">PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="be59b-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="be59b-353">Het maken van een anti-phishingfilter in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="be59b-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="be59b-354">Maak het anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="be59b-355">Maak de anti-phishings regel waarmee het anti-phishings beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="be59b-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="be59b-356">**Opmerkingen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-356">**Notes** :</span></span>

- <span data-ttu-id="be59b-357">U kunt een nieuwe anti-phishings regel maken en er een bestaande, niet-bijbehorend anti-phishings beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="be59b-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="be59b-358">Een anti-phishings regel kan niet worden gekoppeld aan meer dan een anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="be59b-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="be59b-359">U kunt de volgende instellingen configureren voor nieuwe anti-phishings beleidsregels in PowerShell die niet beschikbaar zijn in het beveiligings & compliance Center totdat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="be59b-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="be59b-360">Het nieuwe beleid maken als uitgeschakeld ( _ingeschakeld_ `$false` in de **nieuwe AntiPhishRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="be59b-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="be59b-361">De prioriteit van het beleid instellen voor het maken _Priority_ van de _\<Number\>_ **nieuwe AntiPhishRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="be59b-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="be59b-362">Een nieuw anti-phishings beleid dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een anti-phishing regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="be59b-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="be59b-363">Stap 1: PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="be59b-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="be59b-364">Voor het maken van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="be59b-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="be59b-365">In dit voorbeeld wordt een anti-phishings beleid met de naam onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="be59b-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="be59b-366">Het beleid is ingeschakeld (de parameter _enabled_ wordt niet gebruikt en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="be59b-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="be59b-367">De beschrijving luidt: afdelings beleid voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="be59b-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="be59b-368">Schakelt de bescherming van organisatie domeinen in voor alle geaccepteerde domeinen en gerichte domeinbeveiliging voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="be59b-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="be59b-369">Hiermee wordt Mai Fujito (mfujito@fabrikam.com) opgegeven als de gebruiker die de gebruiker wil beschermen tegen onbevoegden.</span><span class="sxs-lookup"><span data-stu-id="be59b-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="be59b-370">Schakelt postvak informatie in.</span><span class="sxs-lookup"><span data-stu-id="be59b-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="be59b-371">Schakelt de functie voor Postvak beveiliging in en geeft de quarantaine actie aan.</span><span class="sxs-lookup"><span data-stu-id="be59b-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="be59b-372">Maakt veiligheidstips.</span><span class="sxs-lookup"><span data-stu-id="be59b-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="be59b-373">Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="be59b-374">Stap 2: PowerShell gebruiken om een anti-phishings regel te maken</span><span class="sxs-lookup"><span data-stu-id="be59b-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="be59b-375">Voor het maken van een anti-phishing regel gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="be59b-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="be59b-376">In dit voorbeeld wordt een anti-phishing regel genaamd onderzoek afdeling met de volgende voorwaarden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="be59b-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="be59b-377">De regel is verbonden met het anti-phishings beleid met de naam onderzoek quarantaine.</span><span class="sxs-lookup"><span data-stu-id="be59b-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="be59b-378">De regel geldt voor de leden van de groep met de naam onderzoek afdeling.</span><span class="sxs-lookup"><span data-stu-id="be59b-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="be59b-379">Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="be59b-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="be59b-380">Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="be59b-381">PowerShell gebruiken om een anti-phishings beleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="be59b-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="be59b-382">Gebruik de volgende syntaxis om de bestaande anti-phishings beleidsregels te bekijken:</span><span class="sxs-lookup"><span data-stu-id="be59b-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="be59b-383">In dit voorbeeld wordt een overzichtslijst met alle anti-phishing-beleidsregels en de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="be59b-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="be59b-384">In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phishings beleid met de naam leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="be59b-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="be59b-385">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="be59b-386">PowerShell gebruiken om anti-phishings regels te bekijken</span><span class="sxs-lookup"><span data-stu-id="be59b-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="be59b-387">Gebruik de volgende syntaxis om bestaande anti-phishings regels weer te geven:</span><span class="sxs-lookup"><span data-stu-id="be59b-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="be59b-388">In het volgende voorbeeld wordt een overzichtslijst met alle anti-phishing regels met de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="be59b-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="be59b-389">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="be59b-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="be59b-390">In het volgende voorbeeld worden alle eigenschapwaarden voor de anti-phishing-regel genaamd contoso leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="be59b-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="be59b-391">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="be59b-392">PowerShell gebruiken om een anti-phishings beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="be59b-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="be59b-393">Met uitzondering van de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phishings beleid in PowerShell aanpast wanneer u het beleid maakt zoals wordt beschreven in de sectie [stap 1: gebruik PowerShell om een anti-phishings sectie te maken](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="be59b-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="be59b-394">De schakeloptie _MakeDefault_ waarmee het opgegeven beleid wordt omgezet in het standaardbeleid (voor iedereen, de **laagste** prioriteit en het niet verwijderen) is alleen beschikbaar wanneer u een anti-Echobeleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="be59b-395">U kunt niet de naam van een anti-phishings beleid wijzigen (de cmdlet **set-AntiPhishPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="be59b-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="be59b-396">Wanneer u de naam van een anti-phishingfilter wijzigt in de beveiligings & nalevings centrum, kunt u de naam van de anti-phishing _regel_ alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="be59b-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_ .</span></span>

<span data-ttu-id="be59b-397">Voor het wijzigen van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="be59b-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="be59b-398">Zie [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="be59b-399">PowerShell gebruiken om anti-phishings regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="be59b-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="be59b-400">De enige instelling die niet beschikbaar is wanneer u een anti-phishings regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="be59b-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="be59b-401">Zie de volgende sectie als u bestaande anti-Phish regels wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="be59b-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="be59b-402">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phishing regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be59b-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="be59b-403">U kunt dezelfde instellingen gebruiken wanneer u een regel maakt zoals wordt beschreven in [stap 2: PowerShell gebruiken om een anti-phishings sectie te maken](#step-2-use-powershell-to-create-an-anti-phish-rule) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="be59b-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="be59b-404">Gebruik de volgende syntaxis om een anti-phishing regel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="be59b-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="be59b-405">Zie [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="be59b-406">PowerShell gebruiken om anti-phishings regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="be59b-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="be59b-407">Wanneer u een anti-phishing regel in-of uitschakelt in PowerShell, schakelt u het volledige anti-phishings beleid in of uit (de anti-phishings regel en het door u toegekende anti-phishings beleid).</span><span class="sxs-lookup"><span data-stu-id="be59b-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="be59b-408">U kunt het standaard anti-phishingfilter-beleid niet in-of uitschakelen (het wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="be59b-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="be59b-409">U kunt een anti-phishings regel in PowerShell in-of uitschakelen met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="be59b-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="be59b-410">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="be59b-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="be59b-411">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="be59b-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="be59b-412">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="be59b-413">PowerShell gebruiken om de prioriteit van anti-phishings regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="be59b-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="be59b-414">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="be59b-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="be59b-415">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="be59b-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="be59b-416">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="be59b-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="be59b-417">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="be59b-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="be59b-418">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="be59b-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="be59b-419">Als u de prioriteit wilt instellen van een anti-Phish regel in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="be59b-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="be59b-420">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="be59b-420">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="be59b-421">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="be59b-421">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="be59b-422">**Opmerkingen** :</span><span class="sxs-lookup"><span data-stu-id="be59b-422">**Notes** :</span></span>

- <span data-ttu-id="be59b-423">Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="be59b-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="be59b-424">Het anti-phishings beleid heeft geen overeenkomstige anti-phishings regel, en het is altijd de **laagste** ongewijzigde prioriteitswaarde.</span><span class="sxs-lookup"><span data-stu-id="be59b-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest** .</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="be59b-425">PowerShell gebruiken om een anti-phishings beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="be59b-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="be59b-426">Wanneer u PowerShell gebruikt om een anti-phishings beleid te verwijderen, wordt de overeenkomstige anti-phishings regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be59b-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="be59b-427">Gebruik de volgende syntaxis om een anti-phishings beleid te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be59b-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="be59b-428">In dit voorbeeld wordt het anti-phishings beleid met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be59b-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="be59b-429">Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="be59b-430">PowerShell gebruiken om anti-phishings regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="be59b-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="be59b-431">Als u PowerShell gebruikt om een anti-phishing regel te verwijderen, wordt het bijbehorende anti-phishings beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be59b-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="be59b-432">Gebruik de volgende syntaxis om een anti-phishings regel te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be59b-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="be59b-433">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be59b-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="be59b-434">Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="be59b-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="be59b-435">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="be59b-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="be59b-436">Voer een of meer van de volgende stappen uit om te controleren of u het juiste beleid voor het gebruik van ATP anti phishing hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="be59b-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="be59b-437">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="be59b-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span> <span data-ttu-id="be59b-438">Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** .</span><span class="sxs-lookup"><span data-stu-id="be59b-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="be59b-439">Ga op een van de volgende manieren te werk om meer informatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="be59b-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="be59b-440">Selecteer een beleid in de lijst en Bekijk de details in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="be59b-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="be59b-441">Klik op **standaardbeleid** en Bekijk de details in het vervolgmenu.</span><span class="sxs-lookup"><span data-stu-id="be59b-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="be59b-442">In Exchange Online PowerShell vervangt u \<Name\> de naam van het beleid of de regel en voert u de volgende opdracht uit en controleert u de instellingen:</span><span class="sxs-lookup"><span data-stu-id="be59b-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
