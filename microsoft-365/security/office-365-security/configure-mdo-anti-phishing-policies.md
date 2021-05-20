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
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537905"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-103">Anti-phishingbeleid configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cde30-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="cde30-104">**Applies to**</span></span>
- [<span data-ttu-id="cde30-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cde30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cde30-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cde30-107">Anti-phishingbeleid in [Microsoft Defender voor Office 365](defender-for-office-365.md) kan uw organisatie helpen beschermen tegen kwaadaardige phishingaanvallen op basis van imitaties en andere soorten phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="cde30-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="cde30-108">Zie [Anti-phishingbeveiliging](anti-phishing-protection.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in Exchange Online Protection (EOP) en anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cde30-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="cde30-109">Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="cde30-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="cde30-110">Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="cde30-111">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="cde30-112">U kunt anti-phishingbeleid configureren in het Beveiligings- & compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cde30-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="cde30-113">Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor informatie over het configureren van de meer beperkte anti-phishingbeleidsregels die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen organisaties zonder Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="cde30-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="cde30-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="cde30-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="cde30-115">**Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="cde30-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="cde30-116">**De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="cde30-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="cde30-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="cde30-118">Wanneer u een beleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="cde30-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="cde30-119">Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="cde30-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="cde30-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="cde30-121">Wanneer u een beleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cde30-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="cde30-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="cde30-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="cde30-123">Zie de sectie Use Exchange Online PowerShell to configure [anti-phishing policies in Microsoft Defender for Office 365 section verderop](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="cde30-124">Elke Microsoft Defender voor Office 365 heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="cde30-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="cde30-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="cde30-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="cde30-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="cde30-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="cde30-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="cde30-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cde30-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="cde30-129">Als u de effectiviteit van anti-phishingbeveiliging in Microsoft Defender voor Office 365 wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cde30-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cde30-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="cde30-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cde30-131">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cde30-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cde30-132">Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="cde30-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="cde30-133">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cde30-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cde30-134">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="cde30-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cde30-135">Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="cde30-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cde30-136">Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="cde30-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="cde30-137">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cde30-138">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="cde30-138">**Notes**:</span></span>

  - <span data-ttu-id="cde30-139">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cde30-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cde30-140">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="cde30-141">De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="cde30-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="cde30-142"><sup>\*</sup> In het & compliancecentrum kunnen gebruikers met alleen-lezen toegang de instellingen van aangepast anti-phishingbeleid bekijken.</span><span class="sxs-lookup"><span data-stu-id="cde30-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="cde30-143">Alleen-lezen gebruikers kunnen de instellingen niet zien in het standaard anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="cde30-144">Voor onze aanbevolen instellingen voor anti-phishingbeleid in Microsoft Defender voor Office 365, zie [Anti-phishingbeleid in Defender voor Office 365 instellingen.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="cde30-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="cde30-145">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="cde30-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="cde30-146">Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="cde30-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-147">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid te maken in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cde30-148">Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="cde30-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="cde30-149">Wanneer u een anti-phishingbeleid maakt, kunt u alleen de naam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="cde30-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="cde30-150">Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="cde30-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="cde30-151">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-152">Klik op **de pagina Anti-phishing** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="cde30-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="cde30-153">De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="cde30-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="cde30-154">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="cde30-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="cde30-155">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="cde30-156">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="cde30-157">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="cde30-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cde30-158">Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="cde30-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="cde30-159">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="cde30-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="cde30-160">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="cde30-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="cde30-161">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="cde30-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="cde30-162">Klik **op Een voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="cde30-162">Click **Add a condition**.</span></span> <span data-ttu-id="cde30-163">Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="cde30-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="cde30-164">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="cde30-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="cde30-165">**De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="cde30-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="cde30-166">**Het domein van de geadresseerde is:** hiermee geeft u geadresseerden op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="cde30-167">Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**</span><span class="sxs-lookup"><span data-stu-id="cde30-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="cde30-168">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="cde30-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="cde30-169">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="cde30-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="cde30-170">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="cde30-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="cde30-171">Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="cde30-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="cde30-172">Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="cde30-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="cde30-173">Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="cde30-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="cde30-174">Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="cde30-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="cde30-175">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="cde30-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="cde30-176">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="cde30-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cde30-177">Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="cde30-178">U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="cde30-179">Wanneer u klaar bent, klikt u op **Dit beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="cde30-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="cde30-180">Klik **op OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="cde30-181">Nadat u het anti-phishingbeleid met deze algemene instellingen hebt gemaakt, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="cde30-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-182">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender te wijzigen voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cde30-183">Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="cde30-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="cde30-184">Als u er nog niet bent, opent u het Beveiligingscentrum & compliancecentrum en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-185">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="cde30-186">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="cde30-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="cde30-187">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="cde30-188">Als u in **een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="cde30-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="cde30-189">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="cde30-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="cde30-190">Nadat u **in** een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling, maar  u kunt in elke volgorde binnen de pagina's springen en u kunt op Opslaan op een pagina klikken (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** pictogram Annuleren of Sluiten sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="cde30-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="cde30-191">**Beleidsinstelling:** Klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het [beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="cde30-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="cde30-192">**Naam**</span><span class="sxs-lookup"><span data-stu-id="cde30-192">**Name**</span></span>
   - <span data-ttu-id="cde30-193">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="cde30-193">**Description**</span></span>
   - <span data-ttu-id="cde30-194">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="cde30-194">**Applied to**</span></span>
   - <span data-ttu-id="cde30-195">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="cde30-195">**Review your settings**</span></span>

   <span data-ttu-id="cde30-196">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="cde30-197">**Imitatie:** Klik op **Bewerken om** de beveiligde afzenders en beveiligde afzenderdomeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-197">**Impersonation**: Click **Edit** to modify the protected senders and protected sender domains in the policy.</span></span> <span data-ttu-id="cde30-198">Deze instellingen zijn een voorwaarde voor het beleid dat specifieke afzenders identificeert die moeten zoeken (afzonderlijk of per domein) in het Van-adres van binnenkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="cde30-198">These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="cde30-199">Zie Instellingen voor imitatie [in anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cde30-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="cde30-200">**Gebruikers toevoegen om te beveiligen:** De standaardwaarde is  ![ ](../../media/scc-toggle-off.png) Uit-uit.</span><span class="sxs-lookup"><span data-stu-id="cde30-200">**Add users to protect**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="cde30-201">Als u de knop wilt in- of uitschakelen, schuift u de schakelknop naar **Aan** en klikt u vervolgens op de knop Gebruiker ![ toevoegen die wordt ](../../media/scc-toggle-on.png) weergegeven. </span><span class="sxs-lookup"><span data-stu-id="cde30-201">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="cde30-202">Configureer **in het** flyout Gebruiker toevoegen dat wordt weergegeven de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="cde30-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="cde30-203">**E-mailadres**:</span><span class="sxs-lookup"><span data-stu-id="cde30-203">**Email address**:</span></span>

       - <span data-ttu-id="cde30-204">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="cde30-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="cde30-205">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cde30-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="cde30-206">Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cde30-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="cde30-207">**Naam:** Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="cde30-208">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="cde30-209">Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="cde30-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="cde30-210">In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers opgeven (e-mailadressen van afzenders).</span><span class="sxs-lookup"><span data-stu-id="cde30-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="cde30-211">U kunt niet dezelfde beveiligde gebruiker opgeven in meerdere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="cde30-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="cde30-212">Gebruikersbeveiliging werkt niet als de afzender en geadresseerde eerder via e-mail hebben gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="cde30-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="cde30-213">Als de afzender en geadresseerde nooit via e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.</span><span class="sxs-lookup"><span data-stu-id="cde30-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="cde30-214">**Domeinen toevoegen om te beveiligen:** Een of beide van de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="cde30-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="cde30-215">**Automatisch de domeinen opnemen die ik bezit:** De standaardwaarde is **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-215">**Automatically include the domains I own**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="cde30-216">Als u deze wilt in-  of uitschakelen, schuift u de schakelknop naar ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="cde30-216">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

       <span data-ttu-id="cde30-217">Als u de domeinen wilt weergeven die u bezit, selecteert u **Domeinen weergeven van wie ik de eigenaar ben.**</span><span class="sxs-lookup"><span data-stu-id="cde30-217">To view the domains that you own, select **View domains I own**.</span></span>

     - <span data-ttu-id="cde30-218">**Aangepaste domeinen opnemen:** De standaardwaarde is  ![ ](../../media/scc-toggle-off.png) Uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cde30-218">**Include custom domains**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="cde30-219">Als u de knop wilt  in- of uitschakelen, schuift u de schakelknop naar Aan en typt u in het vak Domeinen toevoegen de domeinnaam ![ ](../../media/scc-toggle-on.png) (bijvoorbeeld contoso.com),  drukt u op Enter en herhaalt u dit zo nodig.</span><span class="sxs-lookup"><span data-stu-id="cde30-219">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="cde30-220">U kunt maximaal 50 domeinen hebben in alle anti-phishingbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="cde30-220">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="cde30-221">**Acties**: Klik op **Bewerken**</span><span class="sxs-lookup"><span data-stu-id="cde30-221">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="cde30-222">**Als e-mail wordt** verzonden door een nagebootsde gebruiker: Configureer een van de volgende acties voor berichten waarbij de afzender een van de beveiligde gebruikers is die u hebt opgegeven in Gebruikers toevoegen ter **bescherming:**</span><span class="sxs-lookup"><span data-stu-id="cde30-222">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="cde30-223">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="cde30-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="cde30-224">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="cde30-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="cde30-225">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="cde30-225">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="cde30-226">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="cde30-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="cde30-227">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="cde30-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="cde30-228">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="cde30-228">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="cde30-229">**Als e-mail** wordt verzonden door een nagebootsd domein: Configureer een van de volgende acties voor berichten waarbij het domein van de afzender zich in een van de beveiligde domeinen die u hebt opgegeven in **Domeinen** toevoegen ter bescherming:</span><span class="sxs-lookup"><span data-stu-id="cde30-229">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the sender's domain is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="cde30-230">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="cde30-230">**Don't apply any action**</span></span>
       - <span data-ttu-id="cde30-231">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="cde30-231">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="cde30-232">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="cde30-232">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="cde30-233">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="cde30-233">**Quarantine the message**</span></span>
       - <span data-ttu-id="cde30-234">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="cde30-234">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="cde30-235">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="cde30-235">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="cde30-236">Klik **op veiligheidstips voor imitatie in-** en configureren een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="cde30-236">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="cde30-237">**Tip voor imiteerde gebruikers tonen**</span><span class="sxs-lookup"><span data-stu-id="cde30-237">**Show tip for impersonated users**</span></span>
     - <span data-ttu-id="cde30-238">**Tip voor nagebootste domeinen tonen**</span><span class="sxs-lookup"><span data-stu-id="cde30-238">**Show tip for impersonated domains**</span></span>
     - <span data-ttu-id="cde30-239">**Tip voor ongebruikelijke tekens tonen**</span><span class="sxs-lookup"><span data-stu-id="cde30-239">**Show tip for unusual characters**</span></span>

     <span data-ttu-id="cde30-240">De standaardwaarde voor alle tips is **Uitgeschakeld.** ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="cde30-240">The default value for all tips is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="cde30-241">Als u een van deze in wilt schakelen, schuift u de schakelknop naar  [In-/uitschakelen.](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="cde30-241">To turn any of them on, slide the toggle to **On** [Toggle On](../../media/scc-toggle-on.png).</span></span>

     <span data-ttu-id="cde30-242">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="cde30-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="cde30-243">**Postvakintelligentie:**</span><span class="sxs-lookup"><span data-stu-id="cde30-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="cde30-244">**Postvakintelligentie inschakelen?**: De standaardwaarde is **Ingeschakeld.** [](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="cde30-244">**Enable mailbox intelligence?**: The default value is **On** [Toggle On](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="cde30-245">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-245">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     - <span data-ttu-id="cde30-246">**Postvakintelligentie inschakelen op basis van imitatiebeveiliging?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen is** **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="cde30-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="cde30-247">Schakel deze instelling in om de actie op te geven die u moet ondernemen voor berichten voor imitatiedetecties van postvakinformatieresultaten.</span><span class="sxs-lookup"><span data-stu-id="cde30-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="cde30-248">In **Als e-mail wordt** verzonden door een nagebootsde gebruiker, kunt u een van de volgende acties opgeven (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="cde30-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="cde30-249">**Pas geen actie** toe: houd er rekening mee dat deze waarde hetzelfde resultaat heeft als het inschakelen van postvakinformatie inschakelen? maar postvakintelligentie op basis van  **imitatiebeveiliging inschakelen uitschakelen?**.</span><span class="sxs-lookup"><span data-stu-id="cde30-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="cde30-250">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="cde30-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="cde30-251">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="cde30-251">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="cde30-252">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="cde30-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="cde30-253">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="cde30-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="cde30-254">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="cde30-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="cde30-255">**Vertrouwde afzenders en domeinen toevoegen:** geef uitzonderingen op voor het beleid:</span><span class="sxs-lookup"><span data-stu-id="cde30-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="cde30-256">**Vertrouwde afzenders:**</span><span class="sxs-lookup"><span data-stu-id="cde30-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="cde30-257">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="cde30-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="cde30-258">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cde30-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="cde30-259">Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cde30-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="cde30-260">**Vertrouwde domeinen:** Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op Enter en herhaal indien nodig.</span><span class="sxs-lookup"><span data-stu-id="cde30-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="cde30-261">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="cde30-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="cde30-262">U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="cde30-263">U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="cde30-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="cde30-264">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="cde30-264">**Protected users**</span></span>
       - <span data-ttu-id="cde30-265">**Beveiligde domeinen** \> **Domeinen opnemen die ik bezit**</span><span class="sxs-lookup"><span data-stu-id="cde30-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="cde30-266">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="cde30-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="cde30-267">**Postvakintelligentie**</span><span class="sxs-lookup"><span data-stu-id="cde30-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="cde30-268">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="cde30-269">**Spoof:** Klik op **Bewerken** om spoofinformatie in of uit te schakelen, unauthenticated sender identification in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="cde30-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="cde30-270">Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie over deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="cde30-270">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="cde30-271">Houd er rekening mee dat deze instellingen ook beschikbaar zijn in anti-phishingbeleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="cde30-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="cde30-272">**Filterinstellingen voor spoofing:** gebruik de instelling **Spoof intelligence inschakelen?** om spoofinformatie in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-272">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="cde30-273">De standaardwaarde is **Aan** en we raden u aan deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="cde30-273">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="cde30-274">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-274">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="cde30-275">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-275">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="cde30-276">Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="cde30-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="cde30-277">**Instellingen voor niet-nautische afzenders:** U kunt de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="cde30-277">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="cde30-278">**Unauthenticated sender question mark (?)** symbol inschakelen? : Voeg een vraagteken toe aan de foto van de afzender in het  vak Van in Outlook als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [gaat.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="cde30-278">**Enable unauthenticated sender question mark (?) symbol?**: Add a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="cde30-279">De standaardwaarde is **Aan**.</span><span class="sxs-lookup"><span data-stu-id="cde30-279">The default value is **On**.</span></span> <span data-ttu-id="cde30-280">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-280">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="cde30-281">**Tag 'via' inschakelen?**: Voeg de via-tag (chris@contoso.com via fabrikam.com) toe als het e-mailadres in het vak Van verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.**</span><span class="sxs-lookup"><span data-stu-id="cde30-281">**Enable "via" tag?**: Add the via tag (chris@contoso.com via fabrikam.com) if the email address in the From box is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="cde30-282">De standaardwaarde is **Aan**.</span><span class="sxs-lookup"><span data-stu-id="cde30-282">The default value is **On**.</span></span> <span data-ttu-id="cde30-283">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-283">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="cde30-284">**Acties:** Geef de actie op voor berichten van geblokkeerde vervalste afzenders:</span><span class="sxs-lookup"><span data-stu-id="cde30-284">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="cde30-285">**Als e-mail wordt verzonden door iemand die uw** domein niet mag vervalsen:</span><span class="sxs-lookup"><span data-stu-id="cde30-285">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="cde30-286">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="cde30-286">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="cde30-287">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="cde30-287">**Quarantine the message**</span></span>

   - <span data-ttu-id="cde30-288">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="cde30-288">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="cde30-289">U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-289">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="cde30-290">U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="cde30-290">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="cde30-291">**Instellingen voor spooffilters**</span><span class="sxs-lookup"><span data-stu-id="cde30-291">**Spoof filter settings**</span></span>
       - <span data-ttu-id="cde30-292">**Instellingen voor niet-genauteerde afzender**</span><span class="sxs-lookup"><span data-stu-id="cde30-292">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="cde30-293">**Acties**</span><span class="sxs-lookup"><span data-stu-id="cde30-293">**Actions**</span></span>

   <span data-ttu-id="cde30-294">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="cde30-294">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="cde30-295">**Geavanceerde instellingen:** Klik op **Bewerken om** de geavanceerde phishingdrempels te configureren.</span><span class="sxs-lookup"><span data-stu-id="cde30-295">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="cde30-296">Zie Advanced [phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="cde30-296">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="cde30-297">**Geavanceerde phishingdrempels:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="cde30-297">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="cde30-298">**1 - Standaard** (Dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="cde30-298">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="cde30-299">**2 - Agressief**</span><span class="sxs-lookup"><span data-stu-id="cde30-299">**2 - Aggressive**</span></span>
   - <span data-ttu-id="cde30-300">**3 - Agressiever**</span><span class="sxs-lookup"><span data-stu-id="cde30-300">**3 - More aggressive**</span></span>
   - <span data-ttu-id="cde30-301">**4 - Meest agressief**</span><span class="sxs-lookup"><span data-stu-id="cde30-301">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="cde30-302">**Uw instellingen controleren:** Klik op **Bewerken om** terug te gaan naar de **pagina Geavanceerde phishingdrempels.**</span><span class="sxs-lookup"><span data-stu-id="cde30-302">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="cde30-303">Wanneer u klaar bent, klikt u **op Opslaan** op beide pagina's.</span><span class="sxs-lookup"><span data-stu-id="cde30-303">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="cde30-304">Bekijk de instellingen op **de \<Name\> pagina** Uw beleid bewerken en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="cde30-304">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-305">Gebruik het Beveiligings- & compliancecentrum om het standaard anti-phishingbeleid in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-305">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cde30-306">Het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="cde30-306">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="cde30-307">Als u het standaard anti-phishingbeleid wilt wijzigen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="cde30-307">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="cde30-308">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-309">Klik op **de pagina Anti-phishing** op **Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="cde30-309">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="cde30-310">De **pagina Uw beleid bewerken Office365 AntiPhish Default** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-310">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="cde30-311">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="cde30-311">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="cde30-312">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="cde30-312">**Impersonation**</span></span>
   - <span data-ttu-id="cde30-313">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="cde30-313">**Spoof**</span></span>
   - <span data-ttu-id="cde30-314">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="cde30-314">**Advanced settings**</span></span>

   <span data-ttu-id="cde30-315">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="cde30-315">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="cde30-316">U kunt  de sectie Beleidsinstelling en -waarden  zien, maar er is geen koppeling Bewerken, dus u kunt de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (dit geldt voor alle geadresseerden)).</span><span class="sxs-lookup"><span data-stu-id="cde30-316">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="cde30-317">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cde30-317">You can't delete the default policy.</span></span>
   - <span data-ttu-id="cde30-318">U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="cde30-318">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="cde30-319">Controleer op **de pagina Uw beleid bewerken Office365 AntiPhish Default** uw instellingen en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="cde30-319">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-320">Aangepaste anti-phishingbeleidsregels in- of uitschakelen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-320">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="cde30-321">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-322">Let op de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="cde30-322">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="cde30-323">Schuif de schakelknop naar  ![ Uit-schakelknop uit ](../../media/scc-toggle-off.png) om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-323">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="cde30-324">Schuif de schakelknop naar  ![ Aan-aan om ](../../media/scc-toggle-on.png) het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-324">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="cde30-325">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-325">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-326">De prioriteit instellen van aangepast anti-phishingbeleid in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-326">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cde30-327">Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="cde30-327">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="cde30-328">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="cde30-328">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="cde30-329">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="cde30-329">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="cde30-330">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="cde30-330">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="cde30-331">Aangepaste anti-phishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="cde30-331">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="cde30-332">Het standaard anti-phishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-332">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="cde30-333">**Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cde30-333">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="cde30-334">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="cde30-334">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="cde30-335">Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het Beveiligings- & Compliancecentrum).</span><span class="sxs-lookup"><span data-stu-id="cde30-335">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="cde30-336">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="cde30-336">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="cde30-337">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-337">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-338">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-338">Select the policy that you want to modify.</span></span> <span data-ttu-id="cde30-339">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="cde30-339">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="cde30-340">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-340">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="cde30-341">Het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="cde30-341">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="cde30-342">Het aangepaste anti-phishingbeleid  met de laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="cde30-342">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="cde30-343">Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, hebben  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="cde30-343">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="cde30-344">Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cde30-344">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="cde30-345">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="cde30-345">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-346">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-346">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="cde30-347">Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-347">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-348">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="cde30-348">Do one of the following steps:</span></span>

   - <span data-ttu-id="cde30-349">Selecteer een aangepast anti-phishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-349">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="cde30-350">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="cde30-350">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="cde30-351">Klik **op Standaardbeleid** om het standaardbeleid voor anti-phishing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="cde30-351">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="cde30-352">Het **fly-out \<name\>** Beleid bewerken wordt weergegeven, waar u de instellingen en waarden kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="cde30-352">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-353">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender te verwijderen voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-353">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="cde30-354">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="cde30-355">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cde30-355">Select the policy that you want to remove.</span></span> <span data-ttu-id="cde30-356">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="cde30-356">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="cde30-357">Klik in **het \<name\> flyout** Beleid bewerken dat wordt weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-357">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="cde30-358">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cde30-358">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cde30-359">Gebruik Exchange Online PowerShell om anti-phishingbeleid in Microsoft Defender te configureren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cde30-359">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cde30-360">Zoals eerder beschreven, bestaat een antispambeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="cde30-360">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="cde30-361">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="cde30-361">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="cde30-362">U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="cde30-362">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="cde30-363">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="cde30-363">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="cde30-364">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="cde30-364">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="cde30-365">Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="cde30-365">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="cde30-366">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="cde30-366">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="cde30-367">Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="cde30-367">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="cde30-368">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-368">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="cde30-369">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="cde30-369">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="cde30-370">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="cde30-370">**Notes**:</span></span>

- <span data-ttu-id="cde30-371">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="cde30-371">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="cde30-372">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="cde30-372">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="cde30-373">U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="cde30-373">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="cde30-374">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="cde30-374">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="cde30-375">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="cde30-375">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="cde30-376">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum als u het beleid aan een anti-phish-regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="cde30-376">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="cde30-377">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="cde30-377">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="cde30-378">Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-378">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="cde30-379">In dit voorbeeld wordt anti-phishbeleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="cde30-379">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="cde30-380">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="cde30-380">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="cde30-381">De beschrijving is: Het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="cde30-381">The description is: Research department policy.</span></span>
- <span data-ttu-id="cde30-382">Hiermee wordt de beveiliging van organisatiedomeinen voor alle geaccepteerde domeinen en de bescherming van gerichte domeinen voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="cde30-382">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="cde30-383">Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker die u wilt beschermen tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="cde30-383">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="cde30-384">Hiermee schakelt u postvakintelligentie in.</span><span class="sxs-lookup"><span data-stu-id="cde30-384">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="cde30-385">Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.</span><span class="sxs-lookup"><span data-stu-id="cde30-385">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="cde30-386">Hiermee schakelt u veiligheidstips in.</span><span class="sxs-lookup"><span data-stu-id="cde30-386">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="cde30-387">Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-387">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="cde30-388">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="cde30-388">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="cde30-389">Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-389">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="cde30-390">In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="cde30-390">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="cde30-391">De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="cde30-391">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="cde30-392">De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="cde30-392">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="cde30-393">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="cde30-393">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="cde30-394">Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-394">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="cde30-395">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="cde30-395">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="cde30-396">Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="cde30-396">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cde30-397">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-397">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="cde30-398">Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="cde30-398">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="cde30-399">Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-399">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="cde30-400">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="cde30-400">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="cde30-401">Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-401">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cde30-402">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cde30-402">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="cde30-403">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="cde30-403">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="cde30-404">Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="cde30-404">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="cde30-405">Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-405">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="cde30-406">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="cde30-406">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="cde30-407">Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.</span><span class="sxs-lookup"><span data-stu-id="cde30-407">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="cde30-408">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cde30-408">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="cde30-409">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="cde30-409">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="cde30-410">Wanneer u de naam van een anti-phishingbeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="cde30-410">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="cde30-411">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-411">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="cde30-412">Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-412">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="cde30-413">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="cde30-413">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="cde30-414">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="cde30-414">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="cde30-415">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="cde30-415">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="cde30-416">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="cde30-416">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="cde30-417">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.</span><span class="sxs-lookup"><span data-stu-id="cde30-417">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="cde30-418">Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-418">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="cde30-419">Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-419">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="cde30-420">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="cde30-420">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="cde30-421">Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cde30-421">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="cde30-422">U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="cde30-422">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="cde30-423">Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-423">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="cde30-424">In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cde30-424">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="cde30-425">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cde30-425">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="cde30-426">Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-426">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="cde30-427">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="cde30-427">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="cde30-428">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="cde30-428">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="cde30-429">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="cde30-429">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="cde30-430">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cde30-430">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="cde30-431">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="cde30-431">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="cde30-432">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="cde30-432">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="cde30-433">Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-433">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="cde30-434">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="cde30-434">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="cde30-435">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="cde30-435">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="cde30-436">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="cde30-436">**Notes**:</span></span>

- <span data-ttu-id="cde30-437">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="cde30-437">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="cde30-438">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.</span><span class="sxs-lookup"><span data-stu-id="cde30-438">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="cde30-439">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="cde30-439">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="cde30-440">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cde30-440">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="cde30-441">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-441">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="cde30-442">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cde30-442">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="cde30-443">Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-443">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="cde30-444">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="cde30-444">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="cde30-445">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cde30-445">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="cde30-446">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="cde30-446">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="cde30-447">In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cde30-447">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="cde30-448">Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="cde30-448">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cde30-449">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="cde30-449">How do you know these procedures worked?</span></span>

<span data-ttu-id="cde30-450">Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="cde30-450">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="cde30-451">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="cde30-451">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="cde30-452">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="cde30-452">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="cde30-453">Ga als volgt te werk om meer details weer te geven:</span><span class="sxs-lookup"><span data-stu-id="cde30-453">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="cde30-454">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="cde30-454">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="cde30-455">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="cde30-455">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="cde30-456">Vervang Exchange Online PowerShell door de naam van het beleid of de regel en voer de volgende opdracht uit \<Name\> en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="cde30-456">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```