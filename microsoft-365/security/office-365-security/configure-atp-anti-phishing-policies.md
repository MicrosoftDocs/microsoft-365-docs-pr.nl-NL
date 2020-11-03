---
title: Anti phishingfilter configureren in Microsoft Defender voor Office 365
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
description: Beheerders kunnen leren hoe u het geavanceerde anti-phishingfilter kunt maken, wijzigen en verwijderen, dat beschikbaar is in organisaties met Microsoft Defender voor Office 365.
ms.openlocfilehash: 9e07107c302f83b71a97517b11e71eac81f84f6b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845922"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-103">Anti phishingfilter configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa671-104">Met anti phishingfilter in [Microsoft Defender voor Office 365](office-365-atp.md) kunt u uw organisatie beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige gebruikers en andere typen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="fa671-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="fa671-105">Voor meer informatie over de verschillen tussen een anti-phishingfilter in Exchange Online Protection (EOP) en anti phishingfilter in Microsoft Defender voor Office 365 raadpleegt u [bescherming tegen phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fa671-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="fa671-106">Beheerders kunnen het standaard anti phishingfilter-beleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="fa671-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="fa671-107">Voor een betere granulatie kunt u ook een aangepast anti-phishings beleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="fa671-108">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="fa671-109">U kunt een anti-phishingfilter configureren in het beveiligings & nalevings centrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="fa671-110">Zie [anti phishingberichten configureren in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van het meer beperkte beveiligingsbeleid dat beschikbaar is in Exchange Online Protection-organisaties (dat wil zeggen organisaties zonder Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="fa671-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="fa671-111">De basisonderdelen van een anti phishingfilter zijn:</span><span class="sxs-lookup"><span data-stu-id="fa671-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="fa671-112">**Het anti-virus beleid** : Hiermee geeft u de phishing-beveiliging op om in of uit te schakelen, en de acties voor het toepassen van opties.</span><span class="sxs-lookup"><span data-stu-id="fa671-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="fa671-113">**De anti-phishings regel** : Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (wie het beleid van toepassing is) voor een anti-phishing beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="fa671-114">Het verschil tussen deze twee elementen is niet duidelijk wanneer u een anti-phishing beleid beheert in de beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="fa671-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fa671-115">Wanneer u een beleid maakt, maakt u eigenlijk een anti-phishings regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="fa671-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fa671-116">Wanneer u een beleid wijzigt, worden de instellingen voor de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden de anti-late regel gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="fa671-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="fa671-117">Alle andere instellingen wijzigen het bijbehorende anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="fa671-118">Wanneer u een beleid verwijdert, worden de anti-phishings regel en het bijbehorende anti-onphishings beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fa671-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="fa671-119">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="fa671-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fa671-120">Zie voor meer informatie het artikel [Exchange Online PowerShell gebruiken voor het configureren van anti phishingfilter in Microsoft Defender voor Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) verderop in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="fa671-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="fa671-121">Elke Microsoft Defender voor Office 365-organisatie heeft een ingebouwd anti-phishingfilter-beleid met de naam Office365 AntiPhish standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="fa671-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="fa671-122">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-avond regel (Recipient filters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="fa671-123">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="fa671-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="fa671-124">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="fa671-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="fa671-125">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa671-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="fa671-126">Voor een grotere effectiviteit van de bescherming tegen phishing in Microsoft Defender voor Office 365, kunt u een aangepast anti-phishings beleid maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="fa671-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa671-127">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="fa671-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa671-128">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fa671-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fa671-129">Als u direct naar de pagina voor het gebruik van **ATP anti phishing** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="fa671-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="fa671-130">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="fa671-131">U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="fa671-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="fa671-132">Als u een anti-phishingfilter wilt toevoegen, wijzigen of verwijderen, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="fa671-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fa671-133">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fa671-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fa671-134">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fa671-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="fa671-135">Voor alleen-lezen toegang tot anti phishingfilter moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="fa671-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fa671-136">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fa671-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fa671-137">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fa671-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="fa671-138">Voor de aanbevolen instellingen voor anti-phishing beleid in Microsoft Defender voor Office 365 raadpleegt u [anti phishingfilter in de instellingen van de Defender voor office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="fa671-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="fa671-139">Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="fa671-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="fa671-140">Zie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar anti phishingfilter in de filter pijplijn wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="fa671-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-141">Met behulp van het beveiligings & compliance Center maakt u een anti-phishingfilter in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fa671-142">Als u een aangepast anti-Phishingfilter maakt in het compliance-& Beveiligingscentrum, maakt u op hetzelfde moment de anti-phishing regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="fa671-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="fa671-143">Wanneer u een anti Phishingfilter maakt, kunt u alleen de Beleidsnaam, de beschrijving en het filter voor de ontvanger opgeven waarmee wordt aangegeven voor wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="fa671-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="fa671-144">Nadat u het beleid hebt gemaakt, kunt u het beleid wijzigen, zodat u de standaardinstellingen voor anti phishing kunt wijzigen of bekijken.</span><span class="sxs-lookup"><span data-stu-id="fa671-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="fa671-145">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-146">Op de **anti phishing** -pagina klikt u op **maken**.</span><span class="sxs-lookup"><span data-stu-id="fa671-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="fa671-147">De wizard **nieuw anti-phishingfilterbeleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="fa671-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="fa671-148">Configureer de volgende instellingen op de pagina **naam van uw beleid** :</span><span class="sxs-lookup"><span data-stu-id="fa671-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fa671-149">**Naam** : een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fa671-150">**Beschrijving** : voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fa671-151">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="fa671-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fa671-152">Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="fa671-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="fa671-153">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="fa671-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fa671-154">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="fa671-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="fa671-155">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="fa671-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="fa671-156">Klik op **een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fa671-156">Click **Add a condition**.</span></span> <span data-ttu-id="fa671-157">Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als** :</span><span class="sxs-lookup"><span data-stu-id="fa671-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="fa671-158">**De ontvanger is** : geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="fa671-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fa671-159">**De ontvanger is lid van** : Hiermee geeft u een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="fa671-160">**Het domein van de ontvanger is** : geeft de geadresseerden op in een of meer van de geconfigureerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="fa671-161">Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.</span><span class="sxs-lookup"><span data-stu-id="fa671-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="fa671-162">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="fa671-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="fa671-163">Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="fa671-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="fa671-164">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="fa671-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="fa671-165">Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.</span><span class="sxs-lookup"><span data-stu-id="fa671-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="fa671-166">Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="fa671-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="fa671-167">Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als**.</span><span class="sxs-lookup"><span data-stu-id="fa671-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="fa671-168">Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als**.</span><span class="sxs-lookup"><span data-stu-id="fa671-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="fa671-169">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="fa671-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fa671-170">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="fa671-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fa671-171">Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="fa671-172">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="fa671-173">Wanneer u klaar bent, klikt u op **dit beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="fa671-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="fa671-174">Klik op **OK** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="fa671-175">Nadat u het anti phishingfilter met deze algemene instellingen hebt gemaakt, volgt u de instructies in het volgende gedeelte om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="fa671-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-176">De beveiligings & voor naleving van Beveiligingscentrum gebruiken om anti phishing-beleid te wijzigen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fa671-177">Gebruik de volgende procedures om een anti-phishingfilter te wijzigen: een nieuwe beleidsregels die u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="fa671-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="fa671-178">Als u dit nog niet hebt gedaan, opent u het beveiligings & nalevings centrum en gaat u naar het beleid voor het beleid voor **bedreigings beheer** voor \> **Policy** \> **ATP anti phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-179">Selecteer het aangepaste anti-phishingfilter dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="fa671-180">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="fa671-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fa671-181">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="fa671-182">Als u in een sectie op **bewerken** klikt, krijgt u toegang tot de instellingen in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="fa671-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="fa671-183">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in een willekeurige volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="fa671-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="fa671-184">Nadat u op **bewerken** in een sectie hebt geklikt, worden de beschikbare instellingen in de wizard indeling weergegeven, maar u kunt wel binnen de pagina's in een willekeurige Volg **Cancel** orde springen **Close** , en u kunt op de pagina **Opslaan** of sluiten klikken op het pictogram voor het ![ ](../../media/scc-remove-icon.png) **bewerken van uw beleid \<name\>** (u hoeft niet te klikken op de laatste pagina van de wizard om de pagina te openen</span><span class="sxs-lookup"><span data-stu-id="fa671-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="fa671-185">**Beleidsinstelling** : Klik op **bewerken** als u de instellingen wilt wijzigen die beschikbaar waren wanneer u [het beleid hebt gemaakt](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in de vorige sectie:</span><span class="sxs-lookup"><span data-stu-id="fa671-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="fa671-186">**Naam**</span><span class="sxs-lookup"><span data-stu-id="fa671-186">**Name**</span></span>
   - <span data-ttu-id="fa671-187">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="fa671-187">**Description**</span></span>
   - <span data-ttu-id="fa671-188">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="fa671-188">**Applied to**</span></span>
   - <span data-ttu-id="fa671-189">**De instellingen bekijken**</span><span class="sxs-lookup"><span data-stu-id="fa671-189">**Review your settings**</span></span>

   <span data-ttu-id="fa671-190">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="fa671-191">**Imitatie** : Klik op **bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="fa671-192">Deze instellingen vormen een voorwaarde voor het beleid waarmee vervalste afzenders worden geïdentificeerd om te zoeken naar (afzonderlijk of per domein) in het van-adres van inkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="fa671-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="fa671-193">Zie voor meer informatie [imitatie-instellingen in anti-phishing-beleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="fa671-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="fa671-194">**Gebruikers toevoegen om te beveiligen** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-195">Als u de functie wilt inschakelen, verschuift u de schuifregelaar naar **aan** en klikt u op de knop **gebruiker toevoegen** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="fa671-196">Configureer de volgende waarden in het vervolgmenu **gebruiker toevoegen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="fa671-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="fa671-197">**E-mailadres** :</span><span class="sxs-lookup"><span data-stu-id="fa671-197">**Email address** :</span></span>

        - <span data-ttu-id="fa671-198">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="fa671-198">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="fa671-199">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fa671-199">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="fa671-200">Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fa671-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="fa671-201">**Naam** : deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt dit wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="fa671-202">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="fa671-203">Als u een bestaande vermelding wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="fa671-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="fa671-204">U kunt maximaal 60 gebruikers opgeven in het beveiligings & nalevings centrum of in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-204">You can enter a maximum of 60 users in the Security & Compliance Center or in PowerShell.</span></span>
       
   - <span data-ttu-id="fa671-205">**Domeinen toevoegen die u wilt beveiligen** : Configureer een of beide van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="fa671-205">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="fa671-206">**Automatisch de domeinen opnemen waarvan ik de eigenaar ben** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-206">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-207">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-207">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fa671-208">**Aangepaste domeinen opnemen** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-208">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-209">Als u deze optie wilt inschakelen, verschuift u de schuifregelaar naar **aan** en voert u in het vak **domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaalt u de gewenste stappen.</span><span class="sxs-lookup"><span data-stu-id="fa671-209">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="fa671-210">U kunt maximaal 50 domeinen invoeren in het beveiligings & nalevings centrum of in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-210">You can enter a maximum of 50 domains in the Security & Compliance Center or in PowerShell.</span></span>

   - <span data-ttu-id="fa671-211">**Acties** : Klik op **bewerken**</span><span class="sxs-lookup"><span data-stu-id="fa671-211">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="fa671-212">**Als e-mail wordt verzonden door een geïmiteerde gebruiker** : Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in de **gebruikers toevoegen om te beschermen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-212">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="fa671-213">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="fa671-213">**Don't apply any action**</span></span>
       - <span data-ttu-id="fa671-214">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="fa671-214">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="fa671-215">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="fa671-215">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="fa671-216">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="fa671-216">**Quarantine the message**</span></span>
       - <span data-ttu-id="fa671-217">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="fa671-217">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="fa671-218">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="fa671-218">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="fa671-219">**Als e-mailberichten worden verzonden door een geïmiteerd domein** : Configureer een van de volgende acties voor berichten waarvan de vervalste verzender zich bevindt in een van de beveiligde domeinen die u hebt opgegeven in **domeinen toevoegen om te beschermen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-219">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

     - <span data-ttu-id="fa671-220">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="fa671-220">**Don't apply any action**</span></span>
     - <span data-ttu-id="fa671-221">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="fa671-221">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="fa671-222">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="fa671-222">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="fa671-223">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="fa671-223">**Quarantine the message**</span></span>
     - <span data-ttu-id="fa671-224">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="fa671-224">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="fa671-225">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="fa671-225">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="fa671-226">Klik op de **beveiligingstips voor imitatie inschakelen** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="fa671-226">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="fa671-227">**Tip weergeven voor geïmiteerde gebruikers** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-227">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-228">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-228">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fa671-229">**Tip weergeven voor geïmiteerde domeinen** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-229">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-230">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fa671-231">**Tip voor ongebruikelijk tekens weergeven** : de standaardwaarde is **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-231">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="fa671-232">Schuif de wisselknop **naar aan om** deze optie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-232">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="fa671-233">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="fa671-233">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="fa671-234">**Postvak informatie** :</span><span class="sxs-lookup"><span data-stu-id="fa671-234">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="fa671-235">**Postvak intelligentie inschakelen?** : de standaardwaarde is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-235">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="fa671-236">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-236">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="fa671-237">**Schakelt u de bescherming van imitatie op basis van een postvak in?** : deze instelling is alleen beschikbaar als **Postvak Intelligence inschakelen?** is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-237">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="fa671-238">In **als e-mailbericht wordt verzonden door een geïmiteerde gebruiker** , kunt u een van de volgende acties opgeven voor het uitvoeren van berichten die niet beschikbaar zijn voor de Postvak informatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="fa671-238">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="fa671-239">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="fa671-239">**Don't apply any action**</span></span>
       - <span data-ttu-id="fa671-240">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="fa671-240">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="fa671-241">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="fa671-241">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="fa671-242">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="fa671-242">**Quarantine the message**</span></span>
       - <span data-ttu-id="fa671-243">**Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**</span><span class="sxs-lookup"><span data-stu-id="fa671-243">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="fa671-244">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="fa671-244">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="fa671-245">**Vertrouwde afzenders en domeinen toevoegen** : Geef uitzonderingen voor het beleid op:</span><span class="sxs-lookup"><span data-stu-id="fa671-245">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="fa671-246">**Vertrouwde afzenders** :</span><span class="sxs-lookup"><span data-stu-id="fa671-246">**Trusted senders** :</span></span>

       - <span data-ttu-id="fa671-247">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="fa671-247">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="fa671-248">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fa671-248">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="fa671-249">Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fa671-249">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="fa671-250">**Vertrouwde domeinen** : Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal de gewenste stappen.</span><span class="sxs-lookup"><span data-stu-id="fa671-250">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="fa671-251">**Controleer uw instellingen** : in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-251">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="fa671-252">U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-252">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="fa671-253">U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-253">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="fa671-254">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="fa671-254">**Protected users**</span></span>
       - <span data-ttu-id="fa671-255">**Beveiligde domeinen** \> **Ook domeinen opnemen waarvan ik eigenaar ben**</span><span class="sxs-lookup"><span data-stu-id="fa671-255">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="fa671-256">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="fa671-256">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="fa671-257">**Postvak intelligentie**</span><span class="sxs-lookup"><span data-stu-id="fa671-257">**Mailbox intelligence**</span></span>

   <span data-ttu-id="fa671-258">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-258">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="fa671-259">**Spoof** : Klik op **bewerken** als u de identiteit van spoofing wilt in-of uitschakelen, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en configureer de actie die u wilt toepassen op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="fa671-259">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="fa671-260">Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="fa671-260">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="fa671-261">Deze instellingen zijn ook beschikbaar in het anti-phishings beleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="fa671-261">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="fa671-262">**Instellingen voor spoofing filter** : de standaardwaarde is **ingeschakeld** en u wordt aangeraden deze in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fa671-262">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="fa671-263">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-263">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="fa671-264">Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="fa671-264">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="fa671-265">U hoeft geen anti-spoofing-beveiliging uit te schakelen als uw MX-record niet verwijst naar Microsoft 365. u kunt in plaats hiervan uitgebreid filteren op connectors.</span><span class="sxs-lookup"><span data-stu-id="fa671-265">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="fa671-266">Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="fa671-266">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="fa671-267">**Functie niet-geverifieerde afzender inschakelen** : de standaardwaarde is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="fa671-267">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="fa671-268">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-268">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="fa671-269">**Acties** : de actie opgeven die moet worden uitgevoerd voor berichten die geen spoof Intelligence hebben:</span><span class="sxs-lookup"><span data-stu-id="fa671-269">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="fa671-270">**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen, doet u het** volgende:</span><span class="sxs-lookup"><span data-stu-id="fa671-270">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="fa671-271">**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="fa671-271">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="fa671-272">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="fa671-272">**Quarantine the message**</span></span>

   - <span data-ttu-id="fa671-273">**Controleer uw instellingen** : in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-273">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="fa671-274">U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-274">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="fa671-275">U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-275">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="fa671-276">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="fa671-276">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="fa671-277">**Niet-geverifieerde afzender functie inschakelen**</span><span class="sxs-lookup"><span data-stu-id="fa671-277">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="fa671-278">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="fa671-278">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="fa671-279">**Geavanceerde instellingen** : Klik op **bewerken** om de drempelwaarden voor Geavanceerd phishing te configureren.</span><span class="sxs-lookup"><span data-stu-id="fa671-279">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="fa671-280">Voor meer informatie raadpleegt u [Advanced phishing Thresholds in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="fa671-280">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="fa671-281">**Geavanceerde fraude drempels** : Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="fa671-281">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="fa671-282">**1-standaard** (dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="fa671-282">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="fa671-283">**2-agressief**</span><span class="sxs-lookup"><span data-stu-id="fa671-283">**2 - Aggressive**</span></span>
   - <span data-ttu-id="fa671-284">**3-meer agressief**</span><span class="sxs-lookup"><span data-stu-id="fa671-284">**3 - More aggressive**</span></span>
   - <span data-ttu-id="fa671-285">**4-de scherpste**</span><span class="sxs-lookup"><span data-stu-id="fa671-285">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="fa671-286">**Controleer uw instellingen** : Klik op **bewerken** om terug te gaan naar de pagina Geavanceerde instellingen voor **phishing** .</span><span class="sxs-lookup"><span data-stu-id="fa671-286">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="fa671-287">Wanneer u klaar bent, klikt u op **Opslaan** op een van beide pagina's.</span><span class="sxs-lookup"><span data-stu-id="fa671-287">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="fa671-288">Ga op de pagina **\<Name\> beleid bewerken** naar de instellingen en klik op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="fa671-288">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-289">Met behulp van het nalevings centrum voor beveiliging & u het standaard anti-phishingfilter in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-289">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fa671-290">Het standaard anti-phishingfilter in Microsoft Defender voor Office 365 heeft de naam Office365 AntiPhish standaard en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="fa671-290">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="fa671-291">Ga als volgt te werk om het standaard anti-phishingfilter te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fa671-291">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="fa671-292">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-292">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-293">Klik op de pagina **anti phishing** op **standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="fa671-293">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="fa671-294">De standaardpagina voor het **bewerken van uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-294">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="fa671-295">De volgende secties zijn beschikbaar, met een identieke instelling voor [het wijzigen van een aangepast beleid](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="fa671-295">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="fa671-296">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="fa671-296">**Impersonation**</span></span>
   - <span data-ttu-id="fa671-297">**Met**</span><span class="sxs-lookup"><span data-stu-id="fa671-297">**Spoof**</span></span>
   - <span data-ttu-id="fa671-298">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="fa671-298">**Advanced settings**</span></span>

   <span data-ttu-id="fa671-299">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="fa671-299">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="fa671-300">U ziet de secties en waarden van de **beleidsinstelling** , maar er is geen koppeling voor **bewerken** , zodat u de instellingen (Beleidsnaam en beschrijving, en wie het beleid van toepassing is op alle geadresseerden), niet kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-300">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="fa671-301">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa671-301">You can't delete the default policy.</span></span>
   - <span data-ttu-id="fa671-302">Het is niet mogelijk om de prioriteit van het standaardbeleid te wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="fa671-302">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="fa671-303">Controleer de instellingen op de pagina **uw beleid Office365 AntiPhish standaard** instellen en klik op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="fa671-303">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-304">Aangepaste anti-phishingfilter-beleidsregels in-of uitschakelen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-304">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fa671-305">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-305">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-306">Let op de waarde in de kolom **status** :</span><span class="sxs-lookup"><span data-stu-id="fa671-306">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="fa671-307">Schuif de wisselknop naar **uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-307">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="fa671-308">Schuif de wisselknop naar **aan om het beleid in te** schakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-308">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="fa671-309">U kunt het standaard anti-Phishingfilter niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-309">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-310">De prioriteit van een aangepast anti-phishings beleid instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-310">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fa671-311">Standaard krijgt u een anti-phishingfilter met een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="fa671-311">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="fa671-312">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="fa671-312">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fa671-313">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="fa671-313">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fa671-314">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="fa671-314">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="fa671-315">Een aangepast anti-phishings beleid wordt weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).</span><span class="sxs-lookup"><span data-stu-id="fa671-315">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fa671-316">Het standaard anti-phishingfilter met de naam Office365 AntiPhish standaard heeft de waarde van een aangepaste **prioriteit en kunt** deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="fa671-317">**Opmerking** : in het beveiligings & nalevings centrum kunt u de prioriteit van het anti phishingfilter wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="fa671-317">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="fa671-318">In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor de anti-phishing maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="fa671-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="fa671-319">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **prioriteit verhogen** of **prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **prioriteits** nummer niet rechtstreeks wijzigen in de beveiligings & compliance Center).</span><span class="sxs-lookup"><span data-stu-id="fa671-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="fa671-320">Als u meerdere beleidsregels hebt, kunt u de prioriteit van een beleid alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="fa671-321">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-322">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="fa671-323">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="fa671-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fa671-324">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="fa671-325">Het aangepaste anti-phishingfilter met de **prioriteits** waarde **0** heeft slechts de knop **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="fa671-325">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="fa671-326">Het aangepaste anti-phishingfilter met de laagste **prioriteits** waarde (bijvoorbeeld **3** ) is slechts de knop **prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="fa671-326">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="fa671-327">Als u beschikt over drie of meer aangepaste anti phishingfilter-beleidsregels, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="fa671-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="fa671-328">Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="fa671-329">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="fa671-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-330">Met behulp van het beveiligings & compliance in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-330">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fa671-331">Ga in het beveiligings & compliance Center naar het beleid voor het beheer van bedreigingen en ga naar het beleid voor het **beheer van bedreigingen** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-332">Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="fa671-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="fa671-333">Selecteer een aangepast anti-phishingfilter dat u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="fa671-333">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="fa671-334">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="fa671-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="fa671-335">Klik op **standaardbeleid** om het standaard anti-phishingfilter te bekijken.</span><span class="sxs-lookup"><span data-stu-id="fa671-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="fa671-336">De flyout voor het **beleid \<name\> bewerken** wordt weergegeven, waarin u de instellingen en waarden kunt weergeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-337">De beveiligings & voor nalevings centrum gebruiken om anti phishingfilter te verwijderen uit Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-337">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fa671-338">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fa671-339">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa671-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="fa671-340">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="fa671-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fa671-341">Klik in het vervolgmenu **uw beleidsregels \<name\> bewerken** dat wordt weergegeven op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fa671-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="fa671-342">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fa671-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa671-343">PowerShell van Exchange Online gebruiken om anti phishingfilter te configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fa671-343">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fa671-344">Zoals hierboven beschreven, bestaat een anti-spam beleid en een anti-phishings regel.</span><span class="sxs-lookup"><span data-stu-id="fa671-344">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="fa671-345">In Exchange Online PowerShell is het verschil tussen anti-malwarebeleid en anti-phishing regels zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="fa671-345">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="fa671-346">U een anti-phishings beleid beheert met behulp van de cmdlets **\* AntiPhishPolicy** en u beheert de anti-phishings regels met behulp van de cmdlets voor **\* AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="fa671-346">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="fa671-347">In PowerShell maakt u eerst het anti-phishings beleid en vervolgens maakt u een anti-phishings regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="fa671-347">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fa671-348">In PowerShell wijzigt u de instellingen van het anti-phishings beleid en de anti-phishing regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="fa671-348">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="fa671-349">Wanneer u een anti-phishings beleid verwijdert uit PowerShell, wordt de overeenkomstige anti-phishing regel niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="fa671-349">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="fa671-350">PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="fa671-350">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="fa671-351">Het maken van een anti-phishingfilter in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="fa671-351">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fa671-352">Maak het anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-352">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="fa671-353">Maak de anti-phishings regel waarmee het anti-phishings beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="fa671-353">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="fa671-354">**Opmerkingen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-354">**Notes** :</span></span>

- <span data-ttu-id="fa671-355">U kunt een nieuwe anti-phishings regel maken en er een bestaande, niet-bijbehorend anti-phishings beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="fa671-355">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="fa671-356">Een anti-phishings regel kan niet worden gekoppeld aan meer dan een anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="fa671-356">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="fa671-357">U kunt de volgende instellingen configureren voor nieuwe anti-phishings beleidsregels in PowerShell die niet beschikbaar zijn in het beveiligings & compliance Center totdat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="fa671-357">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="fa671-358">Het nieuwe beleid maken als uitgeschakeld ( _ingeschakeld_ `$false` in de **nieuwe AntiPhishRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="fa671-358">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="fa671-359">De prioriteit van het beleid instellen voor het maken _Priority_ van de _\<Number\>_ **nieuwe AntiPhishRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="fa671-359">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="fa671-360">Een nieuw anti-phishings beleid dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een anti-phishing regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="fa671-360">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="fa671-361">Stap 1: PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="fa671-361">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="fa671-362">Voor het maken van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa671-362">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="fa671-363">In dit voorbeeld wordt een anti-phishings beleid met de naam onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="fa671-363">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="fa671-364">Het beleid is ingeschakeld (de parameter _enabled_ wordt niet gebruikt en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="fa671-364">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="fa671-365">De beschrijving luidt: afdelings beleid voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="fa671-365">The description is: Research department policy.</span></span>
- <span data-ttu-id="fa671-366">Schakelt de bescherming van organisatie domeinen in voor alle geaccepteerde domeinen en gerichte domeinbeveiliging voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="fa671-366">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="fa671-367">Hiermee wordt Mai Fujito (mfujito@fabrikam.com) opgegeven als de gebruiker die de gebruiker wil beschermen tegen onbevoegden.</span><span class="sxs-lookup"><span data-stu-id="fa671-367">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="fa671-368">Schakelt postvak informatie in.</span><span class="sxs-lookup"><span data-stu-id="fa671-368">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="fa671-369">Schakelt de functie voor Postvak beveiliging in en geeft de quarantaine actie aan.</span><span class="sxs-lookup"><span data-stu-id="fa671-369">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="fa671-370">Maakt veiligheidstips.</span><span class="sxs-lookup"><span data-stu-id="fa671-370">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="fa671-371">Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-371">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="fa671-372">Stap 2: PowerShell gebruiken om een anti-phishings regel te maken</span><span class="sxs-lookup"><span data-stu-id="fa671-372">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="fa671-373">Voor het maken van een anti-phishing regel gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa671-373">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="fa671-374">In dit voorbeeld wordt een anti-phishing regel genaamd onderzoek afdeling met de volgende voorwaarden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="fa671-374">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="fa671-375">De regel is verbonden met het anti-phishings beleid met de naam onderzoek quarantaine.</span><span class="sxs-lookup"><span data-stu-id="fa671-375">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="fa671-376">De regel geldt voor de leden van de groep met de naam onderzoek afdeling.</span><span class="sxs-lookup"><span data-stu-id="fa671-376">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="fa671-377">Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="fa671-377">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="fa671-378">Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-378">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="fa671-379">PowerShell gebruiken om een anti-phishings beleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="fa671-379">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="fa671-380">Gebruik de volgende syntaxis om de bestaande anti-phishings beleidsregels te bekijken:</span><span class="sxs-lookup"><span data-stu-id="fa671-380">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa671-381">In dit voorbeeld wordt een overzichtslijst met alle anti-phishing-beleidsregels en de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="fa671-381">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="fa671-382">In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phishings beleid met de naam leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="fa671-382">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="fa671-383">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-383">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="fa671-384">PowerShell gebruiken om anti-phishings regels te bekijken</span><span class="sxs-lookup"><span data-stu-id="fa671-384">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="fa671-385">Gebruik de volgende syntaxis om bestaande anti-phishings regels weer te geven:</span><span class="sxs-lookup"><span data-stu-id="fa671-385">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa671-386">In het volgende voorbeeld wordt een overzichtslijst met alle anti-phishing regels met de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="fa671-386">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="fa671-387">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="fa671-387">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="fa671-388">In het volgende voorbeeld worden alle eigenschapwaarden voor de anti-phishing-regel genaamd contoso leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="fa671-388">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="fa671-389">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-389">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="fa671-390">PowerShell gebruiken om een anti-phishings beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="fa671-390">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="fa671-391">Met uitzondering van de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phishings beleid in PowerShell aanpast wanneer u het beleid maakt zoals wordt beschreven in de sectie [stap 1: gebruik PowerShell om een anti-phishings sectie te maken](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="fa671-391">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="fa671-392">De schakeloptie _MakeDefault_ waarmee het opgegeven beleid wordt omgezet in het standaardbeleid (voor iedereen, de **laagste** prioriteit en het niet verwijderen) is alleen beschikbaar wanneer u een anti-Echobeleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-392">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="fa671-393">U kunt niet de naam van een anti-phishings beleid wijzigen (de cmdlet **set-AntiPhishPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="fa671-393">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fa671-394">Wanneer u de naam van een anti-phishingfilter wijzigt in de beveiligings & nalevings centrum, kunt u de naam van de anti-phishing _regel_ alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fa671-394">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="fa671-395">Voor het wijzigen van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa671-395">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fa671-396">Zie [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-396">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="fa671-397">PowerShell gebruiken om anti-phishings regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="fa671-397">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="fa671-398">De enige instelling die niet beschikbaar is wanneer u een anti-phishings regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="fa671-398">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fa671-399">Zie de volgende sectie als u bestaande anti-Phish regels wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="fa671-399">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="fa671-400">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phishing regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa671-400">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="fa671-401">U kunt dezelfde instellingen gebruiken wanneer u een regel maakt zoals wordt beschreven in [stap 2: PowerShell gebruiken om een anti-phishings sectie te maken](#step-2-use-powershell-to-create-an-anti-phish-rule) eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="fa671-401">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="fa671-402">Gebruik de volgende syntaxis om een anti-phishing regel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fa671-402">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fa671-403">Zie [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-403">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="fa671-404">PowerShell gebruiken om anti-phishings regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="fa671-404">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="fa671-405">Wanneer u een anti-phishing regel in-of uitschakelt in PowerShell, schakelt u het volledige anti-phishings beleid in of uit (de anti-phishings regel en het door u toegekende anti-phishings beleid).</span><span class="sxs-lookup"><span data-stu-id="fa671-405">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="fa671-406">U kunt het standaard anti-phishingfilter-beleid niet in-of uitschakelen (het wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="fa671-406">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="fa671-407">U kunt een anti-phishings regel in PowerShell in-of uitschakelen met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa671-407">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="fa671-408">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fa671-408">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fa671-409">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fa671-409">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fa671-410">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-410">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="fa671-411">PowerShell gebruiken om de prioriteit van anti-phishings regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="fa671-411">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="fa671-412">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="fa671-412">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fa671-413">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="fa671-413">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fa671-414">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fa671-414">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fa671-415">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="fa671-415">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fa671-416">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="fa671-416">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fa671-417">Als u de prioriteit wilt instellen van een anti-Phish regel in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fa671-417">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fa671-418">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="fa671-418">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fa671-419">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="fa671-419">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="fa671-420">**Opmerkingen** :</span><span class="sxs-lookup"><span data-stu-id="fa671-420">**Notes** :</span></span>

- <span data-ttu-id="fa671-421">Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="fa671-421">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="fa671-422">Het anti-phishings beleid heeft geen overeenkomstige anti-phishings regel, en het is altijd de **laagste** ongewijzigde prioriteitswaarde.</span><span class="sxs-lookup"><span data-stu-id="fa671-422">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="fa671-423">PowerShell gebruiken om een anti-phishings beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="fa671-423">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="fa671-424">Wanneer u PowerShell gebruikt om een anti-phishings beleid te verwijderen, wordt de overeenkomstige anti-phishings regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fa671-424">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="fa671-425">Gebruik de volgende syntaxis om een anti-phishings beleid te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa671-425">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fa671-426">In dit voorbeeld wordt het anti-phishings beleid met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fa671-426">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fa671-427">Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-427">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="fa671-428">PowerShell gebruiken om anti-phishings regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="fa671-428">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="fa671-429">Als u PowerShell gebruikt om een anti-phishing regel te verwijderen, wordt het bijbehorende anti-phishings beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fa671-429">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="fa671-430">Gebruik de volgende syntaxis om een anti-phishings regel te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa671-430">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="fa671-431">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fa671-431">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fa671-432">Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="fa671-432">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fa671-433">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="fa671-433">How do you know these procedures worked?</span></span>

<span data-ttu-id="fa671-434">Voer een van de volgende stappen uit om te controleren of u een anti-phishingfilter-beleid hebt geconfigureerd in Microsoft Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="fa671-434">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="fa671-435">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fa671-435">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="fa671-436">Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** .</span><span class="sxs-lookup"><span data-stu-id="fa671-436">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fa671-437">Ga op een van de volgende manieren te werk om meer informatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="fa671-437">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="fa671-438">Selecteer een beleid in de lijst en Bekijk de details in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fa671-438">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="fa671-439">Klik op **standaardbeleid** en Bekijk de details in het vervolgmenu.</span><span class="sxs-lookup"><span data-stu-id="fa671-439">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="fa671-440">In Exchange Online PowerShell vervangt u \<Name\> de naam van het beleid of de regel en voert u de volgende opdracht uit en controleert u de instellingen:</span><span class="sxs-lookup"><span data-stu-id="fa671-440">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
